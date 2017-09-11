---
title: "Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic) | Microsoft-Dokumentation"
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
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
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
ms.openlocfilehash: db40b3426256e7789a5273ab4d0afc8d5b47c8a7
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="21742-102">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21742-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="21742-103">Wenn eine Prozedur einen Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] übergibt der Prozedur einen direkten Verweis auf das Programmierelement, das dem Argument im Aufrufcode zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="21742-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="21742-104">Dies ermöglicht das Verfahren zum Ändern des Werts, der dem Argument im Aufrufcode zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="21742-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="21742-105">In einigen Fällen kann der aufrufende Code eine solche Änderung schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="21742-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="21742-106">Sie können immer ein Argument vor einer Änderung schützen durch deklarieren den entsprechenden Parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="21742-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="21742-107">Wenn Sie ein Argument nur in bestimmten Fällen ändern können möchten, deklarieren Sie es `ByRef` , und lassen Sie den aufrufenden Code übergeben-Mechanismus in jedem Aufruf zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="21742-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="21742-108">Hierzu wird das entsprechende Argument in Klammern für die Übergabe nach Wert einschließen oder es nicht in Klammern zur Übergabe nach Verweis einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="21742-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="21742-109">Weitere Informationen finden Sie unter [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="21742-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21742-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21742-110">Example</span></span>  
 <span data-ttu-id="21742-111">Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente.</span><span class="sxs-lookup"><span data-stu-id="21742-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="21742-112">Die `increase` Prozedur fügt einfach zu jedem Element.</span><span class="sxs-lookup"><span data-stu-id="21742-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="21742-113">Die `replace` -Prozedur weist den Parameter ein neues Array `a()` und fügt dann jedem Element&1; hinzu.</span><span class="sxs-lookup"><span data-stu-id="21742-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="21742-114">Die erneute Zuweisung wirkt sich jedoch nicht auf der zugrunde liegenden Arrayvariablen im Aufrufcode aus.</span><span class="sxs-lookup"><span data-stu-id="21742-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="21742-115">[!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="21742-115">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span></span>  
  
 <span data-ttu-id="21742-116">[!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="21742-116">[!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span></span>  
  
 <span data-ttu-id="21742-117">[!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="21742-117">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span></span>  
  
 <span data-ttu-id="21742-118">Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="21742-118">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="21742-119">Da das Array `n` ist ein Verweistyp, `replace` kann seine Member ändern, obwohl die Übergabemechanismus ist `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="21742-119">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="21742-120">Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="21742-120">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="21742-121">Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` in den aufrufenden Code, indem Sie ein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="21742-121">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="21742-122">Wenn `replace` neue Arrayinstanz erstellt `k` und weist sie auf die lokale Variable `a`, verliert den Verweis auf `n` vom aufrufenden Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="21742-122">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="21742-123">Wenn sie die Mitglieder ändert `a`, nur auf das lokale Array `k` betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="21742-123">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="21742-124">Aus diesem Grund `replace` erhöht sich die Werte des Arrays nicht `n` im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="21742-124">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21742-125">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="21742-125">Compiling the Code</span></span>  
 <span data-ttu-id="21742-126">Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="21742-126">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="21742-127">Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort in jeden deklarierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="21742-127">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="21742-128">Dadurch wird Ihr Code leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="21742-128">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21742-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21742-129">See Also</span></span>  
 <span data-ttu-id="21742-130">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="21742-130">[Procedures](./index.md) </span></span>  
<span data-ttu-id="21742-131"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="21742-131"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="21742-132"> [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="21742-132"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="21742-133"> [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="21742-133"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="21742-134"> [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="21742-134"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="21742-135"> [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="21742-135"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="21742-136"> [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="21742-136"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="21742-137"> [Gewusst wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="21742-137"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="21742-138"> [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="21742-138"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="21742-139"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="21742-139"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
