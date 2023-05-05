# CPP Lib compile

## Build commands

### Static

This will embed the dependencies in the executable, and changes to the dependencies will require the client application to be built again.

```sh
g++ -c shared.cpp
ar -cvq shared.a shared.o
g++ main.cpp shared.a -o main.out
```

### Dynamic

A dynamic dependency (shared / linked library) allows the dependency to be updated without changes to the client code, giving that the interface between the programs remain compatible.

```sh
g++ -c -fPIC shared.cpp
g++ -shared shared.o -o libshared.so
g++ -L. main.cpp -lshared -o main.out
```

## References

- [YoLinux](http://www.yolinux.com/TUTORIALS/LibraryArchives-StaticAndDynamic.html)
- [Jamie King](https://youtu.be/Jzh4ZULXsvo)
- [C Programming](https://www.cprogramming.com/tutorial/shared-libraries-linux-gcc.html)
- [Stackoverflow nested dependencies](https://stackoverflow.com/questions/61775728/gcc-shared-library-undefined-reference-on-nested-dependencies)
