---
title: Function-Prozeduren (Visual Basic) | Microsoft-Dokumentation
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
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fb36ee41e4b53f6e690ce5d48d34bbfc9f86c177
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="50fe2-102">Function-Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50fe2-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="50fe2-103">Ein `Function` Prozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anweisungen, die durch die `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-103">A `Function` procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="50fe2-104">Die `Function` Prozedur eine Aufgabe ausführt, und dann wird die Steuerung an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50fe2-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="50fe2-105">Wenn sie die Steuerung zurückgibt, gibt auch einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="50fe2-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="50fe2-106">Jedes Mal die Prozedur aufgerufen wird, werden ihre Anweisungen ausgeführt werden, beginnend mit der ersten ausführbaren Anweisung nach der `Function` -Anweisung und endet mit dem ersten `End Function`, `Exit Function`, oder `Return` Anweisung aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50fe2-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="50fe2-107">Sie können eine `Function` Prozedur in einem Modul, Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="50fe2-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="50fe2-108">Es ist `Public` standardmäßig d. h. Sie können überall aufrufen in der Anwendung, die Zugriff auf das Modul, Klasse oder Struktur, in der Sie definiert, wurde.</span><span class="sxs-lookup"><span data-stu-id="50fe2-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="50fe2-109">Ein `Function` -Prozeduren können Argumente, wie z. B. Konstanten, Variablen oder Ausdrücke, die durch den Aufrufcode an sie übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="50fe2-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="50fe2-110">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="50fe2-110">Declaration Syntax</span></span>  
 <span data-ttu-id="50fe2-111">Die Syntax zum Deklarieren einer `Function` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="50fe2-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="50fe2-112">Die *Modifizierer* Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing angeben können.</span><span class="sxs-lookup"><span data-stu-id="50fe2-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="50fe2-113">Weitere Informationen finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="50fe2-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="50fe2-114">Sie deklarieren jeden Parameter auf die gleiche Weise bei [Sub-Prozeduren](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="50fe2-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="50fe2-115">Datentyp</span><span class="sxs-lookup"><span data-stu-id="50fe2-115">Data Type</span></span>  
 <span data-ttu-id="50fe2-116">Jede `Function` Prozedur verfügt über einen Datentyp, ebenso wie Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="50fe2-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="50fe2-117">Dieser Datentyp wird angegeben, indem die `As` -Klausel in der `Function` -Anweisung, und es bestimmt den Datentyp des Werts an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50fe2-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="50fe2-118">Die folgenden Beispieldeklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50fe2-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="50fe2-119">Weitere Informationen finden Sie unter "Webparts" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="50fe2-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="50fe2-120">Zurückgeben von Werten</span><span class="sxs-lookup"><span data-stu-id="50fe2-120">Returning Values</span></span>  
 <span data-ttu-id="50fe2-121">Der Wert einer `Function` sendet ihren Rückgabewert zurück an den aufrufenden Code aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="50fe2-122">Die Prozedur gibt diesen Wert zurück, auf zwei Arten:</span><span class="sxs-lookup"><span data-stu-id="50fe2-122">The procedure returns this value in one of two ways:</span></span>  
  
-   <span data-ttu-id="50fe2-123">Er verwendet die `Return` Anweisung an den Rückgabewert und gibt die Steuerung wird sofort an das aufrufende Programm.</span><span class="sxs-lookup"><span data-stu-id="50fe2-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="50fe2-124">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50fe2-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   <span data-ttu-id="50fe2-125">Eigene Funktionsnamen in eine oder mehrere Anweisungen der Prozedur wird ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="50fe2-126">Steuerung ist nicht an das aufrufende Programm, bis ein `Exit Function` oder `End Function` ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50fe2-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="50fe2-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="50fe2-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="50fe2-128">Der Vorteil den Rückgabewert dem Funktionsnamen weisen ist die Steuerung von der Prozedur zurückgibt, bis zum Erreichen einer `Exit Function` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="50fe2-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="50fe2-129">Dadurch können Sie einen vorläufigen Wert zuweisen und ihn später bei Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="50fe2-130">Weitere Informationen zum Zurückgeben von Werten, finden Sie unter [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="50fe2-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="50fe2-131">Informationen zum Zurückgeben von Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="50fe2-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="50fe2-132">Aufrufen der Syntax</span><span class="sxs-lookup"><span data-stu-id="50fe2-132">Calling Syntax</span></span>  
 <span data-ttu-id="50fe2-133">Rufen Sie eine `Function` Prozedur durch den Namen und die Argumente, die entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="50fe2-134">Geben Sie Werte für alle Argumente, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="50fe2-135">Wenn keine Argumente angegeben sind, können Sie die Klammern auch weglassen.</span><span class="sxs-lookup"><span data-stu-id="50fe2-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="50fe2-136">Die Syntax für einen Aufruf einer `Function` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="50fe2-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="50fe2-137">*Lvalue*`=`*Funktionsname* `[(` *Argumentlist*    `)]`</span><span class="sxs-lookup"><span data-stu-id="50fe2-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="50fe2-138">`If ((`*Funktionsname* `[(` *Argumentlist* `)] / 3) <=` *Ausdruck*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="50fe2-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="50fe2-139">Beim Aufruf einer `Function` Prozedur, Sie müssen keinen Rückgabewert verwenden.</span><span class="sxs-lookup"><span data-stu-id="50fe2-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="50fe2-140">Wenn Sie nicht sämtliche Aktionen der Funktion durchgeführt werden, der Rückgabewert wird jedoch ignoriert.</span><span class="sxs-lookup"><span data-stu-id="50fe2-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="50fe2-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>auf diese Weise wird häufig aufgerufen werden.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="50fe2-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="50fe2-142">Darstellung von Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="50fe2-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="50fe2-143">Die folgenden `Function` -Prozedur wird die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks anhand der Werte der beiden anderen Seiten berechnet.</span><span class="sxs-lookup"><span data-stu-id="50fe2-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 <span data-ttu-id="50fe2-144">[!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/function-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="50fe2-144">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="50fe2-145">Das folgende Beispiel zeigt einen normalen Aufruf `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="50fe2-145">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 <span data-ttu-id="50fe2-146">[!code-vb[VbVbcnProcedures&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="50fe2-146">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fe2-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50fe2-147">See Also</span></span>  
 <span data-ttu-id="50fe2-148">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-148">[Procedures](./index.md) </span></span>  
<span data-ttu-id="50fe2-149"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-149"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="50fe2-150"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-150"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="50fe2-151"> [Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-151"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="50fe2-152"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="50fe2-153"> [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-153"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="50fe2-154"> [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-154"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="50fe2-155"> [Gewusst wie: Zurückgeben eines Werts aus einer Prozedur](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="50fe2-155"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="50fe2-156"> [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="50fe2-156"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
