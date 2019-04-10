---
title: 'Vorgehensweise: Erstellen Sie eine Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 56099d334a03e85b816cf48983cbbead0784ef5b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320391"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="085c4-102">Vorgehensweise: Erstellen Sie eine Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="085c4-102">How to: Create a Procedure (Visual Basic)</span></span>
<span data-ttu-id="085c4-103">Schließen Sie eine Prozedur zwischen einer deklarationsanweisung ab (`Sub` oder `Function`) und eine abschließende deklarationsanweisung (`End Sub` oder `End Function`).</span><span class="sxs-lookup"><span data-stu-id="085c4-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="085c4-104">Alle der Prozedur bei der Code liegt zwischen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="085c4-104">All the procedure's code lies between these statements.</span></span>  
  
 <span data-ttu-id="085c4-105">Eine Prozedur kann nicht einer anderen Prozedur enthalten, damit die Anfangs- und Endposition Anweisungen außerhalb einer anderen Prozedur sein müssen.</span><span class="sxs-lookup"><span data-stu-id="085c4-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>  
  
 <span data-ttu-id="085c4-106">Wenn Sie über Code, die an verschiedenen Positionen in die gleiche Aufgabe ausführt verfügen, können Sie die Aufgabe einmal als Prozedur schreiben, und rufen es dann aus unterschiedlichen Quellen in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="085c4-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="085c4-107">Zum Erstellen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="085c4-107">To create a procedure that does not return a value</span></span>  
  
1. <span data-ttu-id="085c4-108">Verwendung außerhalb anderer Prozeduren ein `Sub` -Anweisung, gefolgt von einer `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="085c4-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="085c4-109">In der `Sub` -Anweisung, führen Sie die `Sub` Schlüsselwort durch den Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern angegeben.</span><span class="sxs-lookup"><span data-stu-id="085c4-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="085c4-110">Platzieren Sie Anweisungen von der Prozedur bei der Code zwischen den `Sub` und `End Sub` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="085c4-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="085c4-111">Zum Erstellen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="085c4-111">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="085c4-112">Verwendung außerhalb anderer Prozeduren ein `Function` -Anweisung, gefolgt von einer `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="085c4-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="085c4-113">In der `Function` -Anweisung, führen Sie die `Function` Schlüsselwort durch den Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern ein, und klicken Sie dann eine `As` -Klausel, die den Datentyp des Rückgabewerts angibt.</span><span class="sxs-lookup"><span data-stu-id="085c4-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>  
  
3. <span data-ttu-id="085c4-114">Platzieren Sie Anweisungen von der Prozedur bei der Code zwischen den `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="085c4-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
4. <span data-ttu-id="085c4-115">Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="085c4-115">Use a `Return` statement to return the value to the calling code.</span></span>  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="085c4-116">Ihre neue Prozedur mit der alten, sich wiederholenden Codeblöcke verbinden</span><span class="sxs-lookup"><span data-stu-id="085c4-116">To connect your new procedure with the old, repetitive blocks of code</span></span>  
  
1. <span data-ttu-id="085c4-117">Stellen Sie sicher, dass Sie die neue Prozedur an einer Stelle definieren, in denen der alte Code darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="085c4-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>  
  
2. <span data-ttu-id="085c4-118">Ersetzen Sie in Ihrer alten, sich wiederholenden Codeblock, die Anweisungen, die die sich wiederholende Aufgabe mit einer einzigen Anweisung ausführen, die Aufrufe der `Sub` oder `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="085c4-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>  
  
3. <span data-ttu-id="085c4-119">Wenn die Prozedur ist eine `Function` , die einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung führt eine Aktion mit dem zurückgegebenen Wert, z. B. in einer Variablen speichern oder andernfalls der Wert verloren.</span><span class="sxs-lookup"><span data-stu-id="085c4-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="085c4-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="085c4-120">Example</span></span>  
 <span data-ttu-id="085c4-121">Die folgenden `Function` Prozedur berechnet werden, die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.</span><span class="sxs-lookup"><span data-stu-id="085c4-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="085c4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="085c4-122">See also</span></span>

- [<span data-ttu-id="085c4-123">Verfahren</span><span class="sxs-lookup"><span data-stu-id="085c4-123">Procedures</span></span>](./index.md)
- [<span data-ttu-id="085c4-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="085c4-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="085c4-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="085c4-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="085c4-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="085c4-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="085c4-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="085c4-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="085c4-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="085c4-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="085c4-129">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="085c4-129">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="085c4-130">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="085c4-130">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="085c4-131">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="085c4-131">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="085c4-132">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="085c4-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
