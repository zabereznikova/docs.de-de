---
title: 'Breaking Change: Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Implementierung von OrderBy.First geändert wurde.
ms.date: 11/01/2020
ms.openlocfilehash: 3c4f8fd0bb2051c3e1ac14eab091be11f10f88b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759478"
---
# <a name="complexity-of-linq-orderbyfirstordefault-increased"></a>Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht

Die Implementierung von <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> und <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> wurde geändert, wodurch die Komplexität des Vorgangs erhöht wurde.

## <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 1.x bis 3.x werden Aufrufe von <xref:System.Linq.Enumerable.OrderBy%2A> oder <xref:System.Linq.Enumerable.OrderByDescending%2A> gefolgt von <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> mit der Komplexität `O(N)` durchgeführt. Da nur das erste Element (oder das Standardelement) erforderlich ist, ist nur eine Enumeration erforderlich, um es zu finden. Allerdings wird das für <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> bereitgestellte Prädikat genau `N` Mal aufgerufen. Dabei entspricht `N` der Länge der Sequenz.

In .NET 5.0 und höheren Versionen [wurde eine Änderung eingeführt](https://github.com/dotnet/runtime/pull/36643), durch die Aufrufe von <xref:System.Linq.Enumerable.OrderBy%2A> oder <xref:System.Linq.Enumerable.OrderByDescending%2A> gefolgt von <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> mit der Komplexität `O(N log N)` anstelle von `O(N)` durchgeführt werden. Allerdings kann das für <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> bereitgestellte Prädikat *weniger* als `N` Mal aufgerufen werden, was für die Gesamtleistung wichtiger ist.

> [!NOTE]
> Diese Änderung entspricht der Implementierung und Komplexität des Vorgangs im .NET Framework.

## <a name="reason-for-change"></a>Grund für die Änderung

Der Vorteil weniger Aufrufe des Prädikats überwiegt geringere Gesamtkomplexität, daher wurde die in .NET Core 1.0 eingeführte Implementierung rückgängig gemacht. Weitere Informationen finden Sie in [diesem Dotnet-/Runtime-Issue](https://github.com/dotnet/runtime/issues/31554).

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Der Entwickler muss keine Maßnahmen ergreifen.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
