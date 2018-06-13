---
title: '&lt;Operator &lt;= (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: e5f3886670baa34b0360501ee15280b93fac36bc
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171792"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="e54a5-102">&lt;Operator &lt;= (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e54a5-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="e54a5-103">Der Linksschiebezuweisungs-Operator</span><span class="sxs-lookup"><span data-stu-id="e54a5-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e54a5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e54a5-104">Remarks</span></span>  
 <span data-ttu-id="e54a5-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="e54a5-105">An expression of the form</span></span>  
  
```csharp  
x <<= y  
```  
  
 <span data-ttu-id="e54a5-106">wird als ausgewertet,</span><span class="sxs-lookup"><span data-stu-id="e54a5-106">is evaluated as</span></span>  
  
```csharp  
x = x << y  
```  
  
 <span data-ttu-id="e54a5-107">außer dass `x` nur einmal überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="e54a5-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e54a5-108">Der [Operator <<](../../../csharp/language-reference/operators/left-shift-operator.md) verschiebt `x` um die von `y` angegebenen Schritte nach links.</span><span class="sxs-lookup"><span data-stu-id="e54a5-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="e54a5-109">Der Operator `<<=` kann nicht direkt überladen werden, jedoch können benutzerdefinierte Typen den[<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) überladen (weitere Informationen unter [Operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e54a5-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e54a5-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e54a5-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e54a5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e54a5-111">See Also</span></span>  
 [<span data-ttu-id="e54a5-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e54a5-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e54a5-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e54a5-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e54a5-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e54a5-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
