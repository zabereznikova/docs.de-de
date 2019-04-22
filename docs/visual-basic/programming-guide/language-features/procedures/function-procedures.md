---
title: Function-Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 568489d6034316e895cd999801241fa995aadefa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834243"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="77c28-102">Function-Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77c28-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="77c28-103">Ein `Function` Prozedur ist eine Reihe von Visual Basic Anweisungen durch die `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="77c28-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="77c28-104">Die `Function` Prozedur führt eine Aufgabe aus und gibt dann die Steuerung an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="77c28-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="77c28-105">Wenn er die Steuerung zurückgibt, gibt es auch einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="77c28-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="77c28-106">Jedes Mal, die die Prozedur aufgerufen wird, werden die Anweisungen ausgeführt werden, wobei die erste ausführbare Anweisung nach der `Function` -Anweisung und beendet mit dem ersten `End Function`, `Exit Function`, oder `Return` Anweisung wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="77c28-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="77c28-107">Sie können definieren, eine `Function` Prozedur in einem Modul, Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="77c28-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="77c28-108">Es ist `Public` standardmäßig also können Sie ihn aufrufen, von überall aus in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, die in der Sie definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="77c28-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="77c28-109">Ein `Function` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="77c28-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="77c28-110">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="77c28-110">Declaration Syntax</span></span>  
 <span data-ttu-id="77c28-111">Die Syntax zum Deklarieren einer `Function` Verfahren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="77c28-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="77c28-112">Die *Modifizierer* Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing angeben können.</span><span class="sxs-lookup"><span data-stu-id="77c28-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="77c28-113">Weitere Informationen finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77c28-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="77c28-114">Jeder Parameter deklariert die gleiche Weise für [Sub-Prozeduren](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="77c28-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="77c28-115">Datentyp</span><span class="sxs-lookup"><span data-stu-id="77c28-115">Data Type</span></span>  
 <span data-ttu-id="77c28-116">Jede `Function` Prozedur verfügt über einen Datentyp, ebenso wie Variablen verfügt.</span><span class="sxs-lookup"><span data-stu-id="77c28-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="77c28-117">Dieser Datentyp wird angegeben, durch die `As` -Klausel in der `Function` -Anweisung, und bestimmt den Datentyp des Werts an die Funktion an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="77c28-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="77c28-118">Die folgenden Beispieldeklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="77c28-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="77c28-119">Weitere Informationen finden Sie unter "Teile" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77c28-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="77c28-120">Zurückgeben von Werten</span><span class="sxs-lookup"><span data-stu-id="77c28-120">Returning Values</span></span>  
 <span data-ttu-id="77c28-121">Der Wert einer `Function` sendet zurück an den aufrufenden Code wird den Rückgabewert aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="77c28-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="77c28-122">Die Prozedur gibt diesen Wert zurück, auf zwei Arten:</span><span class="sxs-lookup"><span data-stu-id="77c28-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="77c28-123">Er verwendet den `Return` Anweisung an den Rückgabewert, und gibt die Steuerung wird sofort an das aufrufende Programm.</span><span class="sxs-lookup"><span data-stu-id="77c28-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="77c28-124">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="77c28-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="77c28-125">Es wird eine eigene Funktionsnamen in eine oder mehrere Anweisungen der Prozedur ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="77c28-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="77c28-126">Steuerung wird nicht zurückgegeben, an das aufrufende Programm, bis ein `Exit Function` oder `End Function` -Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="77c28-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="77c28-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="77c28-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="77c28-128">Der Vorteil, den Namen der Funktion den Rückgabewert zugewiesen ist, dass das Steuerelement nicht von der Prozedur erst zurückgegeben wird, es findet ein `Exit Function` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="77c28-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="77c28-129">Dadurch können Sie einen vorläufigen Wert zuweisen, und sie später bei Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="77c28-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="77c28-130">Weitere Informationen zur Rückgabe von Werten finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77c28-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="77c28-131">Informationen zur Rückgabe von Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="77c28-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="77c28-132">Die Syntax aufrufen</span><span class="sxs-lookup"><span data-stu-id="77c28-132">Calling Syntax</span></span>  
 <span data-ttu-id="77c28-133">Rufen Sie eine `Function` Prozedur einschließlich der Namen und die Argumente, die entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="77c28-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="77c28-134">Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="77c28-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="77c28-135">Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="77c28-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="77c28-136">Die Syntax für einen Aufruf einer `Function` Verfahren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="77c28-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="77c28-137">*l-Wert*`=`*Functionname* `[(` *Argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="77c28-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="77c28-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span><span class="sxs-lookup"><span data-stu-id="77c28-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="77c28-139">Beim Aufruf einer `Function` vor, Sie müssen nicht den Rückgabewert zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="77c28-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="77c28-140">Wenn Sie dies nicht tun, werden alle Aktionen der Funktion ausgeführt, aber der Rückgabewert wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="77c28-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="77c28-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> auf diese Weise wird häufig aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="77c28-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="77c28-142">Abbildung der Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="77c28-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="77c28-143">Die folgenden `Function` Prozedur berechnet werden, die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.</span><span class="sxs-lookup"><span data-stu-id="77c28-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="77c28-144">Das folgende Beispiel zeigt einen typischen Aufruf von `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="77c28-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="77c28-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77c28-145">See also</span></span>

- [<span data-ttu-id="77c28-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="77c28-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="77c28-147">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="77c28-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="77c28-148">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="77c28-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="77c28-149">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="77c28-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="77c28-150">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="77c28-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="77c28-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="77c28-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="77c28-152">Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="77c28-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="77c28-153">Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="77c28-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="77c28-154">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="77c28-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
