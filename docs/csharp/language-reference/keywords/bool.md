---
title: Schlüsselwort „bool“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 2041182dffa0330ea601b30e047c0b09731618f2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042399"
---
# <a name="bool-c-reference"></a><span data-ttu-id="dae1f-102">bool (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dae1f-102">bool (C# Reference)</span></span>

<span data-ttu-id="dae1f-103">Das Schlüsselwort `bool` ist ein Alias von <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dae1f-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dae1f-104">Es wird zur Deklaration von Variablen zur Speicherung der booleschen Werte [TRUE](../../../csharp/language-reference/keywords/true.md) und [FALSE](../../../csharp/language-reference/keywords/false.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="dae1f-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dae1f-105">Wenn Sie einen booleschen Wert benötigen, der auch einen Wert von `null` aufweisen kann, verwenden Sie `bool?`.</span><span class="sxs-lookup"><span data-stu-id="dae1f-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="dae1f-106">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="dae1f-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>

## <a name="literals"></a><span data-ttu-id="dae1f-107">Literale</span><span class="sxs-lookup"><span data-stu-id="dae1f-107">Literals</span></span>

<span data-ttu-id="dae1f-108">Sie können einer `bool`-Variablen einen booleschen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="dae1f-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="dae1f-109">Sie können außerdem einer `bool`-Variablen einen Ausdruck, der `bool` ergibt, zuweisen.</span><span class="sxs-lookup"><span data-stu-id="dae1f-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="dae1f-110">Der Standardwert einer `bool`-Variablen ist `false`.</span><span class="sxs-lookup"><span data-stu-id="dae1f-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="dae1f-111">Der Standardwert einer `bool?`-Variablen ist `null`.</span><span class="sxs-lookup"><span data-stu-id="dae1f-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="dae1f-112">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dae1f-112">Conversions</span></span>

<span data-ttu-id="dae1f-113">Der Wert des Typs `bool` kann in C++ in einen Wert des Typs `int` konvertiert werden, d.h. `false` entspricht null und `true` entspricht einem Wert ungleich null.</span><span class="sxs-lookup"><span data-stu-id="dae1f-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="dae1f-114">In C# gibt es keine Konvertierung von Typ `bool` und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="dae1f-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="dae1f-115">Beispielsweise ist die folgende `if`-Anweisung in C# unzulässig:</span><span class="sxs-lookup"><span data-stu-id="dae1f-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="dae1f-116">Um eine Variable des Typs `int` zu testen, müssen Sie sie explizit mit einem Wert, wie z.B. null, vergleichen:</span><span class="sxs-lookup"><span data-stu-id="dae1f-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="dae1f-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dae1f-117">Example</span></span>

<span data-ttu-id="dae1f-118">In diesem Beispiel geben Sie ein Zeichen über die Tastatur ein, und das Programm prüft, ob es sich bei dem eingegebene Zeichen um einen Buchstaben handelt.</span><span class="sxs-lookup"><span data-stu-id="dae1f-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="dae1f-119">Wenn es sich um einen Buchstaben handelt, wird geprüft, ob er groß oder klein geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="dae1f-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="dae1f-120">Dies wird mit <xref:System.Char.IsLetter%2A> und <xref:System.Char.IsLower%2A> geprüft, die beiden den Typ `bool` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="dae1f-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="dae1f-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="dae1f-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dae1f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dae1f-122">See also</span></span>

- [<span data-ttu-id="dae1f-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dae1f-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="dae1f-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dae1f-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="dae1f-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dae1f-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="dae1f-126">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="dae1f-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="dae1f-127">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="dae1f-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="dae1f-128">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dae1f-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="dae1f-129">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dae1f-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  