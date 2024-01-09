# KhanhHoaBlock
#DANH SÁCH CÁC ĐỊA CHỈ IP CÓ HÀNH VI GÂY MẤT AN TOÀN ĐẾN HỆ THỐNG THÔNG TIN
#DANH SÁCH ĐƯỢC CẬP NHẬ HẰNG NGÀY



#I. ĐỂ TRIỂN KHAI CẬP NHẬT DANG SÁCH NGUY HẠI NÀY TRÊN: 


    #****1.ROUTER MIKROTIK:****




          #+ CÀI ĐẶT RouterOS Scripts THEO HƯỚNG DẪN TẠI "https://github.com/eworm-de/routeros-scripts".


          #+ CÀI ĐẶT SCRIPTS fw-addr-lists THEO HƯỚNG DÂN TẠI "https://git.eworm.de/cgit/routeros-scripts/about/doc/fw-addr-lists.md"


            - lƯU Ý: BỔ SUNG LISTS NÀY VÀO DANH MỤC CỦA global-config-overlay.

              # This defines the settings for firewall address-lists (fw-addr-lists).
              #:global FwAddrLists {
                #  "allow"={
                  #  { url="https://eworm.de/ros/fw-addr-lists/allow";
                 #   cert="R3" };
                   # };
                     # "block"={
                       # { url="https://raw.githubusercontent.com/thanhtranntkh/KhanhHoaBlock/main/Backlist_khanhhoa.txt";
                        #    cert="R3" };
                       #   .......
                      #  };
                      #};
                      #:global FwAddrListTimeOut 1d;


#**2.PFSENSE:**
