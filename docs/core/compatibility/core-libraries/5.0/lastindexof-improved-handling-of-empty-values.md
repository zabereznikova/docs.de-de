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
# <a name="lastindexof-has-improved-handling-of-empty-search-strings"></a>LastIndexOf hat die Behandlung leerer Suchzeichenfolgen verbessert.

<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> und ähnliche APIs geben nun beim Suchen nach einer Teilzeichenfolge mit der Länge 0 (oder einem vergleichbaren Wert) in einer größeren Zeichenfolge die richtigen Werte zurück.

## <a name="change-description"></a>Änderungsbeschreibung

Im .NET Framework und in .NET Core 1.0–3.1 geben <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> und ähnliche APIs möglicherweise einen falschen Wert zurück, wenn der Aufrufer nach einer Teilzeichenfolge mit der Länge 0 sucht.

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '4' (incorrect)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '0' (incorrect)
```

Ab .NET 5.0 geben diese APIs den richtigen Wert für `LastIndexOf` zurück.

```csharp
Console.WriteLine("Hello".LastIndexOf("")); // prints '5' (correct)

ReadOnlySpan<char> span = "Hello";
Console.WriteLine(span.LastIndexOf("")); // prints '5' (correct)
```

In diesen Beispielen ist `5` die richtige Antwort, da `"Hello".Substring(5)` und `"Hello".AsSpan().Slice(5)` eine leere Zeichenfolge zurückgeben. Dieser Wert und die gesuchte leere Teilzeichenfolge sind trivial gleich.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung war Teil einer allgemeinen Fehlerbehebung für die Zeichenfolgenverarbeitung in .NET 5. Außerdem kann das Verhalten zwischen Windows- und Nicht-Windows-Plattformen vereinheitlicht werden. Weitere Informationen finden Sie unter [dotnet/runtime#13383](https://github.com/dotnet/runtime/issues/13383) und [dotnet/runtime##13382](https://github.com/dotnet/runtime/issues/13382).

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Sie müssen keine Maßnahmen ergreifen. Die .NET 5.0-Runtime stellt das neue Verhalten automatisch bereit.

Es gibt keine Kompatibilitätsoption, um das alte Verhalten wiederherzustellen.

## <a name="affected-apis"></a>Betroffene APIs

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
