---
title: Operator = (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 9cd1af400a9afdb7942a49dee7e7f7bb78387f2d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507353"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c0f8f-102">Operator = (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c0f8f-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="c0f8f-103">Der Zuweisungsoperator (`=`) speichert den Wert seines rechtsseitigen Operanden an dem Speicherort, in der Eigenschaft oder in dem Indexer, der durch seinen linksseitigen Operanden angegeben wird, und gibt den Wert als Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="c0f8f-104">Die Operanden müssen demselben Typ angehören, oder der rechtsseitige Operand muss implizit in den Typ des linksseitigen Operanden konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0f8f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0f8f-105">Remarks</span></span>  
 <span data-ttu-id="c0f8f-106">Der Zuweisungsoperator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="c0f8f-107">Sie können jedoch implizite Konvertierungsoperatoren für einen Typ definieren, um den Zuweisungsoperator mit dem entsprechenden Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c0f8f-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="c0f8f-108">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="c0f8f-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f8f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c0f8f-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c0f8f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0f8f-110">See Also</span></span>

- [<span data-ttu-id="c0f8f-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c0f8f-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="c0f8f-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c0f8f-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c0f8f-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c0f8f-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
