---
title: Function-Prozeduren
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: b0ba96a875fd8785e45eee565beefe4b961ffc9d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388750"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="f7824-102">Funktions Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7824-102">Function procedures (Visual Basic)</span></span>

<span data-ttu-id="f7824-103">Eine `Function` Prozedur ist eine Reihe von Visual Basic-Anweisungen, die von den `Function` Anweisungen und eingeschlossen werden `End Function` .</span><span class="sxs-lookup"><span data-stu-id="f7824-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="f7824-104">Die `Function` Prozedur führt eine Aufgabe aus und gibt dann die Steuerung an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="f7824-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="f7824-105">Wenn die Steuerung zurückgegeben wird, wird auch ein Wert an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f7824-105">When it returns control, it also returns a value to the calling code.</span></span>

<span data-ttu-id="f7824-106">Jedes Mal, wenn die Prozedur aufgerufen wird, werden Ihre-Anweisungen ausgeführt, beginnend mit der ersten ausführbaren Anweisung nach der `Function` -Anweisung und endende mit der ersten `End Function` , `Exit Function` , oder- `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f7824-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>

<span data-ttu-id="f7824-107">Sie können eine `Function` Prozedur in einem Modul, einer Klasse oder einer Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="f7824-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="f7824-108">Dies `Public` bedeutet standardmäßig, dass Sie Sie von überall in Ihrer Anwendung aufrufen können, die Zugriff auf das Modul, die Klasse oder die Struktur hat, in der Sie Sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="f7824-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>

<span data-ttu-id="f7824-109">Eine `Function` Prozedur kann Argumente, wie z. b. Konstanten, Variablen oder Ausdrücke, verwenden, die vom aufrufenden Code an Sie übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f7824-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="f7824-110">Deklarations Syntax</span><span class="sxs-lookup"><span data-stu-id="f7824-110">Declaration syntax</span></span>

<span data-ttu-id="f7824-111">Die Syntax zum Deklarieren einer `Function` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f7824-111">The syntax for declaring a `Function` procedure is as follows:</span></span>

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

<span data-ttu-id="f7824-112">Die *Modifizierer* können Zugriffsebene und Informationen zum überschreiben, überschreiben, freigeben und shadoading angeben.</span><span class="sxs-lookup"><span data-stu-id="f7824-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="f7824-113">Weitere Informationen finden Sie unter [Function-Anweisung](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f7824-113">For more information, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

<span data-ttu-id="f7824-114">Sie deklarieren jeden Parameter auf dieselbe Weise wie für [unter Prozeduren](./sub-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f7824-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="f7824-115">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f7824-115">Data type</span></span>

<span data-ttu-id="f7824-116">Jede `Function` Prozedur weist einen Datentyp auf, so wie jede Variable dies tut.</span><span class="sxs-lookup"><span data-stu-id="f7824-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="f7824-117">Dieser Datentyp wird von der `As` -Klausel in der `Function` -Anweisung angegeben und bestimmt den Datentyp des Werts, der von der Funktion an den aufrufenden Code zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f7824-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="f7824-118">Dies wird in den folgenden Beispiel Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f7824-118">The following sample declarations illustrate this.</span></span>

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

<span data-ttu-id="f7824-119">Weitere Informationen finden Sie unter "Parts" in der [Function-Anweisung](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f7824-119">For more information, see "Parts" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

### <a name="returning-values"></a><span data-ttu-id="f7824-120">Zurückgeben von Werten</span><span class="sxs-lookup"><span data-stu-id="f7824-120">Returning values</span></span>

<span data-ttu-id="f7824-121">Der Wert, den eine `Function` Prozedur an den aufrufenden Code zurücksendet, wird als Rückgabewert bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f7824-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="f7824-122">Die Prozedur gibt diesen Wert auf zwei Arten zurück:</span><span class="sxs-lookup"><span data-stu-id="f7824-122">The procedure returns this value in one of two ways:</span></span>

- <span data-ttu-id="f7824-123">Dabei wird die `Return` -Anweisung verwendet, um den Rückgabewert anzugeben, und die Steuerung wird sofort an das aufrufenden Programm zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f7824-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="f7824-124">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f7824-124">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- <span data-ttu-id="f7824-125">In einer oder mehreren Anweisungen der Prozedur wird dem eigenen Funktionsnamen ein Wert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7824-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="f7824-126">Das-Steuerelement kehrt erst zum aufrufenden Programm zurück, wenn eine- `Exit Function` oder- `End Function` Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7824-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="f7824-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f7824-127">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

<span data-ttu-id="f7824-128">Der Vorteil der Zuweisung des Rückgabewerts zum Funktionsnamen besteht darin, dass das Steuerelement nicht von der Prozedur zurückgegeben wird, bis auf eine- `Exit Function` oder- `End Function` Anweisung stößt.</span><span class="sxs-lookup"><span data-stu-id="f7824-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="f7824-129">Dies ermöglicht es Ihnen, einen vorläufigen Wert zuzuweisen und ihn später bei Bedarf anzupassen.</span><span class="sxs-lookup"><span data-stu-id="f7824-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>

<span data-ttu-id="f7824-130">Weitere Informationen zum Zurückgeben von Werten finden Sie unter [Function-Anweisung](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f7824-130">For more information about returning values, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="f7824-131">Weitere Informationen zum Zurückgeben von Arrays finden Sie unter [Arrays](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="f7824-131">For information about returning arrays, see [Arrays](../arrays/index.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="f7824-132">Aufruf Syntax</span><span class="sxs-lookup"><span data-stu-id="f7824-132">Calling syntax</span></span>

<span data-ttu-id="f7824-133">Sie rufen eine `Function` Prozedur auf, indem Sie den Namen und die Argumente entweder auf der rechten Seite einer Zuweisungsanweisung oder in einem Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="f7824-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="f7824-134">Sie müssen Werte für alle nicht optionalen Argumente angeben, und Sie müssen die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="f7824-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="f7824-135">Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="f7824-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="f7824-136">Die Syntax für einen aufzurufenden `Function` Vorgang ist wie folgt.</span><span class="sxs-lookup"><span data-stu-id="f7824-136">The syntax for a call to a `Function` procedure is as follows.</span></span>

<span data-ttu-id="f7824-137">*Lvalue* `=` *FunctionName* `[(` Argument *Liste*    `)]`</span><span class="sxs-lookup"><span data-stu-id="f7824-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>

<span data-ttu-id="f7824-138">`If ((`*FunctionName* `[(` Argument *Liste* `)] / 3) <=` *Ausdruck*  `) Then`</span><span class="sxs-lookup"><span data-stu-id="f7824-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>

<span data-ttu-id="f7824-139">Wenn Sie eine Prozedur aufzurufen `Function` , müssen Sie ihren Rückgabewert nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7824-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="f7824-140">Andernfalls werden alle Aktionen der Funktion ausgeführt, aber der Rückgabewert wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="f7824-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="f7824-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>wird häufig auf diese Weise aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f7824-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="f7824-142">Abbildung der Deklaration und des Aufruf</span><span class="sxs-lookup"><span data-stu-id="f7824-142">Illustration of declaration and call</span></span>

<span data-ttu-id="f7824-143">Im folgenden `Function` Verfahren wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f7824-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

<span data-ttu-id="f7824-144">Das folgende Beispiel zeigt einen typischen-Rückruf `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="f7824-144">The following example shows a typical call to `hypotenuse`.</span></span>

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a><span data-ttu-id="f7824-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7824-145">See also</span></span>

- [<span data-ttu-id="f7824-146">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="f7824-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="f7824-147">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f7824-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="f7824-148">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="f7824-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="f7824-149">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="f7824-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="f7824-150">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="f7824-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f7824-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f7824-151">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="f7824-152">Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="f7824-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="f7824-153">Vorgehensweise: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="f7824-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="f7824-154">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="f7824-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
