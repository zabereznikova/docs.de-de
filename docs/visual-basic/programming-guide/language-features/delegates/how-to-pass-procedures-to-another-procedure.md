---
title: 'Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c28ac7a640ec863b37bd7407d0273a1918964ac4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647212"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="cb967-102">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cb967-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="cb967-103">Dieses Beispiel zeigt, wie Delegaten verwenden, um eine Prozedur an eine andere Prozedur übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="cb967-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="cb967-104">Ein Delegat ist ein Typ, den Sie sich wie jeder andere Typ in Visual Basic verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cb967-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="cb967-105">Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf eine Prozedurnamens zurück.</span><span class="sxs-lookup"><span data-stu-id="cb967-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="cb967-106">In diesem Beispiel besteht aus einer Prozedur mit einem Delegatparameter, der einen Verweis auf eine andere Prozedur, durch erzielt werden kann die `AddressOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="cb967-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="cb967-107">Erstellen des Delegaten und dem entsprechenden Verfahren</span><span class="sxs-lookup"><span data-stu-id="cb967-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="cb967-108">Erstellen Sie einen Delegaten mit dem Namen `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="cb967-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="cb967-109">Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewerten, die denen des entsprechen `MathOperator`, damit die Signaturen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cb967-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="cb967-110">Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="cb967-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="cb967-111">Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , das einen Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="cb967-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="cb967-112">Diese Prozedur kann einen Verweis auf akzeptieren `AddNumbers` oder `SubtractNumbers`, da ihre Signaturen entsprechen den `MathOperator` Signatur.</span><span class="sxs-lookup"><span data-stu-id="cb967-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="cb967-113">Erstellen Sie eine Prozedur mit dem Namen `Test` damaligen `DelegateTest` einmal mit der Delegat für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="cb967-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="cb967-114">Wenn `Test` wird aufgerufen, es zuerst zeigt das Ergebnis der `AddNumbers` handelnden auf `5` und `3`, also in 8.</span><span class="sxs-lookup"><span data-stu-id="cb967-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="cb967-115">Klicken Sie dann das Ergebnis des `SubtractNumbers` , agiert `9` und `3` angezeigt wird, ist 6.</span><span class="sxs-lookup"><span data-stu-id="cb967-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb967-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb967-116">See Also</span></span>  
 [<span data-ttu-id="cb967-117">Delegaten</span><span class="sxs-lookup"><span data-stu-id="cb967-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="cb967-118">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="cb967-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="cb967-119">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cb967-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="cb967-120">Gewusst wie: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="cb967-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
