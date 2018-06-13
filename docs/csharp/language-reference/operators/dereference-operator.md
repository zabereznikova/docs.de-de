---
title: -&gt;-Operator (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: 037229b2081a43077cb4b5d02a8929b06ba9e077
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171979"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="0b09b-102">-&gt;-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0b09b-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="0b09b-103">Der Operator `->` kombiniert Zeigerdereferenzierung und Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="0b09b-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b09b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b09b-104">Remarks</span></span>  
 <span data-ttu-id="0b09b-105">Ein Ausdruck der Form</span><span class="sxs-lookup"><span data-stu-id="0b09b-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="0b09b-106">(wobei `x` ein Zeiger vom Typ `T*` und `y` ein Member von `T` ist) ist äquivalent zu</span><span class="sxs-lookup"><span data-stu-id="0b09b-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="0b09b-107">Der Operator `->` kann nur in Code verwendet werden, der als [unsicher](../../../csharp/language-reference/keywords/unsafe.md) markiert ist.</span><span class="sxs-lookup"><span data-stu-id="0b09b-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="0b09b-108">Operator `->` kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="0b09b-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b09b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b09b-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0b09b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b09b-110">See Also</span></span>  
 [<span data-ttu-id="0b09b-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0b09b-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0b09b-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0b09b-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0b09b-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="0b09b-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
