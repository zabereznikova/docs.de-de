---
title: 'Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
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
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59c0486bd9543167e4c17a3109c4b89b3502e80e
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="b3fe7-102">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3fe7-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="b3fe7-103">Wenn eine Prozedur einen Parameter als [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic Code der Prozedur bietet einen direkten Verweis auf das Programmierelement, die dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="b3fe7-104">Dies ermöglicht das Verfahren zum Ändern des Werts, der dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="b3fe7-105">In einigen Fällen kann der aufrufende Code eine solche Änderung schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="b3fe7-106">Sie können ein Argument immer vor Änderung schützen, indem der entsprechende Parameter deklarieren [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="b3fe7-107">Wenn Sie ein bestimmtes Argument in einigen Fällen ändern möchten, deklarieren Sie es `ByRef` , sodass den aufrufenden Code, der den Übergabemechanismus bei jedem Aufruf zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="b3fe7-108">Dies geschieht durch das entsprechende Argument in Klammern für die Übergabe nach Wert einschließen oder schließen Sie es nicht in Klammern einschließen, um ihn als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="b3fe7-109">Weitere Informationen finden Sie unter [wie: erzwingen, dass ein Argument als Wert übergeben werden](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="b3fe7-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3fe7-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3fe7-110">Example</span></span>  
 <span data-ttu-id="b3fe7-111">Das folgende Beispiel zeigt zwei Prozeduren, die eine Arrayvariable und ausgeführt werden, auf deren Elemente.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="b3fe7-112">Die `increase` Verfahren einfach zu jedem Element hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="b3fe7-113">Die `replace` -Prozedur weist den Parameter ein neues Array `a()` , und klicken Sie dann auf jedes Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="b3fe7-114">Die erneute Zuweisung wirkt sich jedoch nicht auf die zugrunde liegende Arrayvariable im aufrufenden Code aus.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 <span data-ttu-id="b3fe7-115">Die erste `MsgBox` -Aufruf zeigt "After increase(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="b3fe7-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="b3fe7-116">Da das Array `n` ist ein Verweistyp `replace` seiner Elemente, können geändert werden, obwohl der Übergabemechanismus ist `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-116">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="b3fe7-117">Die zweite `MsgBox` -Aufruf zeigt "After replace(n):: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="b3fe7-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="b3fe7-118">Da `n` übergeben `ByVal`, `replace` die Variable kann nicht geändert werden `n` im aufrufenden Code, indem Sie ein neues Array zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="b3fe7-119">Wenn `replace` die Instanz des neuen Arrays erstellt `k` und weist sie auf die lokale Variable `a`, geht den Verweis auf `n` vom aufrufenden Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="b3fe7-120">Wenn sie die Mitglieder der ändert `a`, nur die lokale Array `k` betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="b3fe7-121">Aus diesem Grund `replace` erhöht sich die Werte des Arrays nicht `n` im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3fe7-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b3fe7-122">Compiling the Code</span></span>  
 <span data-ttu-id="b3fe7-123">Der Standardwert in Visual Basic ist Argumenten als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="b3fe7-124">Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jeder deklarierte Parameter.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="b3fe7-125">Dadurch wird Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="b3fe7-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fe7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3fe7-126">See Also</span></span>  
 [<span data-ttu-id="b3fe7-127">Verfahren</span><span class="sxs-lookup"><span data-stu-id="b3fe7-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="b3fe7-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b3fe7-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="b3fe7-129">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="b3fe7-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="b3fe7-130">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b3fe7-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="b3fe7-131">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="b3fe7-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="b3fe7-132">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b3fe7-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="b3fe7-133">Gewusst wie: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="b3fe7-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="b3fe7-134">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="b3fe7-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="b3fe7-135">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="b3fe7-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="b3fe7-136">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="b3fe7-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
