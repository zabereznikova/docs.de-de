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
ms.openlocfilehash: 1a49d36b8580812c08e9ee080a9602d9fc2027ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="de6c3-103">??</span><span class="sxs-lookup"><span data-stu-id="de6c3-103">??</span></span> <span data-ttu-id="de6c3-104">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="de6c3-104">Operator (C# Reference)</span></span>
<span data-ttu-id="de6c3-105">Der Operator `??` wird NULL-Sammeloperator genannt.</span><span class="sxs-lookup"><span data-stu-id="de6c3-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="de6c3-106">Der linke Operand wird zurückgegeben, falls dieser nicht NULL ist. Andernfalls wird der rechte Operand zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="de6c3-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de6c3-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de6c3-107">Remarks</span></span>  
 <span data-ttu-id="de6c3-108">Ein Typ, der NULL-Werte zulässt, kann einen Wert aus der Domäne des Typs repräsentieren, oder der Wert kann nicht definiert sein (in diesem Fall ist der Wert NULL).</span><span class="sxs-lookup"><span data-stu-id="de6c3-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="de6c3-109">Können Sie die `??` syntaktischen Ausdruckskraft des Operators, um einen entsprechenden Wert (den rechten Operand) zurückgeben, wenn der linke Operand besitzt einen Nullable-Typ, dessen Wert null ist.</span><span class="sxs-lookup"><span data-stu-id="de6c3-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="de6c3-110">Der Versuch, einen Werttyp, der auf NULL festgelegt werden kann, einem Werttyp, der nicht auf NULL festgelegt werden kann, ohne Verwendung des Operators `??` zuzuweisen, verursacht einen Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="de6c3-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="de6c3-111">Wenn bei einer Typumwandlung der Werttyp, der auf NULL festgelegt werden kann, aktuell nicht definiert ist, wird eine `InvalidOperationException`-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="de6c3-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="de6c3-112">Weitere Informationen finden Sie unter [Nullable-Typen](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="de6c3-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="de6c3-113">Das Ergebnis eines ??-</span><span class="sxs-lookup"><span data-stu-id="de6c3-113">The result of a ??</span></span> <span data-ttu-id="de6c3-114">Operators wird nicht als Konstante angesehen, auch wenn beide Argumente Konstanten sind.</span><span class="sxs-lookup"><span data-stu-id="de6c3-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de6c3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de6c3-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="de6c3-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de6c3-116">See Also</span></span>  
 [<span data-ttu-id="de6c3-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="de6c3-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="de6c3-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="de6c3-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="de6c3-119">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="de6c3-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="de6c3-120">Typen mit Nullwert</span><span class="sxs-lookup"><span data-stu-id="de6c3-120">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
 <span data-ttu-id="de6c3-121">[What exactly does 'lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382) (Was genau bedeutet „Lifted“?)</span><span class="sxs-lookup"><span data-stu-id="de6c3-121">[What Exactly Does 'Lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382)</span></span>
