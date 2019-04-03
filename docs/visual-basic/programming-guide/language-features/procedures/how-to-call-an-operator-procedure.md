---
title: 'Vorgehensweise: Aufrufen einer Operatorprozedur (Visual Basic)'
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
ms.openlocfilehash: 46614ad43e7be72c8396f47ba7f5d02185f62827
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837090"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="0b0fb-102">Vorgehensweise: Aufrufen einer Operatorprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b0fb-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="0b0fb-103">Sie aufrufen mit dem Symbol "Operator" in einem Ausdruck eine Operatorprozedur.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="0b0fb-104">Im Falle eines Konvertierungsoperators rufen Sie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) zum Konvertieren eines Werts aus einem Datentyp in einen anderen.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="0b0fb-105">Sie Operatorprozeduren nicht explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="0b0fb-106">Sie verwenden einfach den Operator an, oder die `CType` -Funktion in einer zuweisungsanweisung oder ein Ausdruck, der die gleiche Weise, die Sie normalerweise einen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="0b0fb-107">Visual Basic ermöglicht den Aufruf an die Operatorprozedur an.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="0b0fb-108">Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="0b0fb-109">Zum Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="0b0fb-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="0b0fb-110">Verwenden Sie das Symbol "Operator" in einem Ausdruck, auf die normale Weise.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="0b0fb-111">Achten Sie darauf, dass die Datentypen der Operanden für den Operator an, und in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="0b0fb-112">Der Operator unterstützt den Wert des Ausdrucks wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="0b0fb-113">Eine Konvertierungsoperatorprozedur aufrufen</span><span class="sxs-lookup"><span data-stu-id="0b0fb-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="0b0fb-114">Verwendung `CType` innerhalb eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="0b0fb-115">Achten Sie darauf, dass die Datentypen der Operanden für die Konvertierung an, und in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="0b0fb-116">`CType` Ruft die Konvertierungsoperatorprozedur und gibt den konvertierten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b0fb-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b0fb-117">Example</span></span>  
 <span data-ttu-id="0b0fb-118">Das folgende Beispiel erstellt zwei <xref:System.TimeSpan> Strukturen, diese zusammenfügt und speichert das Ergebnis in einer dritten <xref:System.TimeSpan> Struktur.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="0b0fb-119">Die <xref:System.TimeSpan> Struktur definiert Operatorprozeduren mehrere Standardoperatoren überladen.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="0b0fb-120">Da <xref:System.TimeSpan> überlädt den Standard `+` -Operator, wird das vorherige Beispiel eine Operatorprozedur an, wenn den Wert des berechnet `combinedSpan`.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="0b0fb-121">Ein Beispiel für eine Konvertierungsoperatorprozedur aufrufen, finden Sie unter [Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0b0fb-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0b0fb-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0b0fb-122">Compiling the Code</span></span>  
 <span data-ttu-id="0b0fb-123">Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0b0fb-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0fb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b0fb-124">See also</span></span>

- [<span data-ttu-id="0b0fb-125">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="0b0fb-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0b0fb-126">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="0b0fb-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="0b0fb-127">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="0b0fb-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="0b0fb-128">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0b0fb-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="0b0fb-129">Widening</span><span class="sxs-lookup"><span data-stu-id="0b0fb-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="0b0fb-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="0b0fb-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="0b0fb-131">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0b0fb-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="0b0fb-132">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="0b0fb-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="0b0fb-133">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0b0fb-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="0b0fb-134">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="0b0fb-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
