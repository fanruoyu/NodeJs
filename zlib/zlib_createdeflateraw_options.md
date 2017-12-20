<!-- YAML
added: v0.5.8
-->

创建并返回一个带有给定 [options][] 的新的 [DeflateRaw][] 对象.

*Note*: An upgrade of zlib from 1.2.8 to 1.2.11 changed behavior when windowBits
is set to 8 for raw deflate streams. zlib would automatically set windowBits
to 9 if was initially set to 8. Newer versions of zlib will throw an exception,
so Node.js restored the original behavior of upgrading a value of 8 to 9,
since passing `windowBits = 9` to zlib actually results in a compressed stream
that effectively uses an 8-bit window only.
