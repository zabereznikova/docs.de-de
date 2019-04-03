---
title: Sub-Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: b70594e002bbf08f0890586e78df901ccb26c7ce
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843109"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="c6bca-102">Sub-Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6bca-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="c6bca-103">Ein `Sub` Prozedur ist eine Reihe von Visual Basic Anweisungen durch die `Sub` und `End Sub` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c6bca-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="c6bca-104">Die `Sub` Prozedur, eine Aufgabe ausführt, und klicken Sie dann die steuerelementrückgabe an den aufrufenden Code, aber es gibt einen Wert nicht an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="c6bca-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="c6bca-105">Jedes Mal, die die Prozedur aufgerufen wird, die Anweisungen ausgeführt wird, beginnend mit der ersten ausführbaren Anweisung nach der `Sub` -Anweisung und beendet mit dem ersten `End Sub`, `Exit Sub`, oder `Return` Anweisung wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="c6bca-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="c6bca-106">Sie können definieren, eine `Sub` Verfahren in Module, Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="c6bca-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="c6bca-107">Es wird standardmäßig `Public`, das bedeutet, dass aus aufrufen können sie überall in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, die in der Sie definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c6bca-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="c6bca-108">Der Begriff *Methode*, beschreibt eine `Sub` oder `Function` Prozedur, die aus, außerhalb dessen definieren zugegriffen wird-Modul, Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="c6bca-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="c6bca-109">Weitere Informationen finden Sie unter [Prozeduren](./index.md).</span><span class="sxs-lookup"><span data-stu-id="c6bca-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="c6bca-110">Ein `Sub` Argumenten, z. B. Konstanten, Variablen oder Ausdrücke, die an ihn, der aufrufende Code übergeben werden kann in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="c6bca-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="c6bca-111">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="c6bca-111">Declaration Syntax</span></span>  
 <span data-ttu-id="c6bca-112">Die Syntax zum Deklarieren einer `Sub` Verfahren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c6bca-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="c6bca-113">`[` *Modifizierer* `] Sub` *Subname* `[(` *Parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="c6bca-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="c6bca-114">Die `modifiers` Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing angeben können.</span><span class="sxs-lookup"><span data-stu-id="c6bca-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="c6bca-115">Weitere Informationen finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c6bca-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="c6bca-116">Parameterdeklaration</span><span class="sxs-lookup"><span data-stu-id="c6bca-116">Parameter Declaration</span></span>  
 <span data-ttu-id="c6bca-117">Jeder Prozedurparameter auf ähnliche Weise wie Sie eine Variable deklarieren Angabe des Parametertyps und deklariert.</span><span class="sxs-lookup"><span data-stu-id="c6bca-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="c6bca-118">Sie können auch angeben, den Übergabemechanismus und gibt an, ob der Parameter optional ist oder ein Parameterarray.</span><span class="sxs-lookup"><span data-stu-id="c6bca-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="c6bca-119">Die Syntax für jeden Parameter in der Liste der Parameter lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c6bca-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="c6bca-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *Parametername*`As`*Datatype*</span><span class="sxs-lookup"><span data-stu-id="c6bca-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="c6bca-121">Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="c6bca-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="c6bca-122">Die Syntax zum Angeben der Standardwert ist wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c6bca-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="c6bca-123">`Optional [ByVal | ByRef]`  *Parametername*`As`*Datatype*`=`*Defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="c6bca-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="c6bca-124">Parameter als lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="c6bca-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="c6bca-125">Wenn die Steuerung an die Prozedur übergeben, wird jeder Parameter als lokale Variable behandelt.</span><span class="sxs-lookup"><span data-stu-id="c6bca-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="c6bca-126">Dies bedeutet, dass seine Lebensdauer identisch mit der Prozedur ist und der Bereich die ganze Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="c6bca-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="c6bca-127">Die Syntax aufrufen</span><span class="sxs-lookup"><span data-stu-id="c6bca-127">Calling Syntax</span></span>  
 <span data-ttu-id="c6bca-128">Rufen Sie eine `Sub` Prozedur explizit mit einer eigenständigen aufrufenden Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c6bca-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="c6bca-129">Sie können nicht durch die Verwendung des Namens in einem Ausdruck aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c6bca-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="c6bca-130">Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="c6bca-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="c6bca-131">Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="c6bca-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="c6bca-132">Die Verwendung der `Call` Schlüsselwort ist optional, jedoch nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="c6bca-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="c6bca-133">Die Syntax für einen Aufruf einer `Sub` Verfahren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c6bca-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="c6bca-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="c6bca-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="c6bca-135">Rufen Sie eine `Sub` Methode außerhalb der Klasse, die es definiert.</span><span class="sxs-lookup"><span data-stu-id="c6bca-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="c6bca-136">Zunächst müssen Sie mit der `New` Schlüsselwort, erstellen Sie eine Instanz der Klasse oder eine Methode aufrufen, gibt eine Instanz der Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="c6bca-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="c6bca-137">Weitere Informationen finden Sie unter [neuer Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c6bca-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="c6bca-138">Anschließend können die folgende Syntax zum Aufrufen der `Sub` Methode für das Instance-Objekt:</span><span class="sxs-lookup"><span data-stu-id="c6bca-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="c6bca-139">*Objekt*. *MethodName*`[(`*Argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="c6bca-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="c6bca-140">Abbildung der Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="c6bca-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="c6bca-141">Die folgenden `Sub` -Prozedur meldet die welche Aufgabe die Anwendung ausführen, sowie einen Zeitstempel an.</span><span class="sxs-lookup"><span data-stu-id="c6bca-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="c6bca-142">Statt diesen Code am Anfang jeder Aufgabe zu wiederholen, ruft die Anwendung nur `tellOperator` an verschiedenen Standorten.</span><span class="sxs-lookup"><span data-stu-id="c6bca-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="c6bca-143">Jeder Aufruf übergibt eine Zeichenfolge in die `task` Argument, das die gestartete Aufgabe identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c6bca-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="c6bca-144">Das folgende Beispiel zeigt einen typischen Aufruf von `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="c6bca-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c6bca-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6bca-145">See also</span></span>

- [<span data-ttu-id="c6bca-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="c6bca-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c6bca-147">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c6bca-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="c6bca-148">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="c6bca-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="c6bca-149">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="c6bca-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="c6bca-150">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c6bca-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c6bca-151">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c6bca-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="c6bca-152">Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="c6bca-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="c6bca-153">Vorgehensweise: Aufrufen eines Ereignishandlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c6bca-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
