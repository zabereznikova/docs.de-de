---
title: "Operator ?: (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 794ff53fe471ef23163503f59599b528df127e2e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="90b0a-102">Operator ?: (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="90b0a-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="90b0a-103">Der bedingte Operator (`?:`) gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="90b0a-103">The conditional operator (`?:`) returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="90b0a-104">Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="90b0a-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="90b0a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90b0a-105">Remarks</span></span>  
 <span data-ttu-id="90b0a-106">`condition` muss mit `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="90b0a-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="90b0a-107">Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="90b0a-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="90b0a-108">Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="90b0a-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="90b0a-109">Nur einer der beiden Ausdrücke wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="90b0a-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="90b0a-110">Entweder muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="90b0a-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="90b0a-111">Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`-Konstruktion benötigen.</span><span class="sxs-lookup"><span data-stu-id="90b0a-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="90b0a-112">Im folgenden Code wird z. B. zuerst eine `if`-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="90b0a-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```  
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="90b0a-113">Der bedingte Operator ist rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="90b0a-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="90b0a-114">Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="90b0a-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="90b0a-115">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="90b0a-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90b0a-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90b0a-116">Example</span></span>  
 <span data-ttu-id="90b0a-117">[!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="90b0a-117">[!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b0a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90b0a-118">See Also</span></span>  
 <span data-ttu-id="90b0a-119">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="90b0a-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="90b0a-120">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="90b0a-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="90b0a-121">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="90b0a-121">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="90b0a-122">[if-else](../../../csharp/language-reference/keywords/if-else.md) </span><span class="sxs-lookup"><span data-stu-id="90b0a-122">[if-else](../../../csharp/language-reference/keywords/if-else.md) </span></span>  
 <span data-ttu-id="90b0a-123">[?.- und ?-Operatoren](../../../csharp/language-reference/operators/null-conditional-operators.md) </span><span class="sxs-lookup"><span data-stu-id="90b0a-123">[?. and ?Operators](../../../csharp/language-reference/operators/null-conditional-operators.md) </span></span>  
 [<span data-ttu-id="90b0a-124">?? Operator</span><span class="sxs-lookup"><span data-stu-id="90b0a-124">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)

