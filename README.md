# ipv6-he-fortigate

#### 1. Đăng ký tài khoản tại https://tunnelbroker.net/
```
Tạo 1 tunnel và chuyển sang tab example config fortigate


config system sit-tunnel
    edit "HE"
        set destination 216.218.221.6
        set ip6 2001:xxxx:xxxx:xxxx::2/64
        set source xxx.xxx.xxx.xxx
    next
end

config router static6
    edit 1
        set device "HE"
    next
end
```
#### 2. Enable IPv6 trong System/Feature Visibility/IPv6
#### 3. Cấu hình IPv6
```
Network/Interface/Trunking/Guest

IPv6 addressing mode: Manual
IPv6 Address/Prefix: 2001:xxxx:xxxx:xxxx::1/64
DHCPv6 Server: On
2001:xxxx:xxxx:xxxx::/64
2001:xxxx:xxxx:xxxx::2-2001:xxxx:xxxx:xxxx::ffff
```
#### 4. Cấu hình NAT
```
Incoming: Guest
Outgoing: HE
source: IPv6 all
destination: IPv6 all
service: all
NAT: on
```
#### source
```
https://securitynetworkinglinux.wordpress.com/2019/07/03/how-to-connect-to-ipv6-from-ipv4-using-a-fortigate-and-a-tunnel-broker/
```
