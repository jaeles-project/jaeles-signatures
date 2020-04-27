
<p align="center">
  <img alt="Jaeles" src="https://image.flaticon.com/icons/svg/1432/1432425.svg" height="140" />
  <p align="center">
    <a href=""><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <a href="http://github.com/jaeles-project/jaeles"><img alt="Release" src="https://img.shields.io/badge/version-beta%20v0.8-red.svg"></a>
  </p>
</p>

***

This repo only contain default Signatures for [Jaeles](http://github.com/jaeles-project/jaeles) project. Pull requests or any ideas are welcome.

Please read the Official Documention [here](https://jaeles-project.github.io/signatures/) for writing your own signature.

### Installation

Try to clone signatures folder to somewhere like this
```
git clone https://github.com/jaeles-project/jaeles-signatures /tmp/jaeles-signatures/
```

then reload them in the DB with this command.
```
jaeles config -a reload --signDir /tmp/jaeles-signatures
```

### Usage 

```
Scan Usage example:
  jaeles scan -s <signature> -u <url>
  jaeles scan -c 50 -s <signature> -U <list_urls> -L <level-of-signatures>
  jaeles scan -c 50 -s <signature> -U <list_urls>
  jaeles scan -c 50 -s <signature> -U <list_urls> -p 'dest=xxx.burpcollaborator.net'
  jaeles scan -c 50 -s <signature> -U <list_urls> -f 'noti_slack "{{.vulnInfo}}"'
  jaeles scan -v -c 50 -s <signature> -U list_target.txt -o /tmp/output
  jaeles scan -s <signature> -s <another-selector> -u http://example.com
  jaeles scan -G -s <signature> -s <another-selector> -x <exclude-selector> -u http://example.com
  cat list_target.txt | jaeles scan -c 100 -s <signature>


Examples:
  jaeles scan -s 'jira' -s 'ruby' -u target.com
  jaeles scan -c 50 -s 'java' -x 'tomcat' -U list_of_urls.txt
  jaeles scan -G -c 50 -s '/tmp/custom-signature/.*' -U list_of_urls.txt
  jaeles scan -v -s '~/my-signatures/products/wordpress/.*' -u 'https://wp.example.com' -p 'root=[[.URL]]'
  cat urls.txt | grep 'interesting' | jaeles scan -L 5 -c 50 -s 'fuzz/.*' -U list_of_urls.txt --proxy http://127.0.0.1:8080

```

***

### Structure of the Repo

Jaeles look for signature as a single file so you can stucture it as whatever you want. This is just an example.

| Page           | Description                        |
|----------------|------------------------------------|
| **common**     | Implement misconfiguration for some popular app  |
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

### Note for using Fuzz signatures
Fuzz signatures may have many false positive because I can't defined exactly what is vulnerable for everything. So make sure you know what are you doing.

## Showcases
More showcase [here](https://jaeles-project.github.io/showcases/)

[![asciicast](https://asciinema.org/a/281205.svg)](https://asciinema.org/a/281205)
<p align="center">
Detect Jira SSRF CVE-2019-8451
</p>


## License

`Jaeles` is made with ♥  by [@j3ssiejjj](https://twitter.com/j3ssiejjj) and it is released under the MIT license.