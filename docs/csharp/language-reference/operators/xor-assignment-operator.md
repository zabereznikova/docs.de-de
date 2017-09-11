---
title: "Operator ^= (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 33b0dccf5031809bb4fcb73d0f7d6a344accdea3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3fb55-102">Operator ^= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3fb55-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="3fb55-103">Der XOR-Zuweisungsoperator („exklusives Oder“)</span><span class="sxs-lookup"><span data-stu-id="3fb55-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fb55-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fb55-104">Remarks</span></span>  
 <span data-ttu-id="3fb55-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="3fb55-105">An expression of the form</span></span>  
  
```  
x ^= y  
```  
  
 <span data-ttu-id="3fb55-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="3fb55-106">is evaluated as</span></span>  
  
```  
x = x ^ y  
```  
  
 <span data-ttu-id="3fb55-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="3fb55-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="3fb55-108">Der [Operator ^](../../../csharp/language-reference/operators/xor-operator.md) führt eine bitweise XOR-Operation für integrale Operanden und eine XOR-Operation für [bool](../../../csharp/language-reference/keywords/bool.md)-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="3fb55-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="3fb55-109">Der Operator ^= kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [operator ^](../../../csharp/language-reference/operators/xor-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3fb55-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fb55-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fb55-110">Example</span></span>  
 <span data-ttu-id="3fb55-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3fb55-111">[!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb55-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fb55-112">See Also</span></span>  
 <span data-ttu-id="3fb55-113">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3fb55-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3fb55-114">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3fb55-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3fb55-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="3fb55-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

