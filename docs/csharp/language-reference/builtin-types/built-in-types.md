---
title: 'Integrierte Typen: C#-Referenz'
description: Hier erfahren Sie mehr über in C# integrierte Werte und Verweistypen.
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 3366f718cd83a28f475fae9b4e65ce37fe7d8c7b
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803201"
---
# <a name="built-in-types-c-reference"></a><span data-ttu-id="bc7e0-103">Integrierte Typen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bc7e0-103">Built-in types (C# reference)</span></span>

<span data-ttu-id="bc7e0-104">In der folgenden Tabelle werden die in C# integrierten [Werttypen](value-types.md) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="bc7e0-104">The following table lists the C# built-in [value](value-types.md) types:</span></span>

|<span data-ttu-id="bc7e0-105">C#-Typschlüsselwort</span><span class="sxs-lookup"><span data-stu-id="bc7e0-105">C# type keyword</span></span>|<span data-ttu-id="bc7e0-106">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="bc7e0-106">.NET type</span></span>|
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

<span data-ttu-id="bc7e0-107">In der folgenden Tabelle werden die in C# integrierten [Verweistypen](../keywords/reference-types.md) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="bc7e0-107">The following table lists the C# built-in [reference](../keywords/reference-types.md) types:</span></span>

|<span data-ttu-id="bc7e0-108">C#-Typschlüsselwort</span><span class="sxs-lookup"><span data-stu-id="bc7e0-108">C# type keyword</span></span>|<span data-ttu-id="bc7e0-109">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="bc7e0-109">.NET type</span></span>|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|
|[`dynamic`](reference-types.md#the-dynamic-type)|<xref:System.Object?displayProperty=nameWithType>|

<span data-ttu-id="bc7e0-110">In den obigen Tabellen ist jedes C#-Typschlüsselwort aus der linken Spalte ein Alias für den entsprechenden .NET-Typ.</span><span class="sxs-lookup"><span data-stu-id="bc7e0-110">In the preceding tables, each C# type keyword from the left column is an alias for the corresponding .NET type.</span></span> <span data-ttu-id="bc7e0-111">Sie können synonym verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc7e0-111">They are interchangeable.</span></span> <span data-ttu-id="bc7e0-112">In den folgenden Deklarationen werden beispielsweise Variablen des gleichen Typs deklariert:</span><span class="sxs-lookup"><span data-stu-id="bc7e0-112">For example, the following declarations declare variables of the same type:</span></span>

```csharp
int a = 123;
System.Int32 b = 123;
```

<span data-ttu-id="bc7e0-113">Das Schlüsselwort [`void`](void.md) markiert das Fehlen eines Typs.</span><span class="sxs-lookup"><span data-stu-id="bc7e0-113">The [`void`](void.md) keyword represents the absence of a type.</span></span> <span data-ttu-id="bc7e0-114">Sie können es als Rückgabetyp einer Methode verwenden, die keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bc7e0-114">You use it as the return type of a method that doesn't return a value.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc7e0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc7e0-115">See also</span></span>

- [<span data-ttu-id="bc7e0-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bc7e0-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bc7e0-117">Standardwerte der C#-Typen</span><span class="sxs-lookup"><span data-stu-id="bc7e0-117">Default values of C# types</span></span>](default-values.md)
