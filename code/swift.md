# swift

## Installing swift

### On macOS

Acquire Xcode. Suffer.

### On Windows

Technically this is on WSL. So this is also the **On Linux** section. Anyway.

```bash
sudo apt-get install clang libicu-dev # install necessary deps

# for swift 5.1.1
curl -o swift.tar.gz https://swift.org/builds/swift-5.1.1-release/ubuntu1804/swift-5.1.1-RELEASE/swift-5.1.1-RELEASE-ubuntu18.04.tar.gz
tar -zxvf swift.tar.gz
```

add `swiftc` (in `swift/usr/bin`) to your PATH and you can now compile and run `.swift` files with `swiftc` on the commandline
