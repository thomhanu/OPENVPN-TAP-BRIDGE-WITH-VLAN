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
<img src= "http://i.imgur.com/T1872Zc.png"> 
<img src= "http://i.imgur.com/ao9ATCD.png"> 
<img src= "http://i.imgur.com/k8I0WEt.png">
**Chú ý**: Chọn Certificate Authority chính là CAs bạn vừa tạo

- Cấu hình trên Pfsense server:

<img src= "http://i.imgur.com/zs9bGh3.png"> 
<img src= "http://i.imgur.com/PbYg5JG.png"> 
<img src= "http://i.imgur.com/8ffekwf.png"> 
<img src= "http://i.imgur.com/JwdgqcP.png"> 
<img src= "http://i.imgur.com/Lt3PLae.png"> 

- Tạo card bridge
Bật card mạng OPT1 và đổi tên. Chọn Network port cho OPT1 là Openvpn server vừa tạo:

<img src= "http://i.imgur.com/G0dK40h.png"> 
- Chuyển sang tab bridge, tạo 1 card bridge bằng cách chọn VLAN và bridge:

<img src= "http://i.imgur.com/pGY7QJh.png">

- Tạo rule cho Openvpn trên WAN và bridge

Tạo  rule trên WAN, sau đó chọn save để lưu
<img src= "http://i.imgur.com/fVjIN9X.png">

<img src= "http://i.imgur.com/sQ7iqwV.png">


Tạo rule trên card bridge


<img src="http://i.imgur.com/6Mr8uOI.png">

- Chọn tab Client export trong OPENVPN để export file :
Chọn file phù hợp để cài đặt vào máy client. Ở đây, chọn Windows Installer : x86-win6 Sau đó copy sang máy client file vừa tải về từ Pfsense server
<img src= "http://i.imgur.com/F95wSP5.png">

Copy file down về vào máy client và cài đặt
<img src= "http://i.imgur.com/E0l7DSO.png">

**Chú ý**: Khi máy của bạn chưa cài đặt TAP-WINDOW, trong quá trình cài đặt OpenVPN yêu cầu cài đặt TAP-WINDOW hãy chọn Install

Click chuột phải vào OpenVPN GUI -> Run as administrator

<img src= "http://i.imgur.com/g627kES.png"> 

Sau đó click chuột phải vào biểu tượng góc phải màn hình và chọn connect
<img src= "http://i.imgur.com/Gi0ENL2.png"> 

Sau khi kết nối thành công, máy clien sẽ nhận địa chỉ của VLAN


