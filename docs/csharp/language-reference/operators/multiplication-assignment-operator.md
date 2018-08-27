---
title: Operator *= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: e47bc5c681c94ac3fc5c345c56b3814350ffa5ec
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932349"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="1793d-102">Operator \*= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1793d-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="1793d-103">Der binäre Multiplikationszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="1793d-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1793d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1793d-104">Remarks</span></span>  
 <span data-ttu-id="1793d-105">Ein Ausdruck mit dem Zuweisungsoperator `*=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="1793d-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="1793d-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="1793d-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="1793d-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="1793d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="1793d-108">Der [Operator \*](../../../csharp/language-reference/operators/multiplication-operator.md) ist für numerische Typen und Multiplikationen vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="1793d-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="1793d-109">Der Operator `*=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [Operator *](../../../csharp/language-reference/operators/multiplication-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="1793d-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1793d-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1793d-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="1793d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1793d-111">See Also</span></span>

- [<span data-ttu-id="1793d-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1793d-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1793d-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1793d-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="1793d-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1793d-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
