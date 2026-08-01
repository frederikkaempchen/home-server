# setup instructions
1. install podman ``` sudo apt-get install podman```
2. create directory in for quadlets: ```mkdir -p ~/.config/containers/systemd```
3. go there ```cd ~/.config/containers/systemd```
4. clone this repo ```git clone https://github.com/frederikkaempchen/home-server```
5. reload daemon in order to regiser these new quadlets ```systemctl --user daemon-reload```
6. remove all services you don't need
7. create filebrowser admin password podman secret ```echo -n 'password123' | podman secret create filebrowser_admin_pwd -```
8. get api key for cloudflare tunnel - follow [instructions here](https://developers.cloudflare.com/tunnel/)
9. enter api key after the --token flag in cloudflared.container
10. start the services: ```systemctl --user start <service name>```
11. check status: ```systemctl --user status <service name>``` or ```podman ps``` or ...

full bash script until step 8 with filebrowser password "password123" for admin user - change that later:
```
sudo apt-get install podman -y && mkdir -p ~/.config/containers/systemd && cd ~/.config/containers/systemd && git clone https://github.com/frederikkaempchen/home-server && systemctl --user daemon-reload && echo -n 'password123' | podman secret create filebrowser_admin_pwd -
```
then continue with steps 8 to 11
