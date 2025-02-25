### Kali Linux to dystrybucja systemu Linux, która jest zaprojektowana specjalnie z myślą o testach penetracyjnych, audytach bezpieczeństwa, analizie forensycznej oraz innych działaniach związanych z cyberbezpieczeństwem. Kali zawiera szeroką gamę narzędzi, które są preinstalowane i gotowe do użycia. Poniżej znajdziesz przegląd najważniejszych kategorii i narzędzi w Kali Linux:

---

### **1. Nmap - Skanowanie Sieci**
Nmap to jedno z najpopularniejszych narzędzi do skanowania sieci. Pozwala na wykrywanie urządzeń, otwartych portów, usług i systemów operacyjnych w sieci. Nmap jest przydatny podczas rozpoznawania i mapowania sieci w celu wykrycia potencjalnych słabych punktów.

**Komendy**:
- `nmap -sP <ip-range>`: Skanowanie aktywnych hostów w danym zakresie IP.
- `nmap -sS <ip>`: Skanowanie za pomocą SYN scan (najbardziej popularna metoda).

### **2. Netcat (nc) - Narzędzie do komunikacji sieciowej**
Netcat to narzędzie do testowania połączeń sieciowych, pozwalające na tworzenie połączeń TCP lub UDP. Używane w analizie sieciowej i do tworzenia backdoorów.

**Komendy**:
- `nc -lvp <port>`: Uruchamia Netcat w trybie nasłuchu na danym porcie.
- `nc <ip> <port>`: Łączy się z danym adresem IP i portem.

### **3. Metasploit Framework**
Metasploit to framework do eksploatacji podatności w systemach komputerowych. Umożliwia automatyczne znajdowanie i wykorzystywanie podatności oraz tworzenie exploitów.

**Komendy**:
- `msfconsole`: Uruchamia konsolę Metasploit.
- `search <nazwa podatności>`: Wyszukuje exploit dla danej podatności.
- `use <exploit>`: Wybiera exploit do użycia.

### **4. Hydra - Atak słownikowy na usługi sieciowe**
Hydra to narzędzie do przeprowadzania ataków słownikowych na usługi sieciowe. Może być używane do łamania haseł w różnych usługach takich jak SSH, FTP, HTTP.

**Komendy**:
- `hydra -l <login> -P <wordlist> <ip> ssh`: Atak słownikowy na protokół SSH.
- `hydra -L <userlist> -P <passwordlist> ftp://<ip>`: Atak na FTP z listą użytkowników i haseł.

### **5. Aircrack-ng - Łamanie Haseł WEP/WPA**
Aircrack-ng jest zestawem narzędzi do przeprowadzania testów penetracyjnych sieci bezprzewodowych. Główne jego zastosowanie to łamanie kluczy WEP i WPA w sieciach Wi-Fi.

**Komendy**:
- `airmon-ng start wlan0`: Uruchamia tryb monitorowania na karcie Wi-Fi.
- `airodump-ng wlan0mon`: Zbiera dane z sieci Wi-Fi.
- `aircrack-ng <capture-file>`: Łamanie klucza z przechwyconych pakietów.

### **6. John the Ripper - Łamanie Haseł**
John the Ripper to potężne narzędzie do łamania haseł. Obsługuje wiele algorytmów, takich jak MD5, SHA1 i inne. Jest używane do łamania haseł z plików hash.

**Komendy**:
- `john <password-file>`: Uruchamia łamanie haseł na podstawie pliku hash.
- `john --wordlist=<path-to-wordlist> <password-file>`: Użycie słownika do łamania haseł.

### **7. Burp Suite - Przechwytywanie i Modyfikowanie Ruchu HTTP/HTTPS**
Burp Suite to zestaw narzędzi do analizy aplikacji webowych. Jest używany do przechwytywania, modyfikowania i analizowania ruchu HTTP/HTTPS.

**Komendy**:
- Burp Suite uruchamia się za pomocą:
  ```bash
  burpsuite
  ```

**Funkcje**:
- Intercept (przechwytywanie i modyfikacja danych).
- Scanner (szukaj podatności w aplikacjach webowych).

### **8. Nikto - Skanner podatności w aplikacjach webowych**
Nikto to narzędzie do skanowania aplikacji webowych pod kątem różnych podatności, takich jak SQL injection, XSS, i inne problemy związane z bezpieczeństwem.

**Komendy**:
- `nikto -h <target>`: Skanuje wskazany adres URL pod kątem podatności.

### **9. Maltego - Analiza Powiązań**
Maltego to narzędzie do analizy powiązań w sieci, umożliwiające wizualizację danych i odkrywanie powiązań między osobami, organizacjami i domenami. Jest wykorzystywane w analizie forensycznej i OSINT.

