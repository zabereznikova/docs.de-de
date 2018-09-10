---
title: Schlüsselwort „const“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: f586b6d097a8592fd74e92df7886b519d623e478
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513383"
---
# <a name="const-c-reference"></a><span data-ttu-id="b3ec7-102">const (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b3ec7-102">const (C# Reference)</span></span>

<span data-ttu-id="b3ec7-103">Sie verwenden das `const`-Schlüsselwort, um ein konstantes Feld oder eine konstante lokale Variable zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="b3ec7-104">Konstante Felder und lokale Felder sind keine Variablen und können daher nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="b3ec7-105">Konstanten können Nummern, boolesche Werte, Zeichenfolgen oder ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="b3ec7-106">Erstellen Sie keine Konstante, um Informationen darzustellen, von denen Sie ausgehen, dass sie sich einmal ändern.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="b3ec7-107">Verwenden Sie beispielsweise kein konstantes Feld, um den Preis einer Dienstleistung, einer Produktversionsnummer oder den Markennamen eines Unternehmens zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="b3ec7-108">Diese Werte können sich im Laufe der Zeit ändern, und da Compiler Konstanten weitergeben, muss anderer Code, der mit Ihren Bibliotheken kompiliert wird, neu kompiliert werden, damit die Änderungen sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="b3ec7-109">Weitere Informationen finden Sie auch unter dem [readonly](../../../csharp/language-reference/keywords/readonly.md)-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-109">See also the [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword.</span></span> <span data-ttu-id="b3ec7-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b3ec7-110">For example:</span></span>

```csharp
const int x = 0;
public const double gravitationalConstant = 6.673e-11;
private const string productName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="b3ec7-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3ec7-111">Remarks</span></span>

<span data-ttu-id="b3ec7-112">Der Typ einer Konstantendeklaration gibt den Typ der Member an, die durch die Deklaration eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="b3ec7-113">Der Initialisierer einer konstanten lokalen Variable oder eines konstanten Felds muss ein konstanter Ausdruck sein, der implizit in den Zieltyp konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="b3ec7-114">Ein konstanter Ausdruck ist ein Ausdruck, der während der Kompilierung vollständig ausgewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="b3ec7-115">Daher sind `string` und ein NULL-Verweis die einzig möglichen Werte für Verweistypkonstanten.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="b3ec7-116">In der Konstantendeklaration können mehrere Konstanten deklariert werden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="b3ec7-116">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double x = 1.0, y = 2.0, z = 3.0;
```

<span data-ttu-id="b3ec7-117">Der `static`-Modifizierer ist in einer Konstantendeklaration nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-117">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="b3ec7-118">Eine Konstante kann wie folgt einen Teil eines konstanten Ausdrucks darstellen:</span><span class="sxs-lookup"><span data-stu-id="b3ec7-118">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int c1 = 5;
public const int c2 = c1 + 100;
```

> [!NOTE]
> <span data-ttu-id="b3ec7-119">Das [readonly](../../../csharp/language-reference/keywords/readonly.md)-Schlüsselwort unterscheidet sich vom `const`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-119">The [readonly](../../../csharp/language-reference/keywords/readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="b3ec7-120">Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="b3ec7-121">Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="b3ec7-122">Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="b3ec7-123">Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld für Laufzeitkonstanten verwendet werden kann, wie in der folgenden Codezeile: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="b3ec7-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3ec7-124">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="b3ec7-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3ec7-125">Example</span></span>

<span data-ttu-id="b3ec7-126">In diesem Beispiel wird das Verwenden von Konstanten als lokale Variablen demonstriert.</span><span class="sxs-lookup"><span data-stu-id="b3ec7-126">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="b3ec7-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b3ec7-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b3ec7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3ec7-128">See also</span></span>

- [<span data-ttu-id="b3ec7-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b3ec7-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b3ec7-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b3ec7-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b3ec7-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b3ec7-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="b3ec7-132">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="b3ec7-132">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="b3ec7-133">readonly</span><span class="sxs-lookup"><span data-stu-id="b3ec7-133">readonly</span></span>](../../../csharp/language-reference/keywords/readonly.md)
