---
title: as (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: aee80b3262ccd9432d7c311dddec47185b66d05f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44098862"
---
# <a name="as-c-reference"></a><span data-ttu-id="cbed1-102">as (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cbed1-102">as (C# Reference)</span></span>
<span data-ttu-id="cbed1-103">Sie können den `as`-Operator verwenden, um bestimmte Arten von Konvertierungen zwischen kompatiblen Verweistypen oder [auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/index.md) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="cbed1-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="cbed1-104">Der folgende Code zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cbed1-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]
  
## <a name="remarks"></a><span data-ttu-id="cbed1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbed1-105">Remarks</span></span>  
 <span data-ttu-id="cbed1-106">Der `as`-Operator kann mit einem Umwandlungsvorgang verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="cbed1-106">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="cbed1-107">Wenn die Konvertierung jedoch nicht möglich ist, gibt `as` `null` zurück, statt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="cbed1-107">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="cbed1-108">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cbed1-108">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="cbed1-109">Der Code ist äquivalent zu folgendem Ausdruck, jedoch wird die `expression`-Variable nur einmal ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="cbed1-109">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="cbed1-110">Beachten Sie, dass der `as`-Operator nur Verweis- und Boxingkonvertierungen sowie Konvertierungen mit Nullwert durchführt.</span><span class="sxs-lookup"><span data-stu-id="cbed1-110">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="cbed1-111">Der `as`-Operator kann keine anderen Konvertierungen wie z.B. benutzerdefinierte Konvertierungen durchführen, die stattdessen mithilfe der Cast-Ausdrücke ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="cbed1-111">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbed1-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbed1-112">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="cbed1-113">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="cbed1-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cbed1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbed1-114">See Also</span></span>  
- [<span data-ttu-id="cbed1-115">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cbed1-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="cbed1-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cbed1-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="cbed1-117">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cbed1-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="cbed1-118">is</span><span class="sxs-lookup"><span data-stu-id="cbed1-118">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="cbed1-119">?:-Operator</span><span class="sxs-lookup"><span data-stu-id="cbed1-119">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="cbed1-120">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="cbed1-120">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
