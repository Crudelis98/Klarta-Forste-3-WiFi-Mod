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

## API
**Gotowe**
- HTTP - 100%<br>
  ON/OFF    POST   http://"IP"/kf3?pw=1<br>
  Buzzer    POST   http://"IP"/kf3?bz=1<br>
  Speed     POST   http://"IP"/kf3?sp=1<br>
  Anion     POST   http://"IP"/kf3?an=1<br>
  Sleep     POST   http://"IP"/kf3?sl=1<br>
  Child Lock     POST   http://"IP"/kf3?cl=1<br>
  
**Planowane**
- MQTT - 50%<br>
- Home Assistant autodiscovery - 20%<br>
- Domoticz - 0%

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

## FAQ
Q: Nieprawidłowe hasło do Wi-Fi<br>
A: Należy zresetować urządzenie, przez kilkukrotne właczenie/wyłącznie urzedzęnie z prądu lub przytrzymać switch na module (nawet 40s).

Q: PM 0 na wyświetlaczu<br>
A: Mniejsza wtyczka nie jest włożona prawidłowo.
