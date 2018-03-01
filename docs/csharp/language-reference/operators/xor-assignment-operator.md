---
title: "Operator ^= (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8d4de06dbfd269dc5e0f2cc5003e8981068220a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="83555-102">Operator ^= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="83555-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="83555-103">Der XOR-Zuweisungsoperator („exklusives Oder“)</span><span class="sxs-lookup"><span data-stu-id="83555-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83555-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83555-104">Remarks</span></span>  
 <span data-ttu-id="83555-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="83555-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="83555-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="83555-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="83555-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="83555-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="83555-108">Der [Operator ^](../../../csharp/language-reference/operators/xor-operator.md) führt eine bitweise XOR-Operation für integrale Operanden und eine XOR-Operation für [bool](../../../csharp/language-reference/keywords/bool.md)-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="83555-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="83555-109">Der Operator ^= kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [operator ^](../../../csharp/language-reference/operators/xor-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="83555-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="83555-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="83555-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="83555-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83555-111">See Also</span></span>  
 [<span data-ttu-id="83555-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="83555-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="83555-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="83555-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="83555-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="83555-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
