# Certbot

Certbot 是 Let's Encrypt 官方推荐的一个客户端，用于SSL证书的生成和更新。

SSL 证书选择有很多，其中有很多免费的方案可供选择，各大云厂商也提供有一定数量的免费证书。免费 SSL 证书中普遍认为 Let's Encrypt 做的还不错，下面简单介绍一下 Let's Encrypt 在 Ubuntu 上的安装和使用。

## 简介

[Let's Encrypt](https://letsencrypt.org/) 是一家免费、开放、自动化的证书颁发机构（CA），为公众的利益而运行。 它是一项由 Internet Security Research Group (ISRG) 提供的服务。

其原则为：

- 免费

  任何拥有域名的人都可以使用 Let’s Encrypt 免费获取受信的证书。

- 自动化

  运行于服务器上的软件可以与 Let’s Encrypt 直接交互，以便轻松获取证书，安全地配置它，并自动进行续期。

- 安全

  Let’s Encrypt 将成为一个推动 TLS 安全最佳实践发展的的平台，无论是作为一个证书颁发机构（CA）还是通过帮助网站运营商正确地保护其服务器。

- 透明

  所有颁发或吊销的证书将被公开记录，供任何人查阅。

- 开放

  自动签发和续订协议 已经发布 作为其他人可以采用的开放标准。

- 乐于合作

  就像互联网底层协议本身一样，Let’s Encrypt 是为了让整个互联网社区受益而做出的共同努力，它不受任何单一组织的控制。


## 安装

使用 snapd 安装 certbot：

    sudo apt install snapd
    sudo snap install core; sudo snap refresh core
    sudo snap install --classic certbot
    sudo ln -s /snap/bin/certbot /usr/bin/certbot

## 使用

创建证书：

    sudo certbot --nginx

实例：

    $ sudo certbot --nginx
    Saving debug log to /var/log/letsencrypt/letsencrypt.log
    
    Which names would you like to activate HTTPS for?
    We recommend selecting either all domains, or all domains in a VirtualHost/server block.
    - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    1: backre.com
    2: endrawing.com
    4: ohmycommit.com
    - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    Select the appropriate numbers separated by commas and/or spaces, or leave input
    blank to select all options shown (Enter 'c' to cancel): 1
    Requesting a certificate for backre.com
    
    Successfully received certificate.
    Certificate is saved at: /etc/letsencrypt/live/backre.com/fullchain.pem
    Key is saved at:         /etc/letsencrypt/live/backre.com/privkey.pem
    This certificate expires on 2023-05-05.
    These files will be updated when the certificate renews.
    Certbot has set up a scheduled task to automatically renew this certificate in the background.
    
    Deploying certificate
    Successfully deployed certificate for backre.com to /etc/nginx/sites-enabled/backre.com
    Congratulations! You have successfully enabled HTTPS on https://backre.com
    
    - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
    If you like Certbot, please consider supporting our work by:
     * Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
     * Donating to EFF:                    https://eff.org/donate-le
    - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

配置自动做好了，证书更新也是自动的，好方便！

## 参考资源

[How to Install Let’s Encrypt SSL on Ubuntu with Certbot](https://www.inmotionhosting.com/support/website/ssl/lets-encrypt-ssl-ubuntu-with-certbot/)