**Funkcje**:
- Wizualizacja powiązań między elementami.
- Analiza sieci i danych związanych z atakami.

### **10. Social-Engineer Toolkit (SET) - Narzędzie do inżynierii społecznej**
SET to narzędzie wykorzystywane do przeprowadzania ataków z wykorzystaniem inżynierii społecznej. Może tworzyć fałszywe strony phishingowe, a także wysyłać złośliwe pliki.

**Komendy**:
- Uruchomienie SET:
  ```bash
  setoolkit
  ```

---

### **11. OWASP ZAP (Zed Attack Proxy) - Testy Bezpieczeństwa Aplikacji Webowych**
OWASP ZAP to narzędzie służące do testowania bezpieczeństwa aplikacji webowych. Umożliwia przeprowadzanie ataków takich jak SQL Injection, XSS i inne.

**Komendy**:
- `zap`: Uruchamia aplikację w trybie GUI.
- Skanowanie aplikacji webowej z interfejsem webowym.

### **12. Responder - Ataki na Protokół NetBIOS i LLMNR**
Responder to narzędzie używane do przeprowadzania ataków na sieci lokalne, szczególnie te, które używają NetBIOS i LLMNR. Umożliwia przechwytywanie haseł i ataki Man-in-the-Middle.

**Komendy**:
- `responder -I eth0`: Uruchomienie Respondera na interfejsie eth0 w celu przechwytywania danych.

---

### **13. Snort - System Wykrywania Włamań (IDS)**
Snort to system wykrywania włamań, który analizuje ruch sieciowy i identyfikuje potencjalne ataki.

**Komendy**:
- `snort -A console -c /etc/snort/snort.conf -i eth0`: Uruchamia Snort w trybie konsoli z plikiem konfiguracyjnym.

### **14. THC-Hydra - Narzędzie do Brute Force**
THC-Hydra to narzędzie do przeprowadzania ataków brute-force na różne usługi, takie jak SSH, FTP, HTTP, itd.

**Komendy**:
- `hydra -l <login> -P <wordlist> <ip> ssh`: Atak słownikowy na protokół SSH.

### **15. Wifite - Automatyczne Łamanie Haseł Wi-Fi**
Wifite to narzędzie, które automatycznie łamie hasła do sieci Wi-Fi. Obsługuje WEP, WPA, i WPA2.

**Komendy**:
- `wifite`: Uruchamia automatyczne łamanie haseł Wi-Fi.
Dalej przedstawiam kolejne narzędzia Kali Linux z krótkim opisem, sposobem użycia i komendami:

---

### **16. TCPDump - Skanowanie i Analiza Ruchu Sieciowego**
TCPDump to narzędzie do analizy pakietów w sieci. Pozwala na przechwytywanie i analizowanie ruchu sieciowego, co jest pomocne przy diagnozowaniu problemów sieciowych lub przeprowadzaniu audytów bezpieczeństwa.

**Komendy**:
- `tcpdump -i eth0`: Nasłuchiwanie ruchu na interfejsie eth0.
- `tcpdump -i eth0 port 80`: Nasłuchiwanie tylko na port 80 (HTTP).

### **17. Ettercap - Man-In-The-Middle (MITM)**
Ettercap jest narzędziem do przeprowadzania ataków typu Man-In-The-Middle. Pozwala na przechwytywanie, modyfikowanie i blokowanie komunikacji w sieci lokalnej. Można go używać do ataków na protokoły takie jak HTTP, HTTPS, FTP, itp.

**Komendy**:
- `ettercap -G`: Uruchamia graficzny interfejs Ettercap.
- `ettercap -T -q -i eth0 -M arp:remote /<target1>/ /<target2>/`: Atak ARP poisoning na dwóch celach.

### **18. Nikto - Skaner Webowy**
Nikto to narzędzie do skanowania aplikacji webowych pod kątem podatności, takich jak SQL Injection, XSS, i innych. Nikto skanuje serwery HTTP i HTTPS, oferując obszerną listę testów na różne podatności.

**Komendy**:
- `nikto -h <ip-or-domain>`: Rozpoczyna skanowanie wskazanej strony lub serwera.

### **19. Wireshark - Narzędzie do Przechwytywania Pakietów**
Wireshark to narzędzie służące do przechwytywania i analizy ruchu sieciowego. Obsługuje wiele protokołów sieciowych i jest używane do diagnostyki sieciowej oraz wykrywania ataków.

**Komendy**:
- `wireshark`: Uruchamia Wireshark w trybie graficznym.
- `tshark`: Uruchamia wersję konsolową Wireshark.

### **20. Recon-ng - Framework do Przeprowadzania OSINT**
Recon-ng to framework do przeprowadzania otwartej analizy informacji (OSINT). Pozwala na automatyczne zbieranie informacji o celach z różnych źródeł, takich jak wyszukiwarki, media społecznościowe, rejestry WHOIS, itd.

