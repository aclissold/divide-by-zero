Divide By Zero
==============
Some quick examples of what happens in different programming languages if you
attempt to divide by zero.

C
--
    1534718608

Go
--
    panic: runtime error: integer divide by zero
    [signal 0x8 code=0x7 addr=0x202f pc=0x202f]

    goroutine 1 [running]:
    main.main()
            /Users/aclissold/Code/divide-by-zero/example.go:7 +0x2f

    goroutine 2 [runnable]:
    runtime.forcegchelper()
            /usr/local/go/src/runtime/proc.go:90
    runtime.goexit()
            /usr/local/go/src/runtime/asm_amd64.s:2232 +0x1

    goroutine 3 [runnable]:
    runtime.bgsweep()
            /usr/local/go/src/runtime/mgc0.go:82
    runtime.goexit()
            /usr/local/go/src/runtime/asm_amd64.s:2232 +0x1

    goroutine 4 [runnable]:
    runtime.runfinq()
            /usr/local/go/src/runtime/malloc.go:712
    runtime.goexit()
            /usr/local/go/src/runtime/asm_amd64.s:2232 +0x1
    exit status 2

JavaScript
----------
    Infinity

Python
------
    Traceback (most recent call last):
      File "example.py", line 1, in <module>
        1/0
    ZeroDivisionError: integer division or modulo by zero

Ruby
----
    example.rb:1:in `/': divided by 0 (ZeroDivisionError)
        from example.rb:1:in `<main>'

Swift
-----
        0  swift                    0x000000010cdbda18 llvm::sys::PrintStackTrace(__sFILE*) + 40
        1  swift                    0x000000010cdbdef4 SignalHandler(int) + 452
        2  libsystem_platform.dylib 0x00007fff8f1ecf1a _sigtramp + 26
        3  libswiftCore.dylib       0x000000010fa62008 GCC_except_table20 + 41628
        4  swift                    0x000000010cbce0a4 llvm::MCJIT::runFunction(llvm::Function*, std::__1::vector<llvm::GenericValue, std::__1::allocator<llvm::GenericValue> > const&) + 276
        5  swift                    0x000000010debc5b6 llvm::ExecutionEngine::runFunctionAsMain(llvm::Function*, std::__1::vector<std::__1::basic_string<char, std::__1::char_traits<char>, std::__1::allocator<char> >, std::__1::allocator<std::__1::basic_string<char, std::__1::char_traits<char>, std::__1::allocator<char> > > > const&, char const* const*) + 1174
        6  swift                    0x000000010c9337b9 swift::RunImmediately(swift::CompilerInstance&, std::__1::vector<std::__1::basic_string<char, std::__1::char_traits<char>, std::__1::allocator<char> >, std::__1::allocator<std::__1::basic_string<char, std::__1::char_traits<char>, std::__1::allocator<char> > > > const&, swift::IRGenOptions&, swift::SILOptions const&) + 1737
        7  swift                    0x000000010c6a7598 frontend_main(llvm::ArrayRef<char const*>, char const*, void*) + 6408
        8  swift                    0x000000010c6a5ae6 main + 1814
        9  libdyld.dylib            0x00007fff8fb485c9 start + 1
        10 libdyld.dylib            0x000000000000000c start + 1883994692
        Stack dump:
        0.      Program arguments: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/swift -frontend -interpret example.swift -target x86_64-apple-darwin14.3.0 -enable-objc-interop -sdk /Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.10.sdk -color-diagnostics -module-name example
        zsh: illegal hardware instruction  swift example.swift
