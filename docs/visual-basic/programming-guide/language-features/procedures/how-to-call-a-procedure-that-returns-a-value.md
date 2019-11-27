---
title: 'Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 7f5d46babf31ea3c6babb29c0f1c08a23e51d598
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340733"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="82180-102">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82180-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="82180-103">Eine `Function` Prozedur gibt einen Wert an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="82180-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="82180-104">Sie werden aufgerufen, indem Sie den Namen und die Argumente entweder auf der rechten Seite einer Zuweisungsanweisung oder in einem Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="82180-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="82180-105">So greifen Sie eine Funktions Prozedur innerhalb eines Ausdrucks an</span><span class="sxs-lookup"><span data-stu-id="82180-105">To call a Function procedure within an expression</span></span>  
  
1. <span data-ttu-id="82180-106">Verwenden Sie den `Function` Prozedur Namen auf dieselbe Weise wie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="82180-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="82180-107">Sie können einen `Function` Prozedur aufrufen überall dort verwenden, wo Sie eine Variable oder Konstante in einem Ausdruck verwenden können.</span><span class="sxs-lookup"><span data-stu-id="82180-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2. <span data-ttu-id="82180-108">Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="82180-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="82180-109">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="82180-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="82180-110">Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="82180-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="82180-111">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="82180-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="82180-112">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Function` Prozedur die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="82180-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="82180-113">Alternativ können Sie ein oder mehrere Argumente nach Namen übergeben.</span><span class="sxs-lookup"><span data-stu-id="82180-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="82180-114">Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="82180-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4. <span data-ttu-id="82180-115">Der Wert, der von der-Prozedur zurückgegeben wird, nimmt genauso an, wie der Wert einer Variablen oder Konstanten.</span><span class="sxs-lookup"><span data-stu-id="82180-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="82180-116">So greifen Sie eine Funktions Prozedur in einer Zuweisungsanweisung an</span><span class="sxs-lookup"><span data-stu-id="82180-116">To call a Function procedure in an assignment statement</span></span>  
  
1. <span data-ttu-id="82180-117">Verwenden Sie den Namen der `Function` Prozedur nach dem Gleichheitszeichen (`=`) in der Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="82180-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2. <span data-ttu-id="82180-118">Befolgen Sie den Namen der Prozedur mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="82180-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="82180-119">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="82180-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="82180-120">Durch die Verwendung der Klammern wird der Code jedoch leichter lesbar.</span><span class="sxs-lookup"><span data-stu-id="82180-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3. <span data-ttu-id="82180-121">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="82180-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="82180-122">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die `Function` Prozedur die entsprechenden Parameter definiert, es sei denn, Sie übergeben Sie nach Namen.</span><span class="sxs-lookup"><span data-stu-id="82180-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4. <span data-ttu-id="82180-123">Der von der Prozedur zurückgegebene Wert wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="82180-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82180-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="82180-124">Example</span></span>  
 <span data-ttu-id="82180-125">Im folgenden Beispiel wird der Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> aufgerufen, um den Wert einer Betriebssystem-Umgebungsvariablen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="82180-125">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="82180-126">Die erste Zeile ruft `Environ` innerhalb eines Ausdrucks auf, und die zweite Zeile ruft Sie in einer Zuweisungsanweisung auf.</span><span class="sxs-lookup"><span data-stu-id="82180-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="82180-127">`Environ` nimmt den Variablennamen als das einzige Argument an.</span><span class="sxs-lookup"><span data-stu-id="82180-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="82180-128">Der Wert der Variablen wird an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="82180-128">It returns the variable's value to the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="82180-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82180-129">See also</span></span>

- [<span data-ttu-id="82180-130">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="82180-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="82180-131">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="82180-131">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="82180-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="82180-132">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="82180-133">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="82180-133">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="82180-134">Gewusst wie: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="82180-134">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="82180-135">Gewusst wie: Aufrufen einer Prozedur, die keinen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="82180-135">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)
