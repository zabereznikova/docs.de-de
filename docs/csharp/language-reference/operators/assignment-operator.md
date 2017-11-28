---
title: "Operator = (C#-Referenz)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: =_CSharpKeyword
helpviewer_keywords: = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c7188abe54cb69678720b4dbbf4dbdea1be4abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6ce64-102">Operator = (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6ce64-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="6ce64-103">Der Zuweisungsoperator (`=`) speichert den Wert seines rechtsseitigen Operanden an dem Speicherort, in der Eigenschaft oder in dem Indexer, der durch seinen linksseitigen Operanden angegeben wird, und gibt den Wert als Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="6ce64-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="6ce64-104">Die Operanden müssen demselben Typ angehören, oder der rechtsseitige Operand muss implizit in den Typ des linksseitigen Operanden konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="6ce64-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ce64-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ce64-105">Remarks</span></span>  
 <span data-ttu-id="6ce64-106">Der Zuweisungsoperator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="6ce64-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="6ce64-107">Sie können jedoch implizite Konvertierungsoperatoren für einen Typ definieren, um den Zuweisungsoperator mit dem entsprechenden Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ce64-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="6ce64-108">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="6ce64-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ce64-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ce64-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="6ce64-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ce64-110">See Also</span></span>  
 [<span data-ttu-id="6ce64-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6ce64-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6ce64-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6ce64-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6ce64-113">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="6ce64-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
