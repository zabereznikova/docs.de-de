---
title: Operator *=
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: b06ebcb4f4100a0621f52a769543c0fb24fbb4bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401497"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="02e8b-102">\*=-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02e8b-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="02e8b-103">Multipliziert den Wert einer Variablen oder Eigenschaft mit dem Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="02e8b-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02e8b-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="02e8b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="02e8b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="02e8b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="02e8b-106">Required.</span></span> <span data-ttu-id="02e8b-107">Eine beliebige numerische Variable oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="02e8b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="02e8b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="02e8b-108">Required.</span></span> <span data-ttu-id="02e8b-109">Ein beliebiger numerischer Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="02e8b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02e8b-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="02e8b-110">Remarks</span></span>  
 <span data-ttu-id="02e8b-111">Das Element auf der linken Seite des `*=` Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein.</span><span class="sxs-lookup"><span data-stu-id="02e8b-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="02e8b-112">Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../modifiers/readonly.md)</span><span class="sxs-lookup"><span data-stu-id="02e8b-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="02e8b-113">Der `*=` Operator multipliziert zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators) mit dem Wert der Variablen oder der Eigenschaft (auf der linken Seite des Operators).</span><span class="sxs-lookup"><span data-stu-id="02e8b-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="02e8b-114">Der-Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="02e8b-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="02e8b-115">Überladen</span><span class="sxs-lookup"><span data-stu-id="02e8b-115">Overloading</span></span>  
 <span data-ttu-id="02e8b-116">Der [Operator \*](multiplication-operator.md) kann *überladen*werden. das bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="02e8b-116">The [\* Operator](multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="02e8b-117">Das Überladen des- `*` Operators wirkt sich auf das Verhalten des- `*=` Operators aus.</span><span class="sxs-lookup"><span data-stu-id="02e8b-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="02e8b-118">Wenn Ihr Code `*=` für eine Klasse oder Struktur verwendet, die überlastet `*` ist, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="02e8b-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="02e8b-119">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="02e8b-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="02e8b-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02e8b-120">Example</span></span>  
 <span data-ttu-id="02e8b-121">Im folgenden Beispiel wird der `*=` -Operator verwendet, um eine `Integer` Variable mit einer Sekunde zu multiplizieren und das Ergebnis der ersten Variablen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="02e8b-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="02e8b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02e8b-122">See also</span></span>

- [<span data-ttu-id="02e8b-123">\*-Operator</span><span class="sxs-lookup"><span data-stu-id="02e8b-123">\* Operator</span></span>](multiplication-operator.md)
- [<span data-ttu-id="02e8b-124">Zuweisungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="02e8b-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="02e8b-125">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="02e8b-125">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="02e8b-126">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02e8b-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="02e8b-127">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="02e8b-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="02e8b-128">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="02e8b-128">Statements</span></span>](../../programming-guide/language-features/statements.md)
