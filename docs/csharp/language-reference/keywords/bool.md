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
ms.openlocfilehash: a274083ad2e518f8f29384e51d692bcf9a9cb61e
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237245"
---
# <a name="bool-c-reference"></a><span data-ttu-id="66b42-102">bool (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="66b42-102">bool (C# Reference)</span></span>

<span data-ttu-id="66b42-103">Das Schlüsselwort `bool` ist ein Alias von <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="66b42-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="66b42-104">Es wird zur Deklaration von Variablen zur Speicherung der booleschen Werte [TRUE](true-literal.md) und [FALSE](false-literal.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="66b42-104">It is used to declare variables to store the Boolean values: [true](true-literal.md) and [false](false-literal.md).</span></span>

> [!NOTE]
> <span data-ttu-id="66b42-105">Wenn Sie einen booleschen Wert benötigen, der auch einen Wert von `null` aufweisen kann, verwenden Sie `bool?`.</span><span class="sxs-lookup"><span data-stu-id="66b42-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="66b42-106">Weitere Informationen finden Sie im Abschnitt [Der „bool?“-Typ](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) im Artikel [Verwenden von Typen mit Nullwert](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="66b42-106">For more information, see [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="literals"></a><span data-ttu-id="66b42-107">Literale</span><span class="sxs-lookup"><span data-stu-id="66b42-107">Literals</span></span>

<span data-ttu-id="66b42-108">Sie können einer `bool`-Variablen einen booleschen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="66b42-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="66b42-109">Sie können außerdem einer `bool`-Variablen einen Ausdruck, der `bool` ergibt, zuweisen.</span><span class="sxs-lookup"><span data-stu-id="66b42-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

<span data-ttu-id="66b42-110">Der Standardwert einer `bool`-Variablen ist `false`.</span><span class="sxs-lookup"><span data-stu-id="66b42-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="66b42-111">Der Standardwert einer `bool?`-Variablen ist `null`.</span><span class="sxs-lookup"><span data-stu-id="66b42-111">The default value of a `bool?` variable is `null`.</span></span>

## <a name="conversions"></a><span data-ttu-id="66b42-112">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="66b42-112">Conversions</span></span>

<span data-ttu-id="66b42-113">Der Wert des Typs `bool` kann in C++ in einen Wert des Typs `int` konvertiert werden, d.h. `false` entspricht null und `true` entspricht einem Wert ungleich null.</span><span class="sxs-lookup"><span data-stu-id="66b42-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="66b42-114">In C# gibt es keine Konvertierung von Typ `bool` und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="66b42-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="66b42-115">Beispielsweise ist die folgende `if`-Anweisung in C# unzulässig:</span><span class="sxs-lookup"><span data-stu-id="66b42-115">For example, the following `if` statement is invalid in C#:</span></span>

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

<span data-ttu-id="66b42-116">Um eine Variable des Typs `int` zu testen, müssen Sie sie explizit mit einem Wert, wie z.B. null, vergleichen:</span><span class="sxs-lookup"><span data-stu-id="66b42-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a><span data-ttu-id="66b42-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66b42-117">Example</span></span>

<span data-ttu-id="66b42-118">In diesem Beispiel geben Sie ein Zeichen über die Tastatur ein, und das Programm prüft, ob es sich bei dem eingegebene Zeichen um einen Buchstaben handelt.</span><span class="sxs-lookup"><span data-stu-id="66b42-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="66b42-119">Wenn es sich um einen Buchstaben handelt, wird geprüft, ob er groß oder klein geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="66b42-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="66b42-120">Dies wird mit <xref:System.Char.IsLetter%2A> und <xref:System.Char.IsLower%2A> geprüft, die beiden den Typ `bool` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="66b42-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="66b42-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="66b42-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="66b42-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66b42-122">See also</span></span>

- [<span data-ttu-id="66b42-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="66b42-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="66b42-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="66b42-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="66b42-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="66b42-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="66b42-126">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="66b42-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
- [<span data-ttu-id="66b42-127">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="66b42-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
- [<span data-ttu-id="66b42-128">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="66b42-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
- [<span data-ttu-id="66b42-129">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="66b42-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  