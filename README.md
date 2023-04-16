<!-- @format -->

# Example in Rust

This is an example of an API in rust. To run this file you must have rust installed. Follow this instruction from their oficial website: https://www.rust-lang.org/tools/install

# BUILD - To compile the files for production write in the terminal:

This Build Script can be use in any CI/CD tool of your preference. It is the advantage of write a bash script, you can run it in CI/CD tools. Tools like GitHub Actionsm, Jenkins, Circle, TeamCity and other are able to run Bash Scripts.

```
cargo build --release
```

Additonally you can use the script build in the russt-example folder. run in the termninal ./build_rust

You will find the compile file in /target/release/backend
To run the compile file write in the terminal

```
./backend
```

# To run this program write in the terminal:

```
cargo run
```

# To run the Unit Test Cases

```

cargo test
```

- In the file main.rs , you will find 5 unit test cases. The case 4 and 5 file.
