---
title: 'Vorgehensweise: Ändern des Werts eines Prozedurarguments (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: 096bc6adfa7a8c95674d235f0112d23f7a45caf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672291"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="21af0-102">Vorgehensweise: Ändern des Werts eines Prozedurarguments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21af0-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="21af0-103">Wenn Sie eine Prozedur aufrufen, entspricht jedes Argument, das Sie angeben, einer der Parameter in der Prozedur definiert.</span><span class="sxs-lookup"><span data-stu-id="21af0-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="21af0-104">In einigen Fällen kann der Code der Prozedur den Wert, der zugrunde liegenden Argument im aufrufenden Code ändern.</span><span class="sxs-lookup"><span data-stu-id="21af0-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="21af0-105">In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="21af0-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="21af0-106">Wenn Sie die Prozedur aufrufen, handelt es sich bei Visual Basic ermöglicht eine lokale Kopie von jedem Argument, das übergeben wird [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="21af0-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="21af0-107">Für jedes Argument übergebenen [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic bietet der Code der Prozedur einen direkten Verweis auf das Programmierelement zugrunde liegenden Arguments im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="21af0-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="21af0-108">Wenn das zugrunde liegende Element im aufrufenden Code ein Element geändert werden kann wird, und das Argument übergeben wird `ByRef`, der Code der Prozedur können den direkten Verweis so ändern Sie den Wert des Elements im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="21af0-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="21af0-109">Den zugrunde liegenden Wert ändern</span><span class="sxs-lookup"><span data-stu-id="21af0-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="21af0-110">Zum Ändern des zugrunde liegenden Werts eines Prozedurarguments im aufrufenden code</span><span class="sxs-lookup"><span data-stu-id="21af0-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="21af0-111">Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter mit dem Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="21af0-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="21af0-112">Übergeben Sie im aufrufenden Code ein änderbares Programmierelement als Argument ein.</span><span class="sxs-lookup"><span data-stu-id="21af0-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="21af0-113">Schließen Sie in den aufrufenden Code nicht das Argument in Klammern in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="21af0-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="21af0-114">Können Sie der Name des Parameters im Code Prozedur um das zugrunde liegende Element im aufrufenden Code einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="21af0-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="21af0-115">Siehe das Beispiel weiter unten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21af0-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="21af0-116">Ändern von lokalen Kopien</span><span class="sxs-lookup"><span data-stu-id="21af0-116">Changing Local Copies</span></span>  
 <span data-ttu-id="21af0-117">Wenn das zugrunde liegende Element im aufrufenden Code eine als nicht änderbar ist, oder wenn das Argument übergeben wird `ByVal`, die Prozedur Wert im aufrufenden Code nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="21af0-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="21af0-118">Die Prozedur kann jedoch die lokale Kopie der derartiges Argument ändern.</span><span class="sxs-lookup"><span data-stu-id="21af0-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="21af0-119">So ändern Sie die Kopie eines Prozedurarguments im Code Prozedur</span><span class="sxs-lookup"><span data-stu-id="21af0-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="21af0-120">Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter mit dem Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="21af0-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="21af0-121">- oder - </span><span class="sxs-lookup"><span data-stu-id="21af0-121">-or-</span></span>  
  
     <span data-ttu-id="21af0-122">Setzen Sie in den aufrufenden Code das Argument in Klammern in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="21af0-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="21af0-123">Dies zwingt Visual Basic, um das Argument als Wert übergeben, selbst wenn der entsprechende Parameter gibt an, `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="21af0-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="21af0-124">Können Sie der Name des Parameters im Code Prozedur um die lokale Kopie des Arguments einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="21af0-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="21af0-125">Der zugrunde liegenden Wert im aufrufenden Code wird nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="21af0-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21af0-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21af0-126">Example</span></span>  
 <span data-ttu-id="21af0-127">Das folgende Beispiel zeigt zwei Verfahren, die eine Arrayvariable und ausgeführt werden, die Elemente.</span><span class="sxs-lookup"><span data-stu-id="21af0-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="21af0-128">Die `increase` Verfahren einfach zu jedem Element hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="21af0-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="21af0-129">Die `replace` Prozedur weist ein neues Array, an den Parameter `a()` , und klicken Sie dann auf die einzelnen Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="21af0-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="21af0-130">Die erste `MsgBox` aufrufen, zeigt "nach increase(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="21af0-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="21af0-131">Da das Array `n` ist ein Verweistyp, `replace` können ihre Member, ändern, auch wenn der Übergabemechanismus ist `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="21af0-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="21af0-132">Die zweite `MsgBox` aufrufen, zeigt "nach Replace(n):: 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="21af0-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="21af0-133">Da `n` übergeben wird `ByRef`, `replace` ändern können Sie die Variable `n` im aufrufenden Code und weisen Sie ein neues Array zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="21af0-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="21af0-134">Da `n` ist ein Verweistyp, `replace` können Member auch ändern.</span><span class="sxs-lookup"><span data-stu-id="21af0-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="21af0-135">Sie können verhindern, dass das Verfahren ändern die Variable im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="21af0-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="21af0-136">Weitere Informationen finden Sie unter [How to: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="21af0-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21af0-137">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="21af0-137">Compiling the Code</span></span>  
 <span data-ttu-id="21af0-138">Wenn Sie eine Variable als Verweis übergeben, müssen Sie verwenden die `ByRef` Schlüsselwort, um diesen Mechanismus angeben.</span><span class="sxs-lookup"><span data-stu-id="21af0-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="21af0-139">Der Standardwert in Visual Basic ist, Argumente als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="21af0-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="21af0-140">Allerdings ist es guter Programmierstil, auch die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für jeden deklarierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="21af0-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="21af0-141">Dadurch wird Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="21af0-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="21af0-142">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="21af0-142">.NET Framework Security</span></span>  
 <span data-ttu-id="21af0-143">Es ist immer ein potenzielles Risiko einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="21af0-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="21af0-144">Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und auf Gültigkeit überprüft werden vor der Verwendung vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="21af0-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21af0-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21af0-145">See also</span></span>
- [<span data-ttu-id="21af0-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="21af0-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="21af0-147">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="21af0-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="21af0-148">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="21af0-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="21af0-149">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="21af0-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="21af0-150">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="21af0-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="21af0-151">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="21af0-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="21af0-152">Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="21af0-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="21af0-153">Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="21af0-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="21af0-154">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="21af0-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="21af0-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="21af0-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
