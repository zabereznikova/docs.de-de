---
title: IsFalse-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="afaeb-102">IsFalse-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afaeb-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="afaeb-103">Bestimmt, ob ein Ausdruck ist `False`.</span><span class="sxs-lookup"><span data-stu-id="afaeb-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="afaeb-104">Sie können nicht aufrufen `IsFalse` explizit in Code, jedoch in Visual Basic Compiler können sie zum Generieren von Code aus `AndAlso` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="afaeb-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="afaeb-105">Wenn Sie eine Klasse oder Struktur definieren und verwenden Sie eine Variable dieses Typs in eine `AndAlso` -Klausel, müssen Sie definieren `IsFalse` für diese Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="afaeb-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="afaeb-106">Der Compiler betrachtet die `IsFalse` und `IsTrue` Operatoren als eine *zueinander passendes Paar*.</span><span class="sxs-lookup"><span data-stu-id="afaeb-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="afaeb-107">Dies bedeutet, dass wenn Sie eine von ihnen definieren, Sie auch die anderen Knoten definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="afaeb-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afaeb-108">Die `IsFalse` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn Operanden den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="afaeb-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="afaeb-109">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="afaeb-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="afaeb-110">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="afaeb-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="afaeb-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afaeb-111">Example</span></span>  
 <span data-ttu-id="afaeb-112">Im folgenden Codebeispiel wird definiert, den Überblick über eine Struktur, die Definitionen für die `IsFalse` und `IsTrue` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="afaeb-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="afaeb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afaeb-113">See Also</span></span>  
 [<span data-ttu-id="afaeb-114">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="afaeb-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="afaeb-115">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="afaeb-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="afaeb-116">AndAlso-Operator</span><span class="sxs-lookup"><span data-stu-id="afaeb-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
