---
title: 'Vorgehensweise: Aufrufen einer Operatorprozedur'
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
ms.openlocfilehash: 0e88ff7b36535a709671a1f9b838f2b4488d1d37
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075186"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="ac149-102">Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac149-102">How to: Call an Operator Procedure (Visual Basic)</span></span>

<span data-ttu-id="ac149-103">Sie wenden eine Operator Prozedur mit dem Operator Symbol in einem Ausdruck an.</span><span class="sxs-lookup"><span data-stu-id="ac149-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="ac149-104">Im Fall eines Konvertierungs Operators wird die [CType-Funktion](../../../language-reference/functions/ctype-function.md) aufgerufen, um einen Wert von einem Datentyp in einen anderen zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ac149-104">In the case of a conversion operator, you call the [CType Function](../../../language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="ac149-105">Operator Prozeduren werden nicht explizit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac149-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="ac149-106">Sie verwenden einfach den-Operator oder die- `CType` Funktion in einer Zuweisungsanweisung oder einem Ausdruck auf die gleiche Weise, wie Sie normalerweise einen Operator verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac149-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="ac149-107">Visual Basic führt den aufzurufenden Operator Prozedur Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="ac149-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="ac149-108">Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ac149-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="ac149-109">So wenden Sie eine Operator Prozedur an</span><span class="sxs-lookup"><span data-stu-id="ac149-109">To call an operator procedure</span></span>  
  
1. <span data-ttu-id="ac149-110">Verwenden Sie das Operator Symbol in einem Ausdruck auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="ac149-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2. <span data-ttu-id="ac149-111">Stellen Sie sicher, dass die Datentypen der Operanden für den Operator und in der richtigen Reihenfolge geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="ac149-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3. <span data-ttu-id="ac149-112">Der Operator trägt wie erwartet zum Wert des Ausdrucks bei.</span><span class="sxs-lookup"><span data-stu-id="ac149-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="ac149-113">So können Sie eine Konvertierungs Operator Prozedur aufzurufen</span><span class="sxs-lookup"><span data-stu-id="ac149-113">To call a conversion operator procedure</span></span>  
  
1. <span data-ttu-id="ac149-114">Verwendung `CType` innerhalb eines Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="ac149-114">Use `CType` inside an expression.</span></span>  
  
2. <span data-ttu-id="ac149-115">Stellen Sie sicher, dass die Datentypen der Operanden für die Konvertierung und in der richtigen Reihenfolge geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="ac149-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3. <span data-ttu-id="ac149-116">`CType` Ruft die Konvertierungs Operator Prozedur auf und gibt den konvertierten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="ac149-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac149-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ac149-117">Example</span></span>  

 <span data-ttu-id="ac149-118">Im folgenden Beispiel werden zwei- <xref:System.TimeSpan> Strukturen erstellt, addiert, und das Ergebnis wird in einer dritten <xref:System.TimeSpan> Struktur gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ac149-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="ac149-119">Die- <xref:System.TimeSpan> Struktur definiert Operator Prozeduren zum Überladen mehrerer Standard Operatoren.</span><span class="sxs-lookup"><span data-stu-id="ac149-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 <span data-ttu-id="ac149-120">Da <xref:System.TimeSpan> den-Standard Operator über lädt `+` , wird im vorherigen Beispiel eine Operator Prozedur aufgerufen, wenn der Wert von berechnet wird `combinedSpan` .</span><span class="sxs-lookup"><span data-stu-id="ac149-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="ac149-121">Ein Beispiel für den Aufruf einer Konversations Operator Prozedur finden Sie unter Gewusst [wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).</span><span class="sxs-lookup"><span data-stu-id="ac149-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="ac149-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ac149-122">Compile the code</span></span>  

 <span data-ttu-id="ac149-123">Stellen Sie sicher, dass die verwendete Klasse oder Struktur den Operator definiert, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ac149-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac149-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac149-124">See also</span></span>

- [<span data-ttu-id="ac149-125">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="ac149-125">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="ac149-126">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="ac149-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)
- [<span data-ttu-id="ac149-127">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="ac149-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="ac149-128">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="ac149-128">Operator Statement</span></span>](../../../language-reference/statements/operator-statement.md)
- [<span data-ttu-id="ac149-129">Widening</span><span class="sxs-lookup"><span data-stu-id="ac149-129">Widening</span></span>](../../../language-reference/modifiers/widening.md)
- [<span data-ttu-id="ac149-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="ac149-130">Narrowing</span></span>](../../../language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="ac149-131">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="ac149-131">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="ac149-132">Vorgehensweise: Deklarieren einer Struktur</span><span class="sxs-lookup"><span data-stu-id="ac149-132">How to: Declare a Structure</span></span>](../data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="ac149-133">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ac149-133">Implicit and Explicit Conversions</span></span>](../data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="ac149-134">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="ac149-134">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
