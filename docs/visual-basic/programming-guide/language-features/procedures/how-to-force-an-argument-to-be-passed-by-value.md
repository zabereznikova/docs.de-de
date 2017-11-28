---
title: "Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)"
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
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdb2df7e114f49c23db9f5b322ca9dd32135ac88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="a0337-102">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0337-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="a0337-103">In der Prozedurdeklaration des Übergabemechanismus.</span><span class="sxs-lookup"><span data-stu-id="a0337-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="a0337-104">Wenn ein deklarierter Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erwartet, dass das entsprechende Argument als Verweis zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="a0337-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="a0337-105">Dadurch wird das Verfahren zum Ändern des Werts, der das Programmierelement, die dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="a0337-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="a0337-106">Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie überschreiben die `ByRef` Übergabemechanismus in der Prozedur aufrufen, indem der Name des Arguments in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="a0337-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="a0337-107">Die Klammern sind zusätzlich zu der Klammern, die die Argumentliste im Aufruf einschließen.</span><span class="sxs-lookup"><span data-stu-id="a0337-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="a0337-108">Der aufrufende Code kann nicht überschrieben werden eine [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="a0337-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="a0337-109">So erzwingen ein Argument als Wert übergeben werden</span><span class="sxs-lookup"><span data-stu-id="a0337-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="a0337-110">Wenn der entsprechende Parameter deklariert wird `ByVal` in der Prozedur Sie brauchen keine zusätzlichen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a0337-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="a0337-111">bereits erwartet, dass das Argument als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="a0337-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="a0337-112">Wenn der entsprechende Parameter deklariert wird `ByRef` setzen Sie in der Prozedur das Argument in Klammern in dem Prozeduraufruf.</span><span class="sxs-lookup"><span data-stu-id="a0337-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0337-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a0337-113">Example</span></span>  
 <span data-ttu-id="a0337-114">Im folgenden Beispiel wird eine `ByRef` Parameterdeklaration.</span><span class="sxs-lookup"><span data-stu-id="a0337-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="a0337-115">Im Aufruf erzwingt `ByVal`, beachten Sie die beiden Ebenen von Klammern.</span><span class="sxs-lookup"><span data-stu-id="a0337-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="a0337-116">Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist der `setNewString` Prozedur dessen Wert in der aufrufende Code kann nicht geändert werden und `MsgBox` "Kann nicht ersetzt werden, wenn ByVal überschritten" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0337-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="a0337-117">Wenn `str` nicht gesetzt in zusätzlichen Klammern, die Prozedur kann ggf. geändert und `MsgBox` zeigt "This is einen neuen Wert für das Argument InString."</span><span class="sxs-lookup"><span data-stu-id="a0337-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0337-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a0337-118">Compiling the Code</span></span>  
 <span data-ttu-id="a0337-119">Wenn Sie keine Variable nach Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.</span><span class="sxs-lookup"><span data-stu-id="a0337-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="a0337-120">Die Standardeinstellung in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Argumenten als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a0337-120">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="a0337-121">Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort mit jeder deklarierte Parameter.</span><span class="sxs-lookup"><span data-stu-id="a0337-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="a0337-122">Dadurch wird Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a0337-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a0337-123">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a0337-123">Robust Programming</span></span>  
 <span data-ttu-id="a0337-124">Wenn eine Prozedur einen Parameter deklariert [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), die korrekte Ausführung des Codes abhängen, wird das zugrunde liegende Element im aufrufenden Code ändern können.</span><span class="sxs-lookup"><span data-stu-id="a0337-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="a0337-125">Wenn der aufrufende Code diese Aufrufmechanismus überschreibt, indem das Argument in Klammern einschließen oder übergibt ein Argument nicht veränderbaren, kann nicht das Verfahren der zugrunde liegenden Elemente ändern.</span><span class="sxs-lookup"><span data-stu-id="a0337-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="a0337-126">Dies kann unerwartete Ergebnisse im aufrufenden Code erzeugen.</span><span class="sxs-lookup"><span data-stu-id="a0337-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a0337-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a0337-127">.NET Framework Security</span></span>  
 <span data-ttu-id="a0337-128">In einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt, ist immer ein Sicherheitsrisiko dar.</span><span class="sxs-lookup"><span data-stu-id="a0337-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="a0337-129">Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und es auf Gültigkeit zu überprüfen, vor der Verwendung vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="a0337-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0337-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0337-130">See Also</span></span>  
 [<span data-ttu-id="a0337-131">Verfahren</span><span class="sxs-lookup"><span data-stu-id="a0337-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a0337-132">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a0337-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="a0337-133">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="a0337-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="a0337-134">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="a0337-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="a0337-135">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="a0337-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="a0337-136">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="a0337-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="a0337-137">Gewusst wie: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="a0337-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="a0337-138">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="a0337-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="a0337-139">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="a0337-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="a0337-140">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="a0337-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
