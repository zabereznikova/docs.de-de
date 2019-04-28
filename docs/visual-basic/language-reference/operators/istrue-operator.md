---
title: IsTrue-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 6c5ec6d953d174b525dee7ad3034d2d01ae4950f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768367"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="fc0d2-102">IsTrue-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc0d2-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="fc0d2-103">Bestimmt, ob ein Ausdruck ist `True`.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="fc0d2-104">Sie können nicht aufrufen `IsTrue` explizit in Ihrem Code, aber die Visual Basic Compiler können sie zum Generieren von Code aus `OrElse` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="fc0d2-105">Wenn Sie eine Klasse oder Struktur definieren und verwenden Sie dann auf eine Variable dieses Typs in eine `OrElse` -Klausel, müssen Sie definieren `IsTrue` für diese Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="fc0d2-106">Der Compiler betrachtet die `IsTrue` und `IsFalse` Operatoren als eine *zueinander passendes Paar*.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="fc0d2-107">Dies bedeutet, dass wenn Sie einen dieser definieren, Sie auch die anderen Knoten definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="fc0d2-108">Verwendung von "IsTrue" durch den Compiler</span><span class="sxs-lookup"><span data-stu-id="fc0d2-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="fc0d2-109">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in eine `For`, `If`, `Else If`, oder `While` -Anweisung oder in eine `When` Klausel.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="fc0d2-110">Wenn Sie dies tun, erfordert der Compiler einen Operator, der den Typ in konvertiert eine `Boolean` nutzen, damit sie eine Bedingung testen kann.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="fc0d2-111">Es sucht nach einem geeigneten Operator in der folgenden Reihenfolge:</span><span class="sxs-lookup"><span data-stu-id="fc0d2-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="fc0d2-112">Erweiternde Operator für die Konvertierung aus der Klasse oder Struktur `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="fc0d2-113">Erweiternde Operator für die Konvertierung aus der Klasse oder Struktur `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="fc0d2-114">Die `IsTrue` Operators für die Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="fc0d2-115">Eine einschränkende Konvertierung in `Boolean?` , ist eine Konvertierung von nicht beinhalten `Boolean` zu `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="fc0d2-116">Eine einschränkende Konvertierungsoperator aus der Klasse oder Struktur, `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="fc0d2-117">Wenn Sie nicht die Konvertierung zu definiert haben `Boolean` oder `IsTrue` -Operator, der Compiler signalisiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc0d2-118">Die `IsTrue` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn der Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="fc0d2-119">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fc0d2-120">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fc0d2-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc0d2-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc0d2-121">Example</span></span>  
 <span data-ttu-id="fc0d2-122">Das folgende Codebeispiel definiert die Gliederung einer Struktur, die Definitionen für enthält die `IsFalse` und `IsTrue` Operatoren.</span><span class="sxs-lookup"><span data-stu-id="fc0d2-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="fc0d2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc0d2-123">See also</span></span>

- [<span data-ttu-id="fc0d2-124">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="fc0d2-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="fc0d2-125">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="fc0d2-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="fc0d2-126">OrElse-Operator</span><span class="sxs-lookup"><span data-stu-id="fc0d2-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
