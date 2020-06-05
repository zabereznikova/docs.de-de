---
title: 'Vorgehensweise: Ändern des Werts eines Prozedurarguments'
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
ms.openlocfilehash: 46cf9062d01e248b6e90882a923a48210780f7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388503"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="b27fe-102">Gewusst wie: Ändern des Werts eines Prozedurarguments (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b27fe-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="b27fe-103">Wenn Sie eine Prozedur aufzurufen, entspricht jedes von Ihnen bereitgestellte Argument einem der in der Prozedur definierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="b27fe-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="b27fe-104">In einigen Fällen kann der Prozedur Code den Wert ändern, der einem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b27fe-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="b27fe-105">In anderen Fällen kann die Prozedur nur die lokale Kopie eines Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="b27fe-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="b27fe-106">Wenn Sie die Prozedur aufzurufen, erstellt Visual Basic eine lokale Kopie jedes Arguments, das [ByVal](../../../language-reference/modifiers/byval.md)übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="b27fe-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="b27fe-107">Für jedes Argument, das [ByRef](../../../language-reference/modifiers/byref.md)übergibt, gibt Visual Basic dem Prozedur Code einen direkten Verweis auf das Programmier Element, das dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b27fe-107">For each argument passed [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="b27fe-108">Wenn das zugrunde liegende Element im aufrufenden Code ein änderbares Element ist und das Argument weitergegeben wird `ByRef` , kann der Prozedur Code den direkten Verweis verwenden, um den Wert des Elements im aufrufenden Code zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b27fe-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="b27fe-109">Ändern des zugrunde liegenden Werts</span><span class="sxs-lookup"><span data-stu-id="b27fe-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="b27fe-110">So ändern Sie den zugrunde liegenden Wert eines Procedure-Arguments im aufrufenden Code</span><span class="sxs-lookup"><span data-stu-id="b27fe-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="b27fe-111">Geben Sie in der Prozedur Deklaration [ByRef](../../../language-reference/modifiers/byref.md) für den Parameter an, der dem Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="b27fe-111">In the procedure declaration, specify [ByRef](../../../language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="b27fe-112">Übergeben Sie im aufrufenden Code ein änderbares Programmier Element als Argument.</span><span class="sxs-lookup"><span data-stu-id="b27fe-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="b27fe-113">Schließen Sie das Argument im aufrufenden Code nicht in Klammern in der Argumentliste ein.</span><span class="sxs-lookup"><span data-stu-id="b27fe-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="b27fe-114">Verwenden Sie im Prozedur Code den Parameternamen, um dem zugrunde liegenden Element im aufrufenden Code einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b27fe-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="b27fe-115">Eine Demonstration finden Sie im Beispiel weiter unten.</span><span class="sxs-lookup"><span data-stu-id="b27fe-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="b27fe-116">Ändern von lokalen Kopien</span><span class="sxs-lookup"><span data-stu-id="b27fe-116">Changing Local Copies</span></span>  
 <span data-ttu-id="b27fe-117">Wenn das zugrunde liegende Element im aufrufenden Code ein nicht änderbares Element ist oder wenn das Argument übermittelt wird `ByVal` , kann die Prozedur den Wert im aufrufenden Code nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b27fe-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="b27fe-118">Die Prozedur kann jedoch Ihre lokale Kopie eines solchen Arguments ändern.</span><span class="sxs-lookup"><span data-stu-id="b27fe-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="b27fe-119">So ändern Sie die Kopie eines Prozedur Arguments im Prozedur Code</span><span class="sxs-lookup"><span data-stu-id="b27fe-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="b27fe-120">Geben Sie in der Prozedur Deklaration [ByVal](../../../language-reference/modifiers/byval.md) für den Parameter an, der dem-Argument entspricht.</span><span class="sxs-lookup"><span data-stu-id="b27fe-120">In the procedure declaration, specify [ByVal](../../../language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="b27fe-121">Oder</span><span class="sxs-lookup"><span data-stu-id="b27fe-121">-or-</span></span>  
  
     <span data-ttu-id="b27fe-122">Schließen Sie das Argument im aufrufenden Code in Klammern in die Argumentliste ein.</span><span class="sxs-lookup"><span data-stu-id="b27fe-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="b27fe-123">Dies erzwingt Visual Basic, das Argument als Wert zu übergeben, auch wenn der entsprechende Parameter angibt `ByRef` .</span><span class="sxs-lookup"><span data-stu-id="b27fe-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="b27fe-124">Verwenden Sie im Prozedur Code den Parameternamen, um der lokalen Kopie des Arguments einen Wert zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b27fe-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="b27fe-125">Der zugrunde liegende Wert im aufrufenden Code wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="b27fe-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b27fe-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b27fe-126">Example</span></span>  
 <span data-ttu-id="b27fe-127">Das folgende Beispiel zeigt zwei Prozeduren, die eine Array Variable akzeptieren und deren Elemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b27fe-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="b27fe-128">Die `increase` Prozedur fügt einem Element einfach ein Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="b27fe-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="b27fe-129">Die `replace` Prozedur weist dem-Parameter ein neues Array zu `a()` und fügt dann einem-Element einen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b27fe-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="b27fe-130">Der erste-Befehl `MsgBox` zeigt "After Increase (n): 11, 21, 31, 41" an.</span><span class="sxs-lookup"><span data-stu-id="b27fe-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="b27fe-131">Da es sich bei dem Array `n` um einen Verweistyp handelt, `replace` kann seine Member ändern, auch wenn der Übergabe Mechanismus ist `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="b27fe-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="b27fe-132">Der zweite- `MsgBox` Befehl zeigt "After replace (n): 101, 201, 301" an.</span><span class="sxs-lookup"><span data-stu-id="b27fe-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="b27fe-133">Da erfolgreich `n` ist `ByRef` , `replace` kann die Variable `n` im aufrufenden Code ändern und ihr ein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b27fe-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="b27fe-134">Da `n` ein Verweistyp ist, `replace` kann auch seine Member ändern.</span><span class="sxs-lookup"><span data-stu-id="b27fe-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="b27fe-135">Sie können verhindern, dass die Prozedur die Variable selbst im aufrufenden Code ändert.</span><span class="sxs-lookup"><span data-stu-id="b27fe-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="b27fe-136">Weitere Informationen finden [Sie unter Gewusst wie: Schützen eines Prozedur Arguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md).</span><span class="sxs-lookup"><span data-stu-id="b27fe-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="b27fe-137">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b27fe-137">Compile the code</span></span>  
 <span data-ttu-id="b27fe-138">Wenn Sie eine Variable als Verweis übergeben, müssen Sie dieses Verfahren mit dem- `ByRef` Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="b27fe-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="b27fe-139">Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b27fe-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="b27fe-140">Es ist jedoch eine gute Programmier Übung, das [ByVal](../../../language-reference/modifiers/byval.md) -oder [ByRef](../../../language-reference/modifiers/byref.md) -Schlüsselwort mit jedem deklarierten Parameter einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b27fe-140">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="b27fe-141">Dadurch wird Ihr Code leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="b27fe-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b27fe-142">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b27fe-142">.NET Framework Security</span></span>  
 <span data-ttu-id="b27fe-143">Es besteht immer ein potenzielles Risiko, dass eine Prozedur den Wert ändern kann, der einem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b27fe-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="b27fe-144">Stellen Sie sicher, dass dieser Wert geändert wird, und dass Sie darauf vorbereitet sind, ihn vor der Verwendung auf Gültigkeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b27fe-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27fe-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b27fe-145">See also</span></span>

- [<span data-ttu-id="b27fe-146">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b27fe-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b27fe-147">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b27fe-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b27fe-148">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="b27fe-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="b27fe-149">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b27fe-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b27fe-150">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="b27fe-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="b27fe-151">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b27fe-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="b27fe-152">Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="b27fe-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="b27fe-153">Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="b27fe-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="b27fe-154">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="b27fe-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="b27fe-155">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="b27fe-155">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
