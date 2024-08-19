# Unifi-Netflix-Bypass
Unifi Policy-Based Route for Netflix

This is for users who want to access a Netflix account without purchasing an additional "Home Location"

I will update the "Netflix Urls.txt" as I discover more.

> [!IMPORTANT]
> 1. This guide only works if both locations have a Unifi Cloud Gateway.
> [Here](https://store.ui.com/us/en?category=all-unifi-cloud-gateways)
>
> 2. Netflix has IPv6 addresses and Unifi's Policy-Based Routes do not work for IPv6.
>    - A workaround is to disable IPv6 (Host and Client)
>    - Settings > Internet > WAN1
>
> 
>  ![alt text](<IMGs/13.png>)

## Setting up the Host VPN
> [!NOTE]
> The host side of the VPN is going to be the "Home" location of the Netflix account
> Unifi's Policy-Based Routes do not work for IPv6.

- Navigate to Settings > VPN > VPN Server
  - Select "WireGuard"

![alt text](<IMGs/1.png>)

- Click "Add Client"
  - Give it a Name
  - Press the "Download" button next to the QR code
  - Once Downloaded Press "Add"

 ![alt text](<IMGs/2.png>)

 - Press "Add" at the bottom of the page

 ![alt text](<IMGs/3.png>)

## Setting up the Client VPN

> [!NOTE]
> The client side of the VPN is where you want to access Netflix from whithout purchasing an additional "Home Location"

- Navigate to Settings > VPN > VPN Client
  - Click "Create New"
 
 ![alt text](<IMGs/4.png>)

- Select "WireGuard"
  - Give it a name
  - Press "Upload"

 ![alt text](<IMGs/5.png>)

 - Select the .conf file we downloaded earlier

 ![alt text](<IMGs/6.png>)

## Setting up the Routing

On the Client Side
- Navigate to Settings > Routing > Policy-Based Routes
  - Give it a name
  - Select "Specific Traffic" for What to Route?
  - Select "All Devices" for Source
  - Select "Domain Name" for Destination
  - Select your Cliant VPN from the Interface Drop down. (Netflix Bypass in my example)
  - Leave Fallback unchecked
  - Click "Batch Add"

 ![alt text](<IMGs/7.png>)

- Download the Netflix Url file [Here](https://github.com/esmith443/Unifi-Netflix-Bypass/blob/main/Netflix%20Urls.txt)
  - Press the Download Raw File button in the top right

 ![alt text](<IMGs/8.png>)

- Click "Import from a File"

 ![alt text](<IMGs/9.png>)

- Select the "Netflix Urls.txt" file you downloaded

 ![alt text](<IMGs/10.png>)

- Click "Add"

 ![alt text](<IMGs/11.png>)

- Click "Add Entry"

 ![alt text](<IMGs/12.png>)
