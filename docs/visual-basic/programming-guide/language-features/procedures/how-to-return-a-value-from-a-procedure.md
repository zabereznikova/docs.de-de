---
title: "Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce7aa0942be413986cb010963753447ea18cdf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="9a34e-102">Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a34e-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="9a34e-103">Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code entweder durch das Ausführen einer `Return` Anweisung oder beim Auftreten einer `Exit Function` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9a34e-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="9a34e-104">Einen Wert, der mithilfe der Return-Anweisung zurückgegeben</span><span class="sxs-lookup"><span data-stu-id="9a34e-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="9a34e-105">Versetzen einer `Return` Anweisung, an dem Punkt, bei dem die Aufgabe der Prozedur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9a34e-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="9a34e-106">Führen Sie die `Return` Schlüsselwort durch einen Ausdruck, der den Wert ergibt, an den aufrufenden Code zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a34e-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="9a34e-107">Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="9a34e-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="9a34e-108">Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, und gibt ihn an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="9a34e-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     <span data-ttu-id="9a34e-109">Das folgende Beispiel zeigt einen typischen Aufruf `hypotenuse`, die den zurückgegebenen Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="9a34e-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="9a34e-110">Einen Wert, der mit Exit Function oder End Function zurückgegeben</span><span class="sxs-lookup"><span data-stu-id="9a34e-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="9a34e-111">Mindestens ein direkt in die `Function` Prozedur, weisen Sie einen Wert, der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="9a34e-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="9a34e-112">Beim Ausführen einer `Exit Function` oder `End Function` -Anweisung [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gibt den Namen der Prozedur zuletzt zugewiesenen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="9a34e-112">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="9a34e-113">Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="9a34e-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="9a34e-114">Sie sind nur möglich `End Function` -Anweisung in einem `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="9a34e-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="9a34e-115">Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9a34e-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a34e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a34e-116">See Also</span></span>  
 [<span data-ttu-id="9a34e-117">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9a34e-117">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="9a34e-118">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9a34e-118">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="9a34e-119">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="9a34e-119">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="9a34e-120">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="9a34e-120">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="9a34e-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9a34e-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="9a34e-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9a34e-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="9a34e-123">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9a34e-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="9a34e-124">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="9a34e-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="9a34e-125">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="9a34e-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
