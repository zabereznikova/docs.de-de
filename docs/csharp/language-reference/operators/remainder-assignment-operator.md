---
title: Operator %= (C#-Referenz)
ms.date: 04/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: 009c162b13fab05ba349d0535fe8dfae206502f3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998655"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7df96-102">Operator %= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7df96-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="7df96-103">Der Restzuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="7df96-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7df96-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7df96-104">Remarks</span></span>  
 <span data-ttu-id="7df96-105">Ein Ausdruck mit dem Zuweisungsoperator `%=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="7df96-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```csharp  
x %= y  
```  
  
 <span data-ttu-id="7df96-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="7df96-106">is equivalent to</span></span>  
  
```csharp  
x = x % y  
```  
  
 <span data-ttu-id="7df96-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="7df96-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="7df96-108">Der [Operator %](../../../csharp/language-reference/operators/remainder-operator.md) ist für numerische Typen vordefiniert, um den Rest nach einer Division zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="7df96-108">The [% operator](../../../csharp/language-reference/operators/remainder-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="7df96-109">Der Operator `%=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[Operator /](../../../csharp/language-reference/operators/remainder-operator.md) überladen (weitere Informationen unter [operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="7df96-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/remainder-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7df96-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7df96-110">Example</span></span>  
 [!code-csharp[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7df96-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7df96-111">See Also</span></span>

- [<span data-ttu-id="7df96-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7df96-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7df96-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7df96-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7df96-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7df96-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
