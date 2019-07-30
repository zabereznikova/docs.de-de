---
title: Enumerationen
description: Erfahren Sie, wie F# Sie anstelle von literalen Enumerationen verwenden, um den Code besser lesbar und verwallegbar zu machen.
ms.date: 05/16/2016
ms.openlocfilehash: 784cd9612b199e4648bb64432d3b4422ad35f649
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630337"
---
# <a name="enumerations"></a><span data-ttu-id="0b869-103">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="0b869-103">Enumerations</span></span>

<span data-ttu-id="0b869-104">*Enumerationen*, die *auch als*Enumerationen bezeichnet werden, sind ganzzahlige Typen, bei denen Bezeichnungen einer Teilmenge der Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0b869-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="0b869-105">Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.</span><span class="sxs-lookup"><span data-stu-id="0b869-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b869-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b869-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="0b869-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b869-107">Remarks</span></span>

<span data-ttu-id="0b869-108">Eine Enumeration sieht in etwa wie eine Unterscheidungs-Union mit einfachen Werten aus, mit dem Unterschied, dass die Werte angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="0b869-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="0b869-109">Bei den Werten handelt es sich in der Regel um ganze Zahlen, die bei 0 oder 1 beginnen, oder ganze Zahlen, die Bitpositionen darstellen.</span><span class="sxs-lookup"><span data-stu-id="0b869-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="0b869-110">Wenn eine Enumeration Bitpositionen darstellen soll, sollten Sie auch das [Flags](xref:System.FlagsAttribute) -Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b869-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="0b869-111">Der zugrunde liegende Typ der Enumeration wird vom verwendeten Literaltyp bestimmt, sodass Sie z. b. Literale mit einem Suffix, z `1u`. b., `2u`usw., für einen ganzzahligen ganzzahligen Typ (`uint32`) verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0b869-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="0b869-112">Wenn Sie auf die benannten Werte verweisen, müssen Sie den Namen des Enumerationstyps selbst als Qualifizierer verwenden, `enum-name.value1`d. h., nicht nur. `value1`</span><span class="sxs-lookup"><span data-stu-id="0b869-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="0b869-113">Dieses Verhalten unterscheidet sich von der Unterscheidungs-Unions.</span><span class="sxs-lookup"><span data-stu-id="0b869-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="0b869-114">Dies liegt daran, dass Enumerationen immer das Attribut "Requirements [qualifiedaccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) " aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0b869-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="0b869-115">Der folgende Code zeigt die Deklaration und Verwendung einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b869-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="0b869-116">Sie können Enumerationen problemlos in den zugrunde liegenden Typ konvertieren, indem Sie den entsprechenden-Operator verwenden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b869-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="0b869-117">Enumerierte Typen können einen der folgenden zugrunde liegenden Typen aufweisen `sbyte`: `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, und `char`.</span><span class="sxs-lookup"><span data-stu-id="0b869-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="0b869-118">Enumerationstypen werden in der .NET Framework als Typen dargestellt, die `System.Enum`von geerbt werden, die wiederum von `System.ValueType`geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="0b869-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="0b869-119">Daher handelt es sich um Werttypen, die sich auf dem Stapel oder Inline im enthaltenden Objekt befinden, und jeder Wert des zugrunde liegenden Typs ist ein gültiger Wert der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0b869-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="0b869-120">Dies ist bei einem Muster Vergleich für Enumerationswerte von Bedeutung, da Sie ein Muster angeben müssen, das die unbenannten Werte abfängt.</span><span class="sxs-lookup"><span data-stu-id="0b869-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="0b869-121">Die `enum` -Funktion in F# der-Bibliothek kann verwendet werden, um einen Enumerationswert zu generieren, sogar einen anderen Wert als einen der vordefinierten benannten Werte.</span><span class="sxs-lookup"><span data-stu-id="0b869-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="0b869-122">Sie verwenden die `enum` -Funktion wie folgt.</span><span class="sxs-lookup"><span data-stu-id="0b869-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="0b869-123">Die Standard `enum` Funktion funktioniert mit dem `int32`-Typ.</span><span class="sxs-lookup"><span data-stu-id="0b869-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="0b869-124">Daher kann Sie nicht mit Enumerationstypen verwendet werden, die andere zugrunde liegende Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0b869-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="0b869-125">Verwenden Sie stattdessen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0b869-125">Instead, use the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="0b869-126">Außerdem werden Fälle für-Aufgaben immer als `public`ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b869-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="0b869-127">Dies ist so, dass Sie sich C# an und dem Rest der .NET-Plattform orientieren.</span><span class="sxs-lookup"><span data-stu-id="0b869-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b869-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b869-128">See also</span></span>

- [<span data-ttu-id="0b869-129">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="0b869-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0b869-130">Umwandlung und Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0b869-130">Casting and Conversions</span></span>](casting-and-conversions.md)
