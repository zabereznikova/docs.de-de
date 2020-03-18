---
title: Memory- und Span-Elemente
ms.date: 10/03/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- Memory<T>
- Span<T>
- buffers"
- pipeline processing
ms.openlocfilehash: b61b1dbbedf4658fe113986fbb4a792a2f574534
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73121990"
---
# <a name="memory--and-span-related-types"></a><span data-ttu-id="011b0-102">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="011b0-102">Memory- and span-related types</span></span>

<span data-ttu-id="011b0-103">Ab .NET Core 2.1 umfasst .NET eine Reihe von zueinander in Beziehung stehender Typen, die eine zusammenhängende, stark typisierte Region eines beliebigen Speichers darstellen.</span><span class="sxs-lookup"><span data-stu-id="011b0-103">Starting with .NET Core 2.1, .NET includes a number of interrelated types that represent a contiguous, strongly-typed region of arbitrary memory.</span></span> <span data-ttu-id="011b0-104">Dazu gehören:</span><span class="sxs-lookup"><span data-stu-id="011b0-104">These include:</span></span>

- <span data-ttu-id="011b0-105"><xref:System.Span%601?displayProperty=nameWithType>: Dieser Typ wird verwendet, um auf einen zusammenhängenden Speicherbereich zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="011b0-105"><xref:System.Span%601?displayProperty=nameWithType>, a type that is used to access a contiguous region of memory.</span></span> <span data-ttu-id="011b0-106">Eine <xref:System.Span%601>-Instanz kann sich auf ein Array vom Typ `T`, ein <xref:System.String>, einen mit [stackalloc](../../csharp/language-reference/operators/stackalloc.md) zugeordneten Puffer oder auf einen Zeiger auf nicht verwalteten Speicher stützen.</span><span class="sxs-lookup"><span data-stu-id="011b0-106">A <xref:System.Span%601> instance can be backed by an array of type `T`, a <xref:System.String>, a buffer allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), or a pointer to unmanaged memory.</span></span> <span data-ttu-id="011b0-107">Da die Zuordnung im Stapel erfolgen muss, gelten einige Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="011b0-107">Because it has to be allocated on the stack, it has a number of restrictions.</span></span> <span data-ttu-id="011b0-108">Beispielsweise kann ein Feld in einer Klasse nicht den Typ <xref:System.Span%601> aufweisen, und ein Span-Element kann nicht in asynchronen Vorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="011b0-108">For example, a field in a class cannot be of type <xref:System.Span%601>, nor can span be used in asynchronous operations.</span></span>

- <span data-ttu-id="011b0-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>: Eine unveränderliche Version der <xref:System.Span%601>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="011b0-109"><xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Span%601> structure.</span></span>

- <span data-ttu-id="011b0-110"><xref:System.Memory%601?displayProperty=nameWithType>: Eine zusammenhängende Speicherregion, die nicht im Stapel, sondern im verwalteten Heap zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="011b0-110"><xref:System.Memory%601?displayProperty=nameWithType>, a contiguous region of memory that is allocated on the managed heap rather than the stack.</span></span> <span data-ttu-id="011b0-111">Eine <xref:System.Memory%601>-Instanz kann durch ein Array vom Typ `T` oder einen <xref:System.String> gestützt werden.</span><span class="sxs-lookup"><span data-stu-id="011b0-111">A <xref:System.Memory%601> instance can be backed by an array of type `T` or a <xref:System.String>.</span></span> <span data-ttu-id="011b0-112"><xref:System.Memory%601> kann im verwalteten Heap gespeichert werden, deshalb gelten keine der Einschränkungen von <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="011b0-112">Because it can be stored on the managed heap, <xref:System.Memory%601> has none of the limitations of <xref:System.Span%601>.</span></span>

- <span data-ttu-id="011b0-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>: Eine unveränderliche Version der <xref:System.Memory%601>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="011b0-113"><xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>, an immutable version of the <xref:System.Memory%601> structure.</span></span>

