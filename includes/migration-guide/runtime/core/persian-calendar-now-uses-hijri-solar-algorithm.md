---
ms.openlocfilehash: e4d9efe7d2a06a1e501b070c23184dcd913dba71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621282"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a>Der persische Kalender verwendet jetzt den Hijri-Solaralgorithmus

#### <a name="details"></a>Details

Ab .NET Framework 4.6 verwendet die <xref:System.Globalization.PersianCalendar?displayProperty=fullName>-Klasse den Hijri-Solaralgorithmus. Das Konvertieren von Datumsangaben zwischen <xref:System.Globalization.PersianCalendar?displayProperty=fullName> und anderen Kalendern erzeugt ab .NET Framework 4.6 für Datumsangaben vor 1800 oder nach 2023 (gregorianisch) möglicherweise ein etwas anderes Ergebnis. Darüber hinaus entspricht <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> nun <code>March 22, 0622</code> anstatt <code>March 21, 0622</code>.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass einige frühe oder späte Datumsangaben bei der Verwendung des persischen Kalenders in .NET Framework 4.6 möglicherweise etwas anders aussehen. Speichern Sie zudem beim Serialisieren von Daten zwischen Prozessen, die möglicherweise unter verschiedenen Versionen von .NET Framework ausgeführt werden, die Daten nicht als PersionCalendar-Datumszeichenfolgen (da diese Werte abweichen können).

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Globalization.PersianCalendar?displayProperty=nameWithType></li></ul>|
