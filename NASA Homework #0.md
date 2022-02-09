# NASA Homework \#0 
# Network Administration
## 1. True/False
### Question 1
**[ Reference ]**
- https://www.qualcomm.com/5g/what-is-5g
- https://myfone.blog/2020-5g-smartphone/?gclid

**[ Answer ]**
- 錯誤，5G、4G指的是"網路"本身、是一種訊息傳遞方式，並非"速度"，而5G的網路速度比4G快。

<br>

### Question 2
**[ Reference ]**
- https://slts.osu.edu/articles/whats-a-mac-address-and-how-do-i-find-it/

**[ Answer ]**
- 錯誤，每個網路卡(Network Interface Controller (NIC))都會連接著一個MAC address，但不保證每個裝置只會有一個網路卡(可能兩個或更多)。

<br>

### Question 3
**[ Reference ]**
- http://www.tsnien.idv.tw/Manager_WebBook/chap9/9-3%20%E7%B6%B2%E8%B7%AF%E4%BD%8D%E5%9D%80%E8%BD%89%E8%AD%AF.html
- https://www.netadmin.com.tw/netadmin/zh-tw/technology/9E69BC3BDD3E427C8D1DAF3272983130?page=3

**[ Answer ]**
- 錯誤，如果是選用"靜態NAT"，封包與IP之間是一對一轉換因此不同封包會有不同的Source IP。

<br>

### Question 4
**[ Reference ]**
- http://www.tsnien.idv.tw/Security_WebBook/%E7%AC%AC%E5%8D%81%E4%BA%8C%E7%AB%A0%20%E8%99%9B%E6%93%AC%E7%A7%81%E6%9C%89%E7%B6%B2%E8%B7%AF.html

**[ Answer ]**
- 正確，VPN會直接修改Source IP，使其他使用者無法取得原本Source IP，增加安全性。

<br>

### Question 5
**[ Reference ]**
- http://www.tsnien.idv.tw/Internet_WebBook/chap3/3-8%20%E7%B6%B2%E8%B7%AF%E9%96%98%E9%96%80.html
- http://www.tsnien.idv.tw/Network_WebBook/chap13/13-3%20IP%20%E9%80%9A%E8%A8%8A%E5%8D%94%E5%AE%9A.html

**[ Answer ]**
- 錯誤，若是intranet中同一區域網路內的傳輸，就不需要經過gateway。

<br>

### Question 6
**[ Reference ]**
- 輸入command: `nslookup 155.155.15.15`，發現他沒有對應的domain
    > 155.155.15.15是我自己隨機嘗試的IP

