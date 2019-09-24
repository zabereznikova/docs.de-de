---
title: 'Vorgehensweise: Erstellen einer Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216722"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="9d157-102">Vorgehensweise: Erstellen einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d157-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="9d157-103">Sie schließen eine Prozedur zwischen einer Anweisung zum Starten der Deklaration `Function`(`Sub` oder) und einer endedeklarations Anweisung (`End Sub` oder `End Function`) ein.</span><span class="sxs-lookup"><span data-stu-id="9d157-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="9d157-104">Der gesamte Code der Prozedur liegt zwischen diesen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="9d157-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="9d157-105">Eine Prozedur kann keine andere Prozedur enthalten, sodass Ihre Start-und End-Anweisungen außerhalb anderer Prozeduren liegen müssen.</span><span class="sxs-lookup"><span data-stu-id="9d157-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="9d157-106">Wenn Sie über Code verfügen, mit dem dieselbe Aufgabe an unterschiedlichen Stellen durchführt, können Sie die Aufgabe einmal als Prozedur schreiben und Sie dann von unterschiedlichen Stellen im Code aus aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9d157-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="9d157-107">So erstellen Sie eine Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="9d157-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="9d157-108">Verwenden Sie außerhalb einer anderen Prozedur eine `Sub` -Anweisung, gefolgt von `End Sub` einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9d157-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="9d157-109">Befolgen Sie `Sub` in der-Anweisung `Sub` das-Schlüsselwort mit dem Namen der Prozedur und der Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="9d157-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="9d157-110">Platzieren Sie die Code Anweisungen der Prozedur zwischen `Sub` der `End Sub` -Anweisung und der-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9d157-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="9d157-111">So erstellen Sie eine Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="9d157-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="9d157-112">Verwenden Sie außerhalb einer anderen Prozedur eine `Function` -Anweisung, gefolgt von `End Function` einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9d157-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="9d157-113">Befolgen Sie `Function` in der-Anweisung `Function` das-Schlüsselwort mit dem Namen der Prozedur, anschließend die Parameterliste in Klammern und eine `As` -Klausel, die den Datentyp des Rückgabewerts angibt.</span><span class="sxs-lookup"><span data-stu-id="9d157-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="9d157-114">Platzieren Sie die Code Anweisungen der Prozedur zwischen `Function` der `End Function` -Anweisung und der-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9d157-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="9d157-115">Verwenden Sie `Return` eine-Anweisung, um den Wert an den aufrufenden Code zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="9d157-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="9d157-116">So verbinden Sie die neue Prozedur mit den alten, sich wiederholenden Code Blöcken</span><span class="sxs-lookup"><span data-stu-id="9d157-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="9d157-117">Stellen Sie sicher, dass Sie die neue Prozedur an einem Ort definieren, an dem der alte Code darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9d157-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="9d157-118">Ersetzen Sie in Ihrem alten, sich wiederholenden Codeblock die-Anweisungen, die die wiederkehrende Aufgabe ausführen, durch `Sub` eine `Function` einzelne Anweisung, die die-oder-Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="9d157-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="9d157-119">Wenn Ihre Prozedur eine `Function` ist, die einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung eine Aktion mit dem zurückgegebenen Wert ausführt, z. b. Wenn Sie in einer Variablen gespeichert wird. Andernfalls geht der Wert verloren.</span><span class="sxs-lookup"><span data-stu-id="9d157-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="9d157-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9d157-120">Example</span></span>

 <span data-ttu-id="9d157-121">Im folgenden `Function` Verfahren wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="9d157-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="9d157-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d157-122">See also</span></span>

- [<span data-ttu-id="9d157-123">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9d157-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="9d157-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9d157-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="9d157-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9d157-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="9d157-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="9d157-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="9d157-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="9d157-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="9d157-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9d157-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9d157-129">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9d157-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="9d157-130">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="9d157-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="9d157-131">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="9d157-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="9d157-132">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d157-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
