---
title: ?? Operator (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ??_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
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
ms.openlocfilehash: 86e50b97d7ded8adc74f031faf026b69ccdd0c87
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="7df5a-103">??</span><span class="sxs-lookup"><span data-stu-id="7df5a-103">??</span></span> <span data-ttu-id="7df5a-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7df5a-104">Operator (C# Reference)</span></span>
<span data-ttu-id="7df5a-105">Der Operator `??` wird NULL-Sammeloperator genannt.</span><span class="sxs-lookup"><span data-stu-id="7df5a-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="7df5a-106">Der linke Operand wird zurückgegeben, falls dieser nicht NULL ist. Andernfalls wird der rechte Operand zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7df5a-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7df5a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7df5a-107">Remarks</span></span>  
 <span data-ttu-id="7df5a-108">Ein Typ, der NULL-Werte zulässt, kann einen Wert aus der Domäne des Typs repräsentieren, oder der Wert kann nicht definiert sein (in diesem Fall ist der Wert NULL).</span><span class="sxs-lookup"><span data-stu-id="7df5a-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="7df5a-109">Sie können mit der syntaktischen Ausdruckskraft des `??`-Operators einen entsprechenden Wert (den rechten Operand) zurückgeben, wenn der linke Operand einen Typ aufweist, der NULL-Werte zulässt und dessen Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="7df5a-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullible type whose value is null.</span></span> <span data-ttu-id="7df5a-110">Der Versuch, einen Werttyp, der auf NULL festgelegt werden kann, einem Werttyp, der nicht auf NULL festgelegt werden kann, ohne Verwendung des Operators `??` zuzuweisen, verursacht einen Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="7df5a-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="7df5a-111">Wenn bei einer Typumwandlung der Werttyp, der auf NULL festgelegt werden kann, aktuell nicht definiert ist, wird eine `InvalidOperationException`-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7df5a-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="7df5a-112">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="7df5a-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="7df5a-113">Das Ergebnis eines ??-</span><span class="sxs-lookup"><span data-stu-id="7df5a-113">The result of a ??</span></span> <span data-ttu-id="7df5a-114">Operators wird nicht als Konstante angesehen, auch wenn beide Argumente Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="7df5a-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7df5a-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7df5a-115">Example</span></span>  
 <span data-ttu-id="7df5a-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7df5a-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df5a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7df5a-117">See Also</span></span>  
 <span data-ttu-id="7df5a-118">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="7df5a-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="7df5a-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7df5a-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7df5a-120">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="7df5a-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="7df5a-121">[Typen, die NULL-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="7df5a-121">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 <span data-ttu-id="7df5a-122">[What exactly does 'lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382) (Was genau bedeutet „Lifted“?)</span><span class="sxs-lookup"><span data-stu-id="7df5a-122">[What Exactly Does 'Lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382)</span></span>

