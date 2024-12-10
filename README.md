
## LLVM14 and Later
NDK LLVM: https://android.googlesource.com/toolchain/llvm-project

Apple LLVM: https://github.com/apple/llvm-project

Normal LLVM: https://github.com/llvm/llvm-project

### LegacyPass
```
wget https://heroims.github.io/obfuscator/LegacyPass/ollvm14.patch
git clone -b release/14.x git@github.com:llvm/llvm-project.git
cd llvm-project
git apply ../ollvm14.patch
```
### NewPass
```
wget https://heroims.github.io/obfuscator/NewPass/ollvm14.patch
git clone -b release/14.x git@github.com:llvm/llvm-project.git
cd llvm-project
git apply ../ollvm14.patch
```
### Resolve Conflict
```
git apply --reject --ignore-whitespace ../ollvm14.patch
```
And then follow the .rej prompts to modify

## Please have a look at the [wiki](https://github.com/heroims/obfuscator/wiki)!

You can cite Obfuscator-LLVM using the following Bibtex entry:

```
@INPROCEEDINGS{ieeespro2015-JunodRWM,
  author={Pascal Junod and Julien Rinaldini and Johan Wehrli and Julie Michielin},
  booktitle={Proceedings of the {IEEE/ACM} 1st International Workshop on Software Protection, {SPRO'15}, Firenze, Italy, May 19th, 2015},
  editor = {Brecht Wyseur},
  publisher = {IEEE},
  title={Obfuscator-{LLVM} -- Software Protection for the Masses},
  year={2015},
  pages={3--9},
  doi={10.1109/SPRO.2015.10},
}
```
编译参数OLLVM 编译后替换 clang.exe 等到VS2019

替换路径 C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Tools\Llvm\x64\bin

mkdir build
cd build
D:\CMake\bin\cmake -G “Visual Studio 16 2019” -DLLVM_ENABLE_PROJECTS=“clang” -DCMAKE_BUILD_TYPE=Release -DLLVM_INCLUDE_TESTS=OFF -DLLVM_ENABLE_NEW_PASS_MANAGER=OFF ..\llvm


