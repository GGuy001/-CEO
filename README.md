# -CEO
GitHub Docs
ผู้บริหารองค์กร/ภาพรวม/ภาพรวมของระบบ
ในบทความนี้
สถาปัตยกรรมการจัดเก็บ
ตัวเลือกการใช้งาน
การเก็บรักษาข้อมูลและความซ้ำซ้อนของดาต้าเซ็นเตอร์
ความปลอดภัย
การพึ่งพาโอเพนซอร์สสำหรับ GitHub Enterprise Server
อ่านเพิ่มเติม
ภาพรวมของระบบ
GitHub Enterprise Server เป็นสำเนาส่วนตัวขององค์กรของคุณของ GitHub ที่อยู่ภายในอุปกรณ์เสมือน โฮสต์ในองค์กรหรือในระบบคลาวด์ ที่คุณกำหนดค่าและควบคุม

สถาปัตยกรรมการจัดเก็บ
GitHub Enterprise Server ต้องการวอลุ่มการจัดเก็บข้อมูลสองวอลุ่ม อันหนึ่งต่อกับพาธระบบไฟล์รูท ( /) และอีกอันหนึ่งกับพาธระบบไฟล์ของผู้ใช้ ( /data/user) สถาปัตยกรรมนี้ช่วยลดความยุ่งยากในการอัปเกรด การย้อนกลับ และขั้นตอนการกู้คืนโดยแยกสภาพแวดล้อมซอฟต์แวร์ที่ทำงานอยู่ออกจากข้อมูลแอปพลิเคชันที่คงอยู่

ระบบไฟล์รูทจะรวมอยู่ในอิมเมจเครื่องแบบกระจาย ประกอบด้วยระบบปฏิบัติการพื้นฐานและสภาพแวดล้อมแอปพลิเคชัน GitHub Enterprise Server ระบบไฟล์รูทควรได้รับการปฏิบัติเป็นแบบชั่วคราว ข้อมูลใดๆ บนระบบไฟล์รูทจะถูกแทนที่เมื่ออัปเกรดเป็น GitHub Enterprise Server รุ่นต่อๆ ไป

ระบบไฟล์รูทประกอบด้วย:

ใบรับรองผู้ออกใบรับรองแบบกำหนดเอง (CA) (ใน/usr/local/share/ca-certificates )
การกำหนดค่าเครือข่ายแบบกำหนดเอง
การกำหนดค่าไฟร์วอลล์แบบกำหนดเอง
สถานะการจำลองแบบ
ระบบไฟล์ผู้ใช้ประกอบด้วยการกำหนดค่าและข้อมูลของผู้ใช้ เช่น:

ที่เก็บ Git
ฐานข้อมูล
ค้นหาดัชนี
เนื้อหาที่เผยแพร่บนเว็บไซต์ GitHub Pages
ไฟล์ขนาดใหญ่จาก Git Large File Storage
สภาพแวดล้อมของตะขอรับล่วงหน้า
ตัวเลือกการใช้งาน
คุณสามารถปรับใช้ GitHub Enterprise Server เป็นอุปกรณ์เสมือนเครื่องเดียวหรือในการกำหนดค่าความพร้อมใช้งานสูง สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การกำหนดค่า GitHub Enterprise Server สำหรับความพร้อมใช้งานสูง "

บางองค์กรที่มีนักพัฒนานับหมื่นอาจได้รับประโยชน์จาก GitHub Enterprise Server Clustering สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " เกี่ยวกับการทำคลัสเตอร์ "

การเก็บรักษาข้อมูลและความซ้ำซ้อนของดาต้าเซ็นเตอร์
ก่อนที่จะใช้ GitHub Enterprise Server ในสภาพแวดล้อมที่ใช้งานจริง เราขอแนะนำให้คุณตั้งค่าการสำรองข้อมูลและแผนการกู้คืนจากความเสียหาย สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การกำหนดค่าการสำรองข้อมูลบนอุปกรณ์ของคุณ "

