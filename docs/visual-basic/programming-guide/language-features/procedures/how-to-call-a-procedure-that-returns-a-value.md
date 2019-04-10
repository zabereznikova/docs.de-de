---
title: 'Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 6f45f01489ee84b6addb1f7c7c8dc584332f38dd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333885"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="33308-102">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33308-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="33308-103">Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="33308-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="33308-104">Rufen Sie sie einschließlich der Namen und die Argumente entweder auf der rechten Seite einer zuweisungsanweisung oder in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="33308-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="33308-105">Um eine Funktion innerhalb eines Ausdrucks aufzurufen</span><span class="sxs-lookup"><span data-stu-id="33308-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="33308-106">Verwenden Sie die `Function` Prozedur benennen Sie die gleiche Weise verwenden Sie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="33308-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="33308-107">Sie können eine `Function` Prozedur aufrufen anywhere können Sie eine Variable oder Konstante in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="33308-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="33308-108">Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="33308-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="33308-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="33308-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="33308-110">Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="33308-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="33308-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="33308-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="33308-112">Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Function` Prozedur definiert, die entsprechenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="33308-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="33308-113">Alternativ können Sie ein oder mehrere Argumente anhand des Namens übergeben.</span><span class="sxs-lookup"><span data-stu-id="33308-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="33308-114">Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="33308-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="33308-115">Der von der Prozedur zurückgegebene Wert ist Teil des Ausdrucks ebenso wie der Wert einer Variablen oder Konstanten würde.</span><span class="sxs-lookup"><span data-stu-id="33308-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="33308-116">Um eine Funktion in einer zuweisungsanweisung aufzurufen</span><span class="sxs-lookup"><span data-stu-id="33308-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="33308-117">Verwenden der `Function` Prozedurnamen folgen den Gleichheitsoperator (`=`) melden Sie sich die zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="33308-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="33308-118">Führen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="33308-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="33308-119">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="33308-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="33308-120">Allerdings wird bei der Klammern verwenden die Ihr Code einfacher zu lesen.</span><span class="sxs-lookup"><span data-stu-id="33308-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="33308-121">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="33308-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="33308-122">Werden Sie sicher, dass Sie die Argumente in der gleichen Reihenfolge angeben, die die `Function` Prozedur definiert die entsprechenden Parameter, es sei denn, Sie über den Namen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="33308-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="33308-123">Der von der Prozedur zurückgegebene Wert ist in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="33308-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33308-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33308-124">Example</span></span>  
 <span data-ttu-id="33308-125">Im folgenden Beispiel wird die Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> zum Abrufen des Werts einer Betriebssystem-Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="33308-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="33308-126">Die erste Zeile ruft `Environ` in einen Ausdruck ein, und die zweite Zeile ruft es in einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="33308-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> `Environ` <span data-ttu-id="33308-127">akzeptiert den Namen den Variablen als einziges Argument.</span><span class="sxs-lookup"><span data-stu-id="33308-127">takes the variable name as its sole argument.</span></span> <span data-ttu-id="33308-128">Der Wert der Variablen zurückgegeben an den aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="33308-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="33308-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33308-129">See also</span></span>

- [<span data-ttu-id="33308-130">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="33308-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="33308-131">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="33308-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="33308-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="33308-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="33308-133">Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="33308-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="33308-134">Vorgehensweise: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="33308-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="33308-135">Vorgehensweise: Aufrufen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="33308-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
