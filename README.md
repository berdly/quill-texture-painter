*Quill Texture Painter*

Build instructions:
This project makes use of the Emscripten toolchain for compiling C++ to WebAssembly and CMake for building.
Please refer to the following link for details on installing these tools: 
https://emscripten.org/docs/getting_started/downloads.html

Once the Emscripten toolchain and CMake are installed, the project can be built using the following commands from the root of the repo:
emcmake cmake -B build .
cmake --build build

And a it can be served locally with the command:
emrun build/quill.html
