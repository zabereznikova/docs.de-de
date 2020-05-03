---
title: 'Enumerationstypen: C#-Referenz'
description: Weitere Informationen zu C#-Enumerationstypen, die eine Auswahl oder eine Kombination aus Auswahlmöglichkeiten darstellen
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 617c5ec037ad7a47b43cca2c13da4a77aa682997
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739093"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="9c8ae-103">Enumerationstypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9c8ae-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="9c8ae-104">Ein *Enumerationstyp* (oder *enum-Typ*) ist ein [Werttyp](value-types.md), der durch eine Reihe benannter Konstanten des zugrunde liegenden [integralen numerischen](integral-numeric-types.md) Typs definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="9c8ae-105">Um einen Enumerationstyp zu definieren, verwenden Sie das `enum`-Schlüsselwort und geben die Namen von *Enumerationsmembern* an:</span><span class="sxs-lookup"><span data-stu-id="9c8ae-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="9c8ae-106">Standardmäßig sind die zugeordneten Konstantenwerte von Enumerationsmembern vom Typ `int`. Sie beginnen mit null und erhöhen sich um eins gemäß der Definitionstextreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="9c8ae-107">Sie können einen beliebigen anderen [integralen numerischen](integral-numeric-types.md) Typ als zugrunde liegenden Typ eines Enumerationstyps explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="9c8ae-108">Sie können auch explizit die zugeordneten Konstantenwerte angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9c8ae-108">You can also explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="9c8ae-109">In der Definition eines Enumerationstyps kann keine Methode definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="9c8ae-110">Zum Hinzufügen von Funktionen zu einem Enumerationstyp erstellen Sie eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="9c8ae-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="9c8ae-111">Der Standardwert eines Enumerationstyps `E` ist der Wert, der vom Ausdruck `(E)0` generiert wird, auch wenn NULL nicht über den entsprechenden Enumerationsmember verfügt.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="9c8ae-112">Sie verwenden einen Enumerationstyp, um eine Auswahl aus einer Reihe von sich gegenseitig ausschließenden Werten oder eine Kombination aus Auswahlmöglichkeiten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="9c8ae-113">Um eine Kombination aus Auswahlmöglichkeiten darzustellen, definieren Sie einen Enumerationstyp als Bitflags.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="9c8ae-114">Enumerationstypen als Bitflags</span><span class="sxs-lookup"><span data-stu-id="9c8ae-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="9c8ae-115">Wenn ein Enumerationstyp eine Kombination aus Auswahlmöglichkeiten darstellen soll, definieren Sie Enumerationsmember für diese Auswahlmöglichkeiten, sodass eine einzelne Auswahl ein Bitfeld ist.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="9c8ae-116">Das heißt, die zugeordneten Werte dieser Enumerationsmember sollten Zweierpotenzen sein.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="9c8ae-117">Anschließend können Sie die [bitweisen logischen Operatoren `|` oder `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) verwenden, um Auswahlmöglichkeiten bzw. Schnittmengen von Auswahlmöglichkeiten zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="9c8ae-118">Um anzugeben, dass ein Enumerationstyp Bitfelder deklariert, wenden Sie das Attribut [Flags](xref:System.FlagsAttribute) darauf an.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="9c8ae-119">Wie im folgenden Beispiel gezeigt, können Sie auch einige typische Kombinationen in die Definition eines Enumerationstyps einschließen.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-119">As the following example shows, you can also include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](snippets/EnumType.cs#Flags)]

<span data-ttu-id="9c8ae-120">Weitere Informationen und Beispiele finden Sie auf der Referenzseite zur <xref:System.FlagsAttribute?displayProperty=nameWithType>-API und im Abschnitt [Nicht exklusive Member und das Flags-Attribut](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) der Referenzseite zur <xref:System.Enum?displayProperty=nameWithType>-API.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="9c8ae-121">Der System.Enum-Typ und die enum-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="9c8ae-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="9c8ae-122">Der <xref:System.Enum?displayProperty=nameWithType>-Typ ist die abstrakte Basisklasse aller Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="9c8ae-123">Er bietet eine Reihe von Methoden, um Informationen zu einem Enumerationstyp und seinen Werten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="9c8ae-124">Weitere Informationen und Beispiele finden Sie auf der Referenzseite zur <xref:System.Enum?displayProperty=nameWithType>-API.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="9c8ae-125">Ab C# 7.3 können Sie `System.Enum` in einer Basisklasseneinschränkung (die als [enum-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints) bezeichnet wird) verwenden, um anzugeben, dass ein Typparameter ein Enumerationstyp ist.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="conversions"></a><span data-ttu-id="9c8ae-126">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="9c8ae-126">Conversions</span></span>

<span data-ttu-id="9c8ae-127">Für jeden Enumerationstyp gibt es explizite Konvertierungen zwischen dem Enumerationstyp und dem zugrunde liegenden integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-127">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="9c8ae-128">Wenn Sie einen Enumerationswert in den zugrunde liegenden Typ [umwandeln](../operators/type-testing-and-cast.md#cast-expression), ist das Ergebnis der zugeordnete integrale Wert eines Enumerationsmembers.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-128">If you [cast](../operators/type-testing-and-cast.md#cast-expression) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](snippets/EnumType.cs#Conversions)]

<span data-ttu-id="9c8ae-129">Verwenden Sie die <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>-Methode, um zu ermitteln, ob ein Enumerationstyp einen Enumerationsmember mit dem bestimmten zugeordneten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-129">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="9c8ae-130">Für jeden Enumerationstyp gibt es [Boxing- und Unboxing](../../programming-guide/types/boxing-and-unboxing.md)-Konvertierungen in bzw. aus dem <xref:System.Enum?displayProperty=nameWithType>-Typ.</span><span class="sxs-lookup"><span data-stu-id="9c8ae-130">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9c8ae-131">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="9c8ae-131">C# language specification</span></span>

<span data-ttu-id="9c8ae-132">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="9c8ae-132">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="9c8ae-133">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9c8ae-133">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="9c8ae-134">Enum values and operations (Enumerationswerte und -vorgänge)</span><span class="sxs-lookup"><span data-stu-id="9c8ae-134">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [<span data-ttu-id="9c8ae-135">Logische Enumerationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9c8ae-135">Enumeration logical operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [<span data-ttu-id="9c8ae-136">Enumerationsvergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="9c8ae-136">Enumeration comparison operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [<span data-ttu-id="9c8ae-137">Explizite Enumerationskonvertierungen</span><span class="sxs-lookup"><span data-stu-id="9c8ae-137">Explicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [<span data-ttu-id="9c8ae-138">Implizite Enumerationskonvertierungen</span><span class="sxs-lookup"><span data-stu-id="9c8ae-138">Implicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a><span data-ttu-id="9c8ae-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c8ae-139">See also</span></span>

- [<span data-ttu-id="9c8ae-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9c8ae-140">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9c8ae-141">Enumerationsformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9c8ae-141">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="9c8ae-142">Entwurfsrichtlinien: Enumerationsentwurf</span><span class="sxs-lookup"><span data-stu-id="9c8ae-142">Design guidelines - Enum design</span></span>](../../../standard/design-guidelines/enum.md)
- [<span data-ttu-id="9c8ae-143">Entwurfsrichtlinien: Namenskonventionen für Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9c8ae-143">Design guidelines - Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="9c8ae-144">switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9c8ae-144">switch statement</span></span>](../keywords/switch.md)
