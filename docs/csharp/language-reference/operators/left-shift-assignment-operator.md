---
title: '&lt;Operator &lt;= (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5c2a177182561075442afc3f1b76603c6646bd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="892a2-102">&lt;Operator &lt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="892a2-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="892a2-103">Der Linksschiebezuweisungs-Operator</span><span class="sxs-lookup"><span data-stu-id="892a2-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="892a2-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="892a2-104">Remarks</span></span>  
 <span data-ttu-id="892a2-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="892a2-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="892a2-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="892a2-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="892a2-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="892a2-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="892a2-108">Der [Operator <<](../../../csharp/language-reference/operators/left-shift-operator.md) verschiebt `x` um die von `y` angegebenen Schritte nach links.</span><span class="sxs-lookup"><span data-stu-id="892a2-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="892a2-109">Der Operator `<<=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) überladen (weitere Informationen unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="892a2-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="892a2-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="892a2-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="892a2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="892a2-111">See Also</span></span>  
 [<span data-ttu-id="892a2-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="892a2-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="892a2-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="892a2-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="892a2-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="892a2-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
