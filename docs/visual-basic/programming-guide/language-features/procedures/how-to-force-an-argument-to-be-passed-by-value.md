---
title: "Gewusst wie: erzwingen, dass ein Argument als Wert (Visual Basic) übergeben werden | Microsoft-Dokumentation"
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
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
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
ms.openlocfilehash: b151c319489ccda357faa082ce0b3c1addad0458
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="7c0f6-102">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c0f6-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="7c0f6-103">Den Übergabemechanismus der Prozedurdeklaration.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="7c0f6-104">Wenn ein Parameter deklariert ist [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erwartet, dass das entsprechende Argument als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="7c0f6-105">Dadurch wird die Vorgehensweise zum Ändern des Werts des Programmierelements dem Argument im Aufrufcode zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="7c0f6-106">Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie überschreiben die `ByRef` übergeben Mechanismus in der Prozedur aufrufen, indem Sie den Namen des Arguments in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="7c0f6-107">Die Klammern sind zusätzlich zu den Klammern, die die Argumentliste im Aufruf einschließen.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="7c0f6-108">Der aufrufende Code kann nicht überschrieben werden eine [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="7c0f6-109">Erzwingen Sie ein Argument als Wert übergeben werden</span><span class="sxs-lookup"><span data-stu-id="7c0f6-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="7c0f6-110">Wenn der entsprechende Parameter deklariert ist `ByVal` in der Prozedur Sie brauchen keine zusätzlichen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7c0f6-111">bereits erwartet, dass das Argument als Wert übergeben.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="7c0f6-112">Wenn der entsprechende Parameter deklariert ist `ByRef` im Verfahren setzen Sie das Argument im Prozeduraufruf in Klammern.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c0f6-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c0f6-113">Example</span></span>  
 <span data-ttu-id="7c0f6-114">Im folgenden Beispiel wird eine `ByRef` Parameterdeklaration.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="7c0f6-115">In den Aufruf, der erzwingt `ByVal`, beachten Sie die zwei Ebenen von Klammern.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 <span data-ttu-id="7c0f6-116">[!code-vb[VbVbcnProcedures Nr.&39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c0f6-116">[!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span></span>  
  
 <span data-ttu-id="7c0f6-117">[!code-vb[VbVbcnProcedures&#40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7c0f6-117">[!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span></span>  
  
 <span data-ttu-id="7c0f6-118">Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist die `setNewString` Prozedur Wert in den aufrufenden Code, nicht ändern und `MsgBox` "Kann nicht ersetzt werden, wenn ByVal übergeben" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-118">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="7c0f6-119">Wenn `str` nicht gesetzt in zusätzlichen Klammern kann die Prozedur ändern, und `MsgBox` wird "Dies ist der Wert".</span><span class="sxs-lookup"><span data-stu-id="7c0f6-119">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c0f6-120">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7c0f6-120">Compiling the Code</span></span>  
 <span data-ttu-id="7c0f6-121">Wenn Sie eine Variable als Verweis übergeben, müssen Sie mithilfe der `ByRef` Schlüsselwort dieser Mechanismus angeben.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-121">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="7c0f6-122">Die Standardeinstellung für [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Argumente als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-122">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="7c0f6-123">Allerdings ist es guter Programmierstil, entweder enthalten die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) -Schlüsselwort in jeden deklarierten Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-123">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="7c0f6-124">Dadurch wird Ihr Code leichter zu lesen.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-124">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7c0f6-125">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="7c0f6-125">Robust Programming</span></span>  
 <span data-ttu-id="7c0f6-126">Wenn eine Prozedur einen Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), die richtige Ausführung des Codes abhängen, wird das zugrunde liegende Element im Aufrufcode ändern können.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-126">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="7c0f6-127">Wenn der Aufrufcode diesen Aufrufmechanismus überschreibt, indem das Argument in Klammern einschließen, oder es ein unveränderliches Argument übergibt, kann nicht in die Prozedur das zugrunde liegende Element ändern.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-127">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="7c0f6-128">Dies kann im Aufrufcode unerwartete Ergebnisse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-128">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7c0f6-129">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7c0f6-129">.NET Framework Security</span></span>  
 <span data-ttu-id="7c0f6-130">Es ist immer ein potenzielles Risiko einer Prozedur so ändern Sie den Wert, der einem Argument im Aufrufcode zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-130">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="7c0f6-131">Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und bereiten Sie sich vor der Verwendung auf Gültigkeit überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7c0f6-131">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0f6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c0f6-132">See Also</span></span>  
 <span data-ttu-id="7c0f6-133">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-133">[Procedures](./index.md) </span></span>  
<span data-ttu-id="7c0f6-134"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-134"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="7c0f6-135"> [Gewusst wie: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-135"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="7c0f6-136"> [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-136"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="7c0f6-137"> [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-137"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="7c0f6-138"> [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-138"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="7c0f6-139"> [Gewusst wie: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="7c0f6-140"> [Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="7c0f6-141"> [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="7c0f6-141"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="7c0f6-142"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="7c0f6-142"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
