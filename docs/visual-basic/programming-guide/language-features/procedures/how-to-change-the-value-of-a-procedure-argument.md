---
title: "Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic) | Microsoft-Dokumentation"
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
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
ms.openlocfilehash: 3f192d738ca2753cd12b6fffca1f4f94a606a42c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="075f7-102">Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="075f7-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="075f7-103">Wenn Sie eine Prozedur aufrufen, entspricht jedes Argument, das Sie Bereitstellen einer der in der Prozedur definierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="075f7-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="075f7-104">In einigen Fällen kann der Code der Prozedur den Wert, der einem Argument im Aufrufcode zugrunde liegt ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="075f7-105">In anderen Fällen kann die Prozedur nur ihre lokale Kopie eines Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="075f7-106">Beim Aufrufen der Prozedur [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] wird eine lokale Kopie jedes Argument übergeben [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="075f7-106">When you call the procedure, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="075f7-107">Für jedes Argument übergebenen [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] übergibt der Prozedur einen direkten Verweis auf das Programmierelement, das dem Argument im Aufrufcode zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="075f7-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="075f7-108">Wenn das zugrunde liegende Element im Aufrufcode ein veränderbares Element ist und das Argument übergeben wird `ByRef`, Code der Prozedur können den direkten Verweis der Wert des Elements im Aufrufcode ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="075f7-109">Ändern des zugrunde liegenden Werts</span><span class="sxs-lookup"><span data-stu-id="075f7-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="075f7-110">So ändern Sie den zugrunde liegenden Wert eines Prozedurarguments im Aufrufcode</span><span class="sxs-lookup"><span data-stu-id="075f7-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="075f7-111">Geben Sie in der Prozedurdeklaration [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) für den Parameter entspricht dem Argument.</span><span class="sxs-lookup"><span data-stu-id="075f7-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="075f7-112">Übergeben Sie in den Aufrufcode ein änderbares Programmierelement als Argument.</span><span class="sxs-lookup"><span data-stu-id="075f7-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="075f7-113">Schließen Sie in den aufrufenden Code nicht das Argument in Klammern in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="075f7-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="075f7-114">Verwenden Sie im Code Prozedur den Namen des Parameters an das zugrunde liegende Element im Aufrufcode einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="075f7-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="075f7-115">Siehe das Beispiel weiter unten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="075f7-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="075f7-116">Ändern von lokalen Kopien</span><span class="sxs-lookup"><span data-stu-id="075f7-116">Changing Local Copies</span></span>  
 <span data-ttu-id="075f7-117">Wenn das zugrunde liegende Element im Aufrufcode ein nicht änderbares Element ist oder wenn das Argument übergeben wird `ByVal`, die Prozedur Wert im aufrufenden Code nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="075f7-118">Die Prozedur kann jedoch die lokale Kopie eines solchen Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="075f7-119">So ändern Sie die Kopie eines Prozedurarguments im Prozedurcode</span><span class="sxs-lookup"><span data-stu-id="075f7-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="075f7-120">Geben Sie in der Prozedurdeklaration [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) für den Parameter entspricht dem Argument.</span><span class="sxs-lookup"><span data-stu-id="075f7-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="075f7-121">- oder - </span><span class="sxs-lookup"><span data-stu-id="075f7-121">-or-</span></span>  
  
     <span data-ttu-id="075f7-122">Setzen Sie in den aufrufenden Code das Argument in Klammern in der Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="075f7-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="075f7-123">Dies zwingt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] , das Argument als Wert zu übergeben, auch wenn der entsprechende Parameter gibt `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="075f7-123">This forces [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="075f7-124">Verwenden Sie im Code Prozedur den Parameternamen, um die lokale Kopie des Arguments einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="075f7-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="075f7-125">Der zugrunde liegende Wert im Aufrufcode wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="075f7-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="075f7-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="075f7-126">Example</span></span>  
 <span data-ttu-id="075f7-127">Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente.</span><span class="sxs-lookup"><span data-stu-id="075f7-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="075f7-128">Die `increase` Prozedur fügt einfach zu jedem Element.</span><span class="sxs-lookup"><span data-stu-id="075f7-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="075f7-129">Die `replace` -Prozedur weist den Parameter ein neues Array `a()` und fügt dann jedem Element&1; hinzu.</span><span class="sxs-lookup"><span data-stu-id="075f7-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 <span data-ttu-id="075f7-130">[!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="075f7-130">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]</span></span>  
  
 <span data-ttu-id="075f7-131">[!code-vb[VbVbcnProcedures Nr.&36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="075f7-131">[!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]</span></span>  
  
 <span data-ttu-id="075f7-132">[!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="075f7-132">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]</span></span>  
  
 <span data-ttu-id="075f7-133">Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="075f7-133">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="075f7-134">Da das Array `n` ist ein Verweistyp, `replace` kann seine Member ändern, obwohl die Übergabemechanismus ist `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="075f7-134">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="075f7-135">Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="075f7-135">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="075f7-136">Da `n` übergeben `ByRef`, `replace` ändern Sie die Variable `n` in den aufrufenden Code, und weisen Sie ein neues Array.</span><span class="sxs-lookup"><span data-stu-id="075f7-136">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="075f7-137">Da `n` ist ein Verweistyp `replace` Membern können auch ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-137">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="075f7-138">Sie können verhindern, dass die Prozedur die Variable im aufrufenden Code ändern.</span><span class="sxs-lookup"><span data-stu-id="075f7-138">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="075f7-139">Finden Sie unter [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="075f7-139">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="075f7-140">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="075f7-140">Compiling the Code</span></span>  
 <span data-ttu-id="075f7-141">Wenn Sie eine Variable als Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.</span><span class="sxs-lookup"><span data-stu-id="075f7-141">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="075f7-142">Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="075f7-142">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="075f7-143">Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort in jeden deklarierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="075f7-143">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="075f7-144">Dadurch wird Ihr Code leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="075f7-144">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="075f7-145">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="075f7-145">.NET Framework Security</span></span>  
 <span data-ttu-id="075f7-146">Es ist immer ein potenzielles Risiko einer Prozedur so ändern Sie den Wert, der einem Argument im Aufrufcode zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="075f7-146">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="075f7-147">Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und bereiten Sie sich vor der Verwendung auf Gültigkeit überprüfen.</span><span class="sxs-lookup"><span data-stu-id="075f7-147">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="075f7-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="075f7-148">See Also</span></span>  
 <span data-ttu-id="075f7-149">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-149">[Procedures](./index.md) </span></span>  
<span data-ttu-id="075f7-150"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-150"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="075f7-151"> [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-151"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="075f7-152"> [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-152"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="075f7-153"> [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-153"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="075f7-154"> [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-154"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="075f7-155"> [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="075f7-156"> [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="075f7-157"> [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="075f7-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="075f7-158"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="075f7-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
