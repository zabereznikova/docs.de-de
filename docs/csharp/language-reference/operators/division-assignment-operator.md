---
title: Operator /= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 26096d9b5dfc565c9933f1ed8ffb241dc900d9ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="e4286-102">Operator /= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e4286-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="e4286-103">Der Divisionszuweisungsoperator</span><span class="sxs-lookup"><span data-stu-id="e4286-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4286-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4286-104">Remarks</span></span>  
 <span data-ttu-id="e4286-105">Ein Ausdruck mit dem Zuweisungsoperator `/=`, z.B.</span><span class="sxs-lookup"><span data-stu-id="e4286-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="e4286-106">für die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="e4286-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="e4286-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="e4286-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e4286-108">Die [/ operator](../../../csharp/language-reference/operators/division-operator.md) ist für numerische Typen vordefiniert, um Division auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e4286-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="e4286-109">Der Operator `/=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[/ operator](../../../csharp/language-reference/operators/division-operator.md) überladen (weitere Informationen unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e4286-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e4286-110">Bei allen Zusammensetzungszuweisungsoperatoren wird die entsprechende Verbundzuweisung durch das Überladen des binären Operators implizit überladen.</span><span class="sxs-lookup"><span data-stu-id="e4286-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4286-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4286-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e4286-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4286-112">See Also</span></span>  
 [<span data-ttu-id="e4286-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e4286-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e4286-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e4286-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e4286-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e4286-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
