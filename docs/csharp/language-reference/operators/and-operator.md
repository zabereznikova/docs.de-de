---
title: '&amp;-Operator (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eceee8e01ba46f65c6b182a40d14e62aaba5dd53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="7d04e-102">Operator &amp; (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7d04e-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="7d04e-103">Der Operator & kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7d04e-103">The & operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d04e-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d04e-104">Remarks</span></span>  
 <span data-ttu-id="7d04e-105">Der unäre Operator & gibt die Adresse des Operanden zurück (erfordert [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext).</span><span class="sxs-lookup"><span data-stu-id="7d04e-105">The unary & operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="7d04e-106">Binäre &-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="7d04e-106">Binary & operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="7d04e-107">Für integrale Typen berechnet & die bitweise logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="7d04e-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="7d04e-108">Für `bool`-Operanden berechnet & die logische AND-Operation seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn beide Operanden `true` sind.</span><span class="sxs-lookup"><span data-stu-id="7d04e-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="7d04e-109">Der `&`-Operator wertet beide Operanden unabhängig vom Wert des ersten aus.</span><span class="sxs-lookup"><span data-stu-id="7d04e-109">The `&` operator evaluates both operators regardless of the first one's value.</span></span> <span data-ttu-id="7d04e-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7d04e-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="7d04e-111">Benutzerdefinierte Typen können den binären `&`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7d04e-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7d04e-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="7d04e-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="7d04e-113">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="7d04e-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d04e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d04e-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7d04e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d04e-115">See Also</span></span>  
 [<span data-ttu-id="7d04e-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7d04e-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7d04e-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7d04e-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7d04e-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7d04e-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
