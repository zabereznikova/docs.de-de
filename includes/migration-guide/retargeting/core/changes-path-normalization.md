---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614463"
---
### <a name="changes-in-path-normalization"></a>Änderungen an der Pfadnormalisierung

#### <a name="details"></a>Details

Bei Apps, die die Zielplattform .NET Framework 4.6.2 und höher verwenden, wurde im Vergleich zu früheren Versionen die Art und Weise verändert, in der die Laufzeit Pfade normalisiert. Das Normalisieren eines Pfads umfasst das Verändern der Zeichenfolge, die einen Pfad oder eine Datei identifiziert, sodass sie einem gültigen Pfad auf dem Zielbetriebssystem entspricht. Normalisierung umfasst ist in der Regel:

- Die Kanonisierung von Komponenten- und Verzeichnistrennzeichen.
- Die Anwendung des aktuellen Verzeichnisses auf einen relativen Pfad.
- Die Auswertung des relativen Verzeichnisses (.) oder des übergeordneten Verzeichnisses (..) in einem Pfad.
- Das Verkürzen um angegebene Zeichen.
Für Apps, die die Zielplattform .NET Framework 4.6.2 und höher verwenden, sind die folgenden Änderungen an der Pfadnormalisierung standardmäßig aktiviert:
  - Die Runtime greift auf die Funktion [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) des Betriebssystems zurück, um Pfade zu normalisieren.
- Die Normalisierung beinhaltet nicht mehr das Verkürzen des Endes von Verzeichnissegmenten (etwa im Fall eines Leerzeichens am Ende eines Verzeichnisnamens).
- Unterstützung für Gerätepfadsyntax mit vollem Vertrauen, einschließlich `\\.\` und `\\?\` für Datei-E/A-APIs in mscorlib.dll.
- Die Runtime überprüft Gerätesyntaxpfade nicht.
- Die Verwendung von Gerätesyntax für den Zugriff auf alternative Datenströme wird unterstützt.
Diese Änderungen verbessern die Leistung und ermöglichen zugleich Methoden den Zugriff auf zuvor nicht zugängliche Pfade. Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, sind von dieser Änderung nicht betroffen.

#### <a name="suggestion"></a>Vorschlag

Apps mit der Zielplattform .NET Framework 4.6.2 oder höher können die Änderung deaktivieren und die Legacynormalisierung verwenden, indem dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei Folgendes hinzugefügt wird:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

Für Apps mit der Zielplattform .NET Framework 4.6.1 oder niedriger, die unter .NET Framework 4.6.2 oder höher ausgeführt werden, können die Änderungen an der Pfadnormalisierung aktiviert werden, indem dem Abschnitt `<runtime>` der Anwendungskonfigurationsdatei die folgende Zeile hinzugefügt wird:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.6.2       |
| Typ    | Neuzuweisung |
