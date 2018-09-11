---
title: '&amp;-Operator (C#-Referenz)'
ms.date: 04/04/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: b257c7d41618464e26ab3b54bcfb1f1e2c2e420e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467373"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="cf7a0-102">&amp;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cf7a0-102">&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="cf7a0-103">Der `&`-Operator kann entweder als unärer oder als binärer Operator funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-103">The `&` operator can function as either a unary or a binary operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf7a0-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf7a0-104">Remarks</span></span>  
 <span data-ttu-id="cf7a0-105">Der unäre `&`-Operator gibt die Adresse des Operanden zurück (erfordert [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext).</span><span class="sxs-lookup"><span data-stu-id="cf7a0-105">The unary `&` operator returns the address of its operand (requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context).</span></span>  
  
 <span data-ttu-id="cf7a0-106">Binäre `&`-Operatoren sind für integrale Typen und `bool` vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-106">Binary `&` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="cf7a0-107">Für integrale Typen berechnet & die bitweise logische AND-Operation der Operanden.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-107">For integral types, & computes the logical bitwise AND of its operands.</span></span> <span data-ttu-id="cf7a0-108">Für `bool`-Operanden berechnet & die logische AND-Operation seiner Operanden. Das bedeutet, dass das Ergebnis nur dann `true` ist, wenn beide Operanden `true` sind.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-108">For `bool` operands, & computes the logical AND of its operands; that is, the result is `true` if and only if both its operands are `true`.</span></span>  
  
 <span data-ttu-id="cf7a0-109">Im Gegensatz zum [bedingten AND-Operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&` wertet der binäre `&`-Operator beide Operanden unabhängig vom Wert des ersten Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-109">The binary `&` operator evaluates both operands regardless of the first one's value, in contrast to the [conditional AND operator](../../../csharp/language-reference/operators/conditional-and-operator.md) `&&`.</span></span> <span data-ttu-id="cf7a0-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cf7a0-110">For example:</span></span>  
  
 [!code-csharp[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 <span data-ttu-id="cf7a0-111">Benutzerdefinierte Typen können den binären `&`-Operator überladen (weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="cf7a0-111">User-defined types can overload the binary `&` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="cf7a0-112">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-112">Operations on integral types are generally allowed on enumeration.</span></span> <span data-ttu-id="cf7a0-113">Wenn ein binärer Operator überladen ist, wird der zugehörige Zuweisungsoperator, sofern er vorhanden ist, auch implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf7a0-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf7a0-114">Example</span></span>  
 [!code-csharp[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="cf7a0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf7a0-115">See Also</span></span>

- [<span data-ttu-id="cf7a0-116">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cf7a0-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="cf7a0-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cf7a0-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="cf7a0-118">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="cf7a0-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
