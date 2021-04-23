all: www/app/main.wasm

www/app/main.wasm: target/wasm32-unknown-unknown/release/main.wasm
	mkdir -p www/app
	cp target/wasm32-unknown-unknown/release/main.wasm www/app/

target/wasm32-unknown-unknown/release/main.wasm: src/lib.rs
	cargo build --release --target wasm32-unknown-unknown
	mv -f target/wasm32-unknown-unknown/release/min_wasm.wasm target/wasm32-unknown-unknown/release/main.wasm

clean:
	rm -R target www/app
