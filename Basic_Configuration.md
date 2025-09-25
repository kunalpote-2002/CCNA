# Basic Configuration (1 Router + 1 PC)

## 🖧 Topology

### 🔹 Step 1: Devices Required
- 1 Router  
- 1 PC  
- 1 Copper Straight-Through Cable  

---

### Step 2: Connections
- Connect **PC0 → FastEthernet0**  
- Connect **Router0 → FastEthernet0/0**  

<img width="375" alt="Screenshot 2025-09-12 214649" src="https://github.com/user-attachments/assets/a300017c-04c6-4353-b90f-ee46fa8e7611" />

---

### Step 3: Router Configuration
1. Click on router
2. Go to cli

   <img width="550" alt="Screenshot 2025-09-12 215128" src="https://github.com/user-attachments/assets/8dd55ba7-ea31-4dfc-ba4c-309973584154" />

3. Enter Privileged Mode
```
Router> enable
```
<img width="652" alt="Screenshot 2025-09-12 215229" src="https://github.com/user-attachments/assets/08503f29-77a7-4cfa-9463-b230f22bf908" />

4. Enter Global Configuration Mode
```
Router# configure terminal
```
<img width="513" alt="Screenshot 2025-09-12 215321" src="https://github.com/user-attachments/assets/cb1b9671-703b-41ab-b349-db12390a42e7" />


5. Set Hostname
```
Router(config)# hostname R1
kunal(config)#
```
<img width="272" height="49" alt="image" src="https://github.com/user-attachments/assets/cee0b40e-f827-4d12-b759-650fe5ae365f" />



6. Set Enable Password (for privileged exec mode)
```
kunal(config)# enable password Praju
```
<img width="336" height="56" alt="image" src="https://github.com/user-attachments/assets/ca4eeb11-c1c7-4416-a182-3d89de10665a" />



7. Encrypt All Passwords
```
kunal(config)# service password-encryption
```
<img width="381" height="72" alt="image" src="https://github.com/user-attachments/assets/5aa724ad-46fe-4c76-bf70-242ce53f44c4" />



8. Set MOTD Banner (Message of the Day)
```
kunal(config)# banner motd # Welcome To NextGen Education #
```
<img width="539" height="104" alt="image" src="https://github.com/user-attachments/assets/d223a495-2a09-4f06-bd4c-3d63bbee8622" />




9. Configure Interfaces
```
kunal(config)# interface fastEthernet 0/0
kunal(config-if)# ip address 192.168.1.1 255.255.255.0
kunal(config-if)# no shutdown
kunal(config-if)# exit
```
<img width="584" height="223" alt="image" src="https://github.com/user-attachments/assets/a6cb21da-43b7-4ed4-a3d3-e00436469b25" />


 10. Save Configuration
```
kunal# copy running-config startup-config
```
<img width="370" height="151" alt="image" src="https://github.com/user-attachments/assets/39e863a1-b1b3-4851-a04a-e2975b510460" />


11. Pc Configuration
- Click PC0 → Desktop → IP Configuration.

<img width="527" height="430" alt="image" src="https://github.com/user-attachments/assets/fba01614-370d-465c-96fc-e6e31b259c5e" />

- Enter:
  - IP Address: 10.0.0.2
  - Subnet Mask: 255.0.0.0
  - Default Gateway: 10.0.0.1
  <img width="538" alt="Screenshot 2025-09-12 221129" src="https://github.com/user-attachments/assets/ae230d21-b30a-4a60-83ff-93095160d007" />

  
 ### Verification Commands

1. Check hostname & banner
```
kunal# show running-config
```
<img width="396" height="441" alt="image" src="https://github.com/user-attachments/assets/45199ed3-3c47-4797-b29a-52333b860b5b" />



2. Check interfaces
```
kunal# show ip interface brief
```
<img width="764" height="280" alt="image" src="https://github.com/user-attachments/assets/548324e3-2fdd-4478-95db-37050a81ec0b" />



3. Test connectivity
```
kunal# ping 192.168.1.2
```
<img width="621" height="171" alt="image" src="https://github.com/user-attachments/assets/b5349eb9-e86c-4f78-b415-856785e49a3e" />

