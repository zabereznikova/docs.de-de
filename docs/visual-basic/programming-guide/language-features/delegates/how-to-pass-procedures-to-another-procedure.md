---
title: 'Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: cf5a8447cbedcd8071da98ac6763ff06eb608199
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506757"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="ff753-102">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ff753-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="ff753-103">Dieses Beispiel zeigt, wie Sie Delegaten verwenden, um eine Prozedur an eine andere Prozedur zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="ff753-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="ff753-104">Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ff753-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="ff753-105">Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf den Namen einer Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="ff753-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="ff753-106">Dieses Beispiel besteht aus eine Prozedur mit einem Delegate-Parameter, die einen Verweis auf eine andere Prozedur, die mit bezogen ergreifen können die `AddressOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="ff753-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="ff753-107">Erstellen des Delegaten und die entsprechenden Verfahren</span><span class="sxs-lookup"><span data-stu-id="ff753-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="ff753-108">Erstellen Sie einen Delegaten, mit dem Namen `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="ff753-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="ff753-109">Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewert, der übereinstimmen `MathOperator`, damit die Signaturen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ff753-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="ff753-110">Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="ff753-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="ff753-111">Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , der einen Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ff753-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="ff753-112">Diese Prozedur akzeptiert einen Verweis auf `AddNumbers` oder `SubtractNumbers`, da die Signaturen übereinstimmen. die `MathOperator` Signatur.</span><span class="sxs-lookup"><span data-stu-id="ff753-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="ff753-113">Erstellen Sie eine Prozedur mit dem Namen `Test` aufruft, `DelegateTest` einmal mit den Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="ff753-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="ff753-114">Wenn `Test` wird aufgerufen, es zunächst zeigt das Ergebnis der `AddNumbers` -Eigenschaft `5` und `3`, dem ist 8.</span><span class="sxs-lookup"><span data-stu-id="ff753-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="ff753-115">Klicken Sie dann das Ergebnis des `SubtractNumbers` , die auf `9` und `3` angezeigt wird, d.h. auf 6.</span><span class="sxs-lookup"><span data-stu-id="ff753-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff753-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff753-116">See also</span></span>
- [<span data-ttu-id="ff753-117">Delegaten</span><span class="sxs-lookup"><span data-stu-id="ff753-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="ff753-118">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="ff753-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="ff753-119">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff753-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="ff753-120">Vorgehensweise: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="ff753-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
