---
ms.openlocfilehash: 9520f8c6b6671917f5694bc602293a00e2dab82d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568115"
---
### <a name="ziparchiveentry-no-longer-handles-archives-with-inconsistent-entry-sizes"></a>ZipArchiveEntry verarbeitet keine Archive mit inkonsistenten Eintragsgrößen mehr

ZIP-Archive listen sowohl die komprimierte als auch die unkomprimierte Größe im zentralen Verzeichnis und im lokalen Header auf.  Die Eintragsdaten selbst geben die Größe ebenfalls an.  In .NET Core 2.2 und früheren Versionen wurden diese Werte nie auf Konsistenz geprüft. Ab .NET Core 3.0 ist dies jetzt der Fall.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen ist <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType> selbst dann erfolgreich, wenn der lokale Header nicht mit dem zentralen Header der ZIP-Datei übereinstimmt. Die Daten werden dekomprimiert, bis das Ende des komprimierten Datenstroms erreicht ist, auch wenn seine Länge die im zentralen Verzeichnis/lokalen Header angegebene unkomprimierte Dateigröße überschreitet.

Ab .NET Core 3.0 überprüft die <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>-Methode, ob der lokale Header und der zentrale Header hinsichtlich der komprimierten und unkomprimierten Größen eines Eintrags übereinstimmen.  Wenn dies nicht der Fall ist, löst die Methode eine <xref:System.IO.InvalidDataException> aus, wenn die lokalen Größen der Header- und/oder Datendeskriptorlisten des Archivs nicht mit dem zentralen Verzeichnis der ZIP-Datei übereinstimmen. Beim Lesen eines Eintrags werden dekomprimierte Daten auf die nicht komprimierte Dateigröße abgeschnitten, die im Header aufgeführt ist.

Diese Änderung wurde vorgenommen, um sicherzustellen, dass ein <xref:System.IO.Compression.ZipArchiveEntry> die Größe seiner Daten richtig darstellt und nur diese Menge an Daten gelesen wird.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Packen Sie jedes ZIP-Archiv neu, das diese Probleme aufweist.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.Compression.ZipArchiveEntry.Open?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.ExtractToDirectory%2A?displayProperty=nameWithType>

<!--

### Affected APIs

`M:System.IO.Compression.ZipArchiveEntry.Open`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToDirectory%2A`
`Overload:System.IO.Compression.ZipFileExtensions.ExtractToFile%2A`
`Overload:System.IO.Compression.ZipFile.ExtractToDirectory%2A`

-->
