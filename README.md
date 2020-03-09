# google-hosts

[**What**](#what) \| [**How**](#how) \| [**Must**](#must) \| [**Contributing**](#contributing) \| [**License**](#license)

## What

This project provides some tools to help you find google IP.

## How

> [Requirements][Requirements]

**`getssl.sh` get IP detail**

    $ cd google-hosts/scripts

    # get detail of 192.168.1.1
    $ ./getssl.sh 192.168.1.1

**`find.sh` wrapper of getssl.sh, get IP detail from CIDR**

    $ cd google-hosts/scripts

    # find IP from 192.168.1.1/24
    $ ./find.sh 192.168.1.1/24

**`filter.sh` filter IP from output directory(generated by find.sh) for some domain**

    $ cd google-hosts/scripts

    # filter IP for *.google.com
    $ ./filter.sh *.google.com

    # filter IP for mail.google.com
    $ ./filter.sh mail.google.com

**`use.sh` use IP for some domain and update hosts.all**

    $ cd google-hosts/scripts

    # use 192.168.1.1 for *.google.com 
    $ ./use.sh *.google.com 192.168.1.1

    # use 192.168.1.1 for mail.google.com 
    $ ./use.sh mail.google.com 192.168.1.1

**`select.sh` run filter.sh, use.sh, use the best IP for domains in hosts.all**

    $ cd google-hosts/scripts
    $ ./select.sh

**`apply.sh` update ../hosts from hosts.all** 

    $ cd google-hosts/scripts
    $ ./apply.sh

**`auto.sh` find CIDR from a DNS and run find.sh, select.sh, apply.sh**

    $ cd google-hosts/scripts
    $ ./auto.sh DNS # DNS is like 8.8.8.8, but you should try DNS in diffrent countries.

Explaination of output 

| IP  | LOSS        | TIME      | SSL        |
| --- | ----------- | --------- | ---------- |
| IP  | packet loss | ping time | ssl domain |

## Must

-   Use google dns / opendns / other
-   Use international google. Make google no country redirect: <https://www.google.com/ncr>
-   Use `https`

## Contributing

-   vim:ts=4:sw=4:expandtab:ff=unix:encoding=utf8

## License

Licensed under The [MIT][MIT] License

[Requirements]: https://github.com/txthinking/google-hosts/blob/master/scripts/README.md

[MIT]: https://github.com/txthinking/google-hosts/blob/master/LICENSE
