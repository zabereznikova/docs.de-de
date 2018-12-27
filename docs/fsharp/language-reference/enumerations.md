---
title: Enumerationen
description: Erfahren Sie, wie Sie mit F# Enumerationen anstelle von Literalen, um den Code besser lesbar und verwaltbar zu gestalten.
ms.date: 05/16/2016
ms.openlocfilehash: a8839b73de074f62606b70ffe969a53b3db753bf
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611730"
---
# <a name="enumerations"></a><span data-ttu-id="d6e41-103">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d6e41-103">Enumerations</span></span>

<span data-ttu-id="d6e41-104">*Enumerationen*, auch bekannt als *Enumerationen*, integrale Typen sind, in dem Bezeichnungen auf eine Teilmenge der Werte zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d6e41-104">*Enumerations*, also known as *enums*, , are integral types where labels are assigned to a subset of the values.</span></span> <span data-ttu-id="d6e41-105">Sie können diese anstelle von Literalen verwenden, um Code lesbarer und verwaltbarer zu machen.</span><span class="sxs-lookup"><span data-stu-id="d6e41-105">You can use them in place of literals to make code more readable and maintainable.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6e41-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6e41-106">Syntax</span></span>

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a><span data-ttu-id="d6e41-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6e41-107">Remarks</span></span>

<span data-ttu-id="d6e41-108">Eine Enumeration sieht ähnlich wie eine Unterscheidungs-Union, die einfache Werte, mit dem Unterschied, dass die Werte angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="d6e41-108">An enumeration looks much like a discriminated union that has simple values, except that the values can be specified.</span></span> <span data-ttu-id="d6e41-109">Die Werte sind in der Regel an ganzen Zahlen, die mit 0 oder 1 beginnen, oder ganze Zahlen, die Bitpositionen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d6e41-109">The values are typically integers that start at 0 or 1, or integers that represent bit positions.</span></span> <span data-ttu-id="d6e41-110">Wenn eine Enumeration Bitpositionen darstellen soll, verwenden Sie auch die [Flags](xref:System.FlagsAttribute) Attribut.</span><span class="sxs-lookup"><span data-stu-id="d6e41-110">If an enumeration is intended to represent bit positions, you should also use the [Flags](xref:System.FlagsAttribute) attribute.</span></span>

<span data-ttu-id="d6e41-111">Der zugrunde liegende Typ der Enumeration wird durch das Literal, das verwendet wird, bestimmt, sodass z. B. Sie z. B. Literale mit Suffix verwenden können `1u`, `2u`usw., für die ganze Zahl ohne Vorzeichen (`uint32`) Typ.</span><span class="sxs-lookup"><span data-stu-id="d6e41-111">The underlying type of the enumeration is determined from the literal that is used, so that, for example, you can use literals with a suffix, such as `1u`, `2u`, and so on, for an unsigned integer (`uint32`) type.</span></span>

<span data-ttu-id="d6e41-112">Wenn Sie auf die benannten Werte verweisen, müssen Sie die Namen verwenden des Enumerationstyps selbst als Qualifizierer, d. h. `enum-name.value1`und nicht nur `value1`.</span><span class="sxs-lookup"><span data-stu-id="d6e41-112">When you refer to the named values, you must use the name of the enumeration type itself as a qualifier, that is, `enum-name.value1`, not just `value1`.</span></span> <span data-ttu-id="d6e41-113">Dieses Verhalten unterscheidet sich von der Unterscheidungs-Unions.</span><span class="sxs-lookup"><span data-stu-id="d6e41-113">This behavior differs from that of discriminated unions.</span></span> <span data-ttu-id="d6e41-114">Dies ist, da-Enumerationen verfügen immer über die [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) Attribut.</span><span class="sxs-lookup"><span data-stu-id="d6e41-114">This is because enumerations always have the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute.</span></span>

<span data-ttu-id="d6e41-115">Der folgende Code zeigt die Deklaration und Verwendung einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d6e41-115">The following code shows the declaration and use of an enumeration.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

<span data-ttu-id="d6e41-116">Sie können problemlos Enumerationen in den zugrunde liegenden Typ konvertieren mit den geeigneten Operator an, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6e41-116">You can easily convert enumerations to the underlying type by using the appropriate operator, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

<span data-ttu-id="d6e41-117">Aufgelistete Typen können einen der folgenden zugrunde liegende Typen aufweisen: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, und `char`.</span><span class="sxs-lookup"><span data-stu-id="d6e41-117">Enumerated types can have one of the following underlying types: `sbyte`, `byte`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint16`, `uint64`, and `char`.</span></span> <span data-ttu-id="d6e41-118">Enumerationstypen werden in .NET Framework dargestellt, wie Typen, die von übernommenen `System.Enum`, die wiederum von geerbt `System.ValueType`.</span><span class="sxs-lookup"><span data-stu-id="d6e41-118">Enumeration types are represented in the .NET Framework as types that are inherited from `System.Enum`, which in turn is inherited from `System.ValueType`.</span></span> <span data-ttu-id="d6e41-119">Daher sind sie Werttypen, die auf dem Stapel oder Inline in dem Objekt gespeichert sind, und jeder Wert des zugrunde liegenden Typs ist, einen gültigen Wert der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="d6e41-119">Thus, they are value types that are located on the stack or inline in the containing object, and any value of the underlying type is a valid value of the enumeration.</span></span> <span data-ttu-id="d6e41-120">Dies ist wichtig, beim Musterabgleich für Enumeration Werte, denn Sie müssen ein Muster bereit, die die unbenannte Werte abfängt.</span><span class="sxs-lookup"><span data-stu-id="d6e41-120">This is significant when pattern matching on enumeration values, because you have to provide a pattern that catches the unnamed values.</span></span>

<span data-ttu-id="d6e41-121">Die `enum` Funktion in der F# Bibliothek kann verwendet werden, generieren Sie einen Enumerationswert, der auch einen anderen Wert als eine der vordefinierten, benannte Werte.</span><span class="sxs-lookup"><span data-stu-id="d6e41-121">The `enum` function in the F# library can be used to generate an enumeration value, even a value other than one of the predefined, named values.</span></span> <span data-ttu-id="d6e41-122">Sie verwenden die `enum` -Funktion wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d6e41-122">You use the `enum` function as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

<span data-ttu-id="d6e41-123">Der Standardwert `enum` Funktion arbeitet mit dem Typ `int32`.</span><span class="sxs-lookup"><span data-stu-id="d6e41-123">The default `enum` function works with type `int32`.</span></span> <span data-ttu-id="d6e41-124">Es kann nicht aus diesem Grund mit Enumerationstypen verwendet werden, die andere zugrunde liegende Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d6e41-124">Therefore, it cannot be used with enumeration types that have other underlying types.</span></span> <span data-ttu-id="d6e41-125">Verwenden Sie stattdessen die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="d6e41-125">Instead, use the following.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

<span data-ttu-id="d6e41-126">Darüber hinaus Fällen für Enumerationen immer als ausgegeben werden `public`.</span><span class="sxs-lookup"><span data-stu-id="d6e41-126">Additionally, cases for enums are always emitted as `public`.</span></span> <span data-ttu-id="d6e41-127">Dies ist so, dass sie mit c# und den Rest der .NET-Plattform ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="d6e41-127">This is so that they align with C# and the rest of the .NET platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6e41-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6e41-128">See also</span></span>

- [<span data-ttu-id="d6e41-129">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d6e41-129">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="d6e41-130">Umwandlung und Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d6e41-130">Casting and Conversions</span></span>](casting-and-conversions.md)