---
title: Operator &amp; (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
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
ms.openlocfilehash: d92a860df6fcc9acf14aab4ec558556735ac8aac
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="eefd9-102">Operator &amp; (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="eefd9-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="eefd9-103">Der Operator & kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="eefd9-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eefd9-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eefd9-104">Remarks</span></span>  
 <span data-ttu-id="eefd9-105">Der unäre Operator & gibt die Adresse des Operanden zurück (erfordert [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext).</span><span class="sxs-lookup"><span data-stu-id="eefd9-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="eefd9-106">Binäre &-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="eefd9-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="eefd9-107">Für integrale Typen berechnet & die bitweise logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="eefd9-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="eefd9-108">Für `bool`-Operanden berechnet & die logische AND-Operation seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn beide Operanden `true` sind.</span><span class="sxs-lookup"><span data-stu-id="eefd9-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="eefd9-109">Der `&`-Operator wertet beide Operanden unabhängig vom Wert des ersten aus.</span><span class="sxs-lookup"><span data-stu-id="eefd9-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="eefd9-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eefd9-110">For example:</span></span>  
  
 <span data-ttu-id="eefd9-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="eefd9-111">[!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="eefd9-112">Benutzerdefinierte Typen können den binären `&`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="eefd9-112">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="eefd9-113">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="eefd9-113">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="eefd9-114">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="eefd9-114">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eefd9-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eefd9-115">Example</span></span>  
 <span data-ttu-id="eefd9-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="eefd9-116">[!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eefd9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eefd9-117">See Also</span></span>  
 <span data-ttu-id="eefd9-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="eefd9-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="eefd9-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="eefd9-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="eefd9-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="eefd9-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