GitHub Enterprise Server รวมถึงการสนับสนุนสำหรับการสำรองข้อมูลออนไลน์และเพิ่มขึ้นกับสาธารณูปโภคสำรอง GitHub Enterprise Server คุณสามารถใช้สแน็ปช็อตที่เพิ่มขึ้นผ่านลิงก์เครือข่ายที่ปลอดภัย (พอร์ตการดูแลระบบ SSH) ในระยะทางไกลสำหรับพื้นที่จัดเก็บนอกสถานที่หรือที่แยกย้ายกันไปตามภูมิศาสตร์ คุณสามารถกู้คืนสแน็ปช็อตผ่านเครือข่ายไปยังอุปกรณ์ที่จัดเตรียมใหม่ได้ในเวลาที่ทำการกู้คืนในกรณีที่เกิดภัยพิบัติที่ศูนย์ข้อมูลหลัก

นอกจากการสำรองข้อมูลเครือข่ายแล้ว ยังรองรับทั้งสแนปชอตดิสก์ AWS (EBS) และ VMware ของโวลุ่มพื้นที่จัดเก็บของผู้ใช้ในขณะที่อุปกรณ์ออฟไลน์หรืออยู่ในโหมดบำรุงรักษา สแน็ปช็อตของไดรฟ์ข้อมูลปกติสามารถใช้เป็นทางเลือกที่มีต้นทุนต่ำและซับซ้อนต่ำแทนการสำรองข้อมูลเครือข่ายด้วย GitHub Enterprise Server Backup Utilities หากข้อกำหนดระดับบริการของคุณอนุญาตให้มีการบำรุงรักษาแบบออฟไลน์เป็นประจำ

สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การกำหนดค่าการสำรองข้อมูลบนอุปกรณ์ของคุณ "

ความปลอดภัย
GitHub Enterprise Server เป็นอุปกรณ์เสมือนที่ทำงานบนโครงสร้างพื้นฐานของคุณและควบคุมโดยการควบคุมความปลอดภัยของข้อมูลที่มีอยู่ของคุณ เช่น ไฟร์วอลล์, IAM, การตรวจสอบ และ VPN การใช้ GitHub Enterprise Server สามารถช่วยให้คุณหลีกเลี่ยงปัญหาการปฏิบัติตามกฎระเบียบที่เกิดขึ้นจากโซลูชันบนคลาวด์

GitHub Enterprise Server ยังมีคุณลักษณะด้านความปลอดภัยเพิ่มเติมอีกด้วย

ระบบปฏิบัติการ ซอฟต์แวร์ และแพตช์
ความปลอดภัยของเครือข่าย
ความปลอดภัยของแอปพลิเคชัน
การเข้าถึงบริการภายนอกและการสนับสนุน
การสื่อสารที่เข้ารหัส
ผู้ใช้และสิทธิ์การเข้าถึง
การตรวจสอบสิทธิ์
การตรวจสอบและการเข้าถึงการบันทึก
ระบบปฏิบัติการ ซอฟต์แวร์ และแพตช์
GitHub Enterprise Server ใช้งานระบบปฏิบัติการ Linux ที่ปรับแต่งได้เฉพาะกับแอปพลิเคชันและบริการที่จำเป็นเท่านั้น GitHub จัดการการแพตช์ระบบปฏิบัติการหลักของอุปกรณ์โดยเป็นส่วนหนึ่งของวงจรการเปิดตัวผลิตภัณฑ์มาตรฐาน แพตช์แก้ไขการทำงาน ความเสถียร และปัญหาด้านความปลอดภัยที่ไม่สำคัญสำหรับแอปพลิเคชัน GitHub GitHub ยังจัดเตรียมแพตช์ความปลอดภัยที่สำคัญตามความจำเป็นนอกรอบการเผยแพร่ปกติ

GitHub Enterprise Server มีให้เป็นอุปกรณ์และแพ็คเกจระบบปฏิบัติการจำนวนมากได้รับการแก้ไขเมื่อเปรียบเทียบกับการแจกจ่าย Debian ปกติ เราไม่สนับสนุนการแก้ไขระบบปฏิบัติการพื้นฐานด้วยเหตุนี้ (รวมถึงการอัปเกรดระบบปฏิบัติการ) ซึ่งสอดคล้องกับใบอนุญาต GitHub Enterprise Server และข้อตกลงการสนับสนุนภายใต้หัวข้อ 11.3 การยกเว้น

ปัจจุบัน ฐานของอุปกรณ์ GitHub Enterprise Server คือ Debian 9 (Stretch) และได้รับการสนับสนุนภายใต้โปรแกรม Debian Long Term Support มีแผนจะย้ายไปยังระบบปฏิบัติการพื้นฐานที่ใหม่กว่าก่อนสิ้นสุดระยะเวลา Debian LTS สำหรับ Stretch

