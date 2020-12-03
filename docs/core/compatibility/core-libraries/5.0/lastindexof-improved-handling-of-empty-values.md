---
title: 'Breaking Change: LastIndexOf hat die Behandlung leerer Suchzeichenfolgen verbessert'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den LastIndexOf und zugehörige APIs jetzt richtige Werte zurückgeben, wenn nach einer Teilzeichenfolge mit der Länge 0 (null) gesucht wird.
ms.date: 11/01/2020
ms.openlocfilehash: 6d1a676eb2b9ed3de6a745db27d53bd43560a32f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759217"
---
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a><span data-ttu-id="efe12-103">LastIndexOf hat die Behandlung leerer Suchzeichenfolgen verbessert.</span><span class="sxs-lookup"><span data-stu-id="efe12-103">LastIndexOf has improved handling of empty search strings</span></span>

<span data-ttu-id="efe12-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> und ähnliche APIs geben nun beim Suchen nach einer Teilzeichenfolge mit der Länge 0 (oder einem vergleichbaren Wert) in einer größeren Zeichenfolge die richtigen Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="efe12-104"><xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs now return correct values when searching for a zero-length (or zero-length equivalent) substring within a larger string.</span></span>

## <a name="change-description"></a><span data-ttu-id="efe12-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="efe12-105">Change description</span></span>

<span data-ttu-id="efe12-106">Im .NET Framework und in .NET Core 1.0–3.1 geben <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> und ähnliche APIs möglicherweise einen falschen Wert zurück, wenn der Aufrufer nach einer Teilzeichenfolge mit der Länge 0 sucht.</span><span class="sxs-lookup"><span data-stu-id="efe12-106">In .NET Framework and .NET Core 1.0 - 3.1, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> and related APIs might return an incorrect value when the caller searches for a zero-length substring.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

<span data-ttu-id="efe12-107">Ab .NET 5.0 geben diese APIs den richtigen Wert für `LastIndexOf` zurück.</span><span class="sxs-lookup"><span data-stu-id="efe12-107">Starting with .NET 5.0, these APIs return the correct value for `LastIndexOf`.</span></span>

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

<span data-ttu-id="efe12-108">In diesen Beispielen ist `5` die richtige Antwort, da `"Hello".Substring(5)` und `"Hello".AsSpan().Slice(5)` eine leere Zeichenfolge zurückgeben. Dieser Wert und die gesuchte leere Teilzeichenfolge sind trivial gleich.</span><span class="sxs-lookup"><span data-stu-id="efe12-108">In these examples, `5` is the correct answer because `"Hello".Substring(5)` and `"Hello".AsSpan().Slice(5)` both produce an empty string, which is trivially equal to the empty substring that is sought.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="efe12-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="efe12-109">Reason for change</span></span>

<span data-ttu-id="efe12-110">Diese Änderung war Teil einer allgemeinen Fehlerbehebung für die Zeichenfolgenverarbeitung in .NET 5.</span><span class="sxs-lookup"><span data-stu-id="efe12-110">This change was part of an overall bug fixing effort around string handling for .NET 5.</span></span> <span data-ttu-id="efe12-111">Außerdem kann das Verhalten zwischen Windows- und Nicht-Windows-Plattformen vereinheitlicht werden.</span><span class="sxs-lookup"><span data-stu-id="efe12-111">It also helps unify our behavior between Windows and non-Windows platforms.</span></span> <span data-ttu-id="efe12-112">Weitere Informationen finden Sie unter [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) und [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span><span class="sxs-lookup"><span data-stu-id="efe12-112">For more information, see [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) and [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="efe12-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="efe12-113">Version introduced</span></span>

<span data-ttu-id="efe12-114">5.0</span><span class="sxs-lookup"><span data-stu-id="efe12-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="efe12-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="efe12-115">Recommended action</span></span>

<span data-ttu-id="efe12-116">Sie müssen keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="efe12-116">You don't need to take any action.</span></span> <span data-ttu-id="efe12-117">Die .NET 5.0-Runtime stellt das neue Verhalten automatisch bereit.</span><span class="sxs-lookup"><span data-stu-id="efe12-117">The .NET 5.0 runtime provides the new behaviors automatically.</span></span>

<span data-ttu-id="efe12-118">Es gibt keine Kompatibilitätsoption, um das alte Verhalten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="efe12-118">There is no compatibility switch to restore the old behavior.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="efe12-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="efe12-119">Affected APIs</span></span>

- <xref:System.String.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.Globalization.CompareInfo.LastIndexOf%2A?displayProperty=fullName>
- <xref:System.MemoryExtensions.LastIndexOf%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.String.LastIndexOf`
- `Overload:System.Globalization.CompareInfo.LastIndexOf`
- `Overload:System.MemoryExtensions.LastIndexOf`

-->
