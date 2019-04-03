---
title: IsFalse-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 9f25c406038486224c2c4708c86ef86889c44c15
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818487"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="e540f-102">IsFalse-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e540f-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="e540f-103">Bestimmt, ob ein Ausdruck ist `False`.</span><span class="sxs-lookup"><span data-stu-id="e540f-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="e540f-104">Sie können nicht aufrufen `IsFalse` explizit in Ihrem Code, aber die Visual Basic Compiler können sie zum Generieren von Code aus `AndAlso` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="e540f-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="e540f-105">Wenn Sie eine Klasse oder Struktur definieren und verwenden Sie dann auf eine Variable dieses Typs in eine `AndAlso` -Klausel, müssen Sie definieren `IsFalse` für diese Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="e540f-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="e540f-106">Der Compiler betrachtet die `IsFalse` und `IsTrue` Operatoren als eine *zueinander passendes Paar*.</span><span class="sxs-lookup"><span data-stu-id="e540f-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="e540f-107">Dies bedeutet, dass wenn Sie einen dieser definieren, Sie auch die anderen Knoten definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="e540f-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e540f-108">Die `IsFalse` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn der Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="e540f-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="e540f-109">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e540f-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e540f-110">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e540f-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e540f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e540f-111">Example</span></span>  
 <span data-ttu-id="e540f-112">Das folgende Codebeispiel definiert die Gliederung einer Struktur, die Definitionen für enthält die `IsFalse` und `IsTrue` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="e540f-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e540f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e540f-113">See also</span></span>

- [<span data-ttu-id="e540f-114">IsTrue-Operator</span><span class="sxs-lookup"><span data-stu-id="e540f-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="e540f-115">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="e540f-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="e540f-116">AndAlso-Operator</span><span class="sxs-lookup"><span data-stu-id="e540f-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
