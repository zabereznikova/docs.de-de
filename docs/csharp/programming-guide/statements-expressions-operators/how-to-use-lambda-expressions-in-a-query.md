---
title: "Gewusst wie: Verwenden von Lambdaausdrücken in einer Abfrage (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
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
ms.openlocfilehash: 5ad819a0e4d441f6ea092480544195b89e0796ca
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a><span data-ttu-id="371c1-102">Gewusst wie: Verwenden von Lambdaausdrücken in einer Abfrage (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="371c1-102">How to: Use Lambda Expressions in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="371c1-103">Sie können Lambdaausdrücke nicht direkt in der Abfragesyntax verwenden, sondern nur in Methodenaufrufen. Abfrageausdrücke können Methodenaufrufe enthalten.</span><span class="sxs-lookup"><span data-stu-id="371c1-103">You do not use lambda expressions directly in query syntax, but you do use them in method calls, and query expressions can contain method calls.</span></span> <span data-ttu-id="371c1-104">Einige Abfragevorgänge können nur in Methodensyntax ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="371c1-104">In fact, some query operations can only be expressed in method syntax.</span></span> <span data-ttu-id="371c1-105">Weitere Informationen zu den Unterschieden zwischen Abfragesyntax und Methodensyntax finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="371c1-105">For more information about the difference between query syntax and method syntax, see [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="371c1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="371c1-106">Example</span></span>  
 <span data-ttu-id="371c1-107">Das folgende Beispiel veranschaulicht, wie Sie Lambdaausdrücke in methodenbasierten Abfragen mithilfe des Standardabfrageoperators <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> verwenden können.</span><span class="sxs-lookup"><span data-stu-id="371c1-107">The following example demonstrates how to use a lambda expression in a method-based query by using the <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> standard query operator.</span></span> <span data-ttu-id="371c1-108">Bitte beachten Sie, dass die Methode <xref:System.Linq.Enumerable.Where%2A> in diesem Beispiel einen Eingabeparameter des Delegattyps <xref:System.Func%601> aufweist und dass dieser Delegat eine Ganzzahl als Eingabe akzeptiert und einen booleschen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="371c1-108">Note that the <xref:System.Linq.Enumerable.Where%2A> method in this example has an input parameter of the delegate type <xref:System.Func%601> and that delegate takes an integer as input and returns a Boolean.</span></span> <span data-ttu-id="371c1-109">Der Lambdaausdruck kann in diesen Delegat konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="371c1-109">The lambda expression can be converted to that delegate.</span></span> <span data-ttu-id="371c1-110">Wenn dies eine [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]-Abfrage wäre, die die Methode <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName> verwendet, wäre der Parametertyp `Expression<Func\<int,bool>>`, aber der Lambdaausdruck wäre der gleiche.</span><span class="sxs-lookup"><span data-stu-id="371c1-110">If this were a [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] query that used the <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName> method, the parameter type would be an `Expression<Func\<int,bool>>` but the lambda expression would look exactly the same.</span></span> <span data-ttu-id="371c1-111">Weitere Informationen zum Ausdruckstyp finden Sie unter <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="371c1-111">For more information on the Expression type, see <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="371c1-112">[!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="371c1-112">[!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="371c1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="371c1-113">Example</span></span>  
 <span data-ttu-id="371c1-114">Das folgende Beispiel veranschaulicht, wie Sie Lambdaausdrücke in einem Methodenaufruf eines Abfrageausdrucks verwenden können.</span><span class="sxs-lookup"><span data-stu-id="371c1-114">The following example demonstrates how to use a lambda expression in a method call of a query expression.</span></span> <span data-ttu-id="371c1-115">Der Lambdaausdruck ist erforderlich, da der Standardabfrageoperator <xref:System.Linq.Enumerable.Sum%2A> nicht durch Abfragesyntax aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="371c1-115">The lambda is necessary because the <xref:System.Linq.Enumerable.Sum%2A> standard query operator cannot be invoked by using query syntax.</span></span>  
  
 <span data-ttu-id="371c1-116">Die Abfrage gruppiert die Studenten zunächst anhand ihres Jahrs wie in der `GradeLevel`-Enumeration definiert.</span><span class="sxs-lookup"><span data-stu-id="371c1-116">The query first groups the students according to their grade level, as defined in the `GradeLevel` enum.</span></span> <span data-ttu-id="371c1-117">Dann fügt sie die Gesamtergebnisse jedes Studenten in jeder Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="371c1-117">Then for each group it adds the total scores for each student.</span></span> <span data-ttu-id="371c1-118">Dazu sind zwei `Sum`-Operationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="371c1-118">This requires two `Sum` operations.</span></span> <span data-ttu-id="371c1-119">Mit der inneren `Sum`-Operation wird das Gesamtergebnis für jeden Studenten berechnet, und mit der äußeren `Sum`-Operation wird eine kombinierte laufende Summe für alle Studenten in der Gruppe berechnet.</span><span class="sxs-lookup"><span data-stu-id="371c1-119">The inner `Sum` calculates the total score for each student, and the outer `Sum` keeps a running, combined total for all students in the group.</span></span>  
  
 <span data-ttu-id="371c1-120">[!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="371c1-120">[!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="371c1-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="371c1-121">Compiling the Code</span></span>  
 <span data-ttu-id="371c1-122">Um diesen Code auszuführen, kopieren Sie die Methode, und fügen Sie sie in die `StudentClass` ein, die in [Vorgehensweise: Abfragen einer Auflistung von Objekten](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) bereitgestellt wird. Rufen Sie diese Methode dann in der `Main`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="371c1-122">To run this code, copy and paste the method into the `StudentClass` that is provided in [How to: Query a Collection of Objects](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) and call it from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371c1-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="371c1-123">See Also</span></span>  
 <span data-ttu-id="371c1-124">[Lambda-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="371c1-124">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
 [<span data-ttu-id="371c1-125">Ausdrucksbaumstrukturen</span><span class="sxs-lookup"><span data-stu-id="371c1-125">Expression Trees</span></span>](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)

