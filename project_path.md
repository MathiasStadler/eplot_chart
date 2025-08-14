# project_path.md
<!-- keep the format -->
## Create for your own project a new project folder in the console(terminal ,bash shell), e.g. in your own home folder, and open it as a new project inside your program used - in my case MS VSCode / MS VSCodium
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
project_name="rust_main_startup"
echo ${project_name} 
# cd && mkdir <project_name> folder> && cd $_
# command 'cd' change to home folder from logged in user
# command 'mkdir' create the DIRECTORY(ies), if they do not already exist
# command `cd` <folder>`change to the folder
# command '$_' last argument of last command
cd && mkdir ${project_name} && cd $_
```
<!-- keep the format -->
>&nbsp;[!TIP]
><!-- keep the format -->
>- Bash Special Variables (\$0,\$?,\$#, \$@, \$\$, \$*, \$-) [![alt text][1]](https://tecadmin.net/bash-special-variables/)
>- Another desc [1](https://stackoverflow.com/questions/5163144/what-are-the-special-dollar-sign-shell-variables)
<!-- -->
## Create a new rust based project inside the previously generated folder and update the rust binary's system wide to the last stable version
<!-- -->
```bash <!-- markdownlint-disable-line code-block-style -->
touch README.md \
&& ln -s README.md README \
&& cargo init "." \
&& cargo add rustfmt \
&& rustup component add rustfmt \
&& mkdir examples \
&& cp src/main.rs examples/example.rs \
&& sed -i -e 's/world/example/g' examples/example.rs \
&& rustup show \
&& rustup check \
&& rustup toolchain uninstall stable \
&& rustup toolchain install stable \
&& rustup update  --force \
&& rustup show \
&& mkdir tests
```
<!-- keep the format -->
## Show rustc version verbose
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustc --version --verbose
```
<!-- keep the format -->
>&nbsp;[!TIP]
> Make sure the stable toolchain is activated
<!-- keep the format -->
## Show which toolchain is active
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustup show
# or better
rustup show |sed -n '/active toolchain/,/^$/p'
```
<!-- keep the format -->
>[!TIP] Markdownlint - Rules inside files can be enabled, disabled
> <!-- markdownlint-disable-next-line --> [![alt text][1]](https://github.com/DavidAnson/markdownlint)
<!-- keep the format -->
## Set/switch  rust toolchain - switch stable to nightly and back
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
rustup override set nightly
#or
rustup override set stable
```
<!-- keep the format -->
## Cargo clean - Remove artifacts that cargo has generated in the past
<!-- keep the format -->
- -v, --verbose...               Use verbose output (-vv very verbose/build.rs output)
<!-- markdownlint-disable-next-line -->
--color <WHEN>             Coloring [possible values: auto, always, never]
<!-- keep the format -->
```bash <!-- markdownlint-disable-line code-block-style -->
cargo clean -vv --color always
```
<!-- keep the format -->
<!-- make folder and download the link sign vai curl -->
<!-- mkdir -p img && curl --create-dirs --output-dir img -O  "https://raw.githubusercontent.com/MathiasStadler/link_symbol_svg/refs/heads/main/link_symbol.svg"-->
<!-- Link sign - Don't Found a better way :-( - You know a better method? - send me a email -->
[1]: ./img/link_symbol.svg
<!-- keep the format -->