---
title: Memory- und Span-Elemente
ms.date: 10/03/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: c60c08d27c0e41228a15e8acdf01a9af28a23762
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201967"
---
# <a name="memory--and-span-related-types"></a>Memory- und Span-bezogene Typen

Ab .NET Core 2.1 umfasst .NET eine Reihe von zueinander in Beziehung stehender Typen, die eine zusammenhängende, stark typisierte Region eines beliebigen Speichers darstellen. Dazu gehören:

- <xref:System.Span%601?displayProperty=nameWithType>: Dieser Typ wird verwendet, um auf einen zusammenhängenden Speicherbereich zuzugreifen. Eine <xref:System.Span%601>-Instanz kann sich auf ein Array vom Typ `T`, ein <xref:System.String>, einen mit [stackalloc](../../csharp/language-reference/operators/stackalloc.md) zugeordneten Puffer oder auf einen Zeiger auf nicht verwalteten Speicher stützen. Da die Zuordnung im Stapel erfolgen muss, gelten einige Einschränkungen. Beispielsweise kann ein Feld in einer Klasse nicht den Typ <xref:System.Span%601> aufweisen, und ein Span-Element kann nicht in asynchronen Vorgängen verwendet werden.

- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>: Eine unveränderliche Version der <xref:System.Span%601>-Struktur.

- <xref:System.Memory%601?displayProperty=nameWithType>: Eine zusammenhängende Speicherregion, die nicht im Stapel, sondern im verwalteten Heap zugeordnet wird. Eine <xref:System.Memory%601>-Instanz kann durch ein Array vom Typ `T` oder einen <xref:System.String> gestützt werden. <xref:System.Memory%601> kann im verwalteten Heap gespeichert werden, deshalb gelten keine der Einschränkungen von <xref:System.Span%601>.

- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>: Eine unveränderliche Version der <xref:System.Memory%601>-Struktur.

- <xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>: Ordnet einem Besitzer stark typisierte Speicherblöcke aus einem Speicherpool zu. <xref:System.Buffers.IMemoryOwner%601>-Instanzen können durch Aufruf von <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> aus dem Pool bezogen und durch Aufruf von <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType> wieder an den Pool zurückgegeben werden.

- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>: Repräsentiert den Besitzer eines Speicherblocks und steuert die zugehörige Lebenszyklusverwaltung.

- <xref:System.Buffers.MemoryManager%601>: Eine abstrakte Basisklasse, mit der die Implementierung von <xref:System.Memory%601> ersetzt werden kann, sodass <xref:System.Memory%601> durch zusätzliche Typen, z.B. sichere Handles, gestützt werden kann. <xref:System.Buffers.MemoryManager%601> ist ausschließlich für weiterführende Szenarien bestimmt.

- <xref:System.ArraySegment%601>: Ein Wrapper für eine bestimmte Anzahl von Arrayelementen, beginnend bei einem bestimmten Index.

- <xref:System.MemoryExtensions?displayProperty=nameWithType>: Eine Sammlung von Erweiterungsmethoden für die Konvertierung von Zeichenfolgen, Arrays und Arraysegmenten in <xref:System.Memory%601>-Blöcke.

> [!NOTE]
> Für frühere Frameworkversionen stehen <xref:System.Span%601> und <xref:System.Memory%601> im [NuGet-Paket „System.Memory“](https://www.nuget.org/packages/System.Memory/) zur Verfügung.

Weitere Informationen finden Sie unter den Ausführungen zum <xref:System.Buffers?displayProperty=nameWithType>-Namespace.

## <a name="working-with-memory-and-span"></a>Arbeiten mit Memory- und Span-Elementen

Die Memory- und Span-bezogenen Typen werden typischerweise zum Speichern von Daten in einer Verarbeitungspipeline verwendet, deshalb ist es wichtig, dass Entwickler bei der Verwendung von <xref:System.Span%601>, <xref:System.Memory%601> und zugehörigen Typen bestimmte Best Practices einhalten. Diese Best Practices werden im [Leitfaden zur Verwendung von Memory\<T> und Span\<T>](memory-t-usage-guidelines.md) dokumentiert.

## <a name="see-also"></a>Siehe auch

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
