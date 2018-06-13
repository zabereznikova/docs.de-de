---
title: '&lt;&lt;=-Operator (Visual Basic)'
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
ms.openlocfilehash: 559624f7097f90d374ee83e3c0a9ac97d9f93444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600726"
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="a1656-102">&lt;&lt;=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1656-102">&lt;&lt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="a1656-103">Führt eine arithmetische Verschiebung nach links auf den Wert einer Variablen oder Eigenschaft und weist das Ergebnis der Variablen oder Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="a1656-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1656-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1656-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="a1656-105">Teile</span><span class="sxs-lookup"><span data-stu-id="a1656-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a1656-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1656-106">Required.</span></span> <span data-ttu-id="a1656-107">Variable oder eine Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="a1656-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="a1656-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a1656-108">Required.</span></span> <span data-ttu-id="a1656-109">Numerische Ausdruck eines Datentyps, die erweitert `Integer`.</span><span class="sxs-lookup"><span data-stu-id="a1656-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1656-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1656-110">Remarks</span></span>  
 <span data-ttu-id="a1656-111">Das Element auf der linken Seite von der `<<=` Operator kann eine einfache Skalarvariable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="a1656-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a1656-112">Die Variable oder Eigenschaft kann nicht [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a1656-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a1656-113">Die `<<=` -Operator führt eine arithmetische linksverschiebung zuerst auf den Wert der Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1656-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="a1656-114">Der Operator weist das Ergebnis dieses Vorgangs dann wieder auf diese Variablen oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a1656-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="a1656-115">Arithmetische Schichten sind nicht zirkulär, d. h. die Bits verschobene ein Ende des Resultsets nicht am anderen Ende wieder hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a1656-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="a1656-116">In eine arithmetische linksverschiebung der Bits, die außerhalb des Gültigkeitsbereichs für den Ergebnisdatentyp verschoben werden verworfen, und die Bitpositionen auf der rechten Seite ist auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a1656-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a1656-117">Überladen</span><span class="sxs-lookup"><span data-stu-id="a1656-117">Overloading</span></span>  
 <span data-ttu-id="a1656-118">Die [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="a1656-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a1656-119">Überladen der `<<` Operator wirkt sich auf das Verhalten der `<<=` Operator.</span><span class="sxs-lookup"><span data-stu-id="a1656-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="a1656-120">Wenn im Code verwendet `<<=` auf eine Klasse oder Struktur, die Überladungen `<<`, achten Sie verstehen, dass ihr neu definierten Verhalten.</span><span class="sxs-lookup"><span data-stu-id="a1656-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a1656-121">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a1656-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1656-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1656-122">Example</span></span>  
 <span data-ttu-id="a1656-123">Im folgenden Beispiel wird die `<<=` Operator, um das Bitmuster der UMSCHALTTASTE ein `Integer` Variable links von den angegebenen Betrag an und weisen Sie das Ergebnis der Variablen.</span><span class="sxs-lookup"><span data-stu-id="a1656-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a1656-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1656-124">See Also</span></span>  
 [<span data-ttu-id="a1656-125"><<-Operator</span><span class="sxs-lookup"><span data-stu-id="a1656-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [<span data-ttu-id="a1656-126">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a1656-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="a1656-127">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a1656-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="a1656-128">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a1656-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="a1656-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="a1656-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="a1656-130">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="a1656-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
