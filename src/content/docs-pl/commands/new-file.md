---
title: New File — Tworzenie pustego rysunku w KulmanLab CAD
description: Polecenie New File czyści płótno i otwiera świeży pusty rysunek. Automatycznie generowana jest nazwa pliku ze znacznikiem czasu, która jest zapisywana w pamięci przeglądarki.
keywords: [nowy plik CAD, nowy rysunek, puste płótno CAD, tworzenie nowego rysunku online, nowy DXF, KulmanLab nowy plik, resetowanie płótna, czyszczenie rysunku]
group: file
order: 2
---

# New File

Polecenie **Nowy plik** czyści płótno i zaczyna świeży pusty rysunek. Unikalna nazwa pliku ze znacznikiem czasu jest generowana automatycznie.

## Jak utworzyć nowy plik

Kliknij przycisk **Nowy plik** na pasku narzędzi (ikona nowej strony) w panelu Plik. Płótno czyści się natychmiast — bez monitów ani okien dialogowych potwierdzenia.

## Co zawiera nowy plik

Świeżo utworzony plik zaczyna się od:

- **Brak elementów** na płótnie.
- **Jedna domyślna warstwa** o nazwie `0` z białym kolorem i typem linii `Ciągła`.
- **Wygenerowana nazwa pliku**, `kulman.dxf` — lub `kulman (2).dxf`, `kulman (3).dxf`, … jeśli ta nazwa jest już zajęta.

Plik jest automatycznie zapisywany w pamięci przeglądarki, pojawia się w [File Manager](../file-manager/) i można [zmienić jego nazwę](../file-manager/#zmiana-nazwy-pliku) w dowolnym momencie.

## Ostrzeżenie — niezapisana praca zostanie odrzucona

Kliknięcie **Nowy plik** odrzuca wszystkie elementy na bieżącym płótnie bez ostrzeżenia. Jeśli chcesz zachować bieżący rysunek, najpierw [Export](../export/) go.

## Kiedy używać Nowego pliku a Importu

| Sytuacja | Zalecana akcja |
|-----------|-------------------|
| Rozpoczynanie rysunku od zera | **Nowy plik** |
| Otwieranie istniejącego pliku DXF lub JSON | [Import](../import/) |
| Kopiowanie rysunku do pracy nad wariantem | [Export](../export/) bieżący plik, następnie [Import](../import/) kopię |

## Powiązane polecenia

- [Import](../import/) — otwieranie istniejącego rysunku DXF lub JSON
- [Export](../export/) — pobieranie rysunku przed rozpoczęciem od nowa
- [File Manager](../file-manager/) — przywracanie poprzedniego rysunku z pamięci przeglądarki
