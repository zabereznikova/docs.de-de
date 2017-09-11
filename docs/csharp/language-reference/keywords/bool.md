---
title: bool (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- bool_CSharpKeyword
- bool
dev_langs:
- CSharp
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f3b7455ab6b0ec780afe7d81b2ff990d47a31d20
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="bool-c-reference"></a><span data-ttu-id="45c55-102">bool (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="45c55-102">bool (C# Reference)</span></span>
<span data-ttu-id="45c55-103">Das Schlüsselwort `bool` ist ein Alias von <xref:System.Boolean?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="45c55-103">The `bool` keyword is an alias of <xref:System.Boolean?displayProperty=fullName>.</span></span> <span data-ttu-id="45c55-104">Es wird zur Deklaration von Variablen zur Speicherung der booleschen Werte [TRUE](../../../csharp/language-reference/keywords/true.md) und [FALSE](../../../csharp/language-reference/keywords/false.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="45c55-104">It is used to declare variables to store the Boolean values, [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45c55-105">Wenn Sie einen booleschen Wert benötigen, der auch einen Wert von `null` aufweisen kann, verwenden Sie `bool?`.</span><span class="sxs-lookup"><span data-stu-id="45c55-105">If you require a Boolean variable that can also have a value of `null`, use `bool?`.</span></span> <span data-ttu-id="45c55-106">Weitere Informationen finden Sie unter [Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="45c55-106">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
## <a name="literals"></a><span data-ttu-id="45c55-107">Literale</span><span class="sxs-lookup"><span data-stu-id="45c55-107">Literals</span></span>  
 <span data-ttu-id="45c55-108">Sie können einer `bool`-Variablen einen booleschen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="45c55-108">You can assign a Boolean value to a `bool` variable.</span></span> <span data-ttu-id="45c55-109">Sie können außerdem einer `bool`-Variablen einen Ausdruck, der `bool` ergibt, zuweisen.</span><span class="sxs-lookup"><span data-stu-id="45c55-109">You can also assign an expression that evaluates to `bool` to a `bool` variable.</span></span>  
  
 <span data-ttu-id="45c55-110">[!code-cs[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="45c55-110">[!code-cs[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]</span></span>  
  
 <span data-ttu-id="45c55-111">Der Standardwert einer `bool`-Variablen ist `false`.</span><span class="sxs-lookup"><span data-stu-id="45c55-111">The default value of a `bool` variable is `false`.</span></span> <span data-ttu-id="45c55-112">Der Standardwert einer `bool?`-Variablen ist `null`.</span><span class="sxs-lookup"><span data-stu-id="45c55-112">The default value of a `bool?` variable is `null`.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="45c55-113">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="45c55-113">Conversions</span></span>  
 <span data-ttu-id="45c55-114">Der Wert des Typs `bool` kann in C++ in einen Wert des Typs `int` konvertiert werden, d.h. `false` entspricht null und `true` entspricht einem Wert ungleich null.</span><span class="sxs-lookup"><span data-stu-id="45c55-114">In C++, a value of type `bool` can be converted to a value of type `int`; in other words, `false` is equivalent to zero and `true` is equivalent to nonzero values.</span></span> <span data-ttu-id="45c55-115">In C# gibt es keine Konvertierung von Typ `bool` und anderen Typen.</span><span class="sxs-lookup"><span data-stu-id="45c55-115">In C#, there is no conversion between the `bool` type and other types.</span></span> <span data-ttu-id="45c55-116">Beispielsweise ist die folgende `if`-Anweisung in C# unzulässig:</span><span class="sxs-lookup"><span data-stu-id="45c55-116">For example, the following `if` statement is invalid in C#:</span></span>  
  
 <span data-ttu-id="45c55-117">[!code-cs[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="45c55-117">[!code-cs[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]</span></span>  
  
 <span data-ttu-id="45c55-118">Um eine Variable des Typs `int` zu testen, müssen Sie sie explizit mit einem Wert, wie z.B. null, vergleichen:</span><span class="sxs-lookup"><span data-stu-id="45c55-118">To test a variable of the type `int`, you have to explicitly compare it to a value, such as zero, as follows:</span></span>  
  
 <span data-ttu-id="45c55-119">[!code-cs[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="45c55-119">[!code-cs[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="45c55-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45c55-120">Example</span></span>  
 <span data-ttu-id="45c55-121">In diesem Beispiel geben Sie ein Zeichen über die Tastatur ein, und das Programm prüft, ob es sich bei dem eingegebene Zeichen um einen Buchstaben handelt.</span><span class="sxs-lookup"><span data-stu-id="45c55-121">In this example, you enter a character from the keyboard and the program checks if the input character is a letter.</span></span> <span data-ttu-id="45c55-122">Wenn es sich um einen Buchstaben handelt, wird geprüft, ob er groß oder klein geschrieben ist.</span><span class="sxs-lookup"><span data-stu-id="45c55-122">If it is a letter, it checks if it is lowercase or uppercase.</span></span> <span data-ttu-id="45c55-123">Dies wird mit <xref:System.Char.IsLetter%2A> und <xref:System.Char.IsLower%2A> geprüft, die beiden den Typ `bool` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="45c55-123">These checks are performed with the <xref:System.Char.IsLetter%2A>, and <xref:System.Char.IsLower%2A>, both of which return the `bool` type:</span></span>  
  
 <span data-ttu-id="45c55-124">[!code-cs[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="45c55-124">[!code-cs[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="45c55-125">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="45c55-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45c55-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45c55-126">See Also</span></span>  
 <span data-ttu-id="45c55-127">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="45c55-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="45c55-128">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="45c55-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="45c55-129">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="45c55-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="45c55-130">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="45c55-130">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="45c55-131">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="45c55-131">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="45c55-132">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="45c55-132">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="45c55-133">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="45c55-133">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

