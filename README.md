# MobileDataManager

A [RaspAP](https://raspap.com) plugin that manages 4G/LTE QMI modems through
ModemManager (`mmcli`) and NetworkManager (`nmcli`). It shows the modem's state,
signal, operator and registration (home or roaming), and sets up the mobile data
connection (APN, credentials) from the web interface.

It ships with the RaspAP images of
[Citronics](https://github.com/Citronics/debos-citronics) for the Fairphone 2 and
Fairphone 3 running mainline Linux.

## Requirements

- RaspAP 3.x
- `modemmanager`, `network-manager`, `libqmi-utils`
- `rmtfs` on Qualcomm phones

## Installation

Copy this repository to RaspAP's plugin directory and install the sudoers
rules from `manifest.json`:

```sh
sudo git clone https://github.com/Spin42/MobileDataManager /var/www/html/plugins/MobileDataManager
```

The plugin then appears as **Mobile Data** in RaspAP's sidebar.

## Command-line equivalent

```sh
nmcli connection add type gsm ifname '*' con-name gsm apn <YOUR_APN> gsm.initial-eps-bearer-apn <YOUR_APN>
nmcli connection up gsm
```

## License

GPL-3.0, see [LICENSE](LICENSE).
