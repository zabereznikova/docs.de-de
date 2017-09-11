---
title: "Gewusst wie: Aufrufen einer Prozedur, die einen Wert (Visual Basic) zurückgibt. | Microsoft-Dokumentation"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
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
ms.openlocfilehash: cc1e274a705618213c830d7cf4f61a5e64afd980
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="f8f46-102">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8f46-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="f8f46-103">Ein `Function` Verfahren gibt einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="f8f46-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="f8f46-104">Rufen Sie sie einschließlich Name und Argumenten auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f8f46-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="f8f46-105">Zum Aufrufen einer Funktionsprozedur innerhalb eines Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="f8f46-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="f8f46-106">Verwenden Sie die `Function` Prozedur benennen Sie die gleiche Weise verwenden Sie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="f8f46-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="f8f46-107">Sie können eine `Function` Prozeduraufruf anywhere können Sie eine Variable oder Konstante in einem Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8f46-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="f8f46-108">Führen Sie den Namen der Prozedur mit Klammern um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="f8f46-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f8f46-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="f8f46-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="f8f46-110">Allerdings vereinfacht die Verwendung der Klammern Code leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f8f46-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="f8f46-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="f8f46-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f8f46-112">Stellen Sie sicher, geben Sie die Argumente in der gleichen Reihenfolge, die `Function` -Prozedur die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="f8f46-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="f8f46-113">Alternativ können Sie ein oder mehrere Argumente nach Namen übergeben.</span><span class="sxs-lookup"><span data-stu-id="f8f46-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="f8f46-114">Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="f8f46-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="f8f46-115">Der von der Prozedur zurückgegebene Wert ist Teil des Ausdrucks ebenso wie der Wert einer Variablen oder Konstante.</span><span class="sxs-lookup"><span data-stu-id="f8f46-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="f8f46-116">Zum Aufrufen einer Funktionsprozedur in eine Zuweisung</span><span class="sxs-lookup"><span data-stu-id="f8f46-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="f8f46-117">Verwenden der `Function` Name der Prozedur nach dem Gleichheitszeichen (`=`) melden Sie sich bei der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="f8f46-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="f8f46-118">Führen Sie den Namen der Prozedur mit Klammern um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="f8f46-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="f8f46-119">Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="f8f46-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="f8f46-120">Allerdings vereinfacht die Verwendung der Klammern Code leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f8f46-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="f8f46-121">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="f8f46-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="f8f46-122">Stellen Sie sicher, geben Sie die Argumente in der Reihenfolge, die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie über den Namen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8f46-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="f8f46-123">Der von der Prozedur zurückgegebene Wert ist in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f8f46-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8f46-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8f46-124">Example</span></span>  
 <span data-ttu-id="f8f46-125">Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>zum Abrufen des Werts einer Betriebssystem-Umgebungsvariablen.</xref:Microsoft.VisualBasic.Interaction.Environ%2A></span><span class="sxs-lookup"><span data-stu-id="f8f46-125">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="f8f46-126">Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks und die zweite Zeile ruft sie in eine Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="f8f46-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="f8f46-127">`Environ`erfordert den Variablennamen als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="f8f46-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="f8f46-128">Der Wert der Variablen zurückgegeben an den aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="f8f46-128">It returns the variable's value to the calling code.</span></span>  
  
 <span data-ttu-id="f8f46-129">[!code-vb[VbVbcnProcedures&#7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f8f46-129">[!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f46-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8f46-130">See Also</span></span>  
 <span data-ttu-id="f8f46-131">[Function-Prozeduren](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="f8f46-131">[Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="f8f46-132"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="f8f46-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="f8f46-133"> [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f8f46-133"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="f8f46-134"> [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="f8f46-134"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="f8f46-135"> [Gewusst wie: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="f8f46-135"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="f8f46-136"> [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="f8f46-136"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
