# C++ Ast

Inspired heavily by the sucessful broma library I designed this AST to help me 
fix bad ghidra code and be able to safely parse and Fix bad code and having
the ability to work side-by-side with broma to help reverse engineer
games such as geometry dash. However this should theoretically work with C++14
smoothly and help with other things like static anaylisis or other code modifications.



## Things That I needed

- Something Small, Portable and Easy to manipulate and Easy to port to other 
languages such as Python (Which is something I am working towards) or rust (In the future)

- A Parser that Could ignore undefined types in code at will as long as types are being pre-defined 
before the parsing of the AST Tree begins... 

- An Ast Tree with easy ways to modify it and reconstruct the code.

- Something fast and easy to maintain and can run within multiple threads without failure...

- With Robtop's now faster than ever pace at making updates and me wanting a 1 
to 1 decompilation of the latest version of the game while having a part-time job outside of here
and not enough people helping me or active people for that manner, we needed to rethink our approch entirely,
therefore some strategies needed changing from man-work to machine.

- In order to allow the GD Programming community to Help me I am using the same backend as broma uses 


## Things I will be using this library for 

- Fixing and Repairing things that should be Switchblocks
- Finding and replacing Android32 armabei-v7 asembly checks.



# Other Libraries And Ideas I attempted using but ultimately failed

### Editing Raw Strings using Regular expressions
- This was commonly error-prone and made it hard to replace ghidra structs with classes such as 
`basic_string*` to `std::string` or finding and getting rid of repeated variables.

### pycparser
- Did not have ability to register types or class objects before parsing. 
Sure you could write everything down the code as structs before execution 
but in the end it just adds on another layer of things to worry about that 
I didn't feel like I should bother with and I didn't want to bother with
reinventing the wheel entirely.

### LLVM-Clang
- I think you already know why, Types cannot be manipulated or predefined before parsing begins
and who wants to download 500MB to your computer?

### CXXParser
- The Closest thing you can get to a Cython Compiler AST Tree (Which is what I am after but for C++)
However I fear it's ability to handle something like Robtop's code would be very difficult and hard
to achieve. It's not really made for parsing anything past headerfiles...

### antlr-v4
Extremely Close to what I needed but I would've preferred Making Act more like the way Cython Compiler Nodes work...

### Why not use ai?
- I refuse to even touch ai with a 10 foot pole, truth is that the person on the other end is listening
and therefore, your the product which is something I resfuse to participate in. - Calloc




