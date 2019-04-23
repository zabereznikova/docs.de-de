---
title: 'Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 8b53df1634d2b9971bc44c968a17db81cac3924f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307885"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="30d73-102">Vorgehensweise: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30d73-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="30d73-103">Ein `Function` Prozedur gibt einen Wert zurück an den aufrufenden Code entweder durch Ausführen einer `Return` Anweisung oder durch Auftreten einer `Exit Function` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="30d73-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="30d73-104">Zum Zurückgeben eines Werts, der mithilfe der Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d73-104">To return a value using the Return statement</span></span>  
  
1. <span data-ttu-id="30d73-105">Einfügen einer `Return` Anweisung, an dem Punkt, in dem die Aufgabe der Prozedur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="30d73-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2. <span data-ttu-id="30d73-106">Führen Sie die `Return` Schlüsselwort mit einem Ausdruck, der den Wert ergibt, an den aufrufenden Code zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="30d73-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3. <span data-ttu-id="30d73-107">Es können sich mehrere `Return`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="30d73-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="30d73-108">Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, und wird an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="30d73-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="30d73-109">Das folgende Beispiel zeigt einen typischen Aufruf von `hypotenuse`, das den zurückgegebenen Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="30d73-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="30d73-110">Zum Zurückgeben eines Werts, der mit der Funktion "Exit" oder eine End-Funktion</span><span class="sxs-lookup"><span data-stu-id="30d73-110">To return a value using Exit Function or End Function</span></span>  
  
1. <span data-ttu-id="30d73-111">In mindestens einer zentralen Stelle in der `Function` Verfahren, weisen Sie einen Wert, der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="30d73-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2. <span data-ttu-id="30d73-112">Beim Ausführen einer `Exit Function` oder `End Function` -Anweisung, Visual Basic gibt den Wert der Name der Prozedur zuletzt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="30d73-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3. <span data-ttu-id="30d73-113">Es können sich mehrere `Exit Function`-Anweisungen in derselben Prozedur befinden. Außerdem können sich sowohl `Return`- als auch `Exit Function`-Anweisungen in derselben Prozedur befinden.</span><span class="sxs-lookup"><span data-stu-id="30d73-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4. <span data-ttu-id="30d73-114">Sie haben nur eine `End Function` -Anweisung in einem `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="30d73-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="30d73-115">Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="30d73-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d73-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30d73-116">See also</span></span>

- [<span data-ttu-id="30d73-117">Verfahren</span><span class="sxs-lookup"><span data-stu-id="30d73-117">Procedures</span></span>](./index.md)
- [<span data-ttu-id="30d73-118">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="30d73-118">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="30d73-119">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="30d73-119">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="30d73-120">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="30d73-120">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="30d73-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="30d73-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="30d73-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d73-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="30d73-123">Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d73-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)
- [<span data-ttu-id="30d73-124">Vorgehensweise: Erstellen Sie eine Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="30d73-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="30d73-125">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="30d73-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
