---
title: Sub-Prozeduren (Visual Basic) | Microsoft-Dokumentation
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
- Sub procedures, about Sub procedures
- statement blocks
- Sub procedures, calling
- procedures, calling
- Sub procedures, syntax
- Sub procedures
- procedures, Sub
- syntax, Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
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
ms.openlocfilehash: 83f0a16498accf383da96d702c4e3a4b7de1c861
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="16c81-102">Sub-Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16c81-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="16c81-103">Ein `Sub` Prozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anweisungen, die durch die `Sub` und `End Sub` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="16c81-103">A `Sub` procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="16c81-104">Die `Sub` Prozedur eine Aufgabe ausführt, und dann wird die Steuerung an den aufrufenden Code zurückgegeben, aber keinen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="16c81-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="16c81-105">Jedes Mal die Prozedur aufgerufen wird, die Anweisungen ausgeführt werden, beginnend mit der ersten ausführbaren Anweisung nach der `Sub` -Anweisung und endet mit dem ersten `End Sub`, `Exit Sub`, oder `Return` Anweisung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="16c81-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="16c81-106">Sie können eine `Sub` Verfahren in Modulen, Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="16c81-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="16c81-107">In der Standardeinstellung ist `Public`, womit Sie können ihn Aufrufen von überall in Ihrer Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, in der Sie definiert, wurde.</span><span class="sxs-lookup"><span data-stu-id="16c81-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="16c81-108">Der Begriff *Methode*, beschreibt eine `Sub` oder `Function` -Prozedur, die außerhalb der definieren aus zugegriffen werden kann-Modul, die Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="16c81-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="16c81-109">Weitere Informationen finden Sie unter [Prozeduren](./index.md).</span><span class="sxs-lookup"><span data-stu-id="16c81-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="16c81-110">Ein `Sub` -Prozeduren können Argumente, wie z. B. Konstanten, Variablen oder Ausdrücke, die durch den Aufrufcode an sie übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="16c81-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="16c81-111">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="16c81-111">Declaration Syntax</span></span>  
 <span data-ttu-id="16c81-112">Die Syntax zum Deklarieren einer `Sub` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="16c81-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="16c81-113">`[`*modifiers* `] Sub`*subname* `[(` *parameterlist*  `)]`</span><span class="sxs-lookup"><span data-stu-id="16c81-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="16c81-114">Die `modifiers` können Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing angeben.</span><span class="sxs-lookup"><span data-stu-id="16c81-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="16c81-115">Weitere Informationen finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="16c81-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="16c81-116">Parameterdeklaration</span><span class="sxs-lookup"><span data-stu-id="16c81-116">Parameter Declaration</span></span>  
 <span data-ttu-id="16c81-117">Sie deklarieren jeder Prozedurparameter wird auf ähnliche Weise, wie Sie eine Variable deklarieren, den Parametertyp und den Datentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="16c81-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="16c81-118">Sie können auch angeben, den Mechanismus übergeben, und gibt an, ob der Parameter optional ist oder ein Parameterarray.</span><span class="sxs-lookup"><span data-stu-id="16c81-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="16c81-119">Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="16c81-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="16c81-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *Parametername*`As`*Datentyp    *</span><span class="sxs-lookup"><span data-stu-id="16c81-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="16c81-121">Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="16c81-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="16c81-122">Die Syntax zum Angeben der Standardwert lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="16c81-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="16c81-123">`Optional [ByVal | ByRef]`  *Parametername*`As`*Datentyp*`=`*Defaultvalue        *</span><span class="sxs-lookup"><span data-stu-id="16c81-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="16c81-124">Parameter als lokale Variablen</span><span class="sxs-lookup"><span data-stu-id="16c81-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="16c81-125">Wenn die Steuerung an die Prozedur übergeben wird, wird jeder Parameter als lokale Variable behandelt.</span><span class="sxs-lookup"><span data-stu-id="16c81-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="16c81-126">Dies bedeutet, dass seine Lebensdauer identisch mit der Prozedur ist, und der Gültigkeitsbereich die gesamte Prozedur ist.</span><span class="sxs-lookup"><span data-stu-id="16c81-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="16c81-127">Aufrufen der Syntax</span><span class="sxs-lookup"><span data-stu-id="16c81-127">Calling Syntax</span></span>  
 <span data-ttu-id="16c81-128">Rufen Sie eine `Sub` Prozedur explizit mit dem eigenständigen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="16c81-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="16c81-129">Sie können nicht durch die Verwendung des Namens in einem Ausdruck aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="16c81-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="16c81-130">Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="16c81-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="16c81-131">Wenn keine Argumente angegeben sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="16c81-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="16c81-132">Die Verwendung der `Call` -Schlüsselwort ist optional, wird aber empfohlen.</span><span class="sxs-lookup"><span data-stu-id="16c81-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="16c81-133">Die Syntax für einen Aufruf einer `Sub` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="16c81-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="16c81-134">`[Call]`  *Subname* `[(` *Argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="16c81-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="16c81-135">Rufen Sie eine `Sub` -Methode außerhalb der Klasse, die es definiert.</span><span class="sxs-lookup"><span data-stu-id="16c81-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="16c81-136">Zuerst müssen Sie verwenden die `New` -Schlüsselwort verwenden, um eine Instanz der Klasse erstellen oder eine Methode aufrufen, gibt eine Instanz der Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="16c81-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="16c81-137">Weitere Informationen finden Sie unter [Operator New](../../../../visual-basic/language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="16c81-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="16c81-138">Anschließend können die folgende Syntax zum Aufrufen der `Sub` -Methode für das Instanzobjekt:</span><span class="sxs-lookup"><span data-stu-id="16c81-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="16c81-139">*Object*.* MethodName*`[(`*Argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="16c81-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="16c81-140">Darstellung von Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="16c81-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="16c81-141">Die folgenden `Sub` -Prozedur meldet die welche Aufgabe die Anwendung sowie einen Zeitstempel an.</span><span class="sxs-lookup"><span data-stu-id="16c81-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="16c81-142">Anstatt diesen Code am Anfang jeder Aufgabe wiederholt auszuführen, ruft die Anwendung nur `tellOperator` von verschiedenen Standorten.</span><span class="sxs-lookup"><span data-stu-id="16c81-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="16c81-143">Jeder Aufruf übergibt eine Zeichenfolge in der `task` -Argument, das die gestartete Aufgabe identifiziert.</span><span class="sxs-lookup"><span data-stu-id="16c81-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 <span data-ttu-id="16c81-144">[!code-vb[VbVbcnProcedures&#2;](./codesnippet/VisualBasic/sub-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="16c81-144">[!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="16c81-145">Das folgende Beispiel zeigt einen normalen Aufruf `tellOperator`.</span><span class="sxs-lookup"><span data-stu-id="16c81-145">The following example shows a typical call to `tellOperator`.</span></span>  
  
 <span data-ttu-id="16c81-146">[!code-vb[VbVbcnProcedures&3;](./codesnippet/VisualBasic/sub-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="16c81-146">[!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c81-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16c81-147">See Also</span></span>  
 <span data-ttu-id="16c81-148">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-148">[Procedures](./index.md) </span></span>  
<span data-ttu-id="16c81-149"> [Function-Prozeduren](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-149"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="16c81-150"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-150"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="16c81-151"> [Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-151"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="16c81-152"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="16c81-153"> [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-153"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="16c81-154"> [Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt](./how-to-call-a-procedure-that-does-not-return-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="16c81-154"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md) </span></span>  
<span data-ttu-id="16c81-155"> [Gewusst wie: Aufrufen von einem Ereignishandler in Visual Basic](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="16c81-155"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
