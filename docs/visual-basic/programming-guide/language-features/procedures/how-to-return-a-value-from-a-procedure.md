---
title: 'Vorgehensweise: Abrufen eines Werts aus einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: cbc785a07aa8a7b299508a093e08d5d0510b838a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071377"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="51f27-102">Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51f27-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>

<span data-ttu-id="51f27-103">Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück, indem entweder eine-Anweisung ausgeführt wird `Return` oder eine- `Exit Function` oder-Anweisung auftritt `End Function` .</span><span class="sxs-lookup"><span data-stu-id="51f27-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="51f27-104">So geben Sie einen Wert mit der Return-Anweisung zurück</span><span class="sxs-lookup"><span data-stu-id="51f27-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="51f27-105">Legen Sie eine `Return` -Anweisung an der Stelle ab, an der die Aufgabe der Prozedur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="51f27-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="51f27-106">Befolgen Sie das- `Return` Schlüsselwort mit einem Ausdruck, der den Wert ergibt, den Sie an den aufrufenden Code zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="51f27-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="51f27-107">Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="51f27-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="51f27-108">Mit der folgenden `Function` Prozedur wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet und an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="51f27-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="51f27-109">Das folgende Beispiel zeigt einen typischen- `hypotenuse` Aufrufwert, der den zurückgegebenen Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="51f27-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="51f27-110">So geben Sie einen Wert mit der Funktion Exit oder End</span><span class="sxs-lookup"><span data-stu-id="51f27-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="51f27-111">Weisen Sie in der Prozedur mindestens einen `Function` -Wert dem Namen der Prozedur zu.</span><span class="sxs-lookup"><span data-stu-id="51f27-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="51f27-112">Wenn Sie eine- `Exit Function` oder `End Function` -Anweisung ausführen, gibt Visual Basic den Wert zurück, der zuletzt dem Namen der Prozedur zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="51f27-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="51f27-113">Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="51f27-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="51f27-114">Sie können nur eine- `End Function` Anweisung in einer- `Function` Prozedur haben.</span><span class="sxs-lookup"><span data-stu-id="51f27-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="51f27-115">Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in der [Function-Anweisung](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="51f27-115">For more information and an example, see "Return Value" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f27-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51f27-116">See also</span></span>

- [<span data-ttu-id="51f27-117">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="51f27-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="51f27-118">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="51f27-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="51f27-119">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="51f27-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="51f27-120">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="51f27-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="51f27-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="51f27-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="51f27-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="51f27-122">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="51f27-123">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="51f27-123">Return Statement</span></span>](../../../language-reference/statements/return-statement.md)
- [<span data-ttu-id="51f27-124">Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="51f27-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="51f27-125">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="51f27-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
