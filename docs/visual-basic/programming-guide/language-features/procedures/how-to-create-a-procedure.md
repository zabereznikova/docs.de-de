---
title: 'Gewusst wie: Erstellen einer Prozedur (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a44918b7a1426d215cee0ff2981f5763432a48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="4f17a-102">Gewusst wie: Erstellen einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f17a-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="4f17a-103">Sie setzen eine Prozedur zwischen einer Start-deklarationsanweisung (`Sub` oder `Function`) und ein Enddatum deklarationsanweisung (`End Sub` oder `End Function`).</span><span class="sxs-lookup"><span data-stu-id="4f17a-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="4f17a-104">Alle Prozedur Code liegt zwischen diesen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4f17a-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="4f17a-105">Eine Prozedur kann nicht einer anderen Prozedur enthalten, damit die Start- und Enddatum Anweisungen außerhalb eine beliebige andere Prozedur sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4f17a-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="4f17a-106">Wenn Sie über Code, die an verschiedenen Positionen in die gleiche Aufgabe ausführt verfügen, können Sie die Aufgabe einmal als Prozedur schreiben, und von unterschiedlichen Stellen im Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4f17a-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="4f17a-107">So erstellen Sie eine Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="4f17a-107">To create a procedure that does not return a value</span></span>  
  
1.  <span data-ttu-id="4f17a-108">Außerhalb eine beliebige andere Prozedur verwendet eine `Sub` Anweisung, gefolgt von einem `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4f17a-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="4f17a-109">In der `Sub` -Anweisung, befolgen Sie die `Sub` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="4f17a-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="4f17a-110">Platzieren Sie die Prozedur codeanweisungen zwischen der `Sub` und `End Sub` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4f17a-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="4f17a-111">So erstellen Sie eine Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="4f17a-111">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="4f17a-112">Außerhalb eine beliebige andere Prozedur verwendet eine `Function` Anweisung, gefolgt von einem `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4f17a-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="4f17a-113">In der `Function` -Anweisung, befolgen Sie die `Function` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern ein, und klicken Sie dann eine `As` -Klausel, in den Datentyp des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="4f17a-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3.  <span data-ttu-id="4f17a-114">Platzieren Sie die Prozedur codeanweisungen zwischen der `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4f17a-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4.  <span data-ttu-id="4f17a-115">Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4f17a-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="4f17a-116">Eine neue Prozedur mit alten, wiederkehrende Codeblöcke verbinden</span><span class="sxs-lookup"><span data-stu-id="4f17a-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1.  <span data-ttu-id="4f17a-117">Stellen Sie sicher, dass Sie die neue Prozedur an einer Stelle definieren, in denen der alte Code kann zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4f17a-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2.  <span data-ttu-id="4f17a-118">Ersetzen Sie in Ihrer alten, wiederkehrende Codeblock, der Anweisungen, die sich wiederholende Aufgabe mit einer einzigen Anweisung durchführen, die aufruft der `Sub` oder `Function` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4f17a-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3.  <span data-ttu-id="4f17a-119">Wenn die Prozedur ist eine `Function` , die einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung führt eine Aktion mit dem zurückgegebenen Wert, z. B. in einer Variablen speichern, sonst wird der Wert verloren.</span><span class="sxs-lookup"><span data-stu-id="4f17a-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f17a-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f17a-120">Example</span></span>  
 <span data-ttu-id="4f17a-121">Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.</span><span class="sxs-lookup"><span data-stu-id="4f17a-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4f17a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f17a-122">See Also</span></span>  
 [<span data-ttu-id="4f17a-123">Verfahren</span><span class="sxs-lookup"><span data-stu-id="4f17a-123">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="4f17a-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4f17a-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="4f17a-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4f17a-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="4f17a-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="4f17a-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="4f17a-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="4f17a-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="4f17a-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4f17a-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="4f17a-129">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4f17a-129">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="4f17a-130">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="4f17a-130">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="4f17a-131">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="4f17a-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="4f17a-132">Objektorientierte Programmierung</span><span class="sxs-lookup"><span data-stu-id="4f17a-132">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
