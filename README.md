# Klarta Forste 3 WiFi Mod - repozytorium w budowie
## -> English below
Klarta Forste 3 to jeden z najpopualrnijeszy oczyszczaczy powietrza w Polsce. Zajmuje pierwsze miejsce według strony:
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
To repozytorium ma na celu rozwiązanie jedynej wady wymnienionej w powyżyszym rankingu. Dostępny na [Allegro]('') moduł umożliwia sterowanie urządzeniem oraz odczytywanie pm-2.5 z dowolnej przeglądarki. Wykorzystane zostało otwarte oprogramowanie [TASMOTA](https://tasmota.github.io/docs/) które jest szeroko znane wsród fanów autoamtyki domowej. Ponieżej znajduje się zdjęcie przedstawijące moją klarte.<br>
> Jestem twórcą modułu oraz sterownika, z chęcią odpowiem na pytania, błedy oraz problemy njelpeij zgłaszać [tutaj](https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/issues).
<p align="center">
  <img width="500" height="900" src="https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/blob/main/images/tasmota.PNG?raw=true">
</p>
Sterownik został tak skonstruowany aby nie trzeba było go lutować, wpinany jest między 2 taśmy łaczące wyświetlacz klarty oraz zasilacz i czujnik pyłu. Dzięki temu nie tracimy gwarancji, ponieważ może zostać w każdej chwili odłaćzony.
<p align="center">
  <img width="500" height="500" src="https://github.com/Crudelis98/Klarta-Forste-3-WiFi-Mod/blob/main/images/pcb.PNG?raw=true">
</p>

## Możliwości
- Odczytywanie pm-2.5<br>
- Oczytywanie trybu (silent, slow, fast, turbo)<br>
- Oczytywanie czy funkcja anionizacji jest włączona<br>
- Zdalne sterowanie - wszystkie funkcje pilota<br>
- **Dodatkowo możliwość wyciszenia dzwięku klarty!**<br>

## API
**Gotowe**
- HTTP - 100%

**Planowane**
- MQTT - 50%<br>
- Home Assistant autodiscovery - 20%<br>
- Domoticz - 0%

## Instalacja

## Uruchomienie
Dokładnie tak jak [TASMOTA](https://tasmota.github.io/docs/)

## FAQ


