---
title: 'Gewusst wie: Ändern des Werts eines Prozedurarguments'
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
ms.openlocfilehash: e562c0f5ec01380c792b4dc064554171cfb007e7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74339962"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="4344d-102">Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4344d-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="4344d-103">Wenn Sie eine Prozedur aufzurufen, entspricht jedes von Ihnen bereitgestellte Argument einem der in der Prozedur definierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="4344d-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="4344d-104">In einigen Fällen kann der Prozedur Code den Wert ändern, der einem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="4344d-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="4344d-105">In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="4344d-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="4344d-106">Wenn Sie die Prozedur aufzurufen, erstellt Visual Basic eine lokale Kopie jedes Arguments, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="4344d-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="4344d-107">Für jedes Argument, das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)übergibt, gibt Visual Basic dem Prozedur Code einen direkten Verweis auf das Programmier Element, das dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="4344d-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="4344d-108">Wenn das zugrunde liegende Element im aufrufenden Code ein änderbares Element ist und das Argument `ByRef`weitergegeben wird, kann der Prozedur Code den direkten Verweis verwenden, um den Wert des Elements im aufrufenden Code zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4344d-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="4344d-109">Ändern des zugrunde liegenden Werts</span><span class="sxs-lookup"><span data-stu-id="4344d-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="4344d-110">So ändern Sie den zugrunde liegenden Wert eines Procedure-Arguments im aufrufenden Code</span><span class="sxs-lookup"><span data-stu-id="4344d-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="4344d-111">Geben Sie in der Prozedur Deklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter an, der dem Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="4344d-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="4344d-112">Übergeben Sie im aufrufenden Code ein änderbares Programmier Element als Argument.</span><span class="sxs-lookup"><span data-stu-id="4344d-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="4344d-113">Schließen Sie das Argument im aufrufenden Code nicht in Klammern in der Argumentliste ein.</span><span class="sxs-lookup"><span data-stu-id="4344d-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="4344d-114">Verwenden Sie im Prozedur Code den Parameternamen, um dem zugrunde liegenden Element im aufrufenden Code einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4344d-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="4344d-115">Eine Demonstration finden Sie im Beispiel weiter unten.</span><span class="sxs-lookup"><span data-stu-id="4344d-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="4344d-116">Ändern von lokalen Kopien</span><span class="sxs-lookup"><span data-stu-id="4344d-116">Changing Local Copies</span></span>  
 <span data-ttu-id="4344d-117">Wenn das zugrunde liegende Element im aufrufenden Code ein nicht änderbares Element ist, oder wenn das Argument `ByVal`übermittelt wird, kann die Prozedur den Wert im aufrufenden Code nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="4344d-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="4344d-118">Die Prozedur kann jedoch Ihre lokale Kopie eines solchen Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="4344d-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="4344d-119">So ändern Sie die Kopie eines Prozedur Arguments im Prozedur Code</span><span class="sxs-lookup"><span data-stu-id="4344d-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="4344d-120">Geben Sie in der Prozedur Deklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter an, der dem-Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="4344d-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="4344d-121">\- oder -</span><span class="sxs-lookup"><span data-stu-id="4344d-121">-or-</span></span>  
  
     <span data-ttu-id="4344d-122">Schließen Sie das Argument im aufrufenden Code in Klammern in die Argumentliste ein.</span><span class="sxs-lookup"><span data-stu-id="4344d-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="4344d-123">Dies erzwingt Visual Basic, das Argument als Wert zu übergeben, auch wenn der entsprechende Parameter `ByRef`angibt.</span><span class="sxs-lookup"><span data-stu-id="4344d-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="4344d-124">Verwenden Sie im Prozedur Code den Parameternamen, um der lokalen Kopie des Arguments einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4344d-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="4344d-125">Der zugrunde liegende Wert im aufrufenden Code wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="4344d-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4344d-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4344d-126">Example</span></span>  
 <span data-ttu-id="4344d-127">Das folgende Beispiel zeigt zwei Prozeduren, die eine Array Variable akzeptieren und deren Elemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4344d-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="4344d-128">Die `increase` Prozedur fügt einem Element einfach ein Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="4344d-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="4344d-129">Die `replace` Prozedur weist dem Parameter `a()` ein neues Array zu und fügt dann jedem Element eine hinzu.</span><span class="sxs-lookup"><span data-stu-id="4344d-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="4344d-130">Der erste `MsgBox`-aufrufsbefehl zeigt "After Increase (n): 11, 21, 31, 41" an.</span><span class="sxs-lookup"><span data-stu-id="4344d-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="4344d-131">Da das Array `n` ein Referenztyp ist, kann `replace` seine Member ändern, auch wenn der Übergabe Mechanismus `ByVal`ist.</span><span class="sxs-lookup"><span data-stu-id="4344d-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="4344d-132">Der zweite `MsgBox`-Aufrufe zeigt "After replace (n): 101, 201, 301" an.</span><span class="sxs-lookup"><span data-stu-id="4344d-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="4344d-133">Da `n` `ByRef`übermittelt wird, können `replace` die Variable `n` im aufrufenden Code ändern und ihr ein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4344d-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="4344d-134">Da `n` ein Verweistyp ist, können `replace` auch seine Member ändern.</span><span class="sxs-lookup"><span data-stu-id="4344d-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="4344d-135">Sie können verhindern, dass die Prozedur die Variable selbst im aufrufenden Code ändert.</span><span class="sxs-lookup"><span data-stu-id="4344d-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="4344d-136">Weitere Informationen finden [Sie unter Gewusst wie: Schützen eines Prozedur Arguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="4344d-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4344d-137">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4344d-137">Compiling the Code</span></span>  
 <span data-ttu-id="4344d-138">Wenn Sie eine Variable als Verweis übergeben, müssen Sie das `ByRef`-Schlüsselwort verwenden, um diesen Mechanismus anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4344d-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="4344d-139">Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4344d-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="4344d-140">Es ist jedoch eine gute Programmier Übung, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) -oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jedem deklarierten Parameter einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4344d-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="4344d-141">Dadurch wird Ihr Code leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="4344d-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4344d-142">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4344d-142">.NET Framework Security</span></span>  
 <span data-ttu-id="4344d-143">Es besteht immer ein potenzielles Risiko, dass eine Prozedur den Wert ändern kann, der einem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="4344d-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="4344d-144">Stellen Sie sicher, dass dieser Wert geändert wird, und dass Sie darauf vorbereitet sind, ihn vor der Verwendung auf Gültigkeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4344d-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4344d-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4344d-145">See also</span></span>

- [<span data-ttu-id="4344d-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="4344d-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4344d-147">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="4344d-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4344d-148">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="4344d-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4344d-149">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="4344d-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4344d-150">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="4344d-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="4344d-151">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="4344d-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="4344d-152">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="4344d-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="4344d-153">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="4344d-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="4344d-154">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="4344d-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="4344d-155">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4344d-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
