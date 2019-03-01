---
title: << =-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: b2a642b1187c9a08007ee1eddfa0764198fc0877
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981646"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="e1864-102">\<\<=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1864-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="e1864-103">Führt eine arithmetische Verschiebung nach links auf dem Wert einer Variable oder eine Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e1864-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1864-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1864-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="e1864-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e1864-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="e1864-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1864-106">Required.</span></span> <span data-ttu-id="e1864-107">Variable oder eine Eigenschaft, ein ganzzahliger Typ (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="e1864-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="e1864-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1864-108">Required.</span></span> <span data-ttu-id="e1864-109">Numerischer Ausdruck eines Datentyps, die erweitert werden kann, `Integer`.</span><span class="sxs-lookup"><span data-stu-id="e1864-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1864-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1864-110">Remarks</span></span>  
 <span data-ttu-id="e1864-111">Das Element auf der linken Seite von der `<<=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="e1864-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="e1864-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="e1864-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="e1864-113">Die `<<=` -Operator führt eine arithmetische Verschiebung nach links zuerst auf dem Wert der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e1864-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="e1864-114">Der Operator weist das Ergebnis des Vorgangs klicken Sie dann diese Variable oder eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e1864-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="e1864-115">Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e1864-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="e1864-116">In eine arithmetische Verschiebung nach links die Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite werden auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e1864-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="e1864-117">Überladen</span><span class="sxs-lookup"><span data-stu-id="e1864-117">Overloading</span></span>  
 <span data-ttu-id="e1864-118">Die [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="e1864-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="e1864-119">Das Überladen der `<<` Operator beeinflusst das Verhalten von der `<<=` Operator.</span><span class="sxs-lookup"><span data-stu-id="e1864-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="e1864-120">Wenn Ihr Code verwendet `<<=` für eine Klasse oder Struktur, die Überladungen `<<`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="e1864-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="e1864-121">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="e1864-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1864-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1864-122">Example</span></span>  
 <span data-ttu-id="e1864-123">Im folgenden Beispiel wird die `<<=` Operator, um das Bitmuster verschoben ein `Integer` Variable links von den angegebenen Betrag und Zuweisen des Ergebnisses der Variablen.</span><span class="sxs-lookup"><span data-stu-id="e1864-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="e1864-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1864-124">See also</span></span>
- [<span data-ttu-id="e1864-125"><<-Operator</span><span class="sxs-lookup"><span data-stu-id="e1864-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="e1864-126">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e1864-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="e1864-127">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="e1864-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="e1864-128">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1864-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="e1864-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="e1864-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="e1864-130">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="e1864-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
