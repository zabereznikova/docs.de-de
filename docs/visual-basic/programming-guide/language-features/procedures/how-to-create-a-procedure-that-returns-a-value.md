---
title: 'Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 472f55173a4897a23a82812a2b24bf1646c1a6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648436"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="30822-102">Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30822-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="30822-103">Sie verwenden eine `Function` -Prozedur, einen Wert an den aufrufenden Code zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="30822-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="30822-104">So erstellen Sie eine Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="30822-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="30822-105">Außerhalb eine beliebige andere Prozedur verwendet eine `Function` Anweisung, gefolgt von einem `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="30822-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="30822-106">In der `Function` -Anweisung, befolgen Sie die `Function` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann die Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="30822-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="30822-107">Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des zurückgegebenen Werts angeben.</span><span class="sxs-lookup"><span data-stu-id="30822-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="30822-108">Platzieren Sie die Prozedur codeanweisungen zwischen der `Function` und `End Function` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="30822-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="30822-109">Verwenden einer `Return` -Anweisung den Wert an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="30822-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="30822-110">Die folgenden `Function` Prozedur berechnet die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks, anhand der Werte der beiden anderen Seiten.</span><span class="sxs-lookup"><span data-stu-id="30822-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="30822-111">Das folgende Beispiel zeigt einen typischen Aufruf `hypotenuse`.</span><span class="sxs-lookup"><span data-stu-id="30822-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="30822-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30822-112">See Also</span></span>  
 [<span data-ttu-id="30822-113">Verfahren</span><span class="sxs-lookup"><span data-stu-id="30822-113">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="30822-114">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="30822-114">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="30822-115">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="30822-115">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="30822-116">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="30822-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="30822-117">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="30822-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="30822-118">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30822-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="30822-119">Gewusst wie: Abrufen eines Werts aus einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="30822-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="30822-120">Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt</span><span class="sxs-lookup"><span data-stu-id="30822-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
