---
ms.openlocfilehash: bfe406161ac754124a2cc38c68a80c3b9fb2c7f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858403"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Der persische Kalender verwendet jetzt den Hijri-Solaralgorithmus

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6 verwendet die <xref:System.Globalization.PersianCalendar?displayProperty=name>-Klasse den Hijri-Solaralgorithmus. Das Konvertieren von Datumsangaben zwischen <xref:System.Globalization.PersianCalendar?displayProperty=name> und anderen Kalendern erzeugt ab .NET Framework 4.6 für Datumsangaben vor 1800 oder nach 2023 (gregorianisch) möglicherweise ein etwas anderes Ergebnis. Darüber hinaus entspricht <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> nun <code>March 22, 0622</code> anstatt <code>March 21, 0622</code>.|
|Vorschlag|Beachten Sie, dass einige frühe oder späte Datumsangaben bei der Verwendung des persischen Kalenders in .NET Framework 4.6 möglicherweise etwas anders aussehen. Speichern Sie zudem beim Serialisieren von Daten zwischen Prozessen, die möglicherweise unter verschiedenen Versionen von .NET Framework ausgeführt werden, die Daten nicht als PersionCalendar-Datumszeichenfolgen (da diese Werte abweichen können).|
|`Scope`|Nebenversion|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
