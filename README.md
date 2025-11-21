# Home Network Documentation

## 1. Physical Topology

My home network is very simple because I live in a student shared house. We only have one Bell Wi-Fi router, and it is placed in the living room. All devices connect through Wi-Fi.

```
 [Living Room]
      |
   Bell Router
      |
------------------------------------------------
|              |              |               |
My Room    Roommate A     Roommate B      Kitchen
 Laptop       Phones         Laptop        Smart TV
 Phone
```

Around 20 devices in total because each student has multiple devices.

---

## 2. Logical Topology

All devices are in the same subnet: 192.168.0.0/24.
The router provides DHCP and assigns IP addresses automatically.

```
          Bell Router (192.168.0.1)
                   |
      -------------------------------------
      Phones / Laptops / iPad (~20 devices)
```

No VLANs or extra segmentation.

---

## 3. Addressing

(Information slightly modified for privacy.)

| Device        | IP Address (DHCP) | Notes          |
| ------------- | ----------------- | -------------- |
| Router        | 192.168.0.1       | Gateway        |
| My Laptop     | 192.168.0.25      | Auto assigned  |
| My Phone      | 192.168.0.41      | Auto assigned  |
| Other Devices | 192.168.0.50–150  | Roommates' IPs |

* Subnet Mask: 255.255.255.0
* DHCP Range: 192.168.0.10–200

---

## 4. Devices & Services

### Main Device

* Bell Home Hub Router

  * Wi-Fi 2.4G / 5G
  * DHCP
  * NAT
  * Basic firewall

### Other Devices

* Laptops
* Phones
* Tablets
* Smart TV
  No server or special services in the house.

---

## 5. Configurations (Simple Student Level)

### Router Settings

* LAN IP: 192.168.0.1
* DHCP: Enabled
* Wi-Fi Security: WPA2
* Firewall: Default
* No VLAN
* No port forwarding

### My Devices

* IP address: automatic
* DNS: automatic

---

## 6. Password Storage Method

I save the Wi-Fi password and router login password in my phone Notes app.
This method is simple but convenient for me.

---
