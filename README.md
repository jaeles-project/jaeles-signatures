
<p align="center">
  <img alt="Jaeles" src="https://image.flaticon.com/icons/svg/1432/1432425.svg" height="140" />
  <p align="center">
    <a href=""><img alt="Software License" src="https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square"></a>
    <a href="http://github.com/jaeles-project/jaeles"><img alt="Release" src="https://img.shields.io/github/v/release/jaeles-project/jaeles.svg"></a>
  </p>
</p>

***


<p align="center">
  <h4>
    This repo only contain Default Signatures for  project. Pull requests or any ideas are welcome.
  </h4>
  <h4>
  Please read the Official Documentation <a href="https://jaeles-project.github.io/signatures/">here</a> for writing your own signature.
  </h4>
</p>

***

### Installation

Try to clone signatures folder to somewhere like this
```
git clone --depth=1 https://github.com/jaeles-project/jaeles-signatures /tmp/jaeles-signatures/
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
  jaeles scan -v -s '~/my-signatures/products/wordpress/.*' -u 'https://wp.example.com/blog/' -p 'root=[[.URL]]'
  cat urls.txt | grep 'interesting' | jaeles scan -c 50 -s /tmp/jaeles-signatures/cves/sample.yaml -U list_of_urls.txt --proxy http://127.0.0.1:8080

```

***

### Structure of the Repo

Jaeles look for signature as a single file so you can structure it as whatever you want. This is just an example.

| Page           | Description                        |
|----------------|------------------------------------|
| **common**     | Implement misconfiguration for some popular apps  |
| **cves**       | Implement some CVE |
| **sensitvie**       | Some common path with sensitive information |
| **probe**      | Used for detect some technology used by the target|
| **passives**      | Used for [passive detection](https://jaeles-project.github.io/signatures/passive/)|
| **fuzz**       | Some common case for fuzz mode (I know a lot of false positive here) |

## Note for using Fuzz signatures
Fuzz signatures may have many false positive because I can't defined exactly what is vulnerable for everything. So make sure you gotta know what are you doing here.

## Showcases

|  ![apache-status.png](https://github.com/jaeles-project/jaeles-plugins/blob/master/imgs/apache-status.png?raw=true) [**Apache Server Status**](https://youtu.be/nkBcIvzi3H4)  |  ![tableau-dom-xss.png](https://github.com/jaeles-project/jaeles-plugins/blob/master/imgs/tableau-dom-xss.png?raw=true) [**Tableau DOM XSS CVE-2019-19719**](https://youtu.be/EG7Qmt8kt58) |
|:----------:|:-------------:|
| ![rabbitmq-cred.png](https://github.com/jaeles-project/jaeles-plugins/blob/master/imgs/rabbitmq-cred.png?raw=true) [**RabbitMQ Default Credentials**](https://youtu.be/ed4n1sCNu3s) | ![jenkins-xss.png](https://github.com/jaeles-project/jaeles-plugins/blob/master/imgs/jenkins-xss.png?raw=true) [**Jenkins XSS CVE-2020-2096**](https://youtu.be/JfihhEOEWSE) |

<h4 align='center'> More showcase can be found <a href="https://jaeles-project.github.io/showcases/">here</a></h4>

***

### Financial Contributors

Become a financial contributor and help us sustain our community. [[Contribute](https://opencollective.com/jaeles-project/contribute)]


## License

`Jaeles` is made with ♥  by [@j3ssiejjj](https://twitter.com/j3ssiejjj) and it is released under the MIT license.

## Donation

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://paypal.me/j3ssiejjj)
