# QPACK

This is a minimal QPACK implementation in Go. It is minimal in the sense that it doesn't use the dynamic table at all, but just the static table and (Huffman encoded) string literals. Wherever possible, it reuses code from the [HPACK implementation in the Go standard library](https://github.com/golang/net/tree/master/http2/hpack).

It should be able to interoperate with other QPACK implemetations (both encoders and decoders), however it won't achieve a high compression efficiency.

## Running the interop tests

Install the [QPACK interop files](https://github.com/qpackers/qifs/) by running
```bash
git submodule update --init --recursive
```

Then run the tests:
```bash
ginkgo integrationtests
```