- <span data-ttu-id="011b0-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>: Ordnet einem Besitzer stark typisierte Speicherblöcke aus einem Speicherpool zu.</span><span class="sxs-lookup"><span data-stu-id="011b0-114"><xref:System.Buffers.MemoryPool%601?displayProperty=nameWithType>, which allocates strongly-typed blocks of memory from a memory pool to an owner.</span></span> <span data-ttu-id="011b0-115"><xref:System.Buffers.IMemoryOwner%601>-Instanzen können durch Aufruf von <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> aus dem Pool bezogen und durch Aufruf von <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType> wieder an den Pool zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="011b0-115"><xref:System.Buffers.IMemoryOwner%601> instances can be rented from the pool by calling <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> and released back to the pool by calling <xref:System.Buffers.MemoryPool%601.Dispose?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="011b0-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>: Repräsentiert den Besitzer eines Speicherblocks und steuert die zugehörige Lebenszyklusverwaltung.</span><span class="sxs-lookup"><span data-stu-id="011b0-116"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>, which represents the owner of a block of memory and controls its lifetime management.</span></span>

- <span data-ttu-id="011b0-117"><xref:System.Buffers.MemoryManager%601>: Eine abstrakte Basisklasse, mit der die Implementierung von <xref:System.Memory%601> ersetzt werden kann, sodass <xref:System.Memory%601> durch zusätzliche Typen, z.B. sichere Handles, gestützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="011b0-117"><xref:System.Buffers.MemoryManager%601>, an abstract base class that can be used to replace the implementation of <xref:System.Memory%601> so that <xref:System.Memory%601> can be backed by additional types, such as safe handles.</span></span> <span data-ttu-id="011b0-118"><xref:System.Buffers.MemoryManager%601> ist ausschließlich für weiterführende Szenarien bestimmt.</span><span class="sxs-lookup"><span data-stu-id="011b0-118"><xref:System.Buffers.MemoryManager%601> is intended for advanced scenarios.</span></span>

- <span data-ttu-id="011b0-119"><xref:System.ArraySegment%601>: Ein Wrapper für eine bestimmte Anzahl von Arrayelementen, beginnend bei einem bestimmten Index.</span><span class="sxs-lookup"><span data-stu-id="011b0-119"><xref:System.ArraySegment%601>, a wrapper for a particular number of array elements starting at a particular index.</span></span>

- <span data-ttu-id="011b0-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>: Eine Sammlung von Erweiterungsmethoden für die Konvertierung von Zeichenfolgen, Arrays und Arraysegmenten in <xref:System.Memory%601>-Blöcke.</span><span class="sxs-lookup"><span data-stu-id="011b0-120"><xref:System.MemoryExtensions?displayProperty=nameWithType>, a collection of extension methods for converting strings, arrays, and array segments to <xref:System.Memory%601> blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="011b0-121">Für frühere Frameworkversionen stehen <xref:System.Span%601> und <xref:System.Memory%601> im [NuGet-Paket „System.Memory“](https://www.nuget.org/packages/System.Memory/) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="011b0-121">For earlier frameworks, <xref:System.Span%601> and <xref:System.Memory%601> are available in the [System.Memory NuGet package](https://www.nuget.org/packages/System.Memory/).</span></span>

<span data-ttu-id="011b0-122">Weitere Informationen finden Sie unter den Ausführungen zum <xref:System.Buffers?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="011b0-122">For more information, see the <xref:System.Buffers?displayProperty=nameWithType> namespace.</span></span>

## <a name="working-with-memory-and-span"></a><span data-ttu-id="011b0-123">Arbeiten mit Memory- und Span-Elementen</span><span class="sxs-lookup"><span data-stu-id="011b0-123">Working with memory and span</span></span>

<span data-ttu-id="011b0-124">Die Memory- und Span-bezogenen Typen werden typischerweise zum Speichern von Daten in einer Verarbeitungspipeline verwendet, deshalb ist es wichtig, dass Entwickler bei der Verwendung von <xref:System.Span%601>, <xref:System.Memory%601> und zugehörigen Typen bestimmte Best Practices einhalten.</span><span class="sxs-lookup"><span data-stu-id="011b0-124">Because the memory- and span-related types are typically used to store data in a processing pipeline, it is important that developers follow a set of best practices when using <xref:System.Span%601>, <xref:System.Memory%601>, and related types.</span></span> <span data-ttu-id="011b0-125">Diese Best Practices werden im [Leitfaden zur Verwendung von Memory\<T> und Span\<T>](memory-t-usage-guidelines.md) dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="011b0-125">These best practices are documented in [Memory\<T> and Span\<T> usage guidelines](memory-t-usage-guidelines.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="011b0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="011b0-126">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.ReadOnlyMemory%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
- <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>
- <xref:System.Buffers?displayProperty=nameWithType>
