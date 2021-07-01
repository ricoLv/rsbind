## 安装Rustup
- 参考 https://rustup.rs/

~~curl https://sh.rustup.rs -sSf | sh~~
```curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain nightly -y```

- 如果要切换版本
```sh
rustup default stable 
rustup default nightly
rustup default nightly-gnu
rustup default stable-gnu 
rustc —version
```

- 安装格式化代码工具
```sh
rustup component add rustfmt --toolchain nightly-x86_64-apple-darwin
```

## Android:

### 安装targes
```sh
rustup target add aarch64-linux-android arm-linux-androideabi armv7-linux-androideabi i686-linux-android
```
### 安装cargo ndk
```sh
cargo install cargo-ndk
```
### 安装Android NDK和SDK 
省略，自行百度
### 增加环境变量
```sh
export ANDROID_SDK_ROOT=/the/path/to/sdk
export ANDROID_NDK_HOME=/the/path/to/ndk
export PATH="$ANDROID_NDK_HOME/toolchains/llvm/prebuilt/{darwin-x86_64}/bin:$PATH"
```

### 测试环境是否搭建ok
自己在一个路径下新建一个工程： cargo new my_project --lib
编译试一下：cargo rustc  --target arm-linux-androideabi

## iOS:
### 安装targets
```sh
rustup target add aarch64-apple-ios x86_64-apple-ios
```

### 安装cargo-lipo
```sh
cargo install cargo-lipo
```

### xcode配置
```sh
xcode-select --install
xcode-select -s /Applications/Xcode.app/Contents/Developer
xcrun --show-sdk-path -sdk iphoneos
```
