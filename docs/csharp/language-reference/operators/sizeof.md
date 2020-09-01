---
description: 'sizeof-Operator: C#-Verweis'
title: 'sizeof-Operator: C#-Verweis'
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: f1358cbfb6cbc2942cef12e650f7bd362ba37a78
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136875"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="eee65-103">sizeof-Operator (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="eee65-103">sizeof operator (C# reference)</span></span>

<span data-ttu-id="eee65-104">Der `sizeof`-Operator gibt die Anzahl der Bytes zurück, die von einer Variablen eines bestimmten Typs belegt werden.</span><span class="sxs-lookup"><span data-stu-id="eee65-104">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="eee65-105">Das Argument für den `sizeof`-Operator muss der Name eines [nicht verwalteten Typs](../builtin-types/unmanaged-types.md) oder eines Typparameters sein, der darauf [beschränkt](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) ist, ein nicht verwalteter Typ zu sein.</span><span class="sxs-lookup"><span data-stu-id="eee65-105">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="eee65-106">Der `sizeof`-Operator erfordert einen [unsicheren](../keywords/unsafe.md) Kontext.</span><span class="sxs-lookup"><span data-stu-id="eee65-106">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="eee65-107">Die in der folgenden Tabelle dargestellten Ausdrücke werden jedoch in der Kompilierzeit auf die entsprechenden konstanten Werte ausgewertet und erfordern keinen unsicheren Kontext:</span><span class="sxs-lookup"><span data-stu-id="eee65-107">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="eee65-108">expression</span><span class="sxs-lookup"><span data-stu-id="eee65-108">Expression</span></span>|<span data-ttu-id="eee65-109">Konstanter Wert</span><span class="sxs-lookup"><span data-stu-id="eee65-109">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="eee65-110">1</span><span class="sxs-lookup"><span data-stu-id="eee65-110">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="eee65-111">1</span><span class="sxs-lookup"><span data-stu-id="eee65-111">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="eee65-112">2</span><span class="sxs-lookup"><span data-stu-id="eee65-112">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="eee65-113">2</span><span class="sxs-lookup"><span data-stu-id="eee65-113">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="eee65-114">4</span><span class="sxs-lookup"><span data-stu-id="eee65-114">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="eee65-115">4</span><span class="sxs-lookup"><span data-stu-id="eee65-115">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="eee65-116">8</span><span class="sxs-lookup"><span data-stu-id="eee65-116">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="eee65-117">8</span><span class="sxs-lookup"><span data-stu-id="eee65-117">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="eee65-118">2</span><span class="sxs-lookup"><span data-stu-id="eee65-118">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="eee65-119">4</span><span class="sxs-lookup"><span data-stu-id="eee65-119">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="eee65-120">8</span><span class="sxs-lookup"><span data-stu-id="eee65-120">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="eee65-121">16</span><span class="sxs-lookup"><span data-stu-id="eee65-121">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="eee65-122">1</span><span class="sxs-lookup"><span data-stu-id="eee65-122">1</span></span>|

<span data-ttu-id="eee65-123">Sie müssen auch keinen unsicheren Kontext verwenden, wenn der Operand des `sizeof`-Operators der Name eines [Enumerationstyps](../builtin-types/enum.md) ist.</span><span class="sxs-lookup"><span data-stu-id="eee65-123">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../builtin-types/enum.md) type.</span></span>

<span data-ttu-id="eee65-124">Im folgenden Beispiel wird die Verwendung des `sizeof`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="eee65-124">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](snippets/shared/SizeOfOperator.cs)]

<span data-ttu-id="eee65-125">Der `sizeof`-Operator gibt die Anzahl der Bytes zurück, die von der Common Language Runtime im verwalteten Speicher belegt werden.</span><span class="sxs-lookup"><span data-stu-id="eee65-125">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="eee65-126">Wie im vorherigen Beispiel veranschaulicht, enthält dieser Wert für [Strukturtypen](../builtin-types/struct.md) alle Auffüllzeichen.</span><span class="sxs-lookup"><span data-stu-id="eee65-126">For [struct](../builtin-types/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="eee65-127">Das Ergebnis des `sizeof`-Operators unterscheidet sich möglicherweise von dem Ergebnis der <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>-Methode, die die Größe eines Typs in *nicht verwaltetem* Speicher zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="eee65-127">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="eee65-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="eee65-128">C# language specification</span></span>

<span data-ttu-id="eee65-129">Weitere Informationen finden Sie im Abschnitt [Der sizeof-Operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="eee65-129">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eee65-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eee65-130">See also</span></span>

- [<span data-ttu-id="eee65-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="eee65-131">C# reference</span></span>](../index.md)
- [<span data-ttu-id="eee65-132">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="eee65-132">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="eee65-133">Operatoren im Zusammenhang mit Zeigern</span><span class="sxs-lookup"><span data-stu-id="eee65-133">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="eee65-134">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="eee65-134">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="eee65-135">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="eee65-135">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="eee65-136">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="eee65-136">Generics in .NET</span></span>](../../../standard/generics/index.md)
