---
title: Operator &amp;= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 092f46ddd8ca52e2d705200768c93a3473f1520f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="4521a-102">Operator &amp;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4521a-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="4521a-103">Der AND-Zuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="4521a-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4521a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4521a-104">Remarks</span></span>  
 <span data-ttu-id="4521a-105">Ein Ausdruck mit dem Zuweisungsoperator `&=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="4521a-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="4521a-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="4521a-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="4521a-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="4521a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="4521a-108">Der [Operator &](../../../csharp/language-reference/operators/and-operator.md) führt eine bitweise logische AND-Operation für ganzzahlige Operanden und eine logische AND-Operation für `bool`-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="4521a-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="4521a-109">Der Operator `&=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den binären [Operator &](../../../csharp/language-reference/operators/and-operator.md) überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="4521a-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4521a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4521a-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4521a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4521a-111">See Also</span></span>  
 [<span data-ttu-id="4521a-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4521a-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4521a-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4521a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4521a-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="4521a-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
