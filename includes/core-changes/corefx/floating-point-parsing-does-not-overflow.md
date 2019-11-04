---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198438"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a>Gleitkomma-Analysevorgänge lösen keinen Fehler und keine OverflowException mehr aus

Die Gleitkomma-Analysemethoden lösen keine <xref:System.OverflowException> mehr aus und geben auch nicht `false` zurück, wenn sie eine Zeichenfolge analysieren, deren Zahlenwert außerhalb des Bereichs des Gleitkommatyps <xref:System.Single> oder <xref:System.Double> liegt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen lösen die Methoden <xref:System.Double.Parse%2A?displayProperty=nameWithType> und <xref:System.Single.Parse%2A?displayProperty=nameWithType> eine <xref:System.OverflowException> für Werte aus, die außerhalb des Bereichs ihres jeweiligen Typs liegen. Die Methoden <xref:System.Double.TryParse%2A?displayProperty=nameWithType> und <xref:System.Single.TryParse%2A?displayProperty=nameWithType> geben `false` für die Zeichenfolgendarstellungen von numerischen Werten außerhalb des gültigen Bereichs zurück.

Ab .NET Core 3.0 schlagen die Methoden <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> und <xref:System.Single.TryParse%2A?displayProperty=nameWithType> nicht mehr fehl, wenn Sie außerhalb des gültigen Bereichs liegende numerische Zeichenfolgen analysieren. Stattdessen geben die <xref:System.Double>-Analysemethoden <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> für Werte, die <xref:System.Double.MaxValue?displayProperty=nameWithType> überschreiten, und <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> für Werte zurück, die kleiner als <xref:System.Double.MinValue?displayProperty=nameWithType> sind. Analog dazu geben die <xref:System.Single>-Analysemethoden <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> für Werte, die <xref:System.Single.MaxValue?displayProperty=nameWithType> überschreiten, und <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> für Werte zurück, die kleiner als <xref:System.Single.MinValue?displayProperty=nameWithType> sind.

Diese Änderung wurde vorgenommen, um die Konformität mit IEEE 754:2008 zu verbessern.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Diese Änderung kann sich auf zwei Arten auf den Code auswirken:

- Der Code hängt vom Handler für die <xref:System.OverflowException> ab, der ausgeführt wird, wenn ein Überlauf auftritt. In diesem Fall sollten Sie die `catch`-Anweisung entfernen und erforderlichen Code in einer `If`-Anweisung platzieren, die testet, ob <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> oder <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> `true` ist.

- Ihr Code geht davon aus, dass Gleitkommawerte nicht `Infinity` sind. In diesem Fall sollten Sie den erforderlichen Code hinzufügen, um auf Gleitkommawerte des Typs `PositiveInfinity` und `NegativeInfinity` zu prüfen.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
