# PCB

Wszystkie projekty płytek PCB są dostarczone w formacie .lay6, który jest obsługiwany przez dostępny za darmo program Sprint Layout. Wersja demo wystarczy do otworzenia plików projektowych.

[Link do pobrania (lub kupienia) programu](https://www.electronic-software-shop.com/sprint-layout-60.html?language=en)

Katalogi:

1. Sterownik pompy - płytka sterująca pracą pompy. W projekcie zostały użyte 4 egzemplarze, po jednym na każdą pompę. Użyte przekaźniki to HF3FF, zasilanie cewki 12V, maks. obciążalność styków 10A. Użyty tranzystor to BC548. Użyte rezystory to 4.7kOhm, 1.5kOhm oraz 3.3kOhm (każdy z nich został zaznaczony w odpowiednim miejscu na schemacie).
	- "Sterownik pompy v2.lay6" - wersja nieaktualna. Została załączona do dokumentacji ze względu na to, że jest to wersja użyta w projekcie. Posiada błąd polegający na błędnym poprowadzeniu ścieżki do dzielnika napięcia 12V-5V. Konieczne jest wlutowanie rezystora 3.3kOhm *przed* rezystorem 4.7kOhm.
	- "Sterownik pompy v2 6x.lay6" - panel 6 płytek sterownika w wersji 2. Projekt służący przyspieszeniu produkcji większej ilości płytek.
	- "Sterownik pompy v3.lay6" - najnowsza wersja z poprawionym błędem dzielnika napięcia.

2. Sterownik zaworów - płytka sterująca pracą trzech elektrozaworów. Przekaźniki: HF3FF, 12V, max. 10A.
	- "Sterownik zaworow spustowych_v3.lay6"
	- "Sterownik zaworow spustowych_v3 2x.lay6" - panel z dwoma płytkami w celu szybszej produkcji PCB

3. Płyta główna - największa płytka w systemie odpowiedzialna za sterowanie urządzeniami i raportowanie stanu stacji. Stanowi łącznik pomiędzy warstwą sprzętową a oprogramowaniem na Raspberry Pi. Na płytce znajduje się 7 gniazd na mierniki napięcia i natężenia prądu `INA219` oraz 5 gniazd na czujniki ciśnienia `BMP280` (komunikacja z użyciem I2C). Ze względu na specyfikę tych czujników konieczne okazało się użycie multipleksera I2C (`TCA9548A`, adres `0x70`) dzięki któremu możliwe jest podłączenie do 8 urządzeń mających ten sam adres I2C. Na pierwszym złączu od lewej został podłączony również referencyjny czujnik ciśnienia ze zmienionym adresem (`0x77`). Pozostałe czujniki operują z użyciem domyślnego adresu I2C, tj. `0x76` dla BMP280.
    - "PlytaGlownaV2.lay6" - główny plik projektowy
	
