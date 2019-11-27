---
title: 'Gewusst wie: Erstellen einer Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: a831814c18f97991fca8067f1c9c8e491da1b665
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344911"
---
# <a name="how-to-create-a-procedure-visual-basic"></a><span data-ttu-id="d2ffd-102">Gewusst wie: Erstellen einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2ffd-102">How to: Create a Procedure (Visual Basic)</span></span>

<span data-ttu-id="d2ffd-103">Sie schließen eine Prozedur zwischen einer Start Deklarations Anweisung (`Sub` oder `Function`) und einer Anweisung zum Beenden der Deklaration (`End Sub` oder `End Function`) ein.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-103">You enclose a procedure between a starting declaration statement (`Sub` or `Function`) and an ending declaration statement (`End Sub` or `End Function`).</span></span> <span data-ttu-id="d2ffd-104">Der gesamte Code der Prozedur liegt zwischen diesen Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-104">All the procedure's code lies between these statements.</span></span>

 <span data-ttu-id="d2ffd-105">Eine Prozedur kann keine andere Prozedur enthalten, sodass Ihre Start-und End-Anweisungen außerhalb anderer Prozeduren liegen müssen.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-105">A procedure cannot contain another procedure, so its starting and ending statements must be outside any other procedure.</span></span>

 <span data-ttu-id="d2ffd-106">Wenn Sie über Code verfügen, mit dem dieselbe Aufgabe an unterschiedlichen Stellen durchführt, können Sie die Aufgabe einmal als Prozedur schreiben und Sie dann von unterschiedlichen Stellen im Code aus aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-106">If you have code that performs the same task in different places, you can write the task once as a procedure and then call it from different places in your code.</span></span>

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a><span data-ttu-id="d2ffd-107">So erstellen Sie eine Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="d2ffd-107">To create a procedure that does not return a value</span></span>

1. <span data-ttu-id="d2ffd-108">Verwenden Sie außerhalb einer anderen Prozedur eine `Sub`-Anweisung, gefolgt von einer `End Sub`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-108">Outside any other procedure, use a `Sub` statement, followed by an `End Sub` statement.</span></span>

2. <span data-ttu-id="d2ffd-109">Befolgen Sie in der `Sub`-Anweisung das `Sub`-Schlüsselwort mit dem Namen der Prozedur und der Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-109">In the `Sub` statement, follow the `Sub` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>

3. <span data-ttu-id="d2ffd-110">Platzieren Sie die Code Anweisungen der Prozedur zwischen den Anweisungen `Sub` und `End Sub`.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-110">Place the procedure's code statements between the `Sub` and `End Sub` statements.</span></span>

### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="d2ffd-111">So erstellen Sie eine Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="d2ffd-111">To create a procedure that returns a value</span></span>

1. <span data-ttu-id="d2ffd-112">Verwenden Sie außerhalb einer anderen Prozedur eine `Function`-Anweisung, gefolgt von einer `End Function`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-112">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>

2. <span data-ttu-id="d2ffd-113">Befolgen Sie in der `Function`-Anweisung das `Function`-Schlüsselwort mit dem Namen der Prozedur, anschließend die Parameterliste in Klammern und dann eine `As`-Klausel, die den Datentyp des Rückgabewerts angibt.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-113">In the `Function` statement, follow the `Function` keyword with the name of the procedure, then the parameter list in parentheses, and then an `As` clause specifying the data type of the return value.</span></span>

3. <span data-ttu-id="d2ffd-114">Platzieren Sie die Code Anweisungen der Prozedur zwischen den Anweisungen `Function` und `End Function`.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-114">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>

4. <span data-ttu-id="d2ffd-115">Verwenden Sie eine `Return`-Anweisung, um den Wert an den aufrufenden Code zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-115">Use a `Return` statement to return the value to the calling code.</span></span>

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a><span data-ttu-id="d2ffd-116">So verbinden Sie die neue Prozedur mit den alten, sich wiederholenden Code Blöcken</span><span class="sxs-lookup"><span data-stu-id="d2ffd-116">To connect your new procedure with the old, repetitive blocks of code</span></span>

1. <span data-ttu-id="d2ffd-117">Stellen Sie sicher, dass Sie die neue Prozedur an einem Ort definieren, an dem der alte Code darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-117">Make sure you define the new procedure in a place where the old code has access to it.</span></span>

2. <span data-ttu-id="d2ffd-118">Ersetzen Sie in Ihrem alten, sich wiederholenden Codeblock die-Anweisungen, die die wiederkehrende Aufgabe ausführen, durch eine einzelne Anweisung, die die `Sub` oder `Function` Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-118">In your old, repetitive code block, replace the statements that perform the repetitive task with a single statement that calls the `Sub` or `Function` procedure.</span></span>

3. <span data-ttu-id="d2ffd-119">Wenn die Prozedur ein `Function` ist, der einen Wert zurückgibt, stellen Sie sicher, dass die aufrufende Anweisung eine Aktion mit dem zurückgegebenen Wert ausführt, z. b. Wenn Sie in einer Variablen gespeichert wird, oder wenn der Wert verloren geht.</span><span class="sxs-lookup"><span data-stu-id="d2ffd-119">If your procedure is a `Function` that returns a value, ensure that your calling statement performs an action with the returned value, such as storing it in a variable, or else the value will be lost.</span></span>

## <a name="example"></a><span data-ttu-id="d2ffd-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2ffd-120">Example</span></span>

 <span data-ttu-id="d2ffd-121">Mit der folgenden `Function` Prozedur wird die längste Seite (Hypotenuse) eines rechten Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="d2ffd-121">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides:</span></span>

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="d2ffd-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2ffd-122">See also</span></span>

- [<span data-ttu-id="d2ffd-123">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-123">Procedures</span></span>](index.md)
- [<span data-ttu-id="d2ffd-124">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-124">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="d2ffd-125">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-125">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="d2ffd-126">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-126">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="d2ffd-127">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-127">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="d2ffd-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-128">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d2ffd-129">Rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d2ffd-129">Recursive Procedures</span></span>](recursive-procedures.md)
- [<span data-ttu-id="d2ffd-130">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="d2ffd-130">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="d2ffd-131">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="d2ffd-131">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="d2ffd-132">Objektorientierte Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2ffd-132">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)
