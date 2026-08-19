---
title: LayerManager — Zarządzaj wszystkimi warstwami w jednej tabeli
description: Polecenie LayerManager otwiera tabelę wszystkich warstw rysunku, pozwalając dodawać warstwy i edytować bezpośrednio dla każdej zamrożenie, blokadę, wydruk, kolor, grubość linii i typ linii.
keywords: [layer manager, tabela warstw CAD, zarządzanie warstwami CAD, dodaj warstwę CAD, zamroź zablokuj wydrukuj warstwę, zarządzanie warstwami kulmanlab]
group: layer
order: 1
---

# LayerManager

Polecenie `LayerManager` otwiera tabelę zawierającą wszystkie warstwy rysunku, z ustawieniami **Freeze** (zamroź), **Lock** (zablokuj), **Plot** (wydruk), **Kolor**, **Grubość linii** i **Typ linii** edytowalnymi bezpośrednio w wierszu. To centralne miejsce do dodawania nowych warstw i dostosowywania zachowania istniejących — pozostałe polecenia warstw ([LayerMakeCurrent](../layer-make-current/), [LayerMatch](../layer-match/), [LayerIsolate](../layer-isolate/), [LayerUnfreezeAll](../layer-unfreeze-all/)) wykonują każde jedną konkretną czynność bez otwierania tego okna.

## Otwieranie Menedżera warstw

- Wpisz `LayerManager` w terminalu, **lub**
- Kliknij przycisk **Layer Manager** na panelu warstw.

Okno dialogowe otwiera się jako pływający panel; nie trzeba niczego wcześniej zaznaczać.

## Tabela warstw

| Kolumna | Co kontroluje |
|---------|-----------------|
| Name | Nazwa warstwy, wyświetlana w tabeli tylko do odczytu (ustawiana raz, przy tworzeniu) |
| Freeze | Ukrywa elementy warstwy i wyklucza je z zaznaczania, dopóki nie zostanie odmrożona |
| Lock | Zapobiega edycji elementów na warstwie, bez ich ukrywania |
| Plot | Czy elementy warstwy są uwzględniane przy drukowaniu lub eksporcie do PDF |
| Color | Kolor ACI warstwy — kliknij próbkę, aby otworzyć wybór koloru |
| Lineweight | Grubość linii warstwy — kliknij chip, aby otworzyć wybór grubości |
| Linetype | Wzór kreskowania warstwy — kliknij chip, aby otworzyć wybór typu linii |

Przełączenie Freeze, Lock lub Plot działa natychmiast — nie ma osobnego kroku zapisu. Elementy ustawione na **ByLayer** dla koloru, grubości linii lub typu linii (wartość domyślna) przyjmują to, co ustawisz tutaj; elementy z własnym jawnym nadpisaniem pozostają bez zmian.

## Dodawanie warstwy

1. Kliknij **+ Add Layer** na dole tabeli.
2. Wpisz nazwę i naciśnij **Enter**, aby potwierdzić, lub **Escape**, aby anulować.

Nazwy warstw mogą zawierać litery, cyfry, spacje oraz `_`, `-`, `$`. Nazwa pusta, już używana lub zawierająca inny znak jest odrzucana z błędem wyświetlanym w linii, a wiersz pozostaje otwarty do ponownej próby.

Nowe warstwy zaczynają jako **odmrożone, odblokowane, drukowalne**, z kolorem 7 (biały/czarny), grubością linii Default i typem linii Continuous — te same wartości domyślne, które [Import](../import/) przypisuje warstwie `0` w pustym rysunku.

## Czego nie można tu zrobić

Nie ma przycisku usuwania — warstwy nigdy nie są usuwane po utworzeniu, można je tylko zamrozić lub pozostawić nieużywane. Tabela nie wskazuje też, która warstwa jest *bieżąca*; ustawia się to z listy rozwijanej panelu warstw lub za pomocą [LayerMakeCurrent](../layer-make-current/), a nie z tego okna.

## Skróty klawiaturowe

| Klawisz | Akcja |
|---------|-------|
| `Enter` | Potwierdź nazwę nowej warstwy (podczas dodawania) |
| `Escape` | Anuluj dodawanie warstwy lub zamknij okno |

## Powiązane polecenia

| Polecenie | Co robi |
|-----------|---------|
| [LayerMakeCurrent](../layer-make-current/) | Ustawia bieżącą warstwę na warstwę klikniętego elementu |
| [LayerMatch](../layer-match/) | Przypisuje zaznaczone elementy do warstwy elementu źródłowego |
| [LayerIsolate](../layer-isolate/) | Zamraża wszystkie warstwy oprócz warstw zaznaczonych elementów |
| [LayerUnfreezeAll](../layer-unfreeze-all/) | Odmraża wszystkie warstwy w jednym kroku |