**[ Answer ]**
- 錯誤，應為"Non-existent domain"
    ![](https://i.imgur.com/sxDyl2x.png)

<br>

### Question 7
**[ Reference ]**
- 高中資訊課本: 資訊科技概論/蔡志敏著

**[ Answer ]**
- 錯誤，只要有IP，不需要DHCP、DNS 以及NAT(這些只是為了獲取IP的工具)，就能連接到目標server。

<br>

### Question 8
**[ Reference ]**
- https://www.stockfeel.com.tw/dhcp%E4%BC%BA%E6%9C%8D%E5%99%A8%E6%98%AF%E4%BB%80%E9%BA%BC%EF%BC%9F%E5%A6%82%E4%BD%95%E9%81%8B%E7%94%A8%EF%BC%9F/

**[ Answer ]**
- 錯誤，只要有IP位址，就能直接傳送封包給目標server，DHCP server只是用來取得IP位址的。

<br>

### Question 9
**[ Reference ]**
- https://www.cloudflare.com/zh-tw/learning/ssl/why-is-http-not-secure/
- https://tw.alphacamp.co/blog/http-https-difference

**[ Answer ]**
- 正確，因此HTTP安全性低，現今網路較常使用HTTPS(加密後的封包)，增加安全性。


<br>

### Question 10
**[ Reference ]**
- https://www.itread01.com/content/1549849346.html

**[ Answer ]**
- 正確，選擇的金鑰長度越長，安全性越高，但同時加密解密所需時間越長。


<br>
<br>


## 2. Short Answer
1. _
    (a) MAC address
    - Reference
        - https://www.pathsolutions.com/blog/mac-addresses-not-a-cheesy-subject
        - https://slts.osu.edu/articles/whats-a-mac-address-and-how-do-i-find-it/
    - Answer
        - 是用來表示網路裝置的位址，每個網路卡(Network Interface Controller (NIC))都連結著一個且獨一無二的MAC address，表示方法為使用共48 bits(6 bytes)，並以十六進位表示，會使用在Wi-Fi、乙太網路、藍芽等網路型態。

    (b) Switch
    - Reference
        - https://www.cloudflare.com/zh-tw/learning/network-layer/what-is-a-network-switch/
        - https://www.networkworld.com/article/3584876/what-is-a-network-switch-and-how-does-it-work.html

    - Answer
        - 是一個網路硬體裝置，在OSI model中的第二層，使用MAC address辨認要傳遞的封包，並進行資料傳送，可以傳送給另一個switch、router、或另一台電腦。

    (c) broadcast storm
    - Reference
        - https://www.auvik.com/franklyit/blog/broadcast-storms/
    - Answer
        - 指在短時間內，突然出現大量broadcast封包，造成switch負荷量過大，網路效能降低。通常造成此情況的原因有三個：
		    (1) 大量的DHCP要求IP位址。
		    (2) broadcast domain太大
	        (3) Switch設置不正確
            
<br>
<br>
<br>

2. _ 
- Reference
    - 高中資訊課本: 資訊科技概論/蔡志敏著
- Answer
    - Subnet mask: 為一串32 bits的二進位數值，跟IP位址一樣會用"."隔開，用來協助網路判別一個IP位址是屬於哪個網段。
    - 相同subnet: ( b ) ( c )
        - 判斷方式: 
            ```
            192.168.0.1/23
            192.168.0.1 => 11000000.10101000.00000000.00000001
            23 => 11111111.11111111.11111110.00000000
            兩者做binary AND
            => 11000000.10101000.00000000.00000000
                192.      168.     __.       __

            看前面23位，只要跟此數值一樣，就表示在相同subnet下。
            ```
            
            
3. _
- Reference
    - https://microchipdeveloper.com/tcpip:tcp-ip-five-layer-model
	- https://www.educative.io/edpresso/what-is-the-five-layer-internet-protocol-stack
	- https://medium.com/@karthikayanmailsamy/5-layer-network-model-made-simplified-e813da0913ba
	- https://docs.oracle.com/cd/E19683-01/806-4075/ipov-10/index.html

- Answer
    1. Physical Layer
		- 對資料進行編碼和解碼，使資料變成可以在實體通訊電路(ex. 無線電波)中傳遞、或將收到的位元流組裝成data frame，傳到下一層網路。
		- Ex: 10 Base T、802.11

	2. Data Link Layer
		- 處理每個裝置之間的資料傳遞，裝置包含router、switch或另一台電腦，並使用MAC address紀錄封包(此層稱為frame)來源與目的地。
		- Ex: Ethernet、Wi-Fi

	3. Network Layer
		- 在網路中，處理每個系統之間的資料傳遞，利用IP address紀錄封包(此層稱為datagram)來源與目的地。在Transport layer中，會把網路切成子網路，傳進network layer，再透過router找到目標網路，並把資料傳給離目標網路最近的router。
		- Ex: IP、ICMP
	4. Transport Layer
		- 使用TCP或UDP連接不同主機的應用程式，並處理network layer和application layer間端點(socket)的資料傳遞，透過port number紀錄不同端點或應用程式，在此層中的資料傳遞單位為segment。
		- Ex: TCP、UDP

    5. Application Layer
	    - 當應用程式(ex. 瀏覽器、email)需要使用網路、連接到其他主機時，application layer會建立彼此間的連結，在此層中的資料傳遞單位為message。
        - Ex: HTTP、SMTP、FTP、DNS