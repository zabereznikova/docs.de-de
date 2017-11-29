---
title: "Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f6d408eed67fa417f42252bb49ecea28d4458382
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="ca864-102">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca864-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="ca864-103">Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="ca864-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="ca864-104">Rufen Sie sie einschließlich Name und Argumente entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ca864-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="ca864-105">Aufrufen eine Funktionsprozedur innerhalb eines Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="ca864-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="ca864-106">Verwenden Sie die `Function` Prozedur benennen Sie die gleiche Weise verwenden Sie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="ca864-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="ca864-107">Sie können eine `Function` Prozeduraufruf anywhere können Sie eine Variable oder Konstante in einem Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca864-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="ca864-108">Führen Sie den Namen der Prozedur mit Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="ca864-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="ca864-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="ca864-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="ca864-110">Allerdings besser mit den Klammern Code lesen.</span><span class="sxs-lookup"><span data-stu-id="ca864-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="ca864-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="ca864-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="ca864-112">Achten Sie darauf geben Sie die Argumente in der gleichen Reihenfolge, die die `Function` Prozedur definiert, die entsprechenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="ca864-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="ca864-113">Alternativ können Sie anhand des Namens ein oder mehrere Argumente übergeben.</span><span class="sxs-lookup"><span data-stu-id="ca864-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="ca864-114">Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="ca864-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="ca864-115">Von der Prozedur zurückgegebene Wert ist Teil des Ausdrucks wie den Wert einer Variablen oder Konstante.</span><span class="sxs-lookup"><span data-stu-id="ca864-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="ca864-116">Aufrufen einer Funktion in einer zuweisungsanweisung</span><span class="sxs-lookup"><span data-stu-id="ca864-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="ca864-117">Verwenden der `Function` Prozedurnamen nach dem Gleichheitszeichen (`=`) die zuweisungsanweisung anmelden.</span><span class="sxs-lookup"><span data-stu-id="ca864-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="ca864-118">Führen Sie den Namen der Prozedur mit Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="ca864-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="ca864-119">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="ca864-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="ca864-120">Allerdings besser mit den Klammern Code lesen.</span><span class="sxs-lookup"><span data-stu-id="ca864-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="ca864-121">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="ca864-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="ca864-122">Achten Sie darauf geben Sie die Argumente in der gleichen Reihenfolge, die die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie werden anhand des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="ca864-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="ca864-123">Der von der Prozedur zurückgegebene Wert ist in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ca864-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca864-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca864-124">Example</span></span>  
 <span data-ttu-id="ca864-125">Im folgenden Beispiel wird die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> zum Abrufen des Werts einer Betriebssystem-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="ca864-125">The following example calls the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="ca864-126">Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks und die zweite Zeile ruft er in einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="ca864-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="ca864-127">`Environ`akzeptiert den Variablennamen als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="ca864-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="ca864-128">Es gibt den Wert der Variablen an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="ca864-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ca864-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca864-129">See Also</span></span>  
 [<span data-ttu-id="ca864-130">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ca864-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="ca864-131">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ca864-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ca864-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ca864-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="ca864-133">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="ca864-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="ca864-134">Gewusst wie: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="ca864-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="ca864-135">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="ca864-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
