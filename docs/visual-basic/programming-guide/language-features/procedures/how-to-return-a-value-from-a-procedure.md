---
title: 'Gewusst wie: Abrufen eines Werts aus einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346027"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="6b04b-102">Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6b04b-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="6b04b-103">Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück, indem entweder eine `Return`-Anweisung ausgeführt wird oder eine `Exit Function`-oder `End Function`-Anweisung auftritt.</span><span class="sxs-lookup"><span data-stu-id="6b04b-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="6b04b-104">So geben Sie einen Wert mit der Return-Anweisung zurück</span><span class="sxs-lookup"><span data-stu-id="6b04b-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="6b04b-105">Fügen Sie eine `Return`-Anweisung an der Stelle ein, an der die Aufgabe der Prozedur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="6b04b-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="6b04b-106">Befolgen Sie das `Return`-Schlüsselwort mit einem Ausdruck, der den Wert ergibt, den Sie an den aufrufenden Code zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="6b04b-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="6b04b-107">Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="6b04b-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="6b04b-108">Die folgende `Function` Prozedur berechnet die längste Seite (Hypotenuse) eines Rechts Dreiecks und gibt Sie an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="6b04b-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="6b04b-109">Das folgende Beispiel zeigt einen typischen-`hypotenuse`, der den zurückgegebenen Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="6b04b-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="6b04b-110">So geben Sie einen Wert mit der Funktion Exit oder End</span><span class="sxs-lookup"><span data-stu-id="6b04b-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="6b04b-111">Weisen Sie in der `Function` Prozedur mindestens einen-Wert dem Namen der Prozedur zu.</span><span class="sxs-lookup"><span data-stu-id="6b04b-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="6b04b-112">Wenn Sie eine `Exit Function`-oder `End Function`-Anweisung ausführen, gibt Visual Basic den Wert zurück, der zuletzt dem Namen der Prozedur zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="6b04b-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="6b04b-113">Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="6b04b-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="6b04b-114">Sie können in einer `Function` Prozedur nur eine `End Function`-Anweisung ausführen.</span><span class="sxs-lookup"><span data-stu-id="6b04b-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="6b04b-115">Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in der [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6b04b-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b04b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b04b-116">See also</span></span>

- [<span data-ttu-id="6b04b-117">Verfahren</span><span class="sxs-lookup"><span data-stu-id="6b04b-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="6b04b-118">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6b04b-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="6b04b-119">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="6b04b-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6b04b-120">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="6b04b-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="6b04b-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6b04b-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6b04b-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b04b-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="6b04b-123">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b04b-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="6b04b-124">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="6b04b-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="6b04b-125">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="6b04b-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
