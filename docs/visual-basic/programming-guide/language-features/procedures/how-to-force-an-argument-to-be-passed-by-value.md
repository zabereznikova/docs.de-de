---
title: 'Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird'
ms.date: 07/20/2015
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
ms.openlocfilehash: 0be49e7d4aacbb30956bda7f6ee8494a7ded8b78
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071624"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="b607a-102">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b607a-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>

<span data-ttu-id="b607a-103">Die Prozedur Deklaration bestimmt den Übergabe Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="b607a-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="b607a-104">Wenn ein Parameter als [ByRef](../../../language-reference/modifiers/byref.md)deklariert wird, erwartet Visual Basic, dass das entsprechende Argument als Verweis übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b607a-104">If a parameter is declared [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="b607a-105">Dies ermöglicht es der Prozedur, den Wert des Programmier Elements zu ändern, das dem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b607a-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="b607a-106">Wenn Sie das zugrunde liegende Element gegen eine solche Änderung schützen möchten, können Sie den `ByRef` Übergabe Mechanismus im Prozedur aufzurufen überschreiben, indem Sie den Argument Namen in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="b607a-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="b607a-107">Diese Klammern sind zusätzlich zu den Klammern angegeben, die die Argumentliste im-Befehl einschließen.</span><span class="sxs-lookup"><span data-stu-id="b607a-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="b607a-108">Der Aufruf Code kann einen [ByVal](../../../language-reference/modifiers/byval.md) -Mechanismus nicht überschreiben.</span><span class="sxs-lookup"><span data-stu-id="b607a-108">The calling code cannot override a [ByVal](../../../language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="b607a-109">So erzwingen Sie, dass ein Argument als Wert übermittelt wird</span><span class="sxs-lookup"><span data-stu-id="b607a-109">To force an argument to be passed by value</span></span>  
  
- <span data-ttu-id="b607a-110">Wenn der entsprechende Parameter `ByVal` in der Prozedur deklariert ist, müssen Sie keine weiteren Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="b607a-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="b607a-111">Visual Basic erwartet bereits, dass das Argument als Wert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b607a-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
- <span data-ttu-id="b607a-112">Wenn der entsprechende Parameter `ByRef` in der Prozedur deklariert wird, schließen Sie das Argument in Klammern in den Prozedur aufrufen ein.</span><span class="sxs-lookup"><span data-stu-id="b607a-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b607a-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b607a-113">Example</span></span>  

 <span data-ttu-id="b607a-114">Im folgenden Beispiel wird eine `ByRef` Parameter Deklaration überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b607a-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="b607a-115">Beachten Sie in dem von Erzwingung erzwingt `ByVal` die zwei Ebenen von Klammern.</span><span class="sxs-lookup"><span data-stu-id="b607a-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="b607a-116">Wenn `str` in zusätzliche Klammern in der Argumentliste eingeschlossen ist, `setNewString` kann die Prozedur den Wert im aufrufenden Code nicht ändern und `MsgBox` zeigt "kann nicht ersetzt werden, wenn ByVal übergeben wird" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b607a-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="b607a-117">Wenn `str` nicht in zusätzliche Klammern eingeschlossen ist, kann Sie von der Prozedur geändert werden, und es wird `MsgBox` angezeigt, dass dies ein neuer Wert für das inString-Argument ist.</span><span class="sxs-lookup"><span data-stu-id="b607a-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="b607a-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b607a-118">Compile the code</span></span>  

 <span data-ttu-id="b607a-119">Wenn Sie eine Variable als Verweis übergeben, müssen Sie dieses Verfahren mit dem- `ByRef` Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="b607a-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="b607a-120">Der Standardwert in Visual Basic besteht darin, Argumente als Wert zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b607a-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="b607a-121">Es ist jedoch eine gute Programmier Übung, das [ByVal](../../../language-reference/modifiers/byval.md) -oder [ByRef](../../../language-reference/modifiers/byref.md) -Schlüsselwort mit jedem deklarierten Parameter einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="b607a-121">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="b607a-122">Dadurch wird Ihr Code leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="b607a-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b607a-123">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b607a-123">Robust Programming</span></span>  

 <span data-ttu-id="b607a-124">Wenn eine Prozedur einen [ByRef](../../../language-reference/modifiers/byref.md)-Parameter deklariert, hängt die korrekte Ausführung des Codes möglicherweise davon ab, ob das zugrunde liegende Element im aufrufenden Code geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="b607a-124">If a procedure declares a parameter [ByRef](../../../language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="b607a-125">Wenn der aufrufende Code diesen Aufruf Mechanismus überschreibt, indem das Argument in Klammern eingeschlossen wird, oder wenn er ein nicht änderbares Argument übergibt, kann die Prozedur das zugrunde liegende Element nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b607a-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="b607a-126">Dies kann zu unerwarteten Ergebnissen im aufrufenden Code führen.</span><span class="sxs-lookup"><span data-stu-id="b607a-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b607a-127">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b607a-127">.NET Framework Security</span></span>  

 <span data-ttu-id="b607a-128">Es besteht immer ein potenzielles Risiko, dass eine Prozedur den Wert ändern kann, der einem Argument im aufrufenden Code zugrunde liegt.</span><span class="sxs-lookup"><span data-stu-id="b607a-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="b607a-129">Stellen Sie sicher, dass dieser Wert geändert wird, und dass Sie darauf vorbereitet sind, ihn vor der Verwendung auf Gültigkeit zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b607a-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b607a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b607a-130">See also</span></span>

- [<span data-ttu-id="b607a-131">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b607a-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b607a-132">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b607a-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b607a-133">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="b607a-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="b607a-134">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b607a-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b607a-135">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten</span><span class="sxs-lookup"><span data-stu-id="b607a-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="b607a-136">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="b607a-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="b607a-137">Vorgehensweise: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="b607a-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="b607a-138">Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="b607a-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="b607a-139">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="b607a-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="b607a-140">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="b607a-140">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
