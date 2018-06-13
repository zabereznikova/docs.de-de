---
title: '&gt;&gt;=-Operator (Visual Basic)'
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
ms.openlocfilehash: d0c0ea819741f80e30e55a960b1187699898a3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604106"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="b06c0-102">&gt;&gt;=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b06c0-102">&gt;&gt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="b06c0-103">Führt eine arithmetische Verschiebung nach rechts auf den Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="b06c0-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b06c0-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="b06c0-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b06c0-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="b06c0-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b06c0-106">Required.</span></span> <span data-ttu-id="b06c0-107">Variable oder eine Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="b06c0-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="b06c0-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b06c0-108">Required.</span></span> <span data-ttu-id="b06c0-109">Numerische Ausdruck eines Datentyps, die erweitert `Integer`.</span><span class="sxs-lookup"><span data-stu-id="b06c0-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b06c0-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b06c0-110">Remarks</span></span>  
 <span data-ttu-id="b06c0-111">Das Element auf der linken Seite von der `>>=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="b06c0-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="b06c0-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b06c0-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="b06c0-113">Die `>>=` -Operator führt eine arithmetische rechtsverschiebung zuerst auf den Wert der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b06c0-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="b06c0-114">Der Operator weist das Ergebnis dieses Vorgangs dann der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="b06c0-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="b06c0-115">Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b06c0-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="b06c0-116">Klicken Sie in eine arithmetische Verschiebung nach rechts die Bits hinter Bit ganz rechts verschoben werden verworfen, und wird das Bit ganz links auf der linken Seite frei gewordene Bitpositionen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="b06c0-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="b06c0-117">Dies bedeutet, dass bei `variableorproperty` hat einen negativen Wert die frei werdenden Positionen auf 1 gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b06c0-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="b06c0-118">Wenn `variableorproperty` positiv ist, oder wenn der Datentyp ein Typ ohne Vorzeichen ist, werden die frei werdenden Positionen auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b06c0-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="b06c0-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="b06c0-119">Overloading</span></span>  
 <span data-ttu-id="b06c0-120">Die [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="b06c0-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b06c0-121">Überladen der `>>` Operator wirkt sich auf das Verhalten der `>>=` Operator.</span><span class="sxs-lookup"><span data-stu-id="b06c0-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="b06c0-122">Wenn im Code verwendet `>>=` auf eine Klasse oder Struktur, die Überladungen `>>`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b06c0-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b06c0-123">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b06c0-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b06c0-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b06c0-124">Example</span></span>  
 <span data-ttu-id="b06c0-125">Im folgenden Beispiel wird die `>>=` Operator, um das Bitmuster der UMSCHALTTASTE ein `Integer` Variablen nach rechts, um den angegebenen Betrag und das Ergebnis der Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b06c0-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b06c0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b06c0-126">See Also</span></span>  
 [<span data-ttu-id="b06c0-127">>>-Operator</span><span class="sxs-lookup"><span data-stu-id="b06c0-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [<span data-ttu-id="b06c0-128">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b06c0-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="b06c0-129">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b06c0-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="b06c0-130">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b06c0-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b06c0-131">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="b06c0-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b06c0-132">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="b06c0-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
