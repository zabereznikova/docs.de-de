---
title: 'Integrierte Typen: C#-Referenz'
description: Hier erfahren Sie mehr über in C# integrierte Werte und Verweistypen.
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 4f748373350ed0596a5f1d595c273243ae3227c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77095294"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="76a3e-103">Integrierte Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="76a3e-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="76a3e-104">In der folgenden Tabelle werden die in C# integrierten [Werttypen](value-types.md) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="76a3e-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="76a3e-105">C#-Typschlüsselwort</span><span class="sxs-lookup"><span data-stu-id="76a3e-105">C# type keyword</span></span>|<span data-ttu-id="76a3e-106">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="76a3e-106">.NET type</span></span>|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

<span data-ttu-id="76a3e-107">In der folgenden Tabelle werden die in C# integrierten [Verweistypen](../keywords/reference-types.md) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="76a3e-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="76a3e-108">C#-Typschlüsselwort</span><span class="sxs-lookup"><span data-stu-id="76a3e-108">C# type keyword</span></span>|<span data-ttu-id="76a3e-109">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="76a3e-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

<span data-ttu-id="76a3e-110">In den obigen Tabellen ist jedes C#-Typschlüsselwort aus der linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="76a3e-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="76a3e-111">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76a3e-111">They are interchangeable.</span></span> <span data-ttu-id="76a3e-112">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="76a3e-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

## <a name="see-also"></a><span data-ttu-id="76a3e-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76a3e-113">See also</span></span>

- [<span data-ttu-id="76a3e-114">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="76a3e-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="76a3e-115">Standardwerte der C#-Typen</span><span class="sxs-lookup"><span data-stu-id="76a3e-115">Default values of C# types</span></span>](default-values.md)
- [<span data-ttu-id="76a3e-116">`dynamic`Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="76a3e-116">`dynamic` keyword</span></span>](reference-types.md#the-dynamic-type)
