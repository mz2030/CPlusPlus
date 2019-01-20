# CPlusPlus

The C++ language and projects built with open source on any compiler . 
You'll find information about best-practices, gotchas,
and helpful libraries/resources for beginning to develop in C++ at LICENSE file.

Each C++ source file needs to be compiled into an object file. The object files resulting from the compilation of multiple source files are then linked into an executable, a shared library, or a static library (the last of these being just an archive of object files). C++ source files generally have the .cpp, .cxx or .cc extension suffixes.

A C++ source file can include other files, known as header files, with the #include directive. Header files have extensions like .h, .hpp, or .hxx, or have no extension at all like in the C++ standard library and other libraries’ header files (like Qt). The extension doesn’t matter for the C++ preprocessor, which will literally replace the line containing the #include directive with the entire content of the included file.

The first step that the compiler will do on a source file is run the preprocessor on it. Only source files are passed to the compiler (to preprocess and compile it). Header files aren’t passed to the compiler. Instead, they are included from source files.

Each header file can be opened multiple times during the preprocessing phase of all source files, depending on how many source files include them, or how many other header files that are included from source files also include them (there can be many levels of indirection). Source files, on the other hand, are opened only once by the compiler (and preprocessor), when they are passed to it.

For each C++ source file, the preprocessor will build a translation unit by inserting content in it when it finds an #include directive at the same time that it’ll be stripping code out of the source file and of the headers when it finds conditional compilation blocks whose directive evaluates to false. It’ll also do some other tasks like macro replacements.

Once the preprocessor finishes creating that (sometimes huge) translation unit, the compiler starts the compilation phase and produces the object file.

To obtain that translation unit (the preprocessed source code), the -E option can be passed to the g++ compiler, along with the -o option to specify the desired name of the preprocessed source file.
