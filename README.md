# Klarta Forste 3 WiFi Mod - repozytorium w budowie
## -> English below
Klarta Forste 3 to jeden z najpopularniejszych oczyszczaczy powietrza w Polsce. Zajmuje pierwsze miejsce według strony:
[Ranking Oczyszczaczy PL](https://ranking-oczyszczaczy.pl/recenzje/klarta-forste-3/)

**Zalety**:<br>
- Praktycznie bezobsługowy oczyszczacz z idealnym na polskie warunki trybem automatycznym<br>
- Bardzo cicha praca w trybie sleep<br>
- 5 wersji kolorystycznych do wyboru<br>
- Wysoka opłacalność (relacja ceny do oferowanych możliwości)<br>
- Niedrogie filtry wymienne (139 zł za komplet z H13)<br>
- Wskaźnik zużycia filtrów<br>
- Numeryczny wskaźnik cząsteczek PM-2,5<br>
- 3-letnia gwarancja<br>

**Wady**:<br>
- Brak sterowania mobilnego
> Autorem wad i zalet jest [Ranking Oczyszczaczy PL](https://ranking-oczyszczaczy.pl/recenzje/klarta-forste-3/)

## Sterownik Wi-Fi
To repozytorium ma na celu rozwiązanie jedynej wady wymienionej w powyższym rankingu. Dostępny na [Allegro]('') moduł umożliwia sterowanie urządzeniem oraz odczytywanie pm-2.5 z dowolnej przeglądarki. Wykorzystane zostało otwarte oprogramowanie [TASMOTA](https://tasmota.github.io/docs/) które jest szeroko znane wśród fanów automatyki domowej. Poniżej znajduje się zdjęcie przedstawiające moją klarte.<br>
> Jestem twórcą modułu oraz sterownika, z chęcią odpowiem na pytania, błędy oraz problemy najlepiej zgłaszać [tutaj](https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/issues).
<p align="center">
  <img width="500" height="900" src="https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/blob/main/images/tasmota.PNG?raw=true">
</p>
Sterownik został tak skonstruowany aby nie trzeba było go lutować, wpinany jest między 2 taśmy łączące wyświetlacz klarty oraz zasilacz i czujnik pyłu. Dzięki temu nie tracimy gwarancji, ponieważ może zostać w każdej chwili odłączony.
<p align="center">
  <img width="500" height="500" src="https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/blob/main/images/module.PNG?raw=true">
</p>

## Możliwości
- Odczytywanie pm-2.5<br>
- Odczytywanie trybu (silent, slow, fast, turbo)<br>
- Odczytywanie czy funkcja neonizacji jest włączona<br>
- Zdalne sterowanie - wszystkie funkcje pilota<br>
- **Dodatkowo możliwość wyciszenia dźwięku klarty!**<br>

## Komendy

Komendy można wpisywać w konsoli lub przesyłać przez HTTP i MQTT.
- KF3Version
> brak argumentów zwraca JSON z wersją Klarty Forste 3
> 
> KF3Version 2 zmienia pracę modułu Wi-Fi na kompatybilną z Klarty Forste 3 v2
> 
> KF3Version 4 zmienia pracę modułu Wi-Fi na kompatybilną z Klarty Forste 3 v4
- KF3Status
> brak argumentów, zwraca JSON z danymi urządzenia
- KF3PM
> brak argumentów, zwraca JSON z PM2.5
- KF3Power
> brak argumentów, zwraca JSON ze stanem urządzenia
> 
> KF3Power 1 włącza urządzenie
> 
> KF3Power 0 wyłącza urządzenie
> 
> KF3Power TOGGLE przełącznik (włącza urządzenie wyłączane, wyłączone urządzenie włącza)
- KF3Buzzer
> brak argumentów, zwraca JSON ze stanem urządzenia
> 
> KF3Buzzer 1 włącza piszczyk
> 
> KF3Buzzer 0 wyłącza piszczyk
> 
> KF3Buzzer TOGGLE przełącznik (włącza piszczyk wyłączany, wyłączony piszczyk włącza)
- KF3Speed
> brak argumentów, zwraca JSON ze stanem urządzenia
> 
> KF3Speed TOGGLE przełącznik
- KF3Anion
> brak argumentów, zwraca JSON ze stanem urządzenia
> 
> KF3Anion1 włącza jonizacje powietrza
> 
> KF3Anion 0 wyłącza jonizacje powietrza
> 
> KF3AnionTOGGLE przełącznik
- KF3Sleep
> brak argumentów, zwraca JSON ze stanem urządzenia
> 
> KF3SleepTOGGLE przełącznik
- KF3ChildLock
> brak argumentów, zwraca JSON ze stanem urządzenia
> 
> KF3ChildLockTOGGLE przełącznik


## API
**Gotowe**
- HTTP - 100%<br>
> http://----IP----/cm?cmnd=KOMENDA
> 
> np. GET/POST http://192.168.1.162/cm?cmnd=KF3PM
> 
> urządzenie odpowie:
> 
> {"KF3PM": 2}

- MQTT - 100%<br>
> cmnd/----TASMOTA_TOPIC----/KOMENDA
> 
> np. cmnd/DVES_A8B059_fb/KF3PM
> 
> urządzenie odpowie:
> 
> {"KF3PM": 2}
> 
> pod tym tematem stat/DVES_A8B059_fb/RESULT

**Planowane**
- Home Assistant autodiscovery - 80%<br>
- Domoticz - 50%

## Instalacja
- Odłączyć od zasilania i odczekać.
- Zdjąć przedni panel (zasłaniający filtry).
- Odkręcić 5 śrub górnego panela.
- Odkręcić panel wyświetlacza (4 śruby).
- Odkręcić czarną przysłonę wyświetlacza (3 śruby).

Finalnie po odkręceniu wszystkich górnych części, należy podłączyć moduł w następujący sposób:
- dłuższa wtyczka do modułu zasilania.
- dłuższa taśma między modułerm wifi a wyświtlaczem.
- krótka taśma do moduły wifi(od czunika pm).
- krótka wtyczka do modułu wyświetlacza.
> Uwaga ostatnia wtyczka może stawiać opór i/lub zostać włożona w 2 strony!
> Dlatego należy pmaiętać aby czerwony przwód znajdował się na pinie 5V (druk PCB).
- Dioda IR jest zakończona koszulką termokurczliwą, można ją podgrzać aby zacisnęła się na odbiorniku IR modułu wyświetlacza.
> Autor nie bierze żadnej odpowiedzialności.

Całość powinna prezentować się jak na zdjęciu:
<p align="center">
<img width="500" height="900" src="https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/blob/main/images/klarta.jpg?raw=true">
</p>

## Uruchomienie
Dokładnie tak jak [TASMOTA](https://tasmota.github.io/docs/)

- Po prawidłowym podłaćzeniu modułu należy jednorazowo połączyć się z nową siecią Wi-Fi tasmotaXXXXXXX, wcelu konfiguracji Wi-Fi.
- Powinno nastąpić autoamtyczne przekierowanie, jeżeli to nie nastąpi należy w przeglądarce wpisać adress http://192.168.4.1/ w celu otwarcia kreatora konfiguracji
- Następnie podać nazwe (SSID) oraz hasło sieci domowej.
- Kreator poda nowy adres IP urządzenia, jeżeli np. telefon zbyt szybko przeieruje połączenie, można wyszukać urządzenie korzystajac z Advenced IP Scanner
> https://www.advanced-ip-scanner.com/

## FAQ
Q: Nieprawidłowe hasło do Wi-Fi<br>
A: Należy zresetować urządzenie, przez kilkukrotne właczenie/wyłącznie urzedzęnie z prądu lub przytrzymać switch na module (nawet 40s).

Q: PM 0 na wyświetlaczu<br>
A: Odswieżyć przeglądarke.<br>
A: Klarta przy właczeniu do prądu po uruchumieniu jest domyślnie wyłączona należy ją właczyć używając modułu/pilota/panelu przyciskiem ON/OFF. Dopiero wtedy następuje kalibracja czujnika pm 2.5 i mierzona jest wartość pyłu.<br>
A: Mniejsza wtyczka nie jest włożona prawidłowo.
