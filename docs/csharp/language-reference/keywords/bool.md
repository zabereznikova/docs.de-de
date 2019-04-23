---
title: bool-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: d87da29872582e9c0d47a6c999312ce88252a5cc
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59334171"
---
# <a name="bool-c-reference"></a><span data-ttu-id="dc834-102">bool (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="dc834-102">bool (C# Reference)</span></span>

<span data-ttu-id="dc834-103">Das Schlüsselwort `bool` ist ein Alias von <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dc834-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dc834-104">Es wird zur Deklaration von Variablen zur Speicherung der booleschen Werte [TRUE](true-literal.md) und [FALSE](false-literal.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc834-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dc834-105">Verwenden Sie den Typ `bool?`, wenn Sie die dreiwertige Logik unterstützen müssen, z.B. wenn Sie mit Datenbanken arbeiten, die einen dreiwertigen booleschen Typ unterstützen.</span><span class="sxs-lookup"><span data-stu-id="dc834-105">Use the `bool?` type, if you need to support the three-valued logic, for example, when you work with databases that support a three-valued Boolean type.</span></span> <span data-ttu-id="dc834-106">Für die `bool?`-Operanden unterstützen die vordefinierten `&`- und `|`-Operatoren die dreiwertige Logik.</span><span class="sxs-lookup"><span data-stu-id="dc834-106">For the `bool?` operands, the predefined `&` and `|` operators support the three-valued logic.</span></span> <span data-ttu-id="dc834-107">Weitere Informationen finden Sie im Abschnitt [Boolesche logische Operatoren, die NULL-Werte zulassen](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) im Artikel [Boolesche logische Operatoren](../operators/boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="dc834-107">For more information, see the [Nullable Boolean logical operators](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](../operators/boolean-logical-operators.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="dc834-108">Literale</span><span class="sxs-lookup"><span data-stu-id="dc834-108">Literals</span></span>

<span data-ttu-id="dc834-109">Sie können einer `bool`-Variablen einen booleschen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="dc834-109">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="dc834-110">Sie können außerdem einer `bool`-Variablen einen Ausdruck, der `bool` ergibt, zuweisen.</span><span class="sxs-lookup"><span data-stu-id="dc834-110">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="dc834-111">Der Standardwert einer `bool`-Variablen ist `false`.</span><span class="sxs-lookup"><span data-stu-id="dc834-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="dc834-112">Der Standardwert einer `bool?`-Variablen ist `null`.</span><span class="sxs-lookup"><span data-stu-id="dc834-112">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="dc834-113">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dc834-113">Conversions</span></span>

<span data-ttu-id="dc834-114">Der Wert des Typs `bool` kann in C++ in einen Wert des Typs `int` konvertiert werden, d.h. `false` entspricht null und `true` entspricht einem Wert ungleich null.</span><span class="sxs-lookup"><span data-stu-id="dc834-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="dc834-115">In C# gibt es keine Konvertierung von Typ `bool` und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="dc834-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="dc834-116">Beispielsweise ist die folgende `if`-Anweisung in C# unzulässig:</span><span class="sxs-lookup"><span data-stu-id="dc834-116">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="dc834-117">Um eine Variable des Typs `int` zu testen, müssen Sie sie explizit mit einem Wert, wie z.B. null, vergleichen:</span><span class="sxs-lookup"><span data-stu-id="dc834-117">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="dc834-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc834-118">Example</span></span>

<span data-ttu-id="dc834-119">In diesem Beispiel geben Sie ein Zeichen über die Tastatur ein, und das Programm prüft, ob es sich bei dem eingegebene Zeichen um einen Buchstaben handelt.</span><span class="sxs-lookup"><span data-stu-id="dc834-119">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="dc834-120">Wenn es sich um einen Buchstaben handelt, wird geprüft, ob er groß oder klein geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="dc834-120">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="dc834-121">Dies wird mit <xref:System.Char.IsLetter%2A> und <xref:System.Char.IsLower%2A> geprüft, die beiden den Typ `bool` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="dc834-121">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="dc834-122">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="dc834-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dc834-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc834-123">See also</span></span>

- [<span data-ttu-id="dc834-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="dc834-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="dc834-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dc834-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="dc834-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="dc834-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="dc834-127">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="dc834-127">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)
- [<span data-ttu-id="dc834-128">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="dc834-128">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [<span data-ttu-id="dc834-129">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dc834-129">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [<span data-ttu-id="dc834-130">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dc834-130">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
