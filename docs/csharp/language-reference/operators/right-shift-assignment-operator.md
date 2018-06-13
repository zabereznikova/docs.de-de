---
title: '&gt;Operator &gt;= (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: ccc3f688d985b9e35404550f0c53a7acf8095dd5
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171417"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="955af-102">&gt;Operator &gt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="955af-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="955af-103">Der Rechtsschiebezuweisungsoperator.</span><span class="sxs-lookup"><span data-stu-id="955af-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="955af-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="955af-104">Remarks</span></span>  
 <span data-ttu-id="955af-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="955af-105">An expression of the form</span></span>  
  
```csharp  
x >>= y  
```  
  
 <span data-ttu-id="955af-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="955af-106">is evaluated as</span></span>  
  
```csharp  
x = x >> y  
```  
  
 <span data-ttu-id="955af-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="955af-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="955af-108">Der [>>-Operator](../../../csharp/language-reference/operators/right-shift-operator.md) verschiebt `x` um einen durch `y` angegebenen Wert nach rechts.</span><span class="sxs-lookup"><span data-stu-id="955af-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="955af-109">Der >>=-Operator kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den [>>-Operator](../../../csharp/language-reference/operators/right-shift-operator.md) überladen (siehe [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="955af-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="955af-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="955af-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="955af-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="955af-111">See Also</span></span>  
 [<span data-ttu-id="955af-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="955af-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="955af-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="955af-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="955af-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="955af-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
