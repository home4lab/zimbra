# zimbra using ubuntu 18

    sudo rm /etc/hostname
    sudo sh -c 'echo mail.free.com >> /etc/hostname'

sudo sh -c 'echo 192.168.1.1	mail.free.com mail >> /etc/hosts'

    sudo systemctl disable systemd-resolved
    sudo systemctl stop systemd-resolved

    sudo rm /etc/resolv.conf
    sudo sh -c 'echo nameserver 8.8.8.8 >> /etc/resolv.conf'

sudo apt install dnsmasq

    sudo sh -c 'echo '
    sudo sh -c 'echo server=192.168.1.1 >> /etc/dnsmasq.conf'
    sudo sh -c 'echo domain=free.com >> /etc/dnsmasq.conf'
    sudo sh -c 'echo mx-host= free.com, mail.free.com, 5 >> /etc/dnsmasq.conf'
    sudo sh -c 'echo mx-host=mail.free.com, mail.free.com, 5 >> /etc/dnsmasq.conf'
    sudo sh -c 'echo listen-address=127.0.0.1 >> /etc/dnsmasq.conf'

sudo systemctl restart dnsmasq

    wget https://files.zimbra.com/downloads/8.8.15_GA/zcs-8.8.15_GA_3869.UBUNTU18_64.20190918004220.tgz
    tar -xvf zcs-8.8.15_GA_3869.UBUNTU18_64.20190918004220.tgz
    cd zcs-8.8.15_GA_3869.UBUNTU18_64.20190918004220
    sudo ./install.sh


