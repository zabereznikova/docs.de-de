---
title: ?? Operator (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6c2372380d8162d3e7760bba4a43cdb1c568bf5b
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="be216-103">??</span><span class="sxs-lookup"><span data-stu-id="be216-103">??</span></span> <span data-ttu-id="be216-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="be216-104">Operator (C# Reference)</span></span>
<span data-ttu-id="be216-105">Der Operator `??` wird NULL-Sammeloperator genannt.</span><span class="sxs-lookup"><span data-stu-id="be216-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="be216-106">Der linke Operand wird zurückgegeben, falls dieser nicht NULL ist. Andernfalls wird der rechte Operand zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be216-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be216-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be216-107">Remarks</span></span>  
 <span data-ttu-id="be216-108">Ein Typ, der NULL-Werte zulässt, kann einen Wert aus der Domäne des Typs repräsentieren, oder der Wert kann nicht definiert sein (in diesem Fall ist der Wert NULL).</span><span class="sxs-lookup"><span data-stu-id="be216-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="be216-109">Sie können mit der syntaktischen Ausdruckskraft des `??`-Operators einen entsprechenden Wert (den rechten Operand) zurückgeben, wenn der linke Operand einen Typ aufweist, der NULL-Werte zulässt und dessen Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="be216-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="be216-110">Der Versuch, einen Werttyp, der auf NULL festgelegt werden kann, einem Werttyp, der nicht auf NULL festgelegt werden kann, ohne Verwendung des Operators `??` zuzuweisen, verursacht einen Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="be216-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="be216-111">Wenn bei einer Typumwandlung der Werttyp, der auf NULL festgelegt werden kann, aktuell nicht definiert ist, wird eine `InvalidOperationException`-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="be216-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="be216-112">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="be216-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="be216-113">Das Ergebnis eines ??-</span><span class="sxs-lookup"><span data-stu-id="be216-113">The result of a ??</span></span> <span data-ttu-id="be216-114">Operators wird nicht als Konstante angesehen, auch wenn beide Argumente Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="be216-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be216-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be216-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="be216-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be216-116">See Also</span></span>  
 [<span data-ttu-id="be216-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="be216-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="be216-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="be216-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="be216-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="be216-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="be216-120">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="be216-120">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 <span data-ttu-id="be216-121">[What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Was genau bedeutet „Lifted“?)</span><span class="sxs-lookup"><span data-stu-id="be216-121">[What Exactly Does 'Lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)</span></span>
