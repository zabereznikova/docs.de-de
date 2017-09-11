---
title: Operator /= (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: 5e105bf11f5413d77d62be4177ed22ba420312c3
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3b37d-102">Operator /= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3b37d-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="3b37d-103">Der Divisionszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="3b37d-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b37d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b37d-104">Remarks</span></span>  
 <span data-ttu-id="3b37d-105">Ein Ausdruck mit dem Zuweisungsoperator `/=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="3b37d-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="3b37d-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="3b37d-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="3b37d-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="3b37d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="3b37d-108">Die [/ operator](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen vordefiniert, um Division auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3b37d-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="3b37d-109">Der Operator `/=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[/ operator](../../../csharp/language-reference/operators/division-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="3b37d-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="3b37d-110">Bei allen Zusammensetzungszuweisungsoperatoren wird die entsprechende Verbundzuweisung durch das Überladen des binären Operators implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="3b37d-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b37d-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b37d-111">Example</span></span>  
 <span data-ttu-id="3b37d-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3b37d-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b37d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b37d-113">See Also</span></span>  
 <span data-ttu-id="3b37d-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b37d-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3b37d-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3b37d-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3b37d-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="3b37d-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

