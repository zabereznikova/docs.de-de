---
title: "Operator == (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
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
ms.openlocfilehash: 0e3ba284bc700e943b108adfec89d14aba41851a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e3df7-102">Operator == (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e3df7-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="e3df7-103">Für vordefinierte Werttypen gibt der Gleichheitsoperator (`==`) TRUE zurück, wenn die Werte der Operanden gleich sind, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e3df7-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="e3df7-104">Für andere Verweistypen als [string](../../../csharp/language-reference/keywords/string.md) gibt `==` `true` zurück, wenn beide Operanden auf dasselbe Objekt verweisen.</span><span class="sxs-lookup"><span data-stu-id="e3df7-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="e3df7-105">Für den `string`-Typ vergleicht `==` die Werte der Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e3df7-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3df7-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3df7-106">Remarks</span></span>  
 <span data-ttu-id="e3df7-107">Benutzerdefinierte Werttypen können den Operator `==` überladen (weitere Informationen finden Sie unter [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="e3df7-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e3df7-108">Dies können auch benutzerdefinierte Verweistypen, obwohl `==` sich standardmäßig für vordefinierte und benutzerdefinierte Verweistypen wie oben beschrieben verhält.</span><span class="sxs-lookup"><span data-stu-id="e3df7-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="e3df7-109">Wenn `==` überladen ist, muss [!=](../../../csharp/language-reference/operators/not-equal-operator.md) auch überladen werden.</span><span class="sxs-lookup"><span data-stu-id="e3df7-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="e3df7-110">Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.</span><span class="sxs-lookup"><span data-stu-id="e3df7-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3df7-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3df7-111">Example</span></span>  
 <span data-ttu-id="e3df7-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e3df7-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3df7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3df7-113">See Also</span></span>  
 <span data-ttu-id="e3df7-114">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e3df7-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e3df7-115">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e3df7-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e3df7-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e3df7-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

