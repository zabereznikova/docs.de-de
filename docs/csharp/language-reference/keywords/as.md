---
title: as – C#-Referenz
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 84e599340877ce52dc6242ea259c69672915c546
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422017"
---
# <a name="as-c-reference"></a><span data-ttu-id="fa6b8-102">as (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fa6b8-102">as (C# Reference)</span></span>
<span data-ttu-id="fa6b8-103">Sie können den `as`-Operator verwenden, um bestimmte Arten von Konvertierungen zwischen kompatiblen Verweistypen oder [auf NULL festlegbaren Typen](../../../csharp/programming-guide/nullable-types/index.md) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="fa6b8-104">Der folgende Code zeigt ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="fa6b8-105">Wie das Beispiel zeigt, müssen Sie das Ergebnis des `as`-Ausdrucks mit `null` vergleichen, um zu überprüfen, ob eine Konvertierung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="fa6b8-106">Ab C# 7.0 können Sie den [is](is.md)-Ausdruck verwenden, um zu testen, ob eine Konvertierung erfolgreich war. Wenn die Konvertierung erfolgreich war, können Sie den Ausdruck auch verwenden, um bedingt eine Variable zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="fa6b8-107">In vielen Szenarien ist dies präziser als die Verwendung des `as`-Operators.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="fa6b8-108">Weitere Informationen finden Sie im Abschnitt [Typmuster](is.md#type) des Artikels zum [`is`-Operator](is.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b8-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fa6b8-109">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="fa6b8-109">Remarks</span></span>  
 <span data-ttu-id="fa6b8-110">Der `as`-Operator kann mit einem Umwandlungsvorgang verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="fa6b8-111">Wenn die Konvertierung jedoch nicht möglich ist, gibt `as` `null` zurück, statt eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="fa6b8-112">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fa6b8-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="fa6b8-113">Der Code ist äquivalent zu folgendem Ausdruck, jedoch wird die `expression`-Variable nur einmal ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="fa6b8-114">Beachten Sie, dass der `as`-Operator nur Verweis- und Boxingkonvertierungen sowie Konvertierungen mit Nullwert durchführt.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="fa6b8-115">Der `as`-Operator kann keine anderen Konvertierungen wie z.B. benutzerdefinierte Konvertierungen durchführen, die stattdessen mithilfe der Cast-Ausdrücke ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa6b8-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa6b8-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="fa6b8-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="fa6b8-117">C# Language Specification</span></span>  

<span data-ttu-id="fa6b8-118">Weitere Informationen finden Sie unter [Der as-Operator](~/_csharplang/spec/expressions.md#the-as-operator) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="fa6b8-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="fa6b8-119">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="fa6b8-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="fa6b8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa6b8-120">See also</span></span>

- [<span data-ttu-id="fa6b8-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fa6b8-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="fa6b8-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fa6b8-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="fa6b8-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fa6b8-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="fa6b8-124">is</span><span class="sxs-lookup"><span data-stu-id="fa6b8-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
- [<span data-ttu-id="fa6b8-125">?: Operator</span><span class="sxs-lookup"><span data-stu-id="fa6b8-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)
