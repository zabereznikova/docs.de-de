---
title: "Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba23c8f0b4b0b6e751546019af902a6305b9ef53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="75e0a-102">Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75e0a-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="75e0a-103">Wenn Sie eine Prozedur aufrufen, entspricht jedes Argument, das Sie angeben eines Parameters in der Prozedur definiert.</span><span class="sxs-lookup"><span data-stu-id="75e0a-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="75e0a-104">In einigen Fällen kann der Code die Prozedur den Wert, der ein Argument im aufrufenden Code zugrunde liegt, ändern.</span><span class="sxs-lookup"><span data-stu-id="75e0a-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="75e0a-105">In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="75e0a-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="75e0a-106">Wenn Sie die Prozedur aufrufen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] wird eine lokale Kopie jedes Argument, das übergeben wird [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="75e0a-106">When you call the procedure, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="75e0a-107">Für jedes Argument übergebenen [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] übergibt der Prozedur einen direkten Verweis auf das Programmierelement, die dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="75e0a-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="75e0a-108">Wenn das zugrunde liegende Element im aufrufenden Code ein Element geändert werden kann wird und das Argument übergeben `ByRef`, Code der Prozedur mithilfe der direkten Verweis um der Wert des Elements im aufrufenden Code zu ändern.</span><span class="sxs-lookup"><span data-stu-id="75e0a-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="75e0a-109">Ändern des zugrunde liegenden Werts</span><span class="sxs-lookup"><span data-stu-id="75e0a-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="75e0a-110">Zum Ändern des zugrunde liegenden Werts eines Prozedurarguments im aufrufenden code</span><span class="sxs-lookup"><span data-stu-id="75e0a-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="75e0a-111">Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter an das Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="75e0a-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="75e0a-112">Übergeben Sie in der aufrufende Code ein änderbares Programmierelement als Argument.</span><span class="sxs-lookup"><span data-stu-id="75e0a-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="75e0a-113">Schließen Sie in den aufrufenden Code nicht das Argument in Klammern in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="75e0a-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="75e0a-114">Verwenden Sie im Code Prozedur den Namen des Parameters an das zugrunde liegende Element im aufrufenden Code einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="75e0a-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="75e0a-115">Siehe das Beispiel weiter unten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="75e0a-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="75e0a-116">Ändern von lokalen Kopien</span><span class="sxs-lookup"><span data-stu-id="75e0a-116">Changing Local Copies</span></span>  
 <span data-ttu-id="75e0a-117">Wenn das zugrunde liegende Element in der aufrufende Code eine nicht veränderbaren ist oder wenn das Argument übergeben, wird `ByVal`, dessen Wert in den aufrufenden Code von die Prozedur kann nicht geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="75e0a-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="75e0a-118">Die Prozedur kann jedoch die lokale Kopie der ein derartiges Argument ändern.</span><span class="sxs-lookup"><span data-stu-id="75e0a-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="75e0a-119">So ändern Sie die Kopie eines Prozedurarguments im Code Prozedur</span><span class="sxs-lookup"><span data-stu-id="75e0a-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="75e0a-120">Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter an das Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="75e0a-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="75e0a-121">- oder - </span><span class="sxs-lookup"><span data-stu-id="75e0a-121">-or-</span></span>  
  
     <span data-ttu-id="75e0a-122">Setzen Sie in den aufrufenden Code das Argument in Klammern in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="75e0a-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="75e0a-123">Dies zwingt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] das Argument anhand des Werts übergeben werden, auch wenn der entsprechende Parameter gibt `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="75e0a-123">This forces [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="75e0a-124">Verwenden Sie im Code Prozedur der Name des Parameters, um die lokale Kopie des Arguments einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="75e0a-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="75e0a-125">Der zugrunde liegenden Wert im aufrufenden Code wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="75e0a-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75e0a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75e0a-126">Example</span></span>  
 <span data-ttu-id="75e0a-127">Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente.</span><span class="sxs-lookup"><span data-stu-id="75e0a-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="75e0a-128">Die `increase` Verfahren einfach zu jedem Element hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="75e0a-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="75e0a-129">Die `replace` -Prozedur weist den Parameter ein neues Array `a()` , und klicken Sie dann auf jedes Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="75e0a-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="75e0a-130">Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="75e0a-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="75e0a-131">Da das Array `n` ist ein Verweistyp `replace` seiner Elemente, können geändert werden, obwohl der Übergabemechanismus ist `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="75e0a-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="75e0a-132">Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="75e0a-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="75e0a-133">Da `n` übergeben `ByRef`, `replace` ändern Sie die Variable `n` in den aufrufenden Code, und weisen Sie ein neues Array zu.</span><span class="sxs-lookup"><span data-stu-id="75e0a-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="75e0a-134">Da `n` ist ein Verweistyp `replace` Membern können auch ändern.</span><span class="sxs-lookup"><span data-stu-id="75e0a-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="75e0a-135">Sie können verhindern, dass die Prozedur die Variable im aufrufenden Code ändern.</span><span class="sxs-lookup"><span data-stu-id="75e0a-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="75e0a-136">Finden Sie unter [wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="75e0a-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="75e0a-137">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="75e0a-137">Compiling the Code</span></span>  
 <span data-ttu-id="75e0a-138">Wenn Sie keine Variable nach Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.</span><span class="sxs-lookup"><span data-stu-id="75e0a-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="75e0a-139">Die Standardeinstellung in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Argumenten als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="75e0a-139">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="75e0a-140">Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jeder deklarierte Parameter.</span><span class="sxs-lookup"><span data-stu-id="75e0a-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="75e0a-141">Dadurch wird Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="75e0a-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="75e0a-142">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="75e0a-142">.NET Framework Security</span></span>  
 <span data-ttu-id="75e0a-143">In einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt, ist immer ein Sicherheitsrisiko dar.</span><span class="sxs-lookup"><span data-stu-id="75e0a-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="75e0a-144">Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und es auf Gültigkeit zu überprüfen, vor der Verwendung vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="75e0a-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e0a-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75e0a-145">See Also</span></span>  
 [<span data-ttu-id="75e0a-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="75e0a-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="75e0a-147">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="75e0a-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="75e0a-148">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="75e0a-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="75e0a-149">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="75e0a-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="75e0a-150">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="75e0a-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="75e0a-151">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="75e0a-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="75e0a-152">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="75e0a-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="75e0a-153">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="75e0a-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="75e0a-154">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="75e0a-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="75e0a-155">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="75e0a-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
