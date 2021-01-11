# guide for Minecraft v1.13.1 server
# update minecraft server and spigot links for latest versions
 
# get started
mkdir minecraft_py; cd minecraft_py; mkdir spigot; cd spigot
 
# download minecraft server from https://minecraft.net/en-us/download/server/
wget https://launcher.mojang.com/v1/objects/fe123682e9cb30031eae351764f653500b7396c9/server.jar
 
# download spigot server from https://getbukkit.org/download/spigot
wget -O spigot.jar https://cdn.getbukkit.org/spigot/spigot-1.13.1.jar
 
# agree to eula
echo eula=true > eula.txt
 
# get RaspberryJuice from https://dev.bukkit.org/projects/raspberryjuice
mkdir plugins; cd plugins
wget -O raspberryjuice-1.11.jar https://dev.bukkit.org/projects/raspberryjuice/files/2496319/download
 
# get the mcpi libraries from https://github.com/zhuowei/RaspberryJuice
cd ../..
git clone https://github.com/zhuowei/RaspberryJuice.git
mkdir py
cp -r RaspberryJuice/src/main/resources/mcpi/api/python/modded/mcpi py/
 
# download an example python script from https://www.dropbox.com/s/k29ms42nzvgehjk/rainbow.py?dl=0
# alternatively see example here https://dev.bukkit.org/projects/raspberryjuice
cd py
wget -O rainbow.py https://www.dropbox.com/s/k29ms42nzvgehjk/rainbow.py\?dl\=1
 
# run spigot
cd ../spigot; java -jar spigot.jar
 
# in a new terminal under the minecraft_py/py folder
python2 rainbow.py