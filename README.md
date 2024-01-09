# Khanh Hoa Block 
#DANH SÁCH CÁC ĐỊA CHỈ IP CÓ HÀNH VI GÂY MẤT AN TOÀN ĐẾN HỆ THỐNG THÔNG TIN

#DANH SÁCH ĐƯỢC CẬP NHẬ HẰNG NGÀY

#**I. ĐỂ TRIỂN KHAI CẬP NHẬT DANG SÁCH NGUY HẠI NÀY TRÊN:** 


#**1.ROUTER MIKROTIK:**

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




#**3.WATCHGUARD:**

THAM KHẢO: https://www.smartcloudcomputing.net/2021/02/22/how-to-automatically-blacklist-an-attackers-ip-on-palo-alto/


                                        #   TẢI ĐANH SÁCH NÀY VỀ VÀ LÀM TUẦN TỰ CÁC BƯỚC SAU
                                         # 1  Select Setup > Default Threat Protection > Blocked Sites.
                                        #        The Blocked Sites Configuration dialog appears.
                                        #2  To import blocked sites from a file, click the Blocked Sites tab.
                                         #Or, to import blocked sites exceptions, click the Blocked Site Exceptions tab.
                                         #3 Click Import.
                                        #        The Select a File dialog box appears.
                                         #4 Browse to select the file. Click Select a File.
                                         #        The sites in the file appear in the Blocked Sites or Blocked Sites Exceptions list.
                                        #5 Click OK.
 


#**4. SOPHOS:**




#**5. Một số lỗi cú pháp khai cấu hình  regex**

                                        But you have also highlighted the problem with regex -- it is very subtle technology and easy to be disappointed
                                        
                                        "^http://" does not block an https link
                                        "^https?://" blocks both http and https, but not ftp
                                        To block all three protocols, you need something like "(https?|ftp)://", but I would not trust the assertion without some testing.
                                        "http://" will match a url with http protcol, but may also block some URLs with an http string embeddd in the querystring (since the ^ is omitted).
                                        The difference between your second regex and the one that was counterproposed is that one blocks *.baddomain and the other blocks with recursion, such as *.*.baddomain
                                        
                                        I have come to loathe and fear regex mistakes, so I avoid them.   Instead I use website override objects.   
                                        
                                        For this situation, I would simply override the reputation.   
                                        For items that are blocked as uncategorized, the website override specifies the category.   
                                        For partial or full proxy bypass, the website override applies a tag, and then an Exception object defines the features that are disabled, and is applied to "websites with this tag".
                                        The website object can apply to a single host (www.badguys.com), or an organization by specifying badguys.com with the option to "include subdomains".   Unfortunately, the subdomains only apply to one level, *.badguys,com, but not *.*.badguys.com.   In most of my cases, a one level wildcard is sufficient.  The upside is that I omit the protocol and all three protocols are blocked.
                                        
                                        You need to look closely at the exceptions as reported in the policy helpdesk and the log files.   There may be an exception that is causing your problem.
