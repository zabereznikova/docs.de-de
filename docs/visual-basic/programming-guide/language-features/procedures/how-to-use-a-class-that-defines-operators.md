---
title: 'Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert'
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
ms.openlocfilehash: fe15e976e6a5469f2a9d1b3521a70a3e1860fdd3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414349"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a><span data-ttu-id="70b3c-102">Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70b3c-102">How to: Use a Class that Defines Operators (Visual Basic)</span></span>
<span data-ttu-id="70b3c-103">Wenn Sie eine Klasse oder Struktur verwenden, die eigene Operatoren definiert, können Sie von Visual Basic aus auf diese Operatoren zugreifen.</span><span class="sxs-lookup"><span data-stu-id="70b3c-103">If you are using a class or structure that defines its own operators, you can access those operators from Visual Basic.</span></span>  
  
 <span data-ttu-id="70b3c-104">Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="70b3c-104">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70b3c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70b3c-105">Example</span></span>  
 <span data-ttu-id="70b3c-106">Im folgenden Beispiel wird auf die SQL-Struktur zugegriffen <xref:System.Data.SqlTypes.SqlString> , die die Konvertierungs Operatoren ([CType-Funktion](../../../language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und einer Visual Basic Zeichenfolge definiert.</span><span class="sxs-lookup"><span data-stu-id="70b3c-106">The following example accesses the SQL structure <xref:System.Data.SqlTypes.SqlString>, which defines the conversion operators ([CType Function](../../../language-reference/functions/ctype-function.md)) in both directions between a SQL string and a Visual Basic string.</span></span> <span data-ttu-id="70b3c-107">Verwenden Sie `CType(` den *SQL-Zeichen folgen Ausdruck*, `String)` um eine SQL-Zeichenfolge in eine Visual Basic Zeichenfolge zu konvertieren, und `CType(` *Visual Basic Zeichen folgen Ausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` um in die andere Richtung zu konvertieren</span><span class="sxs-lookup"><span data-stu-id="70b3c-107">Use `CType(`*SQL string expression*, `String)` to convert a SQL string to a Visual Basic string, and `CType(`*Visual Basic string expression*, <xref:System.Data.SqlTypes.SqlString>`)` to convert in the other direction.</span></span>  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <span data-ttu-id="70b3c-108">Die <xref:System.Data.SqlTypes.SqlString> -Struktur definiert einen Konvertierungs Operator ([CType-Funktion](../../../language-reference/functions/ctype-function.md)) von `String` bis <xref:System.Data.SqlTypes.SqlString> und einen anderen von <xref:System.Data.SqlTypes.SqlString> zu `String` .</span><span class="sxs-lookup"><span data-stu-id="70b3c-108">The <xref:System.Data.SqlTypes.SqlString> structure defines a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)) from `String` to <xref:System.Data.SqlTypes.SqlString> and another from <xref:System.Data.SqlTypes.SqlString> to `String`.</span></span> <span data-ttu-id="70b3c-109">Die-Anweisung, die zuweist, verwendet `title` `jobTitle` den ersten Operator, und der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktions Aufrufwert verwendet den zweiten.</span><span class="sxs-lookup"><span data-stu-id="70b3c-109">The statement that assigns `title` to `jobTitle` makes use of the first operator, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function call uses the second.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="70b3c-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="70b3c-110">Compile the code</span></span>  
 <span data-ttu-id="70b3c-111">Stellen Sie sicher, dass die verwendete Klasse oder Struktur den Operator definiert, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="70b3c-111">Be sure the class or structure you are using defines the operator you want to use.</span></span> <span data-ttu-id="70b3c-112">Gehen Sie nicht davon aus, dass die Klasse oder Struktur jeden Operator definiert hat, der für das überladen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="70b3c-112">Do not assume that the class or structure has defined every operator available for overloading.</span></span> <span data-ttu-id="70b3c-113">Eine Liste der verfügbaren Operatoren finden Sie unter [Operator Statement](../../../language-reference/statements/operator-statement.md).</span><span class="sxs-lookup"><span data-stu-id="70b3c-113">For a list of available operators, see [Operator Statement](../../../language-reference/statements/operator-statement.md).</span></span>  
  
 <span data-ttu-id="70b3c-114">Fügen Sie die entsprechende- `Imports` Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei ein (in diesem Fall <xref:System.Data.SqlTypes> ).</span><span class="sxs-lookup"><span data-stu-id="70b3c-114">Include the appropriate `Imports` statement for the SQL string at the beginning of your source file (in this case <xref:System.Data.SqlTypes>).</span></span>  
  
 <span data-ttu-id="70b3c-115">Das Projekt muss Verweise auf "System. Data" und "System. xml" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="70b3c-115">Your project must have references to System.Data and System.XML.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b3c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70b3c-116">See also</span></span>

- [<span data-ttu-id="70b3c-117">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="70b3c-117">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="70b3c-118">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="70b3c-118">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="70b3c-119">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="70b3c-119">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="70b3c-120">Vorgehensweise: Aufrufen einer Operatorprozedur</span><span class="sxs-lookup"><span data-stu-id="70b3c-120">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="70b3c-121">Widening</span><span class="sxs-lookup"><span data-stu-id="70b3c-121">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="70b3c-122">Narrowing</span><span class="sxs-lookup"><span data-stu-id="70b3c-122">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="70b3c-123">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="70b3c-123">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="70b3c-124">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="70b3c-124">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="70b3c-125">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="70b3c-125">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="70b3c-126">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="70b3c-126">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
