
<p align="center">
  <img height="50" height="auto" src="https://user-images.githubusercontent.com/38981255/184088981-3f7376ae-7039-4915-98f5-16c3637ccea3.PNG">
</p>

# TASK 3 | Create Your Value Contract

## Install Package

```
wget -qO crud.sh https://raw.githubusercontent.com/bangpateng/inery/main/crud.sh && chmod +x crud.sh && ./crud.sh
```

## Set Path
```
export PATH="$PATH:$HOME/inery.cdt/bin:$HOME/inery-node/inery/bin"
```
## Create Folder
```
mkdir -p $HOME/inrcrud
```
## Write Code (Paste Aja Langsung Kaga Usah di Edat Edit)


```
sudo tee $HOME/inrcrud/inrcrud.cpp >/dev/null <<EOF
#include <inery/inery.hpp>
#include <inery/print.hpp>
#include <string>

using namespace inery;

using std::string;

class [[inery::contract]] inrcrud : public inery::contract {
  public:
    using inery::contract::contract;


        [[inery::action]] void create( uint64_t id, name user, string data ) {
            records recordstable( _self, id );
            auto existing = recordstable.find( id );
            check( existing == recordstable.end(), "record with that ID already exists" );
            check( data.size() <= 256, "data has more than 256 bytes" );

            recordstable.emplace( _self, [&]( auto& s ) {
               s.id         = id;
               s.owner      = user;
               s.data       = data;
            });

            print( "Hello, ", name{user} );
            print( "Created with data: ", data );
        }

         [[inery::action]] void read( uint64_t id ) {
            records recordstable( _self, id );
            auto existing = recordstable.find( id );
            check( existing != recordstable.end(), "record with that ID does not exist" );
            const auto& st = *existing;
            print("Data: ", st.data);
        }

        [[inery::action]] void update( uint64_t id, string data ) {
            records recordstable( _self, id );
            auto st = recordstable.find( id );
            check( st != recordstable.end(), "record with that ID does not exist" );


            recordstable.modify( st, get_self(), [&]( auto& s ) {
               s.data = data;
            });

            print("Data: ", data);
        }

            [[inery::action]] void destroy( uint64_t id ) {
            records recordstable( _self, id );
            auto existing = recordstable.find( id );
            check( existing != recordstable.end(), "record with that ID does not exist" );
            const auto& st = *existing;

            recordstable.erase( st );

            print("Record Destroyed: ", id);

        }

  private:
    struct [[inery::table]] record {
       uint64_t        id;
       name     owner;
       string          data;
       uint64_t primary_key()const { return id; }
    };

    typedef inery::multi_index<"records"_n, record> records;
 };
EOF
```

## Compile Code

<p align="center">
  <img height="auto" height="auto" src="https://user-images.githubusercontent.com/38981255/198983423-565ff60d-e69d-48cd-bc80-96845094e1d8.jpg">
</p>

```
inery-cpp $HOME/inrcrud/inrcrud.cpp -o $HOME/inrcrud/inrcrud.wasm
```

## ✅ OPEN WALLET


```
cline wallet unlock -n Your-name-account
```
**Masukan Kata Sandi Wallet Kalian**

## ✅ SET CONTRACT

```
cline set contract Your-name-account ./inrcrud
```
## ✅ CREATE

```
cline push action Your-name-account create '[1, "Your-name-account", "My first Record"]' -p Your-name-account --json
```
## ✅ READ



```
cline push action Your-name-account read [1] -p Your-name-account --json
```
## ✅ UPDATE


```
cline push action Your-name-account update '[ 1,  "My first Record Modified"]' -p Your-name-account --json
```
## ✅ DESTROY



```
cline push action Your-name-account destroy [1] -p Your-name-account --json
```
**Tinggal Ke Web Testnet Inerynya Dah, Di Bagian Task 3 Klik Read More dan Klik Finish, Done Tunggu Review Approve**
