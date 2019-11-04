---
title: 'sizeof-Operator: C#-Verweis'
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 32103043d4c3a8b38f4c8aad80282f6c0555719f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73038942"
---
# <a name="sizeof-operator-c-reference"></a><span data-ttu-id="17b1f-102">sizeof-Operator (C#-Verweis)</span><span class="sxs-lookup"><span data-stu-id="17b1f-102">sizeof operator (C# reference)</span></span>

<span data-ttu-id="17b1f-103">Der `sizeof`-Operator gibt die Anzahl der Bytes zurück, die von einer Variablen eines bestimmten Typs belegt werden.</span><span class="sxs-lookup"><span data-stu-id="17b1f-103">The `sizeof` operator returns the number of bytes occupied by a variable of a given type.</span></span> <span data-ttu-id="17b1f-104">Das Argument für den `sizeof`-Operator muss der Name eines [nicht verwalteten Typs](../builtin-types/unmanaged-types.md) oder eines Typparameters sein, der darauf [beschränkt](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) ist, ein nicht verwalteter Typ zu sein.</span><span class="sxs-lookup"><span data-stu-id="17b1f-104">The argument to the `sizeof` operator must be the name of an [unmanaged type](../builtin-types/unmanaged-types.md) or a type parameter that is [constrained](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to be an unmanaged type.</span></span>

<span data-ttu-id="17b1f-105">Der `sizeof`-Operator erfordert einen [unsicheren](../keywords/unsafe.md) Kontext.</span><span class="sxs-lookup"><span data-stu-id="17b1f-105">The `sizeof` operator requires an [unsafe](../keywords/unsafe.md) context.</span></span> <span data-ttu-id="17b1f-106">Die in der folgenden Tabelle dargestellten Ausdrücke werden jedoch in der Kompilierzeit auf die entsprechenden konstanten Werte ausgewertet und erfordern keinen unsicheren Kontext:</span><span class="sxs-lookup"><span data-stu-id="17b1f-106">However, the expressions presented in the following table are evaluated in compile time to the corresponding constant values and don't require an unsafe context:</span></span>

|<span data-ttu-id="17b1f-107">expression</span><span class="sxs-lookup"><span data-stu-id="17b1f-107">Expression</span></span>|<span data-ttu-id="17b1f-108">Konstanter Wert</span><span class="sxs-lookup"><span data-stu-id="17b1f-108">Constant value</span></span>|
|---------|---------------|
|`sizeof(sbyte)`|<span data-ttu-id="17b1f-109">1</span><span class="sxs-lookup"><span data-stu-id="17b1f-109">1</span></span>|
|`sizeof(byte)`|<span data-ttu-id="17b1f-110">1</span><span class="sxs-lookup"><span data-stu-id="17b1f-110">1</span></span>|
|`sizeof(short)`|<span data-ttu-id="17b1f-111">2</span><span class="sxs-lookup"><span data-stu-id="17b1f-111">2</span></span>|
|`sizeof(ushort)`|<span data-ttu-id="17b1f-112">2</span><span class="sxs-lookup"><span data-stu-id="17b1f-112">2</span></span>|
|`sizeof(int)`|<span data-ttu-id="17b1f-113">4</span><span class="sxs-lookup"><span data-stu-id="17b1f-113">4</span></span>|
|`sizeof(uint)`|<span data-ttu-id="17b1f-114">4</span><span class="sxs-lookup"><span data-stu-id="17b1f-114">4</span></span>|
|`sizeof(long)`|<span data-ttu-id="17b1f-115">8</span><span class="sxs-lookup"><span data-stu-id="17b1f-115">8</span></span>|
|`sizeof(ulong)`|<span data-ttu-id="17b1f-116">8</span><span class="sxs-lookup"><span data-stu-id="17b1f-116">8</span></span>|
|`sizeof(char)`|<span data-ttu-id="17b1f-117">2</span><span class="sxs-lookup"><span data-stu-id="17b1f-117">2</span></span>|
|`sizeof(float)`|<span data-ttu-id="17b1f-118">4</span><span class="sxs-lookup"><span data-stu-id="17b1f-118">4</span></span>|
|`sizeof(double)`|<span data-ttu-id="17b1f-119">8</span><span class="sxs-lookup"><span data-stu-id="17b1f-119">8</span></span>|
|`sizeof(decimal)`|<span data-ttu-id="17b1f-120">16</span><span class="sxs-lookup"><span data-stu-id="17b1f-120">16</span></span>|
|`sizeof(bool)`|<span data-ttu-id="17b1f-121">1</span><span class="sxs-lookup"><span data-stu-id="17b1f-121">1</span></span>|

<span data-ttu-id="17b1f-122">Sie müssen auch keinen unsicheren Kontext verwenden, wenn der Operand des `sizeof`-Operators der Name eines [Enumerationstyps](../keywords/enum.md) ist.</span><span class="sxs-lookup"><span data-stu-id="17b1f-122">You also don't need to use an unsafe context when the operand of the `sizeof` operator is the name of an [enum](../keywords/enum.md) type.</span></span>

<span data-ttu-id="17b1f-123">Im folgenden Beispiel wird die Verwendung des `sizeof`-Operators veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="17b1f-123">The following example demonstrates the usage of the `sizeof` operator:</span></span>

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

<span data-ttu-id="17b1f-124">Der `sizeof`-Operator gibt die Anzahl der Bytes zurück, die von der Common Language Runtime im verwalteten Speicher belegt werden.</span><span class="sxs-lookup"><span data-stu-id="17b1f-124">The `sizeof` operator returns a number of bytes that would be allocated by the common language runtime in managed memory.</span></span> <span data-ttu-id="17b1f-125">Wie im vorherigen Beispiel veranschaulicht, enthält dieser Wert für [Strukturtypen](../keywords/struct.md) alle Auffüllzeichen.</span><span class="sxs-lookup"><span data-stu-id="17b1f-125">For [struct](../keywords/struct.md) types, that value includes any padding, as the preceding example demonstrates.</span></span> <span data-ttu-id="17b1f-126">Das Ergebnis des `sizeof`-Operators unterscheidet sich möglicherweise von dem Ergebnis der <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>-Methode, die die Größe eines Typs in *nicht verwaltetem* Speicher zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="17b1f-126">The result of the `sizeof` operator might differ from the result of the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, which returns the size of a type in *unmanaged* memory.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="17b1f-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="17b1f-127">C# language specification</span></span>

<span data-ttu-id="17b1f-128">Weitere Informationen finden Sie im Abschnitt [Der sizeof-Operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="17b1f-128">For more information, see [The sizeof operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17b1f-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17b1f-129">See also</span></span>

- [<span data-ttu-id="17b1f-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="17b1f-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="17b1f-131">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="17b1f-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="17b1f-132">Operatoren im Zusammenhang mit Zeigern</span><span class="sxs-lookup"><span data-stu-id="17b1f-132">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="17b1f-133">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="17b1f-133">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="17b1f-134">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="17b1f-134">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="17b1f-135">Generics in .NET</span><span class="sxs-lookup"><span data-stu-id="17b1f-135">Generics in .NET</span></span>](../../../standard/generics/index.md)
