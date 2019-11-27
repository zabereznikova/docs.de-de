---
title: '>>Operator ='
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
ms.openlocfilehash: cad021c7730782d6233c60841483df7173308dc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351995"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="85444-102">> > =-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85444-102">>>= Operator (Visual Basic)</span></span>
<span data-ttu-id="85444-103">Führt eine arithmetische Rechtsverschiebung für den Wert einer Variablen oder Eigenschaft durch und weist das Ergebnis der Variablen oder der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="85444-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85444-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85444-104">Syntax</span></span>  
  
```vb  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="85444-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="85444-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="85444-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="85444-106">Required.</span></span> <span data-ttu-id="85444-107">Variable oder Eigenschaft eines ganzzahligen Typs (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`oder `ULong`).</span><span class="sxs-lookup"><span data-stu-id="85444-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="85444-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="85444-108">Required.</span></span> <span data-ttu-id="85444-109">Numerischer Ausdruck eines Datentyps, der zum `Integer`erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="85444-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85444-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85444-110">Remarks</span></span>  
 <span data-ttu-id="85444-111">Das Element auf der linken Seite des `>>=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="85444-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="85444-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="85444-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="85444-113">Der `>>=`-Operator führt zuerst eine arithmetische Rechtsverschiebung für den Wert der Variablen oder der Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="85444-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="85444-114">Der Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="85444-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="85444-115">Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="85444-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="85444-116">In einer arithmetischen rechten Schicht werden die Bits, die über die bitmost-Bitposition hinaus verschoben werden, verworfen, und das äußteste linke Bit wird an die auf der linken Seite freigegebenen Bitpositionen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="85444-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="85444-117">Dies bedeutet, dass die frei gewordenen Positionen auf einen Wert festgelegt werden, wenn `variableorproperty` einen negativen Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="85444-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="85444-118">Wenn `variableorproperty` positiv ist oder wenn der Datentyp ein nicht signierter Typ ist, werden die frei gewordenen Positionen auf NULL festgelegt.</span><span class="sxs-lookup"><span data-stu-id="85444-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="85444-119">Überladen</span><span class="sxs-lookup"><span data-stu-id="85444-119">Overloading</span></span>  
 <span data-ttu-id="85444-120">Der [> > Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="85444-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="85444-121">Das Überladen des `>>` Operators wirkt sich auf das Verhalten des `>>=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="85444-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="85444-122">Wenn Ihr Code `>>=` in einer Klasse oder Struktur verwendet, die `>>`überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="85444-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="85444-123">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="85444-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85444-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85444-124">Example</span></span>  
 <span data-ttu-id="85444-125">Im folgenden Beispiel wird der `>>=`-Operator verwendet, um das Bitmuster einer `Integer` Variablen rechts um den angegebenen Betrag zu verschieben und das Ergebnis der Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="85444-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="85444-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85444-126">See also</span></span>

- [<span data-ttu-id="85444-127">>>-Operator</span><span class="sxs-lookup"><span data-stu-id="85444-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [<span data-ttu-id="85444-128">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="85444-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="85444-129">Bitverschiebungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="85444-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [<span data-ttu-id="85444-130">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85444-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="85444-131">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="85444-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="85444-132">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="85444-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
