# Unifi-Netflix-Bypass
Unifi Policy-Based Route for Netflix
## Setting up the Host VPN
> [!NOTE]
> The host side of the VPN is going to be the "Home" location of the Netflix account

- Navigate to Settings > VPN > VPN Server
  - Select "WireGuard"

![alt text](<1.png>)

- Click "Add Client"
  - Give it a Name
  - Press the "Download" button next to the QR code

 ![alt text](<2.png>)

 - Press "Add" at the bottom of the page

 ![alt text](<3.png>)

## Setting up the Client VPN

> [!NOTE]
> The client side of the VPN is where you want to access Netflix from whithout adding additional "home location" to the account.

- Navigate to Settings > VPN > VPN Client
  - Click "Create New"
 
 ![alt text](<4.png>)

- Select "WireGuard"
  - Give it a name
  - Press "Upload"

 ![alt text](<5.png>)

 - Select the .conf file we downloaded earlier

 ![alt text](<6.png>)

## Setting up the Routing

On the Client Side
- Navigate to Settings > Routing > Policy-Based Routes
  - Give it a name
  - Select "Specific Traffic" for What to Route?
  - Select "All Devices" for Source
  - Delect "Domain Name" for Destination
  - Select your Cliant VPN from the Interface Drop down. (Netflix Bypass in my example)
  - Leave Fallback unchecked
  - Click "Batch Add"

 ![alt text](<7.png>)

- Download the Netflix Url file [Here](https://github.com/esmith443/Unifi-Netflix-Bypass/blob/main/Netflix%20Urls.txt)
- Press the Download Raw File button in the top right

 ![alt text](<8.png>)
