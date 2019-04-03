---
title: '>>=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 1076ce62077391f2c88ebdd621d1dbd6fb40d647
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838962"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="feee8-102">>> =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="feee8-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="feee8-103">Führt eine arithmetische rechtsverschiebung den Wert einer Variable oder eine Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="feee8-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feee8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="feee8-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="feee8-105">Teile</span><span class="sxs-lookup"><span data-stu-id="feee8-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="feee8-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="feee8-106">Required.</span></span> <span data-ttu-id="feee8-107">Variable oder eine Eigenschaft, ein ganzzahliger Typ (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="feee8-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="feee8-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="feee8-108">Required.</span></span> <span data-ttu-id="feee8-109">Numerischer Ausdruck eines Datentyps, die erweitert werden kann, `Integer`.</span><span class="sxs-lookup"><span data-stu-id="feee8-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="feee8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="feee8-110">Remarks</span></span>  
 <span data-ttu-id="feee8-111">Das Element auf der linken Seite von der `>>=` Operator kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="feee8-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="feee8-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="feee8-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="feee8-113">Die `>>=` -Operator führt eine arithmetische rechtsverschiebung zuerst auf dem Wert der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="feee8-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="feee8-114">Der Operator weist das Ergebnis des Vorgangs klicken Sie dann die Variable oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="feee8-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="feee8-115">Arithmetische Verschiebungen sind nicht zirkuläre, was bedeutet die Bits verschoben aus einem Ende des Resultsets nicht am anderen Ende wieder eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="feee8-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="feee8-116">In eine arithmetische Verschiebung nach rechts die Bits, die hinter der äußere rechte Bit stellt Position verschoben werden verworfen und das Bit ganz links in der Bitpositionen, die auf der linken Seite weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="feee8-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="feee8-117">Dies bedeutet, dass bei `variableorproperty` hat einen negativen Wert an, die frei werdenden Positionen auf 1 gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="feee8-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="feee8-118">Wenn `variableorproperty` positiv ist, oder wenn der Datentyp ein Typ ohne Vorzeichen ist, werden die frei werdenden Stellen 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="feee8-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="feee8-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="feee8-119">Overloading</span></span>  
 <span data-ttu-id="feee8-120">Die [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="feee8-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="feee8-121">Das Überladen der `>>` Operator beeinflusst das Verhalten von der `>>=` Operator.</span><span class="sxs-lookup"><span data-stu-id="feee8-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="feee8-122">Wenn Ihr Code verwendet `>>=` für eine Klasse oder Struktur, die Überladungen `>>`, werden Sie sicher, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="feee8-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="feee8-123">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="feee8-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="feee8-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="feee8-124">Example</span></span>  
 <span data-ttu-id="feee8-125">Im folgenden Beispiel wird die `>>=` Operator, um das Bitmuster verschoben ein `Integer` Variable, um den angegebenen Betrag und Zuweisen des Ergebnisses, auf die Variable nach rechts.</span><span class="sxs-lookup"><span data-stu-id="feee8-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="feee8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="feee8-126">See also</span></span>

- [<span data-ttu-id="feee8-127">>>-Operator</span><span class="sxs-lookup"><span data-stu-id="feee8-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="feee8-128">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="feee8-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="feee8-129">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="feee8-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="feee8-130">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="feee8-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="feee8-131">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="feee8-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="feee8-132">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="feee8-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
