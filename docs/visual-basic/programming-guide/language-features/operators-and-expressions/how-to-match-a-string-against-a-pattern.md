---
title: 'Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster'
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
ms.openlocfilehash: d8a3c363d1a443db4a0b7633e380562af1913aca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403445"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="73800-102">Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73800-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="73800-103">Wenn Sie herausfinden möchten, ob ein Ausdruck des [String-Datentyps](../../../language-reference/data-types/string-data-type.md) ein Muster erfüllt, können Sie den [Like-Operator](../../../language-reference/operators/like-operator.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="73800-103">If you want to find out if an expression of the [String Data Type](../../../language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="73800-104">`Like`erfordert zwei Operanden.</span><span class="sxs-lookup"><span data-stu-id="73800-104">`Like` takes two operands.</span></span> <span data-ttu-id="73800-105">Der linke Operand ist ein Zeichen folgen Ausdruck, und der rechte Operand ist eine Zeichenfolge mit dem Muster, das für den Abgleich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="73800-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="73800-106">`Like`Gibt einen Wert zurück, der `Boolean` angibt, ob der Zeichen folgen Ausdruck dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="73800-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="73800-107">Sie können jedes Zeichen im Zeichen folgen Ausdruck mit einem bestimmten Zeichen, einem Platzhalter Zeichen, einer Zeichen Liste oder einem Zeichenbereich vergleichen.</span><span class="sxs-lookup"><span data-stu-id="73800-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="73800-108">Die Positionen der Spezifikationen in der Muster Zeichenfolge entsprechen den Positionen der Zeichen, die im Zeichen folgen Ausdruck abgeglichen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="73800-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="73800-109">So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einem bestimmten Zeichen an</span><span class="sxs-lookup"><span data-stu-id="73800-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="73800-110">Fügen Sie das jeweilige Zeichen direkt in die Muster Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="73800-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="73800-111">Bestimmte Sonderzeichen müssen in eckige Klammern () eingeschlossen werden `[ ]` .</span><span class="sxs-lookup"><span data-stu-id="73800-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="73800-112">Weitere Informationen finden Sie unter [Like-Operator](../../../language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="73800-112">For more information, see [Like Operator](../../../language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="73800-113">Im folgenden Beispiel wird getestet, ob `myString` genau aus dem einzelnen Zeichen besteht `H` .</span><span class="sxs-lookup"><span data-stu-id="73800-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="73800-114">So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einem Platzhalter Zeichen an</span><span class="sxs-lookup"><span data-stu-id="73800-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="73800-115">Legen Sie ein Fragezeichen ( `?` ) in der Muster Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="73800-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="73800-116">Ein beliebiges gültiges Zeichen an dieser Position stimmt erfolgreich ab.</span><span class="sxs-lookup"><span data-stu-id="73800-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="73800-117">Im folgenden Beispiel wird getestet, ob `myString` aus dem einzelnen Zeichen besteht, auf das `W` genau zwei Zeichen von Werten folgen.</span><span class="sxs-lookup"><span data-stu-id="73800-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="73800-118">So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einer Liste von Zeichen an</span><span class="sxs-lookup"><span data-stu-id="73800-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="73800-119">Legen Sie eckige Klammern ( `[ ]` ) in der Muster Zeichenfolge ab, und legen Sie in den Klammern die Zeichen Liste ab.</span><span class="sxs-lookup"><span data-stu-id="73800-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="73800-120">Trennen Sie die Zeichen nicht durch Kommas oder andere Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="73800-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="73800-121">Alle einzelnen Zeichen in der Liste Stimmen erfolgreich ab.</span><span class="sxs-lookup"><span data-stu-id="73800-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="73800-122">Im folgenden Beispiel wird getestet `myString` , ob aus einem gültigen Zeichen, gefolgt von genau einem der Zeichen `A` , oder, besteht `C` `E` .</span><span class="sxs-lookup"><span data-stu-id="73800-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="73800-123">Beachten Sie, dass die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="73800-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="73800-124">So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einem Zeichenbereich an</span><span class="sxs-lookup"><span data-stu-id="73800-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="73800-125">Legen Sie eckige Klammern ( `[ ]` ) in der Muster Zeichenfolge ab, und legen Sie in den Klammern die niedrigsten und höchsten Zeichen im Bereich ab, getrennt durch einen Bindestrich ( `–` ).</span><span class="sxs-lookup"><span data-stu-id="73800-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="73800-126">Alle einzelnen Zeichen innerhalb des Bereichs Stimmen erfolgreich ab.</span><span class="sxs-lookup"><span data-stu-id="73800-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="73800-127">Im folgenden Beispiel wird getestet, ob `myString` aus den Zeichen besteht, auf die `num` genau eines der Zeichen `i` , `j` , `k` ,, oder folgt `l` `m` `n` .</span><span class="sxs-lookup"><span data-stu-id="73800-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="73800-128">Beachten Sie, dass die Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="73800-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="73800-129">Vergleichen von leeren Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="73800-129">Matching Empty Strings</span></span>

<span data-ttu-id="73800-130">`Like`behandelt die Sequenz `[]` als Zeichenfolge der Länge 0 (NULL `""` ).</span><span class="sxs-lookup"><span data-stu-id="73800-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="73800-131">Sie können verwenden, `[]` um zu testen, ob der gesamte Zeichen folgen Ausdruck leer ist, Sie können ihn jedoch nicht verwenden, um zu testen, ob eine bestimmte Position im Zeichen folgen Ausdruck leer ist.</span><span class="sxs-lookup"><span data-stu-id="73800-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="73800-132">Wenn eine leere Position eine der Optionen ist, die Sie testen müssen, können Sie mehrmals verwenden `Like` .</span><span class="sxs-lookup"><span data-stu-id="73800-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="73800-133">So passen Sie ein Zeichen im Zeichen folgen Ausdruck mit einer Liste von Zeichen oder ohne Zeichen an</span><span class="sxs-lookup"><span data-stu-id="73800-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="73800-134">Rufen Sie den `Like` Operator zweimal für denselben Zeichen folgen Ausdruck auf, und verbinden Sie die beiden Aufrufe entweder mit dem [OR-Operator](../../../language-reference/operators/or-operator.md) oder dem [OrElse-Operator](../../../language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="73800-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../language-reference/operators/or-operator.md) or the [OrElse Operator](../../../language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="73800-135">Fügen Sie in der Muster Zeichenfolge für die erste `Like` Klausel die Zeichen Liste in eckige Klammern ( `[ ]` ) ein.</span><span class="sxs-lookup"><span data-stu-id="73800-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="73800-136">Fügen Sie in der Muster Zeichenfolge für die zweite `Like` Klausel kein Zeichen an der fraglichen Position ein.</span><span class="sxs-lookup"><span data-stu-id="73800-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="73800-137">Im folgenden Beispiel wird die siebenstellige Telefonnummer `phoneNum` für genau drei numerische Ziffern, gefolgt von einem Leerzeichen, einem Bindestrich ( `–` ), einem Punkte ( `.` ) oder keinem Zeichen, gefolgt von genau vier numerischen Ziffern getestet.</span><span class="sxs-lookup"><span data-stu-id="73800-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="73800-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="73800-138">See also</span></span>

- [<span data-ttu-id="73800-139">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="73800-139">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="73800-140">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="73800-140">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="73800-141">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="73800-141">Like Operator</span></span>](../../../language-reference/operators/like-operator.md)
- [<span data-ttu-id="73800-142">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="73800-142">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
