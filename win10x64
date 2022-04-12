echo ":::::Windows 10 x64 RDP By D@rkshadow Myanmar:::::"
echo "Download files windows"
apt-get update && apt-get upgrade -y
apt-get clean
wget -O w10x64.img https://bit.ly/akuhnetW10x64
echo "Load ngrok"
wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip > /dev/null 2>&1
unzip ngrok-stable-linux-amd64.zip > /dev/null 2>&1
read -p "Ctrl + V Authtoken(import token ngrok): " CRP 
./ngrok authtoken $CRP 
nohup ./ngrok tcp 3388 &>/dev/null &
echo Download files from sever
apt-get install qemu
echo "Please wait...."
echo "Start up Windows"
echo RDP Address:
curl --silent --show-error http://127.0.0.1:4040/api/tunnels | sed -nE 's/.*public_url":"tcp:..([^"]*).*/\1/p'
echo "Ctrl+C to Copy"
echo "Wait 1-2 Minutes to complete setup"
echo "Do not close this tab"
echo "Please support Hoang vtmc, thank you"
qemu-system-x86_64 -hda w10x64.img -m 8G -smp cores=4 -net user,hostfwd=tcp::3388-:3389 -net nic -object rng-random,id=rng0,filename=/dev/urandom -device virtio-rng-pci,rng=rng0 -vga vmware -nographic
sleep 43200
