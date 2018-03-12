---
title: "Operator ?: (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bbd434e02ece4843bab4ffded6877f81f622950c
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="93cbb-102">Operator ?: (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="93cbb-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="93cbb-103">Der bedingte Operator (`?:`), gemeinhin als ternärer bedingter Operator bekannt, gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="93cbb-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="93cbb-104">Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="93cbb-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="93cbb-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93cbb-105">Remarks</span></span>  
 <span data-ttu-id="93cbb-106">`condition` muss mit `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="93cbb-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="93cbb-107">Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="93cbb-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="93cbb-108">Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="93cbb-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="93cbb-109">Nur einer der beiden Ausdrücke wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="93cbb-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="93cbb-110">Entweder muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="93cbb-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="93cbb-111">Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`-Konstruktion benötigen.</span><span class="sxs-lookup"><span data-stu-id="93cbb-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="93cbb-112">Im folgenden Code wird z. B. zuerst eine `if`-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="93cbb-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="93cbb-113">Der bedingte Operator ist rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="93cbb-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="93cbb-114">Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="93cbb-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="93cbb-115">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="93cbb-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93cbb-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93cbb-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="93cbb-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93cbb-117">See Also</span></span>  
 [<span data-ttu-id="93cbb-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="93cbb-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="93cbb-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="93cbb-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="93cbb-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="93cbb-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="93cbb-121">if-else</span><span class="sxs-lookup"><span data-stu-id="93cbb-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 [<span data-ttu-id="93cbb-122">?.- und ?-Operatoren</span><span class="sxs-lookup"><span data-stu-id="93cbb-122">?. and ?Operators</span></span>](../../../csharp/language-reference/operators/null-conditional-operators.md)  
 [<span data-ttu-id="93cbb-123">?? Operator</span><span class="sxs-lookup"><span data-stu-id="93cbb-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)
