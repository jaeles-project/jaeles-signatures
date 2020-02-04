
<p align="center">
  <img alt="Jaeles" src="https://image.flaticon.com/icons/svg/1432/1432425.svg" height="140" />
  <p align="center">
    <a href=""><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <a href="http://github.com/jaeles-project/jaeles"><img alt="Release" src="https://img.shields.io/badge/version-beta%20v0.1-red.svg"></a>
  </p>
</p>

***

This repo only contain default Signatures for [Jaeles](http://github.com/jaeles-project/jaeles) project. Pull requests or any ideas are welcome.

Please read the Official Documention [here](https://jaeles-project.github.io/signatures/) for writing your own signature.

### Structure of the Repo

Jaeles look for signature as a single file so you can stucture it as whatever you want. This is just an example.

| Page           | Description                        |
|----------------|------------------------------------|
| **common**     | Simple request for common pattern  |
| **cves**       | Implement some CVE |
| **fuzz**       | Some common case for fuzz mode |
| **sensitvie**       | Some common path with sensitive information |
| **probe**      | Used for detect some technology used by the target|
| **passives**      | Used for [passive detection](https://jaeles-project.github.io/signatures/passive/)|


### Examples

Example for simple single signature in scan mode [phpdebug.yaml](https://github.com/jaeles-project/jaeles-signatures/blob/master/fuzz/phpdebug.yaml)

Example for complex signature in scan mode [phpdebug.yaml](https://github.com/jaeles-project/jaeles-signatures/blob/master/fuzz/phpdebug.yaml)

Example for simple list signature in fuzz mode [content-type.yaml](https://github.com/jaeles-project/jaeles-signatures/blob/master/fuzz/mics/content-type.yaml)

Example for complex signature in fuzz mode [open-redirect-02.yaml](https://github.com/jaeles-project/jaeles-signatures/blob/master/fuzz/open-redirect/open-redirect-param.yaml)


## Showcases
More showcase [here](https://jaeles-project.github.io/showcases/)

[![asciicast](https://asciinema.org/a/281205.svg)](https://asciinema.org/a/281205)
<p align="center">
Detect Jira SSRF CVE-2019-8451
</p>


## License

`Jaeles` is made with ♥  by [@j3ssiejjj](https://twitter.com/j3ssiejjj) and it is released under the MIT license.