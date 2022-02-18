# libsignal-client-alpine

```bash
apk add rustup protoc gcc musl-dev git
rustup-init --default-toolchain nightly -y
source ~/.cargo/env
export RUSTFLAGS="-C target-feature=-crt-static"
cd /home
wget https://github.com/signalapp/libsignal-client/archive/refs/tags/v0.12.3.tar.gz
tar xf v0.12.3.tar.gz
cd libsignal-client-0.12.3/java
sed -i "s/, ':android'//" settings.gradle
sh build_jni.sh desktop
cp ../target/release/libsignal_jni.so /home/out/
```
