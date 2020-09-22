---
title: IsTrue-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 2e67a4adabe58ab12d317ae6318c0a2fac29da7d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866943"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="b5700-102">IsTrue-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5700-102">IsTrue Operator (Visual Basic)</span></span>

<span data-ttu-id="b5700-103">Bestimmt, ob ein Ausdruck ist `True` .</span><span class="sxs-lookup"><span data-stu-id="b5700-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="b5700-104">Sie können nicht `IsTrue` explizit in Ihrem Code aufzurufen, der Visual Basic Compiler kann es jedoch zum Generieren von Code aus `OrElse` Klauseln verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5700-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="b5700-105">Wenn Sie eine Klasse oder Struktur definieren und dann eine Variable dieses Typs in einer- `OrElse` Klausel verwenden, müssen Sie `IsTrue` für diese Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="b5700-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="b5700-106">Der Compiler betrachtet die `IsTrue` `IsFalse` Operatoren und als ein *übereinstimmendes Paar*.</span><span class="sxs-lookup"><span data-stu-id="b5700-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="b5700-107">Dies bedeutet, dass Sie, wenn Sie einen von Ihnen definieren, auch den anderen definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b5700-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="b5700-108">Compilerverwendung von IsTrue</span><span class="sxs-lookup"><span data-stu-id="b5700-108">Compiler Use of IsTrue</span></span>  

 <span data-ttu-id="b5700-109">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie eine Variable dieses Typs in einer-,-,- `For` `If` oder- `Else If` `While` Anweisung oder in einer- `When` Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5700-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="b5700-110">Wenn Sie dies tun, benötigt der Compiler einen Operator, der den Typ in einen-Wert konvertiert, `Boolean` damit eine Bedingung getestet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5700-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="b5700-111">Er sucht in der folgenden Reihenfolge nach einem passenden Operator:</span><span class="sxs-lookup"><span data-stu-id="b5700-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="b5700-112">Ein erweiterter Konvertierungs Operator von der Klasse oder Struktur zu `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b5700-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="b5700-113">Ein erweiterter Konvertierungs Operator von der Klasse oder Struktur zu `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="b5700-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="b5700-114">Der `IsTrue` Operator für die Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="b5700-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="b5700-115">Eine einschränkende Konvertierung in `Boolean?` , die keine Konvertierung von `Boolean` in einschließt `Boolean?` .</span><span class="sxs-lookup"><span data-stu-id="b5700-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="b5700-116">Ein einschränkende Konvertierungs Operator von der Klasse oder Struktur zu `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="b5700-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="b5700-117">Wenn Sie keine Konvertierung in `Boolean` oder einen Operator definiert haben `IsTrue` , signalisiert der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="b5700-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5700-118">Der `IsTrue` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn der Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="b5700-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="b5700-119">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="b5700-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="b5700-120">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="b5700-120">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5700-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5700-121">Example</span></span>  

 <span data-ttu-id="b5700-122">Im folgenden Codebeispiel wird die Gliederung einer-Struktur definiert, die Definitionen für die `IsFalse` `IsTrue` Operatoren und enthält.</span><span class="sxs-lookup"><span data-stu-id="b5700-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="b5700-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5700-123">See also</span></span>

- [<span data-ttu-id="b5700-124">IsFalse-Operator</span><span class="sxs-lookup"><span data-stu-id="b5700-124">IsFalse Operator</span></span>](isfalse-operator.md)
- [<span data-ttu-id="b5700-125">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="b5700-125">How to: Define an Operator</span></span>](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="b5700-126">OrElse-Operator</span><span class="sxs-lookup"><span data-stu-id="b5700-126">OrElse Operator</span></span>](orelse-operator.md)
