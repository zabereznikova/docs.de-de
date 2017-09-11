---
title: "Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic) | Microsoft-Dokumentation"
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
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
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
ms.openlocfilehash: 601cd3adca0105eb829bb6156f94289b5c9f5f72
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="533ff-102">Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="533ff-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="533ff-103">Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code entweder durch Ausführen einer `Return` Anweisung oder beim Auftreten einer `Exit Function` oder `End Function` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="533ff-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="533ff-104">Zum Zurückgeben eines Werts mithilfe der Return-Anweisung</span><span class="sxs-lookup"><span data-stu-id="533ff-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="533ff-105">Einfügen einer `Return` -Anweisung an dem Punkt, an dem die Aufgabe der Prozedur abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="533ff-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="533ff-106">Führen Sie die `Return` -Schlüsselwort ein Ausdruck den Wert ergibt an den aufrufenden Code zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="533ff-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="533ff-107">Stehen Ihnen mehrere `Return` Anweisung in der gleichen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="533ff-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="533ff-108">Die folgenden `Function` die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks berechnet und an den aufrufenden Code zurück.</span><span class="sxs-lookup"><span data-stu-id="533ff-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     <span data-ttu-id="533ff-109">[!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="533ff-109">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="533ff-110">Das folgende Beispiel zeigt einen normalen Aufruf `hypotenuse`, die den zurückgegebenen Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="533ff-110">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     <span data-ttu-id="533ff-111">[!code-vb[VbVbcnProcedures&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="533ff-111">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span></span>  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="533ff-112">Zum Zurückgeben eines Werts mit Exit Function oder End-Funktion</span><span class="sxs-lookup"><span data-stu-id="533ff-112">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="533ff-113">In mindestens einer der `Function` Verfahren, weisen Sie einen Wert, der Name der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="533ff-113">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="533ff-114">Beim Ausführen einer `Exit Function` oder `End Function` -Anweisung [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gibt den Wert der Name der Prozedur zuletzt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="533ff-114">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="533ff-115">Stehen Ihnen mehrere `Exit Function` -Anweisung in die gleiche Prozedur, und Sie können mischen `Return` und `Exit Function` Anweisungen in der gleichen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="533ff-115">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="533ff-116">Stehen Ihnen nur eine `End Function` -Anweisung in einem `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="533ff-116">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="533ff-117">Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="533ff-117">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533ff-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="533ff-118">See Also</span></span>  
 <span data-ttu-id="533ff-119">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-119">[Procedures](./index.md) </span></span>  
<span data-ttu-id="533ff-120"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-120"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="533ff-121"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="533ff-122"> [Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-122"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="533ff-123"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-123"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="533ff-124"> [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-124"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="533ff-125"> [Return-Anweisung](../../../../visual-basic/language-reference/statements/return-statement.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-125"> [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md) </span></span>  
<span data-ttu-id="533ff-126"> [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="533ff-126"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="533ff-127"> [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="533ff-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
