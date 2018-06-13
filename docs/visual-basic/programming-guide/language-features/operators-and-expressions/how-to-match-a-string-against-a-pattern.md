---
title: 'Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: aef378bfc32d6deff431a2caac1261a6cd7520c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655211"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="b6c6d-102">Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6c6d-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="b6c6d-103">Wenn Sie, ob einen Ausdruck eines ermitteln möchten der [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md) einem Muster entspricht, dann können Sie mithilfe der [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="b6c6d-104">`Like` verfügt über zwei Operanden.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-104">`Like` takes two operands.</span></span> <span data-ttu-id="b6c6d-105">Der linke Operand ist ein Zeichenfolgenausdruck, und der Rechte Operand ist eine Zeichenfolge, enthält das Muster für den Abgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="b6c6d-106">`Like` Gibt eine `Boolean` Wert, der angibt, ob der Zeichenfolgenausdruck dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="b6c6d-107">Sie können jedes Zeichen in der Zeichenfolgenausdruck für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einem Bereich von Zeichen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="b6c6d-108">Die Positionen der Angaben in der Musterzeichenfolge entsprechen die Positionen der Zeichen im Zeichenfolgenausdruck verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="b6c6d-109">Um ein Zeichen im Zeichenfolgenausdruck für ein bestimmtes Zeichen</span><span class="sxs-lookup"><span data-stu-id="b6c6d-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="b6c6d-110">Fügen Sie das Zeichen direkt in der Musterzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="b6c6d-111">Bestimmte Sonderzeichen müssen in Klammern eingeschlossen werden (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="b6c6d-112">Weitere Informationen finden Sie unter [Like-Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="b6c6d-113">Im folgenden Beispiel wird getestet, ob `myString` besteht das einzelne Zeichen genau `H`.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="b6c6d-114">Um ein Zeichen im Zeichenfolgenausdruck mit einem Platzhalterzeichen</span><span class="sxs-lookup"><span data-stu-id="b6c6d-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="b6c6d-115">Versetzen ein Fragezeichen (`?`) in der Musterzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="b6c6d-116">An dieser Position irgendeinem gültigen Zeichen ergibt eine Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="b6c6d-117">Im folgenden Beispiel wird getestet, ob `myString` besteht das einzelne Zeichen `W` gefolgt von genau zwei Zeichen aller Werte.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="b6c6d-118">Um ein Zeichen im Zeichenfolgenausdruck mit einer Liste von Zeichen</span><span class="sxs-lookup"><span data-stu-id="b6c6d-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="b6c6d-119">Platzieren von Klammern (`[ ]`) in der Musterzeichenfolge und innerhalb der Klammern setzen die Liste der Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="b6c6d-120">Trennen Sie die Zeichen nicht durch Kommas oder einem anderen Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="b6c6d-121">Beliebiges einzelnes Zeichen in der Liste wird eine erfolgreiche Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="b6c6d-122">Im folgenden Beispiel wird getestet, ob `myString` besteht aus einem beliebigen gültigen Zeichen gefolgt von genau einem Zeichen `A`, `C`, oder `E`.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     <span data-ttu-id="b6c6d-123">Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="b6c6d-124">Um ein Zeichen im Zeichenfolgenausdruck für einen Bereich von Zeichen</span><span class="sxs-lookup"><span data-stu-id="b6c6d-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="b6c6d-125">Platzieren von Klammern (`[ ]`) in der Musterzeichenfolge und innerhalb der Klammern setzen die niedrigsten und höchsten Zeichen im Bereich durch einen Bindestrich getrennt (`–`).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="b6c6d-126">Beliebiges einzelnes Zeichen innerhalb des Bereichs wird eine erfolgreiche Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="b6c6d-127">Im folgenden Beispiel wird getestet, ob `myString` besteht aus den Zeichen `num` gefolgt von genau einem Zeichen `i`, `j`, `k`, `l`, `m`, oder `n`.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     <span data-ttu-id="b6c6d-128">Beachten Sie, dass diese Übereinstimmung Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="b6c6d-129">Übereinstimmende leere Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b6c6d-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="b6c6d-130">`Like` behandelt die Sequenz `[]` als eine Zeichenfolge der Länge 0 (null) (`""`).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="b6c6d-131">Sie können `[]` zu prüfen, ob der gesamte Zeichenfolgenausdruck leer ist, jedoch können sie überprüfen, ob eine bestimmte Position im Zeichenfolgenausdruck leer ist.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="b6c6d-132">Wenn eine leere Position eine der Optionen ist müssen Sie für die Sie verwenden können, testen `Like` mehr als einmal.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="b6c6d-133">Um ein Zeichen im Zeichenfolgenausdruck mit einer Liste von Zeichen oder kein Zeichen</span><span class="sxs-lookup"><span data-stu-id="b6c6d-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="b6c6d-134">Rufen Sie die `Like` Operator zweimal in derselben Zeichenfolgeausdruck, und verbinden Sie die beiden Aufrufe entweder mit der [oder-Operator](../../../../visual-basic/language-reference/operators/or-operator.md) oder [OrElse-Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="b6c6d-135">In der Musterzeichenfolge zum ersten `Like` -Klausel, enthalten die Zeichenliste in Klammern eingeschlossen (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="b6c6d-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="b6c6d-136">In der Musterzeichenfolge für die zweite `Like` -Klausel, nehmen Sie keines Zeichen an der Position fraglichen.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="b6c6d-137">Das folgende Beispiel testet die siebenstellige Telefonnummer `phoneNum` für genau drei Ziffern, gefolgt von einem Leerzeichen, ein Bindestrich (`–`), einen Punkt (`.`), oder keine Zeichen überhaupt, gefolgt von genau vier Ziffern.</span><span class="sxs-lookup"><span data-stu-id="b6c6d-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b6c6d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6c6d-138">See Also</span></span>  
 [<span data-ttu-id="b6c6d-139">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b6c6d-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="b6c6d-140">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="b6c6d-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="b6c6d-141">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="b6c6d-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="b6c6d-142">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="b6c6d-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
