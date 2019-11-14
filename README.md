
<p align="center">
  <img alt="Osmedeus" src="https://image.flaticon.com/icons/svg/1432/1432425.svg" height="140" />
  <p align="center">
    <a href=""><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <a href="https://github.com/j3ssie/Osmedeus"><img alt="Release" src="https://img.shields.io/badge/version-beta%20v0.1-red.svg"></a>
  </p>
</p>

**Jaeles** is a powerful, flexible and easily extensible framework written in Go for building your own Web Application Scanner.

![Architecture](https://github.com/jaeles-project/jaeles-plugins/blob/master/imgs/jaeles-architecture.png?raw=true)

This repo only contain default Signatures for Jaeles project. Please visit the
Official Documention [here](https://jaeles-project.github.io/).

[![asciicast](https://asciinema.org/a/281205.svg)](https://asciinema.org/a/281205)

### Structure of the Repo
Jaeles look for signature as a single file so you can stucture it as whatever you want. This is just an example.

| Page           | Description                        |
|----------------|------------------------------------|
| **common**     | Simple request for common pattern  |
| **cves**       | Implement some CVE |
| **fuzz**       | Some common fuzz case for fuzz mode |
| **probe**      | Used for detect some technology used by the target|

## License

`Jaeles` is made with ♥  by [@j3ssiejjj](https://twitter.com/j3ssiejjj) and it is released under the MIT license.