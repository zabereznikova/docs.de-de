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
ms.openlocfilehash: 887c930cb757b012542c97d64a57a62882a2eed3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655534"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="ad789-102">Function-Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad789-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="ad789-103">Ein `Function` Verfahren besteht aus einer Reihe von Visual Basic-Anweisungen von der `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ad789-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="ad789-104">Die `Function` Prozedur, eine Aufgabe ausführt, und klicken Sie dann die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad789-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="ad789-105">Wenn er die Steuerung zurückgibt, gibt es auch einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="ad789-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="ad789-106">Jedes Mal, die die Prozedur aufgerufen wird, werden die Anweisungen ausgeführt werden, beginnend mit der ersten ausführbaren Anweisung nach der `Function` -Anweisung und endet mit dem ersten `End Function`, `Exit Function`, oder `Return` Anweisung wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="ad789-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="ad789-107">Sie können definieren, eine `Function` Prozedur in einem Modul, Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="ad789-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="ad789-108">Es ist `Public` standardmäßig, d. h. Sie können von überall aus aufrufen in der Anwendung, die Zugriff auf das Modul, Klasse oder Struktur an, in dem Sie definiert, wurde.</span><span class="sxs-lookup"><span data-stu-id="ad789-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="ad789-109">Ein `Function` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="ad789-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="ad789-110">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="ad789-110">Declaration Syntax</span></span>  
 <span data-ttu-id="ad789-111">Die Syntax zum Deklarieren einer `Function` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ad789-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="ad789-112">Die *Modifizierer* Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing angeben können.</span><span class="sxs-lookup"><span data-stu-id="ad789-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="ad789-113">Weitere Informationen finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ad789-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="ad789-114">Deklarieren Sie jeden Parameter genauso wie Sie für [Sub-Prozeduren](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="ad789-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="ad789-115">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ad789-115">Data Type</span></span>  
 <span data-ttu-id="ad789-116">Jede `Function` Prozedur verfügt über einen Datentyp, ebenso wie Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="ad789-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="ad789-117">Dieser Datentyp wird angegeben, indem die `As` -Klausel in der `Function` -Anweisung, und er ermittelt den Datentyp des Werts, der die Funktion an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ad789-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="ad789-118">Die folgenden Beispieldeklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ad789-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="ad789-119">Weitere Informationen finden Sie unter "Teilen" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ad789-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="ad789-120">Zurückgeben von Werten</span><span class="sxs-lookup"><span data-stu-id="ad789-120">Returning Values</span></span>  
 <span data-ttu-id="ad789-121">Der Wert einer `Function` Prozedur sendet zurück an den aufrufenden Code den Rückgabewert aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ad789-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="ad789-122">Die Prozedur gibt diesen Wert zurück, auf zwei Arten:</span><span class="sxs-lookup"><span data-stu-id="ad789-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="ad789-123">Er verwendet die `Return` Anweisung an den Rückgabewert, und gibt die Steuerung wird sofort an das aufrufende Programm.</span><span class="sxs-lookup"><span data-stu-id="ad789-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="ad789-124">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ad789-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="ad789-125">Eigene Funktionsnamen in eine oder mehrere Anweisungen der Prozedur wird ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ad789-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="ad789-126">Steuerung ist nicht an das aufrufende Programm, bis ein `Exit Function` oder `End Function` -Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ad789-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="ad789-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ad789-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="ad789-128">Der Vorteil den Rückgabewert für den Namen der Funktion zuzuweisen ist die Steuerung erst gefundenen nicht aus der Prozedur zurückgegeben wird ein `Exit Function` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ad789-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="ad789-129">Dadurch können Sie einen vorläufigen Wert zuweisen und sie später bei Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="ad789-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="ad789-130">Weitere Informationen zum Zurückgeben von Werten finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ad789-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="ad789-131">Weitere Informationen zu Arrays zurückgeben, finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad789-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="ad789-132">Aufrufen der Syntax</span><span class="sxs-lookup"><span data-stu-id="ad789-132">Calling Syntax</span></span>  
 <span data-ttu-id="ad789-133">Rufen Sie eine `Function` Prozedur durch den Namen und die Argumente, die entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="ad789-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="ad789-134">Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="ad789-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="ad789-135">Wenn keine Argumente übergeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="ad789-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="ad789-136">Die Syntax für einen Aufruf einer `Function` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ad789-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="ad789-137">*Lvalue*`=`*Funktionsname* `[(` *Argumentlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="ad789-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="ad789-138">`If ((` *Funktionsname* `[(` *Argumentlist* `)] / 3) <=` *Ausdruck*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="ad789-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="ad789-139">Beim Aufruf einer `Function` Prozedur, Sie müssen nicht den Rückgabewert verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad789-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="ad789-140">Wenn Sie nicht alle Aktionen, die sich von der Funktion ausgeführt werden, aber der Rückgabewert wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ad789-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="ad789-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> auf diese Weise wird häufig aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ad789-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="ad789-142">Abbildung der Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="ad789-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="ad789-143">Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.</span><span class="sxs-lookup"><span data-stu-id="ad789-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 <span data-ttu-id="ad789-144">Das folgende Beispiel zeigt einen typischen Aufruf `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="ad789-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ad789-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad789-145">See Also</span></span>  
 [<span data-ttu-id="ad789-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="ad789-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ad789-147">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ad789-147">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="ad789-148">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="ad789-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="ad789-149">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="ad789-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="ad789-150">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="ad789-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ad789-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ad789-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="ad789-152">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="ad789-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="ad789-153">Gewusst wie: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="ad789-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="ad789-154">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="ad789-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
