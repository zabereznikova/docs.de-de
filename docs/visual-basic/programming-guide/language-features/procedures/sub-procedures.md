---
title: Sub-Prozeduren
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
ms.openlocfilehash: 7848dc07d6462622685cdbea92202585f4d5d2c4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352523"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="9f429-102">Sub-Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f429-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="9f429-103">Eine `Sub` Prozedur ist eine Reihe von Visual Basic Anweisungen, die von den Anweisungen `Sub` und `End Sub` eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="9f429-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="9f429-104">Die `Sub` Prozedur führt eine Aufgabe aus und gibt dann die Steuerung an den aufrufenden Code zurück, Sie gibt jedoch keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="9f429-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="9f429-105">Jedes Mal, wenn die Prozedur aufgerufen wird, werden die zugehörigen-Anweisungen ausgeführt, beginnend mit der ersten ausführbaren Anweisung nach der `Sub`-Anweisung und mit der ersten `End Sub`, `Exit Sub`oder `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9f429-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="9f429-106">Sie können eine `Sub` Prozedur in Modulen, Klassen und Strukturen definieren.</span><span class="sxs-lookup"><span data-stu-id="9f429-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="9f429-107">Standardmäßig ist es `Public`. Dies bedeutet, dass Sie es von überall in Ihrer Anwendung aufrufen können, das Zugriff auf das Modul, die Klasse oder die Struktur hat, in der Sie es definiert haben.</span><span class="sxs-lookup"><span data-stu-id="9f429-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="9f429-108">Der Begriff " *Methode*" beschreibt eine `Sub` oder `Function` Prozedur, auf die von außerhalb des definierenden Moduls, der Klasse oder Struktur zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9f429-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="9f429-109">Weitere Informationen finden Sie unter [Prozeduren](./index.md).</span><span class="sxs-lookup"><span data-stu-id="9f429-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="9f429-110">Eine `Sub` Prozedur kann Argumente, wie z. b. Konstanten, Variablen oder Ausdrücke, verwenden, die vom aufrufenden Code an ihn übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="9f429-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="9f429-111">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="9f429-111">Declaration Syntax</span></span>  
 <span data-ttu-id="9f429-112">Die Syntax zum Deklarieren einer `Sub` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9f429-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="9f429-113">`[` *Modifizierer* `] Sub`*untergeordneten Namen* `[(` *Parameter List* `)]`</span><span class="sxs-lookup"><span data-stu-id="9f429-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="9f429-114">Der `modifiers` kann die Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadoading angeben.</span><span class="sxs-lookup"><span data-stu-id="9f429-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="9f429-115">Weitere Informationen finden Sie [unter Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9f429-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="9f429-116">Parameter Deklaration</span><span class="sxs-lookup"><span data-stu-id="9f429-116">Parameter Declaration</span></span>  
 <span data-ttu-id="9f429-117">Sie deklarieren jeden Prozedur Parameter entsprechend der Art und Weise, wie Sie eine Variable deklarieren, indem Sie den Parameternamen und Datentyp angeben.</span><span class="sxs-lookup"><span data-stu-id="9f429-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="9f429-118">Sie können auch den Übergabe Mechanismus angeben und angeben, ob der Parameter optional ist, oder ein Parameter Array.</span><span class="sxs-lookup"><span data-stu-id="9f429-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="9f429-119">Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9f429-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="9f429-120">`[Optional] [ByVal | ByRef] [ParamArray]`*Parameter Name*`As`*Datentyp*</span><span class="sxs-lookup"><span data-stu-id="9f429-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="9f429-121">Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="9f429-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="9f429-122">Die Syntax zum Angeben eines Standardwerts lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9f429-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="9f429-123">`Optional [ByVal | ByRef]`*Parameter Name*`As`*Datentyp*`=`*DefaultValue*</span><span class="sxs-lookup"><span data-stu-id="9f429-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="9f429-124">Parameter als lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="9f429-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="9f429-125">Wenn die Steuerung an die Prozedur übergeben wird, wird jeder Parameter als lokale Variable behandelt.</span><span class="sxs-lookup"><span data-stu-id="9f429-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="9f429-126">Dies bedeutet, dass die Lebensdauer der Prozedur entspricht und ihr Bereich das gesamte Verfahren ist.</span><span class="sxs-lookup"><span data-stu-id="9f429-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="9f429-127">Aufruf Syntax</span><span class="sxs-lookup"><span data-stu-id="9f429-127">Calling Syntax</span></span>  
 <span data-ttu-id="9f429-128">Sie rufen eine `Sub` Prozedur explizit mit einer eigenständigen aufrufenden Anweisung auf.</span><span class="sxs-lookup"><span data-stu-id="9f429-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="9f429-129">Sie können Sie nicht mit dem Namen in einem Ausdruck abrufen.</span><span class="sxs-lookup"><span data-stu-id="9f429-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="9f429-130">Sie müssen Werte für alle nicht optionalen Argumente angeben, und Sie müssen die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="9f429-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="9f429-131">Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="9f429-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="9f429-132">Die Verwendung des `Call`-Schlüssel Worts ist optional, wird aber nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9f429-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="9f429-133">Die Syntax für einen aufzurufenden `Sub` Prozeduren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="9f429-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="9f429-134">`[Call]`*unter Name* `[(` *Argument List* `)]`</span><span class="sxs-lookup"><span data-stu-id="9f429-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="9f429-135">Sie können eine `Sub` Methode von außerhalb der Klasse, die Sie definiert, abrufen.</span><span class="sxs-lookup"><span data-stu-id="9f429-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="9f429-136">Zunächst müssen Sie das `New`-Schlüsselwort verwenden, um eine Instanz der-Klasse zu erstellen, oder eine Methode aufzurufen, die eine Instanz der-Klasse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9f429-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="9f429-137">Weitere Informationen finden Sie unter [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9f429-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="9f429-138">Anschließend können Sie die folgende Syntax verwenden, um die `Sub`-Methode für das Instanzobjekt aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="9f429-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="9f429-139">\- *Objekt*. *MethodName*`[(`*Argument List*`)]`</span><span class="sxs-lookup"><span data-stu-id="9f429-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="9f429-140">Abbildung der Deklaration und des Aufruf</span><span class="sxs-lookup"><span data-stu-id="9f429-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="9f429-141">Die folgende `Sub` Prozedur teilt dem Computer Operator mit, welche Aufgabe die Anwendung ausführt, und zeigt außerdem einen Zeitstempel an.</span><span class="sxs-lookup"><span data-stu-id="9f429-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="9f429-142">Anstatt diesen Code zu Beginn jeder Aufgabe zu duplizieren, ruft die Anwendung nur `tellOperator` von verschiedenen Speicherorten auf.</span><span class="sxs-lookup"><span data-stu-id="9f429-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="9f429-143">Jeder-Befehl übergibt eine Zeichenfolge in das `task`-Argument, das den zu startenden Task identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9f429-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="9f429-144">Das folgende Beispiel zeigt einen typischen `tellOperator`-Aufruf.</span><span class="sxs-lookup"><span data-stu-id="9f429-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9f429-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f429-145">See also</span></span>

- [<span data-ttu-id="9f429-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="9f429-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9f429-147">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9f429-147">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="9f429-148">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="9f429-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="9f429-149">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="9f429-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="9f429-150">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9f429-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9f429-151">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9f429-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="9f429-152">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="9f429-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [<span data-ttu-id="9f429-153">Gewusst wie: Abrufen eines Ereignis Handlers in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9f429-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
