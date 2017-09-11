---
title: "Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 95cbcf836b0dad875851052a367666c00cd54e37
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="dac8b-102">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dac8b-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="dac8b-103">Dieses Beispiel zeigt, wie Delegaten verwenden, um eine Prozedur an eine andere Prozedur übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="dac8b-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="dac8b-104">Ein Delegat ist ein Typ, mit denen Sie wie jeden anderen Typ in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="dac8b-104">A delegate is a type that you can use like any other type in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="dac8b-105">Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf eine Prozedurnamens zurück.</span><span class="sxs-lookup"><span data-stu-id="dac8b-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="dac8b-106">In diesem Beispiel wird eine Prozedur mit einem Delegatparameter, die einen Verweis auf eine andere Prozedur, die mit bezogen können die `AddressOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="dac8b-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="dac8b-107">Erstellen des Delegaten und entsprechender Prozeduren</span><span class="sxs-lookup"><span data-stu-id="dac8b-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="dac8b-108">Erstellen Sie einen Delegaten mit dem Namen `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="dac8b-108">Create a delegate named `MathOperator`.</span></span>  
  
     <span data-ttu-id="dac8b-109">[!code-vb[VbVbalrDelegates&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="dac8b-109">[!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="dac8b-110">Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewert, der übereinstimmen `MathOperator`, damit die Signaturen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="dac8b-110">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     <span data-ttu-id="dac8b-111">[!code-vb[VbVbalrDelegates&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="dac8b-111">[!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span></span>  
  
3.  <span data-ttu-id="dac8b-112">Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="dac8b-112">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     <span data-ttu-id="dac8b-113">[!code-vb[VbVbalrDelegates&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="dac8b-113">[!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span></span>  
  
4.  <span data-ttu-id="dac8b-114">Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , die einen Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="dac8b-114">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="dac8b-115">Diese Prozedur akzeptiert einen Verweis auf `AddNumbers` oder `SubtractNumbers`, da ihre Signaturen entsprechen den `MathOperator` Signatur.</span><span class="sxs-lookup"><span data-stu-id="dac8b-115">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     <span data-ttu-id="dac8b-116">[!code-vb[VbVbalrDelegates&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="dac8b-116">[!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span></span>  
  
5.  <span data-ttu-id="dac8b-117">Erstellen Sie eine Prozedur mit dem Namen `Test` aufruft, `DelegateTest` einmal mit dem Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="dac8b-117">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     <span data-ttu-id="dac8b-118">[!code-vb[VbVbalrDelegates&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="dac8b-118">[!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span></span>  
  
     <span data-ttu-id="dac8b-119">Wenn `Test` wird aufgerufen, es zunächst zeigt das Ergebnis der `AddNumbers` handelnden auf `5` und `3`, also 8.</span><span class="sxs-lookup"><span data-stu-id="dac8b-119">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="dac8b-120">Klicken Sie dann auf das Ergebnis des `SubtractNumbers` auf `9` und `3` angezeigt wird, also 6.</span><span class="sxs-lookup"><span data-stu-id="dac8b-120">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac8b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dac8b-121">See Also</span></span>  
 <span data-ttu-id="dac8b-122">[Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="dac8b-122">[Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="dac8b-123"> [AddressOf-Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="dac8b-123"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="dac8b-124"> [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="dac8b-124"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="dac8b-125"> [Gewusst wie: Aufrufen einer Delegatenmethode](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="dac8b-125"> [How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