**Komendy**:
- `recon-ng`: Uruchamia framework.
- `use recon/domains-hosts/google_site_web`: Przykład modułu do zbierania informacji z Google.

### **21. OSRFramework - Inżynieria Społeczna i OSINT**
OSRFramework to zestaw narzędzi do przeprowadzania ataków z zakresu inżynierii społecznej oraz analizy danych z sieci (OSINT). Narzędzie jest pomocne przy pozyskiwaniu danych osobowych lub w kontekście audytów bezpieczeństwa.

**Komendy**:
- `osrframework`: Uruchamia narzędzie w trybie konsolowym.
- `osrframework -m social-media -t twitter`: Zbieranie danych z Twittera.

### **22. Maltego - Wizualizacja Danych i Analiza Powiązań**
Maltego to narzędzie służące do wizualizacji powiązań między elementami w Internecie, takimi jak osoby, organizacje, adresy e-mail, numery telefonów, domeny internetowe itp. Maltego jest często wykorzystywane w dochodzeniach związanych z cyberprzestępczością.

**Komendy**:
- `maltego`: Uruchamia graficzną wersję narzędzia.

### **23. Hashcat - Łamanie Haseł**
Hashcat to jedno z najszybszych narzędzi do łamania haseł. Wykorzystuje potężne procesory i karty graficzne (GPU) do przeprowadzania ataków słownikowych, brute-force oraz ataków hybrydowych.

**Komendy**:
- `hashcat -m <hash-mode> <hash-file> <wordlist>`: Uruchamia atak na wskazany plik z hashem.
- `hashcat -a 0 -m 0 hash.txt wordlist.txt`: Łamanie hasła za pomocą słownika.

### **24. BeEF - Framework do Ataków na Przeglądarki**
BeEF to framework służący do przeprowadzania ataków na przeglądarki internetowe. BeEF (Browser Exploitation Framework) pozwala na wykorzystanie podatności w przeglądarkach i włączanie ich w atak na urządzenia klienckie.

**Komendy**:
- `beef`: Uruchamia framework w trybie lokalnym.
- Wymaga integracji z innymi narzędziami, aby przeprowadzić atak.

### **25. P0f - Narzędzie do Analizy Ruchu Sieciowego i Wykrywania Systemów Operacyjnych**
P0f to narzędzie służące do pasywnej analizy pakietów sieciowych, które pozwala na wykrycie systemów operacyjnych, aplikacji, wersji oprogramowania i innych szczegółów związanych z urządzeniami w sieci.

**Komendy**:
- `p0f -i eth0`: Uruchamia narzędzie na interfejsie eth0.

### **26. Responder - Atak na Sieć Windows**
Responder jest narzędziem służącym do przeprowadzania ataków na sieci lokalne, zwłaszcza w kontekście środowisk Windows. Narzędzie wykorzystuje protokoły takie jak LLMNR, NetBIOS i mDNS do przechwytywania danych i haseł.

**Komendy**:
- `responder -I eth0`: Uruchamia Respondera na interfejsie eth0 w celu przechwytywania danych.

### **27. Armitage - GUI dla Metasploit**
Armitage to graficzny interfejs użytkownika (GUI) dla Metasploit Framework, który umożliwia łatwiejsze wykonywanie ataków, eksplorację podatności oraz zarządzanie exploitami i payloadami.

**Komendy**:
- `armitage`: Uruchamia graficzny interfejs Armitage.
- Interfejs pozwala na wybór exploita i uruchamianie ataków poprzez kliknięcia.

### **28. Sublist3r - Zbieranie Subdomen**
Sublist3r to narzędzie służące do zbierania subdomen dla danej domeny. Wykorzystuje różne publiczne źródła, aby wykryć subdomeny, które mogą być używane w testach penetracyjnych.

**Komendy**:
- `sublist3r -d example.com`: Zbiera subdomeny dla domeny example.com.

### **29. L0phtCrack - Narzędzie do Łamania Haseł**
L0phtCrack to narzędzie służące do łamania haseł w systemach Windows. Może być używane do odzyskiwania haseł z plików z hashami.

**Komendy**:
- Uruchomienie L0phtCrack odbywa się za pomocą GUI, ale także w wersji konsolowej.

### **30. Social-Engineer Toolkit (SET)**
SET jest narzędziem służącym do przeprowadzania ataków z zakresu inżynierii społecznej. Może generować phishingowe strony logowania, złośliwe pliki do wysyłania lub symulować różne scenariusze ataków.

**Komendy**:
- `setoolkit`: Uruchamia narzędzie w trybie tekstowym, a następnie pozwala na wybór ataku.
