---
title: 'Vorgehensweise: Erstellen einer Prozedur, die einen Wert zurückgibt'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 3d28162d2a2103477a20b08fc03c937de8b5a475
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071871"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="e0019-102">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0019-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>

<span data-ttu-id="e0019-103">Sie verwenden eine `Function` Prozedur, um einen Wert an den aufrufenden Code zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0019-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="e0019-104">So erstellen Sie eine Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="e0019-104">To create a procedure that returns a value</span></span>  
  
1. <span data-ttu-id="e0019-105">Verwenden Sie außerhalb einer anderen Prozedur eine- `Function` Anweisung, gefolgt von einer- `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e0019-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2. <span data-ttu-id="e0019-106">`Function`Befolgen Sie in der-Anweisung das `Function` -Schlüsselwort mit dem Namen der Prozedur und anschließend die Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="e0019-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3. <span data-ttu-id="e0019-107">Folgen Sie den Klammern mit einer- `As` Klausel, um den Datentyp des zurückgegebenen Werts anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0019-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4. <span data-ttu-id="e0019-108">Platzieren Sie die Code Anweisungen der Prozedur zwischen der `Function` -Anweisung und der- `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e0019-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5. <span data-ttu-id="e0019-109">Verwenden Sie eine- `Return` Anweisung, um den Wert an den aufrufenden Code zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e0019-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="e0019-110">Im folgenden `Function` Verfahren wird die längste Seite (Hypotenuse) eines Rechts Dreiecks berechnet, wobei die Werte für die beiden anderen Seiten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0019-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     <span data-ttu-id="e0019-111">Das folgende Beispiel zeigt einen typischen-Rückruf `hypotenuse` .</span><span class="sxs-lookup"><span data-stu-id="e0019-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="e0019-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0019-112">See also</span></span>

- [<span data-ttu-id="e0019-113">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="e0019-113">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e0019-114">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e0019-114">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="e0019-115">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="e0019-115">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="e0019-116">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="e0019-116">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e0019-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e0019-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e0019-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e0019-118">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="e0019-119">Vorgehensweise: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="e0019-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="e0019-120">Vorgehensweise: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="e0019-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
