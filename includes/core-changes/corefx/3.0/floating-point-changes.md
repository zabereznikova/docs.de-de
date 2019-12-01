---
ms.openlocfilehash: ce4f09908b1025e8e5a0380c9bf035c6b0db479a
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568189"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a>Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten

Das Verhalten bei der Analyse und Formatierung von Gleitkommawerten (durch die Typen <xref:System.Double> und <xref:System.Single>) ist jetzt IEEE-konform.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen war die Formatierung mit <xref:System.Double.ToString%2A?displayProperty=nameWithType> und <xref:System.Single.ToString%2A?displayProperty=nameWithType> und die Analyse mit <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> und <xref:System.Single.TryParse%2A?displayProperty=nameWithType> nicht IEEE-konform. Daher kann nicht sichergestellt werden, dass ein Wert mit einer unterstützten Zeichenfolge in einem Standardformat oder in einem benutzerdefinierten Format einen Roundtrip durchführt. Bei einigen Eingaben kann bei der Analyse eines formatierten Werts ein Fehler auftreten. Bei anderen Eingaben kann es vorkommen, dass der analysierte Wert nicht dem ursprünglichen Wert entspricht.

Ab .NET Core 3.0 entsprechen Analyse- und Formatierungsvorgänge der Norm IEEE 754. Dadurch wird sichergestellt, dass das Verhalten von Gleitkommatypen in .NET dem Verhalten von IEEE-konformen Sprachen wie C# entspricht. Weitere Informationen finden Sie im Blogbeitrag [Verbesserungen bei Analyse und Formatierung von Gleitkommawerten in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Im Abschnitt „Potenzielle Auswirkungen auf bestehenden Code“ des Blogbeitrags [Verbesserungen bei Analyse und Formatierung von Gleitkommawerten in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) wird vorgeschlagen, den Code zu ändern, wenn eine Verhaltensänderung im Vergleich zu .NET Core 2.2-Anwendungen festgestellt wird. Dazu gehört im Allgemeinen die Verwendung einer anderen Zeichenfolge in einem Standardformat oder in einem benutzerdefinierten Format, um das gewünschte Verhalten zu erzwingen. Für einige Ergebnisse, die zuvor bereits falsch waren, gibt es unter Umständen keine Möglichkeit, das Problem zu umgehen.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
