---
title: 'Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 312c0e0f100e85256ad4ca856ccf7f35dbaa36dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305246"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="04afc-102">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04afc-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="04afc-103">Dieses Beispiel zeigt, wie Sie Delegaten verwenden, um eine Prozedur an eine andere Prozedur zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="04afc-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="04afc-104">Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können.</span><span class="sxs-lookup"><span data-stu-id="04afc-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="04afc-105">Die `AddressOf` Operator gibt ein Delegatobjekt bei Anwendung auf den Namen einer Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="04afc-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="04afc-106">Dieses Beispiel besteht aus eine Prozedur mit einem Delegate-Parameter, die einen Verweis auf eine andere Prozedur, die mit bezogen ergreifen können die `AddressOf` Operator.</span><span class="sxs-lookup"><span data-stu-id="04afc-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="04afc-107">Erstellen des Delegaten und die entsprechenden Verfahren</span><span class="sxs-lookup"><span data-stu-id="04afc-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="04afc-108">Erstellen Sie einen Delegaten, mit dem Namen `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="04afc-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="04afc-109">Erstellen Sie eine Prozedur mit dem Namen `AddNumbers` mit Parametern und Rückgabewert, der übereinstimmen `MathOperator`, damit die Signaturen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="04afc-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="04afc-110">Erstellen Sie eine Prozedur mit dem Namen `SubtractNumbers` mit einer Signatur, die entspricht `MathOperator`.</span><span class="sxs-lookup"><span data-stu-id="04afc-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="04afc-111">Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , der einen Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="04afc-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="04afc-112">Diese Prozedur akzeptiert einen Verweis auf `AddNumbers` oder `SubtractNumbers`, da die Signaturen übereinstimmen. die `MathOperator` Signatur.</span><span class="sxs-lookup"><span data-stu-id="04afc-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="04afc-113">Erstellen Sie eine Prozedur mit dem Namen `Test` aufruft, `DelegateTest` einmal mit den Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="04afc-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="04afc-114">Wenn `Test` wird aufgerufen, es zunächst zeigt das Ergebnis der `AddNumbers` -Eigenschaft `5` und `3`, dem ist 8.</span><span class="sxs-lookup"><span data-stu-id="04afc-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="04afc-115">Klicken Sie dann das Ergebnis des `SubtractNumbers` , die auf `9` und `3` angezeigt wird, d.h. auf 6.</span><span class="sxs-lookup"><span data-stu-id="04afc-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04afc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04afc-116">See also</span></span>

- [<span data-ttu-id="04afc-117">Delegaten</span><span class="sxs-lookup"><span data-stu-id="04afc-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="04afc-118">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="04afc-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="04afc-119">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="04afc-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="04afc-120">Vorgehensweise: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="04afc-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
