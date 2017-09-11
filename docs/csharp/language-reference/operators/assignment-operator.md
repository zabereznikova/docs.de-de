---
title: "Operator = (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
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
ms.openlocfilehash: e40b2f221717461443a5d0247b3401eb527a7b5a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="176f1-102">Operator = (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="176f1-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="176f1-103">Der Zuweisungsoperator (`=`) speichert den Wert seines rechtsseitigen Operanden an dem Speicherort, in der Eigenschaft oder in dem Indexer, der durch seinen linksseitigen Operanden angegeben wird, und gibt den Wert als Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="176f1-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="176f1-104">Die Operanden müssen demselben Typ angehören, oder der rechtsseitige Operand muss implizit in den Typ des linksseitigen Operanden konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="176f1-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="176f1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="176f1-105">Remarks</span></span>  
 <span data-ttu-id="176f1-106">Der Zuweisungsoperator kann nicht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="176f1-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="176f1-107">Sie können jedoch implizite Konvertierungsoperatoren für einen Typ definieren, um den Zuweisungsoperator mit dem entsprechenden Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="176f1-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="176f1-108">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="176f1-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="176f1-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="176f1-109">Example</span></span>  
 <span data-ttu-id="176f1-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="176f1-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176f1-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="176f1-111">See Also</span></span>  
 <span data-ttu-id="176f1-112">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="176f1-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="176f1-113">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="176f1-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="176f1-114">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="176f1-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

