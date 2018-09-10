---
title: Operator ^= (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: d6546f23ffb6dee792339a7e3863bf58ae668d58
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857231"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="43ab9-102">Operator ^= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="43ab9-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="43ab9-103">Der XOR-Zuweisungsoperator („exklusives Oder“)</span><span class="sxs-lookup"><span data-stu-id="43ab9-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43ab9-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43ab9-104">Remarks</span></span>  
 <span data-ttu-id="43ab9-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="43ab9-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="43ab9-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="43ab9-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="43ab9-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="43ab9-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="43ab9-108">Der [Operator ^](../../../csharp/language-reference/operators/xor-operator.md) führt eine bitweise XOR-Operation für integrale Operanden und eine XOR-Operation für [bool](../../../csharp/language-reference/keywords/bool.md)-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="43ab9-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="43ab9-109">Der Operator ^= kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [operator ^](../../../csharp/language-reference/operators/xor-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="43ab9-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43ab9-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43ab9-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="43ab9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43ab9-111">See Also</span></span>

- [<span data-ttu-id="43ab9-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="43ab9-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="43ab9-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="43ab9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="43ab9-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="43ab9-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
