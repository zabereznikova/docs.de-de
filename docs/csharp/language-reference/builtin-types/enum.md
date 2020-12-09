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
ms.openlocfilehash: a21bdf63247dc5fec95922de017e1d3502e08565
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599433"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="90b8c-103">Enumerationstypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="90b8c-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="90b8c-104">Ein *Enumerationstyp* (oder *enum-Typ*) ist ein [Werttyp](value-types.md), der durch eine Reihe benannter Konstanten des zugrunde liegenden [integralen numerischen](integral-numeric-types.md) Typs definiert wird.</span><span class="sxs-lookup"><span data-stu-id="90b8c-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="90b8c-105">Um einen Enumerationstyp zu definieren, verwenden Sie das `enum`-Schlüsselwort und geben die Namen von *Enumerationsmembern* an:</span><span class="sxs-lookup"><span data-stu-id="90b8c-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="90b8c-106">Standardmäßig sind die zugeordneten Konstantenwerte von Enumerationsmembern vom Typ `int`. Sie beginnen mit null und erhöhen sich um eins gemäß der Definitionstextreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="90b8c-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="90b8c-107">Sie können einen beliebigen anderen [integralen numerischen](integral-numeric-types.md) Typ als zugrunde liegenden Typ eines Enumerationstyps explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="90b8c-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="90b8c-108">Sie können auch explizit die zugeordneten Konstantenwerte angeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="90b8c-108">You can also explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="90b8c-109">In der Definition eines Enumerationstyps kann keine Methode definiert werden.</span><span class="sxs-lookup"><span data-stu-id="90b8c-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="90b8c-110">Zum Hinzufügen von Funktionen zu einem Enumerationstyp erstellen Sie eine [Erweiterungsmethode](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="90b8c-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="90b8c-111">Der Standardwert eines Enumerationstyps `E` ist der Wert, der vom Ausdruck `(E)0` generiert wird, auch wenn NULL nicht über den entsprechenden Enumerationsmember verfügt.</span><span class="sxs-lookup"><span data-stu-id="90b8c-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="90b8c-112">Sie verwenden einen Enumerationstyp, um eine Auswahl aus einer Reihe von sich gegenseitig ausschließenden Werten oder eine Kombination aus Auswahlmöglichkeiten darzustellen.</span><span class="sxs-lookup"><span data-stu-id="90b8c-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="90b8c-113">Um eine Kombination aus Auswahlmöglichkeiten darzustellen, definieren Sie einen Enumerationstyp als Bitflags.</span><span class="sxs-lookup"><span data-stu-id="90b8c-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="90b8c-114">Enumerationstypen als Bitflags</span><span class="sxs-lookup"><span data-stu-id="90b8c-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="90b8c-115">Wenn ein Enumerationstyp eine Kombination aus Auswahlmöglichkeiten darstellen soll, definieren Sie Enumerationsmember für diese Auswahlmöglichkeiten, sodass eine einzelne Auswahl ein Bitfeld ist.</span><span class="sxs-lookup"><span data-stu-id="90b8c-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="90b8c-116">Das heißt, die zugeordneten Werte dieser Enumerationsmember sollten Zweierpotenzen sein.</span><span class="sxs-lookup"><span data-stu-id="90b8c-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="90b8c-117">Anschließend können Sie die [bitweisen logischen Operatoren `|` oder `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) verwenden, um Auswahlmöglichkeiten bzw. Schnittmengen von Auswahlmöglichkeiten zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="90b8c-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="90b8c-118">Um anzugeben, dass ein Enumerationstyp Bitfelder deklariert, wenden Sie das Attribut [Flags](xref:System.FlagsAttribute) darauf an.</span><span class="sxs-lookup"><span data-stu-id="90b8c-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="90b8c-119">Wie im folgenden Beispiel gezeigt, können Sie auch einige typische Kombinationen in die Definition eines Enumerationstyps einschließen.</span><span class="sxs-lookup"><span data-stu-id="90b8c-119">As the following example shows, you can also include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](snippets/shared/EnumType.cs#Flags)]

<span data-ttu-id="90b8c-120">Weitere Informationen und Beispiele finden Sie auf der Referenzseite zur <xref:System.FlagsAttribute?displayProperty=nameWithType>-API und im Abschnitt [Nicht exklusive Member und das Flags-Attribut](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) der Referenzseite zur <xref:System.Enum?displayProperty=nameWithType>-API.</span><span class="sxs-lookup"><span data-stu-id="90b8c-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="90b8c-121">Der System.Enum-Typ und die enum-Einschränkung</span><span class="sxs-lookup"><span data-stu-id="90b8c-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="90b8c-122">Der <xref:System.Enum?displayProperty=nameWithType>-Typ ist die abstrakte Basisklasse aller Enumerationstypen.</span><span class="sxs-lookup"><span data-stu-id="90b8c-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="90b8c-123">Er bietet eine Reihe von Methoden, um Informationen zu einem Enumerationstyp und seinen Werten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="90b8c-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="90b8c-124">Weitere Informationen und Beispiele finden Sie auf der Referenzseite zur <xref:System.Enum?displayProperty=nameWithType>-API.</span><span class="sxs-lookup"><span data-stu-id="90b8c-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="90b8c-125">Ab C# 7.3 können Sie `System.Enum` in einer Basisklasseneinschränkung (die als [enum-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints) bezeichnet wird) verwenden, um anzugeben, dass ein Typparameter ein Enumerationstyp ist.</span><span class="sxs-lookup"><span data-stu-id="90b8c-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span> <span data-ttu-id="90b8c-126">Jeder Enumerationstyp erfüllt auch die `struct`-Einschränkung, die verwendet wird, um anzugeben, dass ein Typparameter ein Non-Nullable-Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="90b8c-126">Any enumeration type also satisfies the `struct` constraint, which is used to specify that a type parameter is a non-nullable value type.</span></span>

## <a name="conversions"></a><span data-ttu-id="90b8c-127">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="90b8c-127">Conversions</span></span>

<span data-ttu-id="90b8c-128">Für jeden Enumerationstyp gibt es explizite Konvertierungen zwischen dem Enumerationstyp und dem zugrunde liegenden integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="90b8c-128">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="90b8c-129">Wenn Sie einen Enumerationswert in den zugrunde liegenden Typ [umwandeln](../operators/type-testing-and-cast.md#cast-expression), ist das Ergebnis der zugeordnete integrale Wert eines Enumerationsmembers.</span><span class="sxs-lookup"><span data-stu-id="90b8c-129">If you [cast](../operators/type-testing-and-cast.md#cast-expression) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](snippets/shared/EnumType.cs#Conversions)]

<span data-ttu-id="90b8c-130">Verwenden Sie die <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>-Methode, um zu ermitteln, ob ein Enumerationstyp einen Enumerationsmember mit dem bestimmten zugeordneten Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="90b8c-130">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="90b8c-131">Für jeden Enumerationstyp gibt es [Boxing- und Unboxing](../../programming-guide/types/boxing-and-unboxing.md)-Konvertierungen in bzw. aus dem <xref:System.Enum?displayProperty=nameWithType>-Typ.</span><span class="sxs-lookup"><span data-stu-id="90b8c-131">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="90b8c-132">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="90b8c-132">C# language specification</span></span>

<span data-ttu-id="90b8c-133">Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="90b8c-133">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="90b8c-134">Enumerationen</span><span class="sxs-lookup"><span data-stu-id="90b8c-134">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="90b8c-135">Enum values and operations (Enumerationswerte und -vorgänge)</span><span class="sxs-lookup"><span data-stu-id="90b8c-135">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [<span data-ttu-id="90b8c-136">Logische Enumerationsoperatoren</span><span class="sxs-lookup"><span data-stu-id="90b8c-136">Enumeration logical operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [<span data-ttu-id="90b8c-137">Enumerationsvergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="90b8c-137">Enumeration comparison operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [<span data-ttu-id="90b8c-138">Explizite Enumerationskonvertierungen</span><span class="sxs-lookup"><span data-stu-id="90b8c-138">Explicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [<span data-ttu-id="90b8c-139">Implizite Enumerationskonvertierungen</span><span class="sxs-lookup"><span data-stu-id="90b8c-139">Implicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a><span data-ttu-id="90b8c-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90b8c-140">See also</span></span>

- [<span data-ttu-id="90b8c-141">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="90b8c-141">C# reference</span></span>](../index.md)
- [<span data-ttu-id="90b8c-142">Enumerationsformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="90b8c-142">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="90b8c-143">Entwurfsrichtlinien: Enumerationsentwurf</span><span class="sxs-lookup"><span data-stu-id="90b8c-143">Design guidelines - Enum design</span></span>](../../../standard/design-guidelines/enum.md)
- [<span data-ttu-id="90b8c-144">Entwurfsrichtlinien: Namenskonventionen für Enumerationen</span><span class="sxs-lookup"><span data-stu-id="90b8c-144">Design guidelines - Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="90b8c-145">switch-Anweisung</span><span class="sxs-lookup"><span data-stu-id="90b8c-145">switch statement</span></span>](../keywords/switch.md)
