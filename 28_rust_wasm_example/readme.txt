Rust WebAssembly Example
How to set up a Rust library, compile it to WebAssembly (Wasm), and run it in a web browser.

Prerequisites
Before you begin, ensure you have met the following requirements:

Rust and Cargo are installed. If not, you can install them from https://rustup.rs/.
wasm32-unknown-unknown target is added to Rust. You can add it by running rustup target add wasm32-unknown-unknown.
wasm-bindgen-cli is installed. Install it with cargo install wasm-bindgen-cli.
Python (for running a simple HTTP server). Python comes pre-installed on many Linux distributions, including Fedora. You can check if Python is installed by running python --version or python3 --version.
Project Structure
The project consists of the following files:

Cargo.toml: The Rust package manifest file.
src/lib.rs: The Rust source file.
index.html: A sample HTML file to run the WebAssembly module.
Setup and Compilation
Clone the repository and navigate to the project directory:

bash
Copy code
git clone <your-repository-url>
cd rust_wasm_example
Compile the Rust project:

css
Copy code
cargo build --target wasm32-unknown-unknown --release
Generate the WebAssembly bindings:

sql
Copy code
wasm-bindgen target/wasm32-unknown-unknown/release/rust_wasm_example.wasm --out-dir .
This will generate rust_wasm_example.js and rust_wasm_example_bg.wasm in the project directory.

Running the App
Start a local HTTP server using Python:

For Python 3.x:

Copy code
python3 -m http.server
For Python 2.x:

Copy code
python -m SimpleHTTPServer
This will start a local web server at http://localhost:8000/.

Open your web browser and navigate to http://localhost:8000/.

You should see your HTML page, and the WebAssembly module should run as intended.

Clean Up
To stop the local HTTP server, press Ctrl+C in the terminal where the server is running.

License
Add your license information here.

Please replace <your-repository-url> with the actual URL of your Git repository. Also, adjust any file or directory names if your project structure differs from the assumed one in this guide

/////////////
example html script to run the wasm. 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rust + WebAssembly</title>
  <script type="module">
    import init, { add } from './rust_wasm_example.js';

    async function run() {
      await init();
      alert("2 + 3 = " + add(2, 3));
    }

    run();
  </script>
</head>
<body>
  <h1>Hello, WebAssembly!</h1>
</body>
</html>

