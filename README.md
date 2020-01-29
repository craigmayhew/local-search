# local-search
Search local files, regardless of OS. Optionally, remote locations.

## Objectives / Todo
[x] Manual search links, from a single html file.
[ ] Automated local search!
[ ] Automated remote search (using offline first paradigm)
[ ] Indexed search

## Windows Manual Web Page
[Browser Search Page](search-page-windows.html)

## Command Line Local Search
```sh
# I'm assuming you already have rust installed locally
cargo install ripgrep
```

### Windows Usage
Usage `search something`
```powershell
function search($searchTerms) {
  # search my github folder
  rg $searchTerms $Env:USERPROFILE/Documents/GitHub/;
  # search local rust docs
  rg $searchTerms $Env:USERPROFILE/.rustup/toolchains/stable-x86_64-pc-windows-msvc/share/doc/rust/html/;
  # search local ipfs cache
  rg $searchTerms $Env:USERPROFILE/.ipfs/blocks/
}
```

### Linux Usage
Usage `search something`
```sh
search () {
  # search my github folder
  rg $(echo $1) ~/GitHub/
  # search local rust docs
  rg $(echo $1) ~/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/share/doc/rust/html/;
  # search local ipfs cache
  rg $(echo $1) ~/.ipfs/blocks/
}
```