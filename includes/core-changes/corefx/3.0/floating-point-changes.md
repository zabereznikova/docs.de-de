---
ms.openlocfilehash: 719f336e1b38597674d6ee8f0c5429dd965054b1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032009"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a><span data-ttu-id="417e7-101">Neues Verhalten bei Formatierung und Analyse von Gleitkommawerten</span><span class="sxs-lookup"><span data-stu-id="417e7-101">Floating-point formatting and parsing behavior changed</span></span>

<span data-ttu-id="417e7-102">Das Verhalten bei der Analyse und Formatierung von Gleitkommawerten (durch die Typen <xref:System.Double> und <xref:System.Single>) ist jetzt IEEE-konform.</span><span class="sxs-lookup"><span data-stu-id="417e7-102">Floating point parsing and formatting behavior (by the <xref:System.Double> and <xref:System.Single> types) are now IEEE-compliant.</span></span>

#### <a name="change-description"></a><span data-ttu-id="417e7-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="417e7-103">Change description</span></span>

<span data-ttu-id="417e7-104">In .NET Core 2.2 und früheren Versionen war die Formatierung mit <xref:System.Double.ToString%2A?displayProperty=nameWithType> und <xref:System.Single.ToString%2A?displayProperty=nameWithType> und die Analyse mit <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> und <xref:System.Single.TryParse%2A?displayProperty=nameWithType> nicht IEEE-konform.</span><span class="sxs-lookup"><span data-stu-id="417e7-104">In .NET Core 2.2 and earlier versions, formatting with <xref:System.Double.ToString%2A?displayProperty=nameWithType> and <xref:System.Single.ToString%2A?displayProperty=nameWithType>, and parsing with <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> are not IEEE-compliant.</span></span> <span data-ttu-id="417e7-105">Daher kann nicht sichergestellt werden, dass ein Wert mit einer unterstützten Zeichenfolge in einem Standardformat oder in einem benutzerdefinierten Format einen Roundtrip durchführt.</span><span class="sxs-lookup"><span data-stu-id="417e7-105">As a result, it is impossible to guarantee that a value will roundtrip with any supported standard or custom format string.</span></span> <span data-ttu-id="417e7-106">Bei einigen Eingaben kann bei der Analyse eines formatierten Werts ein Fehler auftreten. Bei anderen Eingaben kann es vorkommen, dass der analysierte Wert nicht dem ursprünglichen Wert entspricht.</span><span class="sxs-lookup"><span data-stu-id="417e7-106">For some inputs, the attempt to parse a formatted value can fail, and for others, the parsed value doesn't equal the original value.</span></span>

<span data-ttu-id="417e7-107">Ab .NET Core 3.0 entsprechen Analyse- und Formatierungsvorgänge der Norm IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="417e7-107">Starting with .NET Core 3.0, parsing and formatting operations are IEEE 754-compliant.</span></span> <span data-ttu-id="417e7-108">Dadurch wird sichergestellt, dass das Verhalten von Gleitkommatypen in .NET dem Verhalten von IEEE-konformen Sprachen wie C# entspricht.</span><span class="sxs-lookup"><span data-stu-id="417e7-108">This ensures that the behavior of floating-point types in .NET matches that of IEEE-compliant languages such as C#.</span></span> <span data-ttu-id="417e7-109">Weitere Informationen finden Sie im Blogbeitrag [Verbesserungen bei Analyse und Formatierung von Gleitkommawerten in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="417e7-109">For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="417e7-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="417e7-110">Version introduced</span></span>

<span data-ttu-id="417e7-111">3.0</span><span class="sxs-lookup"><span data-stu-id="417e7-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="417e7-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="417e7-112">Recommended action</span></span>

<span data-ttu-id="417e7-113">Im Abschnitt „Potenzielle Auswirkungen auf bestehenden Code“ des Blogbeitrags [Verbesserungen bei Analyse und Formatierung von Gleitkommawerten in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) wird vorgeschlagen, den Code zu ändern, wenn eine Verhaltensänderung im Vergleich zu .NET Core 2.2-Anwendungen festgestellt wird. Dazu gehört im Allgemeinen die Verwendung einer anderen Zeichenfolge in einem Standardformat oder in einem benutzerdefinierten Format, um das gewünschte Verhalten zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="417e7-113">The "Potential impact to existing code" section of the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post suggests changes to your code if you observe a change of behavior when compared to .NET Core 2.2 applications Generally, this involves using a different standard or custom format string to enforce the desired behavior.</span></span> <span data-ttu-id="417e7-114">Für einige Ergebnisse, die zuvor bereits falsch waren, gibt es unter Umständen keine Möglichkeit, das Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="417e7-114">Some results may not have a workaround if they were previously incorrect.</span></span>

#### <a name="category"></a><span data-ttu-id="417e7-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="417e7-115">Category</span></span>

<span data-ttu-id="417e7-116">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="417e7-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="417e7-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="417e7-117">Affected APIs</span></span>

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
