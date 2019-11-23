---
title: <<=-Operator
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
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350955"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="70bcb-102">\<\<= Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70bcb-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="70bcb-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="70bcb-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bcb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70bcb-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="70bcb-105">Teile</span><span class="sxs-lookup"><span data-stu-id="70bcb-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="70bcb-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70bcb-106">Required.</span></span> <span data-ttu-id="70bcb-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span><span class="sxs-lookup"><span data-stu-id="70bcb-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="70bcb-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70bcb-108">Required.</span></span> <span data-ttu-id="70bcb-109">Numeric expression of a data type that widens to `Integer`.</span><span class="sxs-lookup"><span data-stu-id="70bcb-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70bcb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70bcb-110">Remarks</span></span>  
 <span data-ttu-id="70bcb-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="70bcb-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="70bcb-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="70bcb-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="70bcb-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span><span class="sxs-lookup"><span data-stu-id="70bcb-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="70bcb-114">The operator then assigns the result of that operation back to that variable or property.</span><span class="sxs-lookup"><span data-stu-id="70bcb-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="70bcb-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span><span class="sxs-lookup"><span data-stu-id="70bcb-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="70bcb-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span><span class="sxs-lookup"><span data-stu-id="70bcb-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="70bcb-117">Überladen</span><span class="sxs-lookup"><span data-stu-id="70bcb-117">Overloading</span></span>  
 <span data-ttu-id="70bcb-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="70bcb-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="70bcb-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span><span class="sxs-lookup"><span data-stu-id="70bcb-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="70bcb-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="70bcb-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="70bcb-121">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="70bcb-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70bcb-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70bcb-122">Example</span></span>  
 <span data-ttu-id="70bcb-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span><span class="sxs-lookup"><span data-stu-id="70bcb-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="70bcb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70bcb-124">See also</span></span>

- [<span data-ttu-id="70bcb-125"><<-Operator</span><span class="sxs-lookup"><span data-stu-id="70bcb-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [<span data-ttu-id="70bcb-126">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="70bcb-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="70bcb-127">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="70bcb-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="70bcb-128">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70bcb-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="70bcb-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="70bcb-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="70bcb-130">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="70bcb-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
