---
title: 'Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 3a7a653bbf238b50e3c7339da76df0f68ab9b59f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085788"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="aa449-102">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa449-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>

<span data-ttu-id="aa449-103">In diesem Beispiel wird gezeigt, wie Delegaten verwendet werden, um eine Prozedur an eine andere Prozedur zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="aa449-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="aa449-104">Ein Delegat ist ein Typ, den Sie wie jeden anderen Typ in Visual Basic verwenden können.</span><span class="sxs-lookup"><span data-stu-id="aa449-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="aa449-105">Der- `AddressOf` Operator gibt ein Delegatobjekt zurück, wenn es auf einen Prozedur Namen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa449-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="aa449-106">Dieses Beispiel enthält eine Prozedur mit einem Delegatparameter, der einen Verweis auf eine andere Prozedur annehmen kann, die mit dem-Operator abgerufen wird `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="aa449-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="aa449-107">Erstellen des Delegaten und der entsprechenden Prozeduren</span><span class="sxs-lookup"><span data-stu-id="aa449-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="aa449-108">Erstellen Sie einen Delegaten namens `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="aa449-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="aa449-109">Erstellen Sie eine Prozedur `AddNumbers` mit dem Namen mit Parametern und Rückgabe Werten, die mit denen von identisch `MathOperator` sind, damit die Signaturen einander entsprechen.</span><span class="sxs-lookup"><span data-stu-id="aa449-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="aa449-110">Erstellen Sie eine Prozedur `SubtractNumbers` mit dem Namen mit einer Signatur, die entspricht `MathOperator` .</span><span class="sxs-lookup"><span data-stu-id="aa449-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="aa449-111">Erstellen Sie eine Prozedur mit dem Namen `DelegateTest` , die einen Delegaten als Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="aa449-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="aa449-112">Diese Prozedur kann einen Verweis auf `AddNumbers` oder akzeptieren `SubtractNumbers` , da ihre Signaturen der `MathOperator` Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="aa449-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="aa449-113">Erstellen Sie eine Prozedur `Test` mit dem Namen, die `DelegateTest` einmal mit dem Delegaten für `AddNumbers` als Parameter und erneut mit dem Delegaten für `SubtractNumbers` als Parameter aufruft.</span><span class="sxs-lookup"><span data-stu-id="aa449-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="aa449-114">Wenn `Test` aufgerufen wird, zeigt es zuerst das Ergebnis der Durchsetzung von `AddNumbers` für `5` und `3` , d. h. 8.</span><span class="sxs-lookup"><span data-stu-id="aa449-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="aa449-115">Anschließend wird das Ergebnis der Durchsetzung von `SubtractNumbers` unter `9` und `3` angezeigt, d. h. 6.</span><span class="sxs-lookup"><span data-stu-id="aa449-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa449-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa449-116">See also</span></span>

- [<span data-ttu-id="aa449-117">Delegaten</span><span class="sxs-lookup"><span data-stu-id="aa449-117">Delegates</span></span>](index.md)
- [<span data-ttu-id="aa449-118">AddressOf-Operator</span><span class="sxs-lookup"><span data-stu-id="aa449-118">AddressOf Operator</span></span>](../../../language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="aa449-119">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aa449-119">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="aa449-120">Vorgehensweise: Aufrufen einer Delegatenmethode</span><span class="sxs-lookup"><span data-stu-id="aa449-120">How to: Invoke a Delegate Method</span></span>](how-to-invoke-a-delegate-method.md)