การอัปเดตโปรแกรมแก้ไขปกติจะออกในหน้าเผยแพร่ GitHub Enterprise Server และหน้าบันทึกประจำรุ่นจะให้ข้อมูลเพิ่มเติม โดยทั่วไปแพตช์เหล่านี้ประกอบด้วยผู้จำหน่ายต้นน้ำและแพตช์ความปลอดภัยของโครงการหลังจากผ่านการทดสอบและรับรองคุณภาพโดยทีมวิศวกรของเรา อาจมีการหน่วงเวลาเล็กน้อยตั้งแต่เมื่ออัปเดตอัปสตรีมจนถึงเมื่อทำการทดสอบและรวมอยู่ในแพตช์ GitHub Enterprise Server ที่กำลังจะวางจำหน่าย

ความปลอดภัยของเครือข่าย
ไฟร์วอลล์ภายในของ GitHub Enterprise Server จำกัดการเข้าถึงเครือข่ายไปยังบริการของอุปกรณ์ เฉพาะบริการที่จำเป็นสำหรับการทำงานของเครื่องเท่านั้นที่สามารถใช้ได้ผ่านเครือข่าย สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " พอร์ตเครือข่าย "

ความปลอดภัยของแอปพลิเคชัน
ทีมรักษาความปลอดภัยแอปพลิเคชันของ GitHub มุ่งเน้นเต็มเวลาในการประเมินช่องโหว่ การทดสอบการเจาะระบบ และการตรวจสอบโค้ดสำหรับผลิตภัณฑ์ GitHub รวมถึง GitHub Enterprise Server GitHub ยังทำสัญญากับบริษัทรักษาความปลอดภัยภายนอกเพื่อให้การประเมินความปลอดภัย ณ จุดเวลาของผลิตภัณฑ์ GitHub

การเข้าถึงบริการภายนอกและการสนับสนุน
GitHub Enterprise Server สามารถทำงานได้โดยไม่ต้องมีการเข้าถึงจากเครือข่ายของคุณไปยังบริการภายนอก คุณสามารถเลือกเปิดใช้งานการผสานรวมกับบริการภายนอกสำหรับการส่งอีเมล การตรวจสอบภายนอก และการส่งต่อบันทึก สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การกำหนดค่าอีเมลสำหรับการแจ้งเตือน " " การตั้งค่าการตรวจสอบภายนอก " และ " การส่งต่อบันทึก "

คุณสามารถรวบรวมและส่งข้อมูลการแก้ปัญหาไปยังฝ่ายสนับสนุน GitHub ได้ด้วยตนเอง สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การให้ข้อมูลแก่ GitHub Support "

การสื่อสารที่เข้ารหัส
GitHub ออกแบบ GitHub Enterprise Server เพื่อทำงานเบื้องหลังไฟร์วอลล์องค์กรของคุณ เพื่อความปลอดภัยของการสื่อสารผ่านสาย เราขอแนะนำให้คุณเปิดใช้งาน Transport Layer Security (TLS) GitHub Enterprise Server รองรับใบรับรอง TLS 2048 บิตและสูงกว่าสำหรับการรับส่งข้อมูล HTTPS สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การกำหนดค่า TLS "

โดยค่าเริ่มต้น อุปกรณ์ยังมีการเข้าถึง Secure Shell (SSH) สำหรับการเข้าถึงที่เก็บโดยใช้ Git และวัตถุประสงค์ด้านการดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " เกี่ยวกับ SSH " และ " การเข้าถึงเชลล์การดูแลระบบ (SSH) "

ผู้ใช้และสิทธิ์การเข้าถึง
GitHub Enterprise Server มีบัญชีสามประเภท

