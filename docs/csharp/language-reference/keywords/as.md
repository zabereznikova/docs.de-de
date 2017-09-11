---
title: as (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- as_CSharpKeyword
- as
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
caps.latest.revision: 24
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
ms.openlocfilehash: 7a55c696ac295eee8d5d35ed56038f3c4a90b215
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="as-c-reference"></a><span data-ttu-id="daa09-102">as (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="daa09-102">as (C# Reference)</span></span>
<span data-ttu-id="daa09-103">Sie können den `as`-Operator verwenden, um bestimmte Arten von Konvertierungen zwischen kompatiblen Verweistypen oder [auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/index.md) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="daa09-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="daa09-104">Der folgende Code zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="daa09-104">The following code shows an example.</span></span>  
  
 <span data-ttu-id="daa09-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="daa09-105">[!code-cs[csrefKeywordsOperator#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daa09-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="daa09-106">Remarks</span></span>  
 <span data-ttu-id="daa09-107">Der `as`-Operator kann mit einem Umwandlungsvorgang verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="daa09-107">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="daa09-108">Wenn die Konvertierung jedoch nicht möglich ist, gibt `as` `null` zurück, statt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="daa09-108">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="daa09-109">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="daa09-109">Consider the following example:</span></span>  
  
```  
expression as type  
```  
  
 <span data-ttu-id="daa09-110">Der Code ist äquivalent zu folgendem Ausdruck, jedoch wird die `expression`-Variable nur einmal ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="daa09-110">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="daa09-111">Beachten Sie, dass der `as`-Operator nur Verweis- und Boxingkonvertierungen sowie Konvertierungen mit Nullwert durchführt.</span><span class="sxs-lookup"><span data-stu-id="daa09-111">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="daa09-112">Der `as`-Operator kann keine anderen Konvertierungen wie z.B. benutzerdefinierte Konvertierungen durchführen, die stattdessen mithilfe der Cast-Ausdrücke ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="daa09-112">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="daa09-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="daa09-113">Example</span></span>  
 <span data-ttu-id="daa09-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="daa09-114">[!code-cs[csrefKeywordsOperator#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/as_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="daa09-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="daa09-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="daa09-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daa09-116">See Also</span></span>  
 <span data-ttu-id="daa09-117">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="daa09-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="daa09-118">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="daa09-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="daa09-119">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="daa09-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="daa09-120">[ ist gleich ](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="daa09-120">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 <span data-ttu-id="daa09-121">[?:-Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="daa09-121">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 [<span data-ttu-id="daa09-122">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="daa09-122">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

