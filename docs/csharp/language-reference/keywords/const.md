---
description: const-Schlüsselwort – C#-Referenz
title: const-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 312725c3a231f0ca766d5b99bf7d9308ddd634c4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142088"
---
# <a name="const-c-reference"></a><span data-ttu-id="264b8-103">const (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="264b8-103">const (C# Reference)</span></span>

<span data-ttu-id="264b8-104">Sie verwenden das `const`-Schlüsselwort, um ein konstantes Feld oder eine konstante lokale Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="264b8-104">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="264b8-105">Konstante Felder und lokale Felder sind keine Variablen und können daher nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="264b8-105">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="264b8-106">Konstanten können Nummern, boolesche Werte, Zeichenfolgen oder ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="264b8-106">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="264b8-107">Erstellen Sie keine Konstante, um Informationen darzustellen, bei denen Sie davon ausgehen, dass sie sich einmal ändern.</span><span class="sxs-lookup"><span data-stu-id="264b8-107">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="264b8-108">Verwenden Sie beispielsweise kein konstantes Feld, um den Preis einer Dienstleistung, einer Produktversionsnummer oder den Markennamen eines Unternehmens zu speichern.</span><span class="sxs-lookup"><span data-stu-id="264b8-108">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="264b8-109">Diese Werte können sich im Laufe der Zeit ändern, und da Compiler Konstanten weitergeben, muss anderer Code, der mit Ihren Bibliotheken kompiliert wird, neu kompiliert werden, damit die Änderungen sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="264b8-109">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="264b8-110">Weitere Informationen finden Sie auch unter dem [readonly](./readonly.md)-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="264b8-110">See also the [readonly](./readonly.md) keyword.</span></span> <span data-ttu-id="264b8-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="264b8-111">For example:</span></span>

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="264b8-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="264b8-112">Remarks</span></span>

<span data-ttu-id="264b8-113">Der Typ einer Konstantendeklaration gibt den Typ der Member an, die durch die Deklaration eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="264b8-113">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="264b8-114">Der Initialisierer einer konstanten lokalen Variable oder eines konstanten Felds muss ein konstanter Ausdruck sein, der implizit in den Zieltyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="264b8-114">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="264b8-115">Ein konstanter Ausdruck ist ein Ausdruck, der während der Kompilierung vollständig ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="264b8-115">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="264b8-116">Daher sind `string` und ein NULL-Verweis die einzig möglichen Werte für Verweistypkonstanten.</span><span class="sxs-lookup"><span data-stu-id="264b8-116">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="264b8-117">In der Konstantendeklaration können mehrere Konstanten deklariert werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="264b8-117">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

<span data-ttu-id="264b8-118">Der `static`-Modifizierer ist in einer Konstantendeklaration nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="264b8-118">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="264b8-119">Eine Konstante kann wie folgt einen Teil eines konstanten Ausdrucks darstellen:</span><span class="sxs-lookup"><span data-stu-id="264b8-119">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> <span data-ttu-id="264b8-120">Das [readonly](./readonly.md)-Schlüsselwort unterscheidet sich vom `const`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="264b8-120">The [readonly](./readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="264b8-121">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="264b8-121">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="264b8-122">Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="264b8-122">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="264b8-123">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="264b8-123">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="264b8-124">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld für Laufzeitkonstanten verwendet werden kann, wie in der folgenden Codezeile: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`.</span><span class="sxs-lookup"><span data-stu-id="264b8-124">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="264b8-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="264b8-125">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="264b8-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="264b8-126">Example</span></span>

<span data-ttu-id="264b8-127">In diesem Beispiel wird das Verwenden von Konstanten als lokale Variablen demonstriert.</span><span class="sxs-lookup"><span data-stu-id="264b8-127">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="264b8-128">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="264b8-128">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="264b8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="264b8-129">See also</span></span>

- [<span data-ttu-id="264b8-130">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="264b8-130">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="264b8-131">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="264b8-131">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="264b8-132">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="264b8-132">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="264b8-133">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="264b8-133">Modifiers</span></span>](index.md)
- [<span data-ttu-id="264b8-134">readonly</span><span class="sxs-lookup"><span data-stu-id="264b8-134">readonly</span></span>](./readonly.md)
