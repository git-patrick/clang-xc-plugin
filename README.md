# clang-xc-plugin
Clang 3.7 Plugin for Xcode

`brew install llvm --with-clang --with-lld --HEAD`

If your <a href="http://brew.sh/" title="homebrew">homebrew</a> is setup to install to `/usr/local` after a lengthy build process you will end up with the most up to date LLVM available installed at `/usr/local/opt/llvm`.  

If your homebrew is setup to install somewhere else, you will need to edit the file `Clang 3.7.xcplugin/Contents/Resources/Clang 3.7.xcspec` in Xcode.  What you want to change is Item0.ExecPath to the full path to your brew installed `clang` executable (defaults to `/usr/local/opt/llvm/bin/clang`), Item1.ExecCplusPlusLinkerPath to the full path to your `clang++` executable, and Item2.ExecPath to the full path to your `clang` as in Item0.ExecPath).

Copy the `Clang 3.7.xcplugin` directory into `/Applications/Xcode.app/Contents/PlugIns/Xcode3Core.ideplugin/Contents/SharedSupport/Developer/Library/Xcode/Plug-ins`.

Restart Xcode.  You should be able to select `LLVM 3.7` under `Build Options -> Compiler for C/C++/Objective-C`.
