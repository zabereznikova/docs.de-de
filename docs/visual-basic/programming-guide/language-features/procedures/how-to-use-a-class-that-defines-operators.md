---
title: 'Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren (Visual Basic) definiert.'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 358e81904f48ad844351a20a448b615a0fef8f89
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972513"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="e785a-102">Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren (Visual Basic) definiert.</span><span class="sxs-lookup"><span data-stu-id="e785a-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="e785a-103">Wenn Sie eine Klasse oder Struktur, die eine eigene Operatoren definiert verwenden, können Sie diese Operatoren in Visual Basic zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e785a-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="e785a-104">Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.</span><span class="sxs-lookup"><span data-stu-id="e785a-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e785a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e785a-105">Example</span></span>  
 <span data-ttu-id="e785a-106">Das folgende Beispiel greift auf die SQL-Struktur <xref:System.Data.SqlTypes.SqlString>, das die Konvertierungsoperatoren definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und eine Visual Basic-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e785a-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="e785a-107">Verwendung `CType(` *SQL Zeichenfolgenausdruck*, `String)` zum Konvertieren von einer SQL-Zeichenfolge in eine Visual Basic-Zeichenfolge, und `CType(` *Visual Basic-Ausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` in die andere Richtung konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e785a-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="e785a-108">Die <xref:System.Data.SqlTypes.SqlString> Struktur definiert einen Konvertierungsoperator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) von `String` zu <xref:System.Data.SqlTypes.SqlString> und eine andere von <xref:System.Data.SqlTypes.SqlString> zu `String`.</span><span class="sxs-lookup"><span data-stu-id="e785a-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="e785a-109">Die Anweisung, zuweist `title` zu `jobTitle` verwendet den ersten Operator und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktionsaufruf mithilfe des zweiten.</span><span class="sxs-lookup"><span data-stu-id="e785a-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e785a-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e785a-110">Compiling the Code</span></span>  
 <span data-ttu-id="e785a-111">Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e785a-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="e785a-112">Gehen Sie nicht davon aus, für die Klasse oder Struktur jeder Operator zur Überladung definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e785a-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="e785a-113">Eine Liste der Operatoren verfügbar sind, finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e785a-113">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="e785a-114">Fügen Sie die entsprechenden `Imports` -Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlTypes>).</span><span class="sxs-lookup"><span data-stu-id="e785a-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="e785a-115">Das Projekt muss es sich um Verweise auf "System.Data" und "System.xml" enthalten.</span><span class="sxs-lookup"><span data-stu-id="e785a-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e785a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e785a-116">See also</span></span>
- [<span data-ttu-id="e785a-117">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="e785a-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="e785a-118">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="e785a-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="e785a-119">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="e785a-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="e785a-120">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="e785a-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="e785a-121">Widening</span><span class="sxs-lookup"><span data-stu-id="e785a-121">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="e785a-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="e785a-122">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="e785a-123">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e785a-123">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="e785a-124">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="e785a-124">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="e785a-125">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="e785a-125">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="e785a-126">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="e785a-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
