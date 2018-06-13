---
title: 'Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: b1dc4477daa4ceb9dfc6a9a6ab3f041e68011acd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649967"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="ca425-102">Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca425-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="ca425-103">Sie aufrufen mit dem Symbol "Operator" in einem Ausdruck eine Operatorprozedur.</span><span class="sxs-lookup"><span data-stu-id="ca425-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="ca425-104">Im Fall eines Konvertierungsoperators rufen Sie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) um einen Wert von einem Datentyp in einen anderen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ca425-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="ca425-105">Operatorprozeduren werden nicht explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ca425-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="ca425-106">Verwenden Sie nur den Operator, oder die `CType` -Funktion in einer zuweisungsanweisung oder einen Ausdruck ein, die gleiche Weise, die Sie in der Regel einen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca425-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="ca425-107">Visual Basic führt der Aufruf die Operatorprozedur an.</span><span class="sxs-lookup"><span data-stu-id="ca425-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="ca425-108">Definieren eines Operators in einer Klasse oder Struktur ist so genannte *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="ca425-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="ca425-109">Aufrufen eine Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="ca425-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="ca425-110">Verwenden Sie das Symbol "Operator" in einem Ausdruck auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="ca425-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="ca425-111">Achten Sie darauf, dass die Datentypen der Operanden für den Operator an, und in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="ca425-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="ca425-112">Der Operator trägt dazu bei, den Wert des Ausdrucks wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="ca425-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="ca425-113">Eine Konvertierungsoperatorprozedur aufrufen</span><span class="sxs-lookup"><span data-stu-id="ca425-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="ca425-114">Verwendung `CType` innerhalb eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="ca425-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="ca425-115">Achten Sie darauf, dass die Datentypen der Operanden für die Konvertierung an, und in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="ca425-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="ca425-116">`CType` Ruft die Konvertierungsoperatorprozedur auf und gibt den konvertierten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="ca425-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca425-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca425-117">Example</span></span>  
 <span data-ttu-id="ca425-118">Das folgende Beispiel erstellt zwei <xref:System.TimeSpan> Strukturen, diese zusammenfügt und speichert das Ergebnis in einer dritten <xref:System.TimeSpan> Struktur.</span><span class="sxs-lookup"><span data-stu-id="ca425-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="ca425-119">Die <xref:System.TimeSpan> Struktur definiert Operatorprozeduren mehrere Standardoperatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="ca425-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <span data-ttu-id="ca425-120">Da <xref:System.TimeSpan> überlädt den Standard `+` -Operator, wird im vorherige Beispiel eine Operatorprozedur an, wenn den Wert des berechnet `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="ca425-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="ca425-121">Ein Beispiel für eine Konvertierungsoperatorprozedur aufrufen, finden Sie unter [Vorgehensweise: Verwenden Sie eine Klasse, dass Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ca425-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca425-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ca425-122">Compiling the Code</span></span>  
 <span data-ttu-id="ca425-123">Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ca425-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca425-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca425-124">See Also</span></span>  
 [<span data-ttu-id="ca425-125">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="ca425-125">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="ca425-126">Gewusst wie: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="ca425-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="ca425-127">Gewusst wie: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="ca425-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="ca425-128">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ca425-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="ca425-129">Widening</span><span class="sxs-lookup"><span data-stu-id="ca425-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="ca425-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="ca425-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="ca425-131">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ca425-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="ca425-132">Gewusst wie: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="ca425-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="ca425-133">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ca425-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="ca425-134">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ca425-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