adminบัญชีผู้ใช้ลินุกซ์มีการควบคุมการเข้าถึงระบบปฏิบัติการที่รองรับรวมทั้งระบบแฟ้มโดยตรงและการเข้าถึงฐานข้อมูล ผู้ดูแลระบบที่เชื่อถือได้กลุ่มเล็กๆ ควรมีสิทธิ์เข้าถึงบัญชีนี้ ซึ่งพวกเขาสามารถเข้าถึงได้ผ่าน SSH สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การเข้าถึงเชลล์การดูแลระบบ (SSH) "
บัญชีผู้ใช้ในเว็บแอปพลิเคชันของอุปกรณ์สามารถเข้าถึงข้อมูลของตนเองและข้อมูลใดๆ ที่ผู้ใช้หรือองค์กรอื่นให้ไว้อย่างชัดเจน
ผู้ดูแลระบบไซต์ในเว็บแอปพลิเคชันของอุปกรณ์คือบัญชีผู้ใช้ที่สามารถจัดการการตั้งค่าเว็บแอปพลิเคชันและอุปกรณ์ระดับสูง การตั้งค่าบัญชีผู้ใช้และองค์กร และข้อมูลที่เก็บ
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการอนุญาตผู้ใช้ของ GitHub Enterprise Server โปรดดูที่ " สิทธิ์การเข้าถึงบน GitHub "

การตรวจสอบสิทธิ์
GitHub Enterprise Server มีวิธีการตรวจสอบสิทธิ์สี่วิธี

การรับรองความถูกต้องของคีย์สาธารณะ SSH ให้ทั้งการเข้าถึงที่เก็บโดยใช้ Git และการเข้าถึงเชลล์ของผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " เกี่ยวกับ SSH " และ " การเข้าถึงเชลล์การดูแลระบบ (SSH) "
การตรวจสอบชื่อผู้ใช้และรหัสผ่านด้วยคุกกี้ HTTP ให้การเข้าถึงเว็บแอปพลิเคชันและการจัดการเซสชันพร้อมการตรวจสอบสิทธิ์แบบสองปัจจัย (2FA) สำหรับข้อมูลเพิ่มเติม โปรดดูที่ " การใช้การตรวจสอบสิทธิ์ในตัว "
External LDAP, SAML, or CAS authentication using an LDAP service, SAML Identity Provider (IdP), or other compatible service provides access to the web application. For more information, see "Authenticating users for your GitHub Enterprise Server instance."
OAuth and Personal Access Tokens provide access to Git repository data and APIs for both external clients and services. For more information, see "Creating a personal access token."
Audit and access logging
GitHub Enterprise Server stores both traditional operating system and application logs. The application also writes detailed auditing and security logs, which GitHub Enterprise Server stores permanently. You can forward both types of logs in real time to multiple destinations via the syslog-ng protocol. For more information, see "Log forwarding."

Access and audit logs include information like the following.

Access logs
Full web server logs for both browser and API access
Full logs for access to repository data over Git, HTTPS, and SSH protocols
Administrative access logs over HTTPS and SSH
Audit logs
User logins, password resets, 2FA requests, email setting changes, and changes to authorized applications and APIs
Site administrator actions, such as unlocking user accounts and repositories
Repository push events, access grants, transfers, and renames
Organization membership changes, including team creation and destruction
Open source dependencies for GitHub Enterprise Server
You can see a complete list of dependencies in your appliance's version of GitHub Enterprise Server, as well as each project's license, at http(s)://HOSTNAME/site/credits.

Tarballs with a full list of dependencies and associated metadata are available on your appliance:

For dependencies common to all platforms, at /usr/local/share/enterprise/dependencies-<GHE version>-base.tar.gz
For dependencies specific to a platform, at /usr/local/share/enterprise/dependencies-<GHE version>-<platform>.tar.gz
Tarballs are also available, with a full list of dependencies and metadata, at https://enterprise.github.com/releases/<version>/download.html.

Further reading
"Setting up a trial of GitHub Enterprise Server"
"Setting up a GitHub Enterprise Server instance"
แผนงานสาธารณะ GitHubในที่ github/roadmapเก็บ
เอกสารนี้ช่วยคุณได้หรือไม่?
นโยบายความเป็นส่วนตัว
ช่วยเราทำให้เอกสารเหล่านี้ยอดเยี่ยม!
เอกสาร GitHub ทั้งหมดเป็นโอเพ่นซอร์ส เห็นอะไรผิดปกติหรือไม่ชัดเจน? ส่งคำขอดึง

หรือเรียนรู้วิธีการมีส่วนร่วม

ยังคงต้องการความช่วยเหลือ?
ถามชุมชน GitHub
ติดต่อฝ่ายสนับสนุน
© 2021 GitHub, Inc.
เงื่อนไข
ความเป็นส่วนตัว
ความปลอดภัย
สถานะ
ช่วย
ติดต่อ GitHub
ราคา
นักพัฒนา API
การฝึกอบรม
บล็อก
เกี่ยวกับ

ภาพรวมของระบบ
