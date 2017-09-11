---
title: 'Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic) | Microsoft-Dokumentation'
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
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
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
ms.openlocfilehash: e4d76788346e08123102d56088c0a1e0f5f2238f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="25920-102">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25920-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="25920-103">Wenn Sie eine Klasse oder Struktur, die ihre eigenen Operatoren definiert verwenden, können Sie diese Operatoren aus zugreifen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="25920-103">If you are using a class or structure that defines its own operators, you can access those operators from [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="25920-104">Definieren eines Operators für eine Klasse oder Struktur ist die Abkürzung *überladen* des Operators.</span><span class="sxs-lookup"><span data-stu-id="25920-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25920-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25920-105">Example</span></span>  
 <span data-ttu-id="25920-106">Das folgende Beispiel ruft die SQL-Struktur <xref:System.Data.SqlTypes.SqlString>, die die Konvertierungsoperatoren definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichenfolge.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="25920-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) in both directions between a SQL string and a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string.</span></span> <span data-ttu-id="25920-107">Verwenden `CType(` *SQL-Zeichenfolgenausdruck*, `String)` konvertieren Sie eine SQL-Zeichenfolge, die eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichenfolge und `CType(` *Visual Basic-Zeichenfolgenausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` für die Konvertierung in die andere Richtung.</xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="25920-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 <span data-ttu-id="25920-108">[!code-vb[VbVbcnProcedures&#30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="25920-108">[!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]</span></span>  
  
 <span data-ttu-id="25920-109">[!code-vb[VbVbcnProcedures&#31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="25920-109">[!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]</span></span>  
  
 <span data-ttu-id="25920-110">Die <xref:System.Data.SqlTypes.SqlString>Struktur einen Konvertierungsoperator definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) von `String` , <xref:System.Data.SqlTypes.SqlString>und anderen von <xref:System.Data.SqlTypes.SqlString>, `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString></span><span class="sxs-lookup"><span data-stu-id="25920-110">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="25920-111">Die Anweisung, zuweist `title` auf `jobTitle` verwendet den ersten Operator, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktionsaufruf verwendet das zweite.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="25920-111">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="25920-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="25920-112">Compiling the Code</span></span>  
 <span data-ttu-id="25920-113">Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25920-113">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="25920-114">Gehen Sie nicht davon aus, dass die Klasse oder Struktur jeder zum Überladen verfügbare Operator definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="25920-114">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="25920-115">Eine Liste der verfügbaren Operatoren finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="25920-115">For a list of available operators, see [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="25920-116">Fügen Sie die entsprechenden `Imports` -Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="25920-116">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="25920-117">Das Projekt muss Verweise auf System.Data und System.XML enthalten.</span><span class="sxs-lookup"><span data-stu-id="25920-117">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25920-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25920-118">See Also</span></span>  
 <span data-ttu-id="25920-119">[Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="25920-119">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="25920-120"> [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="25920-120"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="25920-121"> [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="25920-121"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="25920-122"> [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="25920-122"> [How to: Call an Operator Procedure](./how-to-call-an-operator-procedure.md) </span></span>  
<span data-ttu-id="25920-123"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="25920-123"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="25920-124"> [Einschränkende](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="25920-124"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="25920-125"> [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="25920-125"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="25920-126"> [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="25920-126"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="25920-127"> [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="25920-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="25920-128"> [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="25920-128"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
