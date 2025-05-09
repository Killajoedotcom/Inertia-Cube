Welcome to the tuning section for the Inertia Cube Addative Manufacturing Power Plant.

ICAMPP for short or just i3 or Inertia Cube

> [!NOTE]
> This is for experienced users, if you feel confident in your abilities please proceed.

> [!WARNING]
> We are not responsible for any damage caused to your printer, electronics or configurations

To start, DangerKlipper has been renamed to a feline called Kalico for whatever reason they thought necessary.


>[!CAUTION]
> you will have to reinstall all your goodies! NOT TO WORRY though we have you covered


To start:

SSH into your printer

If desired, make a backup copy of your existing Klipper installation by running:

```bash
mv ~/klipper ~/klipper_old
```

Then clone the Kalico repo and restart the klipper service:

```bash
git clone https://github.com/KalicoCrew/kalico.git ~/klipper
sudo systemctl restart klipper
```
then

```bash
sudo reboot
```

now close putty or whatever ssh terminal you use and re-ssh in again

run these:

```bash
cd klipper
```
then

```bash
git checkout bleeding-edge-v2
```

then

```bash
git pull --rebase
```

>[!tip]
>now were going to install all of your uninstalled goodies.

For probes: 

Beacon is found here:

```bash
cd ~
git clone https://github.com/beacon3d/beacon_klipper.git
./beacon_klipper/install.sh
```

Moonraker Update:

```bash
[update_manager beacon]
type: git_repo
channel: dev
path: ~/beacon_klipper
origin: https://github.com/beacon3d/beacon_klipper.git
env: ~/klippy-env/bin/python
requirements: requirements.txt
install_script: install.sh
is_system_service: False
managed_services: klipper
info_tags:
  desc=Beacon Surface Scanner
```

website link: ```https://docs.beacon3d.com/quickstart/```