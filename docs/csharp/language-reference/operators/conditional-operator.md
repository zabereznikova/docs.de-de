---
title: 'Operator ?: (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 150149453a67d8e5319461266865cb25be180347
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506431"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6e3e7-102">Operator ?: (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6e3e7-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="6e3e7-103">Der bedingte Operator (`?:`), gemeinhin als ternärer bedingter Operator bekannt, gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-103">The conditional operator (`?:`), commonly known as the ternary conditional operator, returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="6e3e7-104">Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="6e3e7-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e3e7-105">Remarks</span></span>  
 <span data-ttu-id="6e3e7-106">`condition` muss mit `true` oder `false` ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="6e3e7-107">Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="6e3e7-108">Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="6e3e7-109">Nur einer der beiden Ausdrücke wird ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="6e3e7-110">Entweder muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="6e3e7-111">Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`-Konstruktion benötigen.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="6e3e7-112">Im folgenden Code wird z. B. zuerst eine `if`-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
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
  
 <span data-ttu-id="6e3e7-113">Der bedingte Operator ist rechtsassoziativ.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="6e3e7-114">Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="6e3e7-115">Der bedingte Operator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="6e3e7-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e3e7-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e3e7-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6e3e7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e3e7-117">See Also</span></span>

- [<span data-ttu-id="6e3e7-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6e3e7-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6e3e7-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6e3e7-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6e3e7-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6e3e7-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="6e3e7-121">if-else</span><span class="sxs-lookup"><span data-stu-id="6e3e7-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
- <span data-ttu-id="6e3e7-122">[?.- und ?[]-Operatoren](../../../csharp/language-reference/operators/null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="6e3e7-122">[?. and ?[] Operators](../../../csharp/language-reference/operators/null-conditional-operators.md)</span></span>  
- [<span data-ttu-id="6e3e7-123">?? Operator</span><span class="sxs-lookup"><span data-stu-id="6e3e7-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-coalescing-operator.md)
