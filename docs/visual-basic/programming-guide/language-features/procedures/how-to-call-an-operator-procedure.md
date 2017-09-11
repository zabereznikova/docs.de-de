---
title: 'Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic) | Microsoft-Dokumentation'
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
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
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
ms.openlocfilehash: cd85a14a6f5534e90497268134f4b2b0cc292249
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="8c5ea-102">Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c5ea-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="8c5ea-103">Sie aufrufen eine Operatorprozedur verwenden Sie das Operatorsymbol in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="8c5ea-104">Im Fall eines Konvertierungsoperators rufen Sie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) einen Wert von einem Datentyp in einen anderen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="8c5ea-105">Operatorprozeduren werden nicht explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="8c5ea-106">Sie verwenden einfach den Operator oder die `CType` -Funktion in eine Zuweisung oder einen Ausdruck ein, wie Sie in der Regel einen Operator.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8c5ea-107">Ruft die Operatorprozedur auf.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="8c5ea-108">Definieren eines Operators für eine Klasse oder Struktur ist die Abkürzung *überladen* des Operators.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="8c5ea-109">Aufrufen eine Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="8c5ea-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="8c5ea-110">Verwenden Sie das Operatorsymbol in einem Ausdruck auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="8c5ea-111">Achten Sie darauf, dass die Datentypen der Operanden für den Operator an, und in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="8c5ea-112">Der Operator trägt auf den Wert des Ausdrucks wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="8c5ea-113">Aufrufen einer Konvertierungsoperatorprozedur</span><span class="sxs-lookup"><span data-stu-id="8c5ea-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="8c5ea-114">Verwendung `CType` innerhalb eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="8c5ea-115">Achten Sie darauf, dass die Datentypen der Operanden für die Konvertierung an, und in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="8c5ea-116">`CType`Ruft die Konvertierungsoperatorprozedur, und gibt den konvertierten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5ea-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c5ea-117">Example</span></span>  
 <span data-ttu-id="8c5ea-118">Das folgende Beispiel erstellt zwei <xref:System.TimeSpan>Strukturen, diese zusammenfügt und speichert das Ergebnis in einer dritten <xref:System.TimeSpan>Struktur.</xref:System.TimeSpan> </xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="8c5ea-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="8c5ea-119">Der <xref:System.TimeSpan>-Struktur definiert Operatorprozeduren, die mehrere Standardoperatoren überladen.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="8c5ea-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 <span data-ttu-id="8c5ea-120">[!code-vb[VbVbcnProcedures&#29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8c5ea-120">[!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="8c5ea-121">Da <xref:System.TimeSpan>überlädt den Standard `+` Operator wird im vorherige Beispiel eine Operatorprozedur aufgerufen, wenn den Wert des berechnet `combinedSpan`.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="8c5ea-121">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="8c5ea-122">Ein Beispiel für das Aufrufen einer Operatorprozedur Unterhaltung, finden Sie unter [Gewusst wie: Verwenden einer Klasse, dass Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="8c5ea-122">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c5ea-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8c5ea-123">Compiling the Code</span></span>  
 <span data-ttu-id="8c5ea-124">Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8c5ea-124">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5ea-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c5ea-125">See Also</span></span>  
 <span data-ttu-id="8c5ea-126">[Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-126">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="8c5ea-127"> [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-127"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="8c5ea-128"> [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-128"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="8c5ea-129"> [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-129"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="8c5ea-130"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-130"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="8c5ea-131"> [Einschränkende](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-131"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="8c5ea-132"> [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-132"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="8c5ea-133"> [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-133"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="8c5ea-134"> [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="8c5ea-134"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="8c5ea-135"> [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="8c5ea-135"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
