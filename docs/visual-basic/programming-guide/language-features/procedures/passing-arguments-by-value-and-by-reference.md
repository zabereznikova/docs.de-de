---
title: "Übergeben von Argumenten als Wert und als Verweis (Visual Basic) | Microsoft-Dokumentation"
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
- ByRef keyword, passing arguments by reference
- Visual Basic code, procedures
- passing arguments, by value or by reference
- ByVal keyword, passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing, by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
caps.latest.revision: 23
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
ms.openlocfilehash: 44107171d6f24e22614788470c65cf7ad8d28640
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="db699-102">Übergeben von Argumenten als Wert und als Verweis (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db699-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="db699-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], können Sie ein Argument an eine Prozedur übergeben *Wert* oder *als Verweis*.</span><span class="sxs-lookup"><span data-stu-id="db699-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="db699-104">Dies wird als bezeichnet die *übergeben Mechanismus*, und es wird bestimmt, ob die Prozedur das Programmelement, das dem Argument im Aufrufcode zugrunde liegt ändern kann.</span><span class="sxs-lookup"><span data-stu-id="db699-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="db699-105">Die Prozedurdeklaration wird der Übergabemechanismus für jeden Parameter durch Angabe der [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="db699-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="db699-106">Unterschiede</span><span class="sxs-lookup"><span data-stu-id="db699-106">Distinctions</span></span>  
 <span data-ttu-id="db699-107">Wenn ein Argument an eine Prozedur übergeben, achten Sie auf mehrere verschiedene Unterschiede, die miteinander interagieren:</span><span class="sxs-lookup"><span data-stu-id="db699-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
-   <span data-ttu-id="db699-108">Gibt an, ob das zugrunde liegende Programmierelement änderbar oder nicht veränderbar ist</span><span class="sxs-lookup"><span data-stu-id="db699-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="db699-109">Gibt an, ob das Argument selbst änderbar oder nicht veränderbar ist</span><span class="sxs-lookup"><span data-stu-id="db699-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
-   <span data-ttu-id="db699-110">Gibt an, ob wird das Argument als Wert oder als Verweis übergeben wird</span><span class="sxs-lookup"><span data-stu-id="db699-110">Whether the argument is being passed by value or by reference</span></span>  
  
-   <span data-ttu-id="db699-111">Gibt an, ob der Datentyp des Arguments ein Werttyp oder ein Verweistyp ist</span><span class="sxs-lookup"><span data-stu-id="db699-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="db699-112">Weitere Informationen finden Sie unter [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) und [Unterschiede zwischen übergeben von Argumenten nach Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span><span class="sxs-lookup"><span data-stu-id="db699-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="db699-113">Auswahl der Standardmechanismus zum übergeben</span><span class="sxs-lookup"><span data-stu-id="db699-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="db699-114">Sie sollten die Übergabemechanismus für jedes Argument sorgfältig auswählen.</span><span class="sxs-lookup"><span data-stu-id="db699-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
-   <span data-ttu-id="db699-115">**Schutz**.</span><span class="sxs-lookup"><span data-stu-id="db699-115">**Protection**.</span></span> <span data-ttu-id="db699-116">Bei der Wahl zwischen zwei übergeben Mechanismen, ist das wichtigste Kriterium die Offenlegung von geändert.</span><span class="sxs-lookup"><span data-stu-id="db699-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="db699-117">Der Vorteil der Argumentübergabe `ByRef` besteht darin, dass die Prozedur einen Wert an den aufrufenden Code durch dieses Argument zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="db699-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="db699-118">Der Vorteil der Argumentübergabe `ByVal` besteht darin, dass es dadurch verhindert, dass eine Variable, die von der Prozedur geändert wird.</span><span class="sxs-lookup"><span data-stu-id="db699-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
-   <span data-ttu-id="db699-119">**Leistung**.</span><span class="sxs-lookup"><span data-stu-id="db699-119">**Performance**.</span></span> <span data-ttu-id="db699-120">Obwohl die Methode übergeben, die Leistung Ihres Codes auswirken kann, ist in der Regel unbedeutend.</span><span class="sxs-lookup"><span data-stu-id="db699-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="db699-121">Eine Ausnahme ist ein übergebener Werttyp `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="db699-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="db699-122">In diesem Fall [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert den gesamten Inhalt des Arguments.</span><span class="sxs-lookup"><span data-stu-id="db699-122">In this case, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] copies the entire data contents of the argument.</span></span> <span data-ttu-id="db699-123">Aus diesem Grund für einen hohen Wert wie z. B. eine Struktur, es kann effizienter sein übergeben `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="db699-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="db699-124">Bei Verweistypen wird nur der Zeiger auf die Daten kopiert (vier Bytes auf 32-Bit-Plattformen, 8 Bytes auf 64-Bit-Plattformen).</span><span class="sxs-lookup"><span data-stu-id="db699-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="db699-125">Deshalb können Sie Argumente des Typs übergeben `String` oder `Object` Wert ohne Leistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="db699-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="db699-126">Bestimmung des Mechanismus übergeben</span><span class="sxs-lookup"><span data-stu-id="db699-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="db699-127">Die Prozedurdeklaration gibt den Übergabemechanismus für jeden Parameter.</span><span class="sxs-lookup"><span data-stu-id="db699-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="db699-128">Der aufrufende Code kann nicht überschrieben werden ein `ByVal` Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="db699-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="db699-129">Wenn ein Parameter mit deklariert ist `ByRef`, der aufrufende Code kann den Mechanismus zum erzwingen `ByVal` durch den Namen des Arguments in Klammern im Aufruf einschließen.</span><span class="sxs-lookup"><span data-stu-id="db699-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="db699-130">Weitere Informationen finden Sie unter [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="db699-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="db699-131">Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="db699-131">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="db699-132">Wenn ein Argument als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="db699-132">When to Pass an Argument by Value</span></span>  
  
-   <span data-ttu-id="db699-133">Wenn der aufrufende Code-Element, das dem Argument zugrunde liegt ein nicht änderbares Element ist, deklarieren Sie den entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="db699-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="db699-134">Kein Code kann den Wert eines nicht veränderbaren Elements ändern.</span><span class="sxs-lookup"><span data-stu-id="db699-134">No code can change the value of a nonmodifiable element.</span></span>  
  
-   <span data-ttu-id="db699-135">Wenn das zugrunde liegende Element geändert werden kann, aber nicht, dass die Prozedur den Wert ändern können möchten, deklarieren Sie den Parameter `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="db699-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="db699-136">Nur der aufrufende Code kann den Wert eines änderbaren Elements übergebener Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="db699-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="db699-137">Wenn ein Argument als Verweis übergeben</span><span class="sxs-lookup"><span data-stu-id="db699-137">When to Pass an Argument by Reference</span></span>  
  
-   <span data-ttu-id="db699-138">Die Prozedur unbedingt das zugrunde liegende Element im Aufrufcode ändern muss, deklarieren Sie den entsprechenden Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span><span class="sxs-lookup"><span data-stu-id="db699-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
-   <span data-ttu-id="db699-139">Wenn die richtige Ausführung des Codes für die Prozedur das zugrunde liegende Element im Aufrufcode ändern abhängig ist, deklarieren Sie den Parameter `ByRef`.</span><span class="sxs-lookup"><span data-stu-id="db699-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="db699-140">Wenn er als Wert übergeben, oder wenn der aufrufende Code überschreibt die `ByRef` Mechanismus übergeben, indem das Argument in Klammern ein, den Aufruf der Prozedur möglicherweise zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="db699-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db699-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db699-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="db699-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db699-142">Description</span></span>  
 <span data-ttu-id="db699-143">Im folgende Beispiel wird veranschaulicht, wann zur Übergabe von Argumenten als Wert und wann sie als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="db699-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="db699-144">Prozedur `Calculate` verfügt sowohl über eine `ByVal` und ein `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="db699-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="db699-145">Erhält einen Zinssatz `rate`, und einer Geldsumme, `debt`, berechnen Sie einen neuen Wert für die Aufgabe der Prozedur ist `debt` , das Ergebnis der Anwendung von der Zinssatz auf den ursprünglichen Wert des `debt`.</span><span class="sxs-lookup"><span data-stu-id="db699-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="db699-146">Da `debt` ist ein `ByRef` -Parameter, die neue Summe wirkt sich der Wert des Arguments in den aufrufenden Code, der entspricht `debt`.</span><span class="sxs-lookup"><span data-stu-id="db699-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="db699-147">Parameter `rate` ist ein `ByVal` Parameter da `Calculate` sollten den Wert nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="db699-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="db699-148">Code</span><span class="sxs-lookup"><span data-stu-id="db699-148">Code</span></span>  
 <span data-ttu-id="db699-149">[!code-vb[VbVbcnProcedures&#74;](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="db699-149">[!code-vb[VbVbcnProcedures#74](./codesnippet/VisualBasic/passing-arguments-by-value-and-by-reference_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db699-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db699-150">See Also</span></span>  
 <span data-ttu-id="db699-151">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="db699-151">[Procedures](./index.md) </span></span>  
<span data-ttu-id="db699-152"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="db699-152"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="db699-153"> [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="db699-153"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="db699-154"> [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="db699-154"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="db699-155"> [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="db699-155"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="db699-156"> [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="db699-156"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="db699-157"> [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="db699-157"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="db699-158"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="db699-158"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
