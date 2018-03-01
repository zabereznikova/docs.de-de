---
title: '&amp;Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76c8fc52a518dfe7850a5680b7d4f06f3d09bf73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="96cd6-102">&amp;Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96cd6-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="96cd6-103">Generiert eine zeichenfolgenverkettung aus zwei Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="96cd6-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96cd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96cd6-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="96cd6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="96cd6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="96cd6-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96cd6-106">Required.</span></span> <span data-ttu-id="96cd6-107">Alle `String` oder `Object` Variable.</span><span class="sxs-lookup"><span data-stu-id="96cd6-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="96cd6-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96cd6-108">Required.</span></span> <span data-ttu-id="96cd6-109">Jeder Ausdruck mit einem Datentyp, der erweitert `String`.</span><span class="sxs-lookup"><span data-stu-id="96cd6-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="96cd6-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96cd6-110">Required.</span></span> <span data-ttu-id="96cd6-111">Jeder Ausdruck mit einem Datentyp, der erweitert `String`.</span><span class="sxs-lookup"><span data-stu-id="96cd6-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96cd6-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96cd6-112">Remarks</span></span>  
 <span data-ttu-id="96cd6-113">Wenn der Datentyp des `expression1` oder `expression2` ist nicht `String` jedoch erweitert wird, um `String`, wird es in konvertiert `String`.</span><span class="sxs-lookup"><span data-stu-id="96cd6-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="96cd6-114">Wenn entweder der Datentypen wird nicht erweitert werden, um `String`, generiert der Compiler einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="96cd6-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="96cd6-115">Der Datentyp des `result` ist `String`.</span><span class="sxs-lookup"><span data-stu-id="96cd6-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="96cd6-116">Wenn einer oder beide Ausdrücke [nichts](../../../visual-basic/language-reference/nothing.md) oder einen Wert von <xref:System.DBNull.Value?displayProperty=nameWithType>, werden sie behandelt, als eine Zeichenfolge mit dem Wert "".</span><span class="sxs-lookup"><span data-stu-id="96cd6-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96cd6-117">Die `&` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="96cd6-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="96cd6-118">Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="96cd6-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="96cd6-119">Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="96cd6-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96cd6-120">Das kaufmännische und-Zeichen (&) können auch zum Identifizieren von Variablen als Typ verwendet werden `Long`.</span><span class="sxs-lookup"><span data-stu-id="96cd6-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="96cd6-121">Weitere Informationen finden Sie unter [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="96cd6-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96cd6-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="96cd6-122">Example</span></span>  
 <span data-ttu-id="96cd6-123">Dieses Beispiel verwendet die `&` Operator zum Verketten von Zeichenfolgen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="96cd6-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="96cd6-124">Das Ergebnis ist ein Zeichenfolgenwert, der die Verkettung von den beiden Zeichenfolgenoperanden darstellt.</span><span class="sxs-lookup"><span data-stu-id="96cd6-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="96cd6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96cd6-125">See Also</span></span>  
 [<span data-ttu-id="96cd6-126">&=-Operator</span><span class="sxs-lookup"><span data-stu-id="96cd6-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="96cd6-127">Verkettungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="96cd6-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="96cd6-128">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96cd6-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="96cd6-129">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="96cd6-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="96cd6-130">Verkettungsoperatoren in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96cd6-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
