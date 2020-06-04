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
ms.openlocfilehash: ff7cbb02a9a10dbe11450491e93fd85fd77b44ba
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370660"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="14d26-102">\<\<Operator = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14d26-102">\<\<= Operator (Visual Basic)</span></span>
<span data-ttu-id="14d26-103">Führt eine arithmetische Verschiebung nach Links für den Wert einer Variablen oder Eigenschaft durch und weist das Ergebnis wieder der Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="14d26-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14d26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14d26-104">Syntax</span></span>  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="14d26-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="14d26-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="14d26-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14d26-106">Required.</span></span> <span data-ttu-id="14d26-107">Variable oder Eigenschaft eines ganzzahligen Typs ( `SByte` , `Byte` , `Short` , `UShort` , `Integer` , `UInteger` , `Long` oder `ULong` ).</span><span class="sxs-lookup"><span data-stu-id="14d26-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="14d26-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14d26-108">Required.</span></span> <span data-ttu-id="14d26-109">Numerischer Ausdruck eines Datentyps, der zu erweitert wird `Integer` .</span><span class="sxs-lookup"><span data-stu-id="14d26-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14d26-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="14d26-110">Remarks</span></span>  
 <span data-ttu-id="14d26-111">Das Element auf der linken Seite des `<<=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="14d26-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="14d26-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="14d26-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="14d26-113">Der `<<=` Operator führt zuerst eine arithmetische linke Verschiebung des Werts der Variablen oder Eigenschaft durch.</span><span class="sxs-lookup"><span data-stu-id="14d26-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="14d26-114">Der Operator weist dann das Ergebnis dieses Vorgangs wieder dieser Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="14d26-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="14d26-115">Arithmetische Verschiebungen sind nicht zirkulär, d. h., dass die Bits, die von einem Ende des Ergebnisses entfernt wurden, nicht erneut am anderen Ende eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="14d26-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="14d26-116">In einer arithmetischen linken Schicht werden die Bits, die nach dem Bereich des Ergebnis Datentyps verschoben werden, verworfen, und die auf der rechten Seite frei gewordenen Bitpositionen werden auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="14d26-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="14d26-117">Überladen</span><span class="sxs-lookup"><span data-stu-id="14d26-117">Overloading</span></span>  
 <span data-ttu-id="14d26-118">Der [<< -Operator](left-shift-operator.md) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="14d26-118">The [<< Operator](left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="14d26-119">Das Überladen des- `<<` Operators wirkt sich auf das Verhalten des- `<<=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="14d26-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="14d26-120">Wenn Ihr Code `<<=` für eine Klasse oder Struktur verwendet, die überlastet `<<` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="14d26-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="14d26-121">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="14d26-121">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="14d26-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14d26-122">Example</span></span>  
 <span data-ttu-id="14d26-123">Im folgenden Beispiel wird der `<<=` -Operator verwendet, um das Bitmuster einer `Integer` Variablen um den angegebenen Betrag nach Links zu verschieben und das Ergebnis der Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="14d26-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="14d26-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14d26-124">See also</span></span>

- [<span data-ttu-id="14d26-125"><< -Operator</span><span class="sxs-lookup"><span data-stu-id="14d26-125"><< Operator</span></span>](left-shift-operator.md)
- [<span data-ttu-id="14d26-126">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="14d26-126">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="14d26-127">Bitschiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="14d26-127">Bit Shift Operators</span></span>](bit-shift-operators.md)
- [<span data-ttu-id="14d26-128">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14d26-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="14d26-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="14d26-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="14d26-130">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="14d26-130">Statements</span></span>](../../programming-guide/language-features/statements.md)
