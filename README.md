## OPENVPN-TAP-BRIDGE-WITH-VLAN

### Mô hình:

<img src= "http://i.imgur.com/mfAEqmS.png"> 

####Yêu cầu:
-	Một máy cài đặt Pfsense server với hai card mạng, 1 card bridge và 1 card private.( Ở bài lab này tôi dùng dải VLAN: 20.0.0.0/24)
-	1 máy client có kết nối Internet

### Cài đặt:
- Cài đặt gói  gói Openvpn Client Export Ultility trên Pfsense:

<img src= "http://i.imgur.com/SF9OL5K.png">
- Tạo chứng thực CAs để cấp phát cho Server và client ( chứng thực khi openvpn)
<img src= "http://i.imgur.com/aYZySca.png">
- Chuyển sang tab certificates để tạo Server Certificate and User Certificate
<img src= "http://i.imgur.com/1p8ddzX.png"> 
<img src= " "> 
<img src= " "> 
<img src= " "> 
<img src= " "> 
<img src= " "> 
