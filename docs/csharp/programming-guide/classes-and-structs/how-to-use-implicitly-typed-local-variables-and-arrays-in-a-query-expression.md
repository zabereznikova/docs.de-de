---
title: 'Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- implicitly-typed local variables [C#], how to use
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
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
ms.openlocfilehash: 60e22aacef05ae2fe1b5e7127396cc66f24661d3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression-c-programming-guide"></a><span data-ttu-id="57162-102">Gewusst wie: Verwenden von implizit typisierten lokalen Variablen und Arrays in einem Abfrageausdruck (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="57162-102">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression (C# Programming Guide)</span></span>
<span data-ttu-id="57162-103">Sie können implizit typisierte lokale Variablen immer dann verwenden, wenn Sie möchten, dass der Compiler den Typ einer lokalen Variablen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="57162-103">You can use implicitly typed local variables whenever you want the compiler to determine the type of a local variable.</span></span> <span data-ttu-id="57162-104">Sie müssen implizit typisierte lokale Variablen verwenden, um anonyme Typen zu speichern, die häufig in Abfrageausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57162-104">You must use implicitly typed local variables to store anonymous types, which are often used in query expressions.</span></span> <span data-ttu-id="57162-105">In den folgenden Beispielen werden sowohl optionale als auch erforderliche Einsatzmöglichkeiten von implizit typisierte lokale Variablen in einer Abfrage veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="57162-105">The following examples illustrate both optional and required uses of implicitly typed local variables in queries.</span></span>  
  
 <span data-ttu-id="57162-106">Implizit typisierte lokale Variablen werden mit dem kontextuellen Schlüsselwort [var](../../../csharp/language-reference/keywords/var.md) deklariert.</span><span class="sxs-lookup"><span data-stu-id="57162-106">Implicitly typed local variables are declared by using the [var](../../../csharp/language-reference/keywords/var.md) contextual keyword.</span></span> <span data-ttu-id="57162-107">Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Implizit typisierte Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="57162-107">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57162-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57162-108">Example</span></span>  
 <span data-ttu-id="57162-109">Im folgenden Beispiel wird ein häufiges Szenario gezeigt, in dem das Schlüsselwort `var` erforderlich ist: ein Abfrageausdruck, der eine Folge anonymer Typen erzeugt.</span><span class="sxs-lookup"><span data-stu-id="57162-109">The following example shows a common scenario in which the `var` keyword is required: a query expression that produces a sequence of anonymous types.</span></span> <span data-ttu-id="57162-110">In diesem Szenario müssen sowohl die Abfragevariable als auch die Iterationsvariable in der `foreach`-Anweisung mit `var` implizit typisiert werden, da Sie keinen Zugriff auf einen Typnamen für den anonymen Typ haben.</span><span class="sxs-lookup"><span data-stu-id="57162-110">In this scenario, both the query variable and the iteration variable in the `foreach` statement must be implicitly typed by using `var` because you do not have access to a type name for the anonymous type.</span></span> <span data-ttu-id="57162-111">Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="57162-111">For more information about anonymous types, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="57162-112">[!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="57162-112">[!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="57162-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57162-113">Example</span></span>  
 <span data-ttu-id="57162-114">In folgendem Beispiel wird das Schlüsselwort `var` in einer ähnlichen Situation verwendet, wobei der Gebrauch von `var` jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="57162-114">The following example uses the `var` keyword in a situation that is similar, but in which the use of `var` is optional.</span></span> <span data-ttu-id="57162-115">Da `student.LastName` eine Zeichenfolge ist, gibt die Ausführung der Abfrage eine Sequenz von Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="57162-115">Because `student.LastName` is a string, execution of the query returns a sequence of strings.</span></span> <span data-ttu-id="57162-116">Deshalb kann der Typ von `queryID` als `System.Collections.Generic.IEnumerable<string>` statt als `var` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="57162-116">Therefore, the type of `queryID` could be declared as `System.Collections.Generic.IEnumerable<string>` instead of `var`.</span></span> <span data-ttu-id="57162-117">Das Schlüsselwort `var` wird aus praktischen Gründen verwendet.</span><span class="sxs-lookup"><span data-stu-id="57162-117">Keyword `var` is used for convenience.</span></span> <span data-ttu-id="57162-118">In dem Beispiel wird die Iterationsvariable in der `foreach`-Anweisung explizit als Zeichenfolge typisiert. Sie könnte aber auch alternativ mit `var` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="57162-118">In the example, the iteration variable in the `foreach` statement is explicitly typed as a string, but it could instead be declared by using `var`.</span></span> <span data-ttu-id="57162-119">Da der Typ der Iterationsvariablen kein anonymer Typ ist, ist das Verwenden von `var` optional aber nicht verpflichtend.</span><span class="sxs-lookup"><span data-stu-id="57162-119">Because the type of the iteration variable is not an anonymous type, the use of `var` is an option, not a requirement.</span></span> <span data-ttu-id="57162-120">Denken Sie daran, das `var` selbst kein Typ ist, sondern eine Anweisung an den Compiler, um den Typen abzuleiten und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="57162-120">Remember, `var` itself is not a type, but an instruction to the compiler to infer and assign the type.</span></span>  
  
 <span data-ttu-id="57162-121">[!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="57162-121">[!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57162-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57162-122">See Also</span></span>  
 <span data-ttu-id="57162-123">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="57162-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="57162-124">[Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="57162-124">[Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
 <span data-ttu-id="57162-125">[LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span><span class="sxs-lookup"><span data-stu-id="57162-125">[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) </span></span>  
 <span data-ttu-id="57162-126">["var"](../../../csharp/language-reference/keywords/var.md) </span><span class="sxs-lookup"><span data-stu-id="57162-126">[var](../../../csharp/language-reference/keywords/var.md) </span></span>  
 [<span data-ttu-id="57162-127">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="57162-127">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

