---
title: bool (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 1045a459491b0d0d6a84c60f6e820297b47efd5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215959"
---
# <a name="bool-c-reference"></a><span data-ttu-id="924d2-102">bool (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="924d2-102">bool (C# Reference)</span></span>
<span data-ttu-id="924d2-103">Das Schlüsselwort `bool` ist ein Alias von <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="924d2-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=nameWithType>.</span></span> <span data-ttu-id="924d2-104">Es wird zur Deklaration von Variablen zur Speicherung der booleschen Werte [TRUE](../../../csharp/language-reference/keywords/true.md) und [FALSE](../../../csharp/language-reference/keywords/false.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="924d2-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="924d2-105">Wenn Sie einen booleschen Wert benötigen, der auch einen Wert von `null` aufweisen kann, verwenden Sie `bool?`.</span><span class="sxs-lookup"><span data-stu-id="924d2-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="924d2-106">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="924d2-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="literals"></a><span data-ttu-id="924d2-107">Literale</span><span class="sxs-lookup"><span data-stu-id="924d2-107">Literals</span></span>  
 <span data-ttu-id="924d2-108">Sie können einer `bool`-Variablen einen booleschen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="924d2-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="924d2-109">Sie können außerdem einer `bool`-Variablen einen Ausdruck, der `bool` ergibt, zuweisen.</span><span class="sxs-lookup"><span data-stu-id="924d2-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 <span data-ttu-id="924d2-110">Der Standardwert einer `bool`-Variablen ist `false`.</span><span class="sxs-lookup"><span data-stu-id="924d2-110">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="924d2-111">Der Standardwert einer `bool?`-Variablen ist `null`.</span><span class="sxs-lookup"><span data-stu-id="924d2-111">The default value of a `bool?` variable is `null`.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="924d2-112">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="924d2-112">Conversions</span></span>  
 <span data-ttu-id="924d2-113">Der Wert des Typs `bool` kann in C++ in einen Wert des Typs `int` konvertiert werden, d.h. `false` entspricht null und `true` entspricht einem Wert ungleich null.</span><span class="sxs-lookup"><span data-stu-id="924d2-113">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="924d2-114">In C# gibt es keine Konvertierung von Typ `bool` und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="924d2-114">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="924d2-115">Beispielsweise ist die folgende `if`-Anweisung in C# unzulässig:</span><span class="sxs-lookup"><span data-stu-id="924d2-115">For example, the following `if` statement is invalid in C#:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 <span data-ttu-id="924d2-116">Um eine Variable des Typs `int` zu testen, müssen Sie sie explizit mit einem Wert, wie z.B. null, vergleichen:</span><span class="sxs-lookup"><span data-stu-id="924d2-116">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="924d2-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="924d2-117">Example</span></span>  
 <span data-ttu-id="924d2-118">In diesem Beispiel geben Sie ein Zeichen über die Tastatur ein, und das Programm prüft, ob es sich bei dem eingegebene Zeichen um einen Buchstaben handelt.</span><span class="sxs-lookup"><span data-stu-id="924d2-118">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="924d2-119">Wenn es sich um einen Buchstaben handelt, wird geprüft, ob er groß oder klein geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="924d2-119">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="924d2-120">Dies wird mit <xref:System.Char.IsLetter%2A> und <xref:System.Char.IsLower%2A> geprüft, die beiden den Typ `bool` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="924d2-120">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="924d2-121">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="924d2-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="924d2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="924d2-122">See Also</span></span>  
 [<span data-ttu-id="924d2-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="924d2-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="924d2-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="924d2-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="924d2-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="924d2-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="924d2-126">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="924d2-126">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="924d2-127">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="924d2-127">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="924d2-128">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="924d2-128">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="924d2-129">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="924d2-129">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
