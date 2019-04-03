---
title: Like-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: 38e56b8c0ec6bab89052ee42a2cd9c24053c658e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835699"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="c205e-102">Like-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c205e-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="c205e-103">Vergleicht eine Zeichenfolge mit einem Muster.</span><span class="sxs-lookup"><span data-stu-id="c205e-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c205e-104">Die `Like` Operator wird in .NET Core und .NET Standard-Projekten derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c205e-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="c205e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c205e-105">Syntax</span></span>  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="c205e-106">Teile</span><span class="sxs-lookup"><span data-stu-id="c205e-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="c205e-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c205e-107">Required.</span></span> <span data-ttu-id="c205e-108">Alle `Boolean` Variable.</span><span class="sxs-lookup"><span data-stu-id="c205e-108">Any `Boolean` variable.</span></span> <span data-ttu-id="c205e-109">Das Ergebnis ist eine `Boolean` Wert, der davon, ob die `string` erfüllt die `pattern`.</span><span class="sxs-lookup"><span data-stu-id="c205e-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="c205e-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c205e-110">Required.</span></span> <span data-ttu-id="c205e-111">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c205e-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="c205e-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c205e-112">Required.</span></span> <span data-ttu-id="c205e-113">Alle `String` Ausdruck, beschriebenen Mustervergleichskonventionen entspricht der Mustervergleich in "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="c205e-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c205e-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c205e-114">Remarks</span></span>  
 <span data-ttu-id="c205e-115">Wenn der Wert in `string` erfüllt das Muster `pattern`, `result` ist `True`.</span><span class="sxs-lookup"><span data-stu-id="c205e-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="c205e-116">Wenn die Zeichenfolge das Muster nicht erfüllt `result` ist `False`.</span><span class="sxs-lookup"><span data-stu-id="c205e-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="c205e-117">Wenn beide `string` und `pattern` sind leere Zeichenfolgen, das Ergebnis ist `True`.</span><span class="sxs-lookup"><span data-stu-id="c205e-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="c205e-118">Methode zum Zeichenfolgenvergleich</span><span class="sxs-lookup"><span data-stu-id="c205e-118">Comparison Method</span></span>  
 <span data-ttu-id="c205e-119">Das Verhalten der `Like` Operator hängt von der [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c205e-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span> <span data-ttu-id="c205e-120">Ist die Standardmethode für jede Quelldatei `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="c205e-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="c205e-121">Musteroptionen für</span><span class="sxs-lookup"><span data-stu-id="c205e-121">Pattern Options</span></span>  
 <span data-ttu-id="c205e-122">Integrierte Mustervergleich bietet ein vielseitiges Tool für Vergleiche von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c205e-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="c205e-123">Der Musterabgleich Funktionen ermöglichen es Ihnen, um jedes Zeichen in `string` für ein bestimmtes Zeichen, ein Platzhalterzeichen, eine Zeichenliste oder einem Bereich von Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c205e-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="c205e-124">Die folgende Tabelle zeigt die zulässigen Zeichen in `pattern` und womit sie übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c205e-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="c205e-125">Zeichen in `pattern`</span><span class="sxs-lookup"><span data-stu-id="c205e-125">Characters in `pattern`</span></span>|<span data-ttu-id="c205e-126">Findet in `string`</span><span class="sxs-lookup"><span data-stu-id="c205e-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="c205e-127">Ein beliebiges einzelnes Zeichen</span><span class="sxs-lookup"><span data-stu-id="c205e-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="c205e-128">NULL oder mehr Zeichen</span><span class="sxs-lookup"><span data-stu-id="c205e-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="c205e-129">Eine beliebige einzelne Ziffer (0 – 9)</span><span class="sxs-lookup"><span data-stu-id="c205e-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="c205e-130">In jedem beliebigen einzelnen Zeichen `charlist`</span><span class="sxs-lookup"><span data-stu-id="c205e-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="c205e-131">Beliebiges einzelnes Zeichen, die nicht in `charlist`</span><span class="sxs-lookup"><span data-stu-id="c205e-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="c205e-132">Zeichenlisten</span><span class="sxs-lookup"><span data-stu-id="c205e-132">Character Lists</span></span>  
 <span data-ttu-id="c205e-133">Eine Gruppe von ein oder mehrere Zeichen (`charlist`) in eckige Klammern eingeschlossen (`[ ]`) kann verwendet werden, um einem beliebigen einzelnen Zeichen entspricht `string` und kann beinahe jeder Zeichencode, einschließlich Ziffern enthalten.</span><span class="sxs-lookup"><span data-stu-id="c205e-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="c205e-134">Ein Ausrufezeichen (`!`) am Anfang des `charlist` bedeutet, die eine Übereinstimmung festgestellt wurde, wenn ein beliebiges Zeichen, mit Ausnahme der Zeichen in `charlist` befindet sich im `string`.</span><span class="sxs-lookup"><span data-stu-id="c205e-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="c205e-135">Wenn Sie außerhalb der Klammern verwendet, entspricht das Ausrufezeichen selbst.</span><span class="sxs-lookup"><span data-stu-id="c205e-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="c205e-136">Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="c205e-136">Special Characters</span></span>  
 <span data-ttu-id="c205e-137">Entsprechend Sonderzeichen für die öffnende Klammer (`[`), Fragezeichen (`?`), Nummernzeichen (`#`), und das Sternchen (`*`), schließen Sie sie in Klammern.</span><span class="sxs-lookup"><span data-stu-id="c205e-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="c205e-138">Die Rechte eckige Klammer (`]`) kann nicht innerhalb einer Gruppe verwendet werden, entsprechend selbst, aber es kann als ein einzelnes Zeichen außerhalb einer Gruppe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c205e-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="c205e-139">Die Zeichensequenz `[]` gilt als eine Zeichenfolge der Länge 0 (null) (`""`).</span><span class="sxs-lookup"><span data-stu-id="c205e-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="c205e-140">Es kann nicht jedoch, der ein Zeichen enthalten, die in eckige Klammern eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="c205e-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="c205e-141">Sollten Sie prüfen, ob eine Position im `string` enthält mindestens ein von einer Gruppe von Zeichen oder keine Zeichen im Vorfeld für alle, können Sie `Like` zweimal.</span><span class="sxs-lookup"><span data-stu-id="c205e-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="c205e-142">Ein Beispiel finden Sie unter [Gewusst wie: Vergleichen einer Zeichenfolge mit einem Muster](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="c205e-142">For an example, see [How to: Match a String against a Pattern](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="c205e-143">Zeichenbereiche</span><span class="sxs-lookup"><span data-stu-id="c205e-143">Character Ranges</span></span>  
 <span data-ttu-id="c205e-144">Mithilfe eines Bindestrichs (`–`) trennen Sie die untere und obere Grenze des Bereichs `charlist` können einen Bereich von Zeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="c205e-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="c205e-145">Z. B. `[A–Z]` ergibt eine Übereinstimmung, wenn die entsprechende in Zeichenposition `string` enthält alle Zeichen innerhalb des Bereichs `A`–`Z`, und `[!H–L]` ergibt eine Übereinstimmung, wenn das entsprechende Zeichen zu positionieren. beliebiges Zeichen außerhalb des Bereichs enthält `H`–`L`.</span><span class="sxs-lookup"><span data-stu-id="c205e-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="c205e-146">Wenn Sie einen Bereich von Zeichen angeben, müssen die werden in aufsteigender Sortierreihenfolge, d. h. vom niedrigsten zum höchsten.</span><span class="sxs-lookup"><span data-stu-id="c205e-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="c205e-147">Daher `[A–Z]` ist ein gültiges Muster, sondern `[Z–A]` nicht.</span><span class="sxs-lookup"><span data-stu-id="c205e-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="c205e-148">Mehrere Zeichenbereiche</span><span class="sxs-lookup"><span data-stu-id="c205e-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="c205e-149">Wenn mehrere Bereiche für die gleiche Position angeben möchten, fügen Sie sie innerhalb der gleichen Klammern ohne Trennzeichen ein.</span><span class="sxs-lookup"><span data-stu-id="c205e-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="c205e-150">Z. B. `[A–CX–Z]` ergibt eine Übereinstimmung, wenn die entsprechende in Zeichenposition `string` enthält alle Zeichen im Bereich entweder `A`–`C` oder den Bereich `X`–`Z`.</span><span class="sxs-lookup"><span data-stu-id="c205e-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="c205e-151">Verwenden des Bindestrichs</span><span class="sxs-lookup"><span data-stu-id="c205e-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="c205e-152">Ein Bindestrich (`–`) kann auftreten, entweder am Anfang (nach einem Ausrufezeichen, sofern vorhanden) oder am Ende der `charlist` entsprechend selbst.</span><span class="sxs-lookup"><span data-stu-id="c205e-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="c205e-153">In einem beliebigen anderen Ort identifiziert der Bindestrich einen Bereich von Zeichen, die durch die Zeichen auf beiden Seiten des Bindestrichs getrennt.</span><span class="sxs-lookup"><span data-stu-id="c205e-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="c205e-154">Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="c205e-154">Collating Sequence</span></span>  
 <span data-ttu-id="c205e-155">Die Bedeutung eines angegebenen Bereichs ist abhängig von der Zeichenreihenfolge zur Laufzeit vom `Option Compare` und dem Gebietsschema des Systems, auf der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c205e-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="c205e-156">Mit `Option Compare Binary`, den Bereich `[A–E]` entspricht `A`, `B`, `C`, `D`, und `E`.</span><span class="sxs-lookup"><span data-stu-id="c205e-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="c205e-157">Mit `Option Compare Text`, `[A–E]` entspricht `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, und `e`.</span><span class="sxs-lookup"><span data-stu-id="c205e-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="c205e-158">Der Bereich entspricht nicht `Ê` oder `ê` da Zeichen mit Akzent nach Zeichen ohne Akzent Zeichen in der Sortierreihenfolge sortieren.</span><span class="sxs-lookup"><span data-stu-id="c205e-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="c205e-159">Digraph Zeichen</span><span class="sxs-lookup"><span data-stu-id="c205e-159">Digraph Characters</span></span>  
 <span data-ttu-id="c205e-160">In einigen Sprachen sind alphabetische Zeichen, die zwei separate Zeichen darstellen.</span><span class="sxs-lookup"><span data-stu-id="c205e-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="c205e-161">Mehrere Sprachen verwenden Sie z. B. das Zeichen `æ` zur Darstellung der Zeichen `a` und `e` Wenn sie zusammen auftreten.</span><span class="sxs-lookup"><span data-stu-id="c205e-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="c205e-162">Die `Like` -Operator erkennt, dass die einzelnen Digraphzeichen und die zwei einzelne Zeichen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c205e-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="c205e-163">Wenn eine Sprache, die ein Zeichen Digraph verwendet in die Einstellungen für das Gebietsschema angegeben wird, ein Vorkommen des Zeichens in einem einzelnen Digraph `pattern` oder `string` entspricht der entsprechende Sequenz von zwei Zeichen in die andere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="c205e-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="c205e-164">Auf ähnliche Weise einen Digraph Zeichen in `pattern` in eckige Klammern eingeschlossen (allein in einer Liste oder in einem Bereich) entspricht in der entsprechenden zwei Zeichen bestehende Folge `string`.</span><span class="sxs-lookup"><span data-stu-id="c205e-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="c205e-165">Überladen</span><span class="sxs-lookup"><span data-stu-id="c205e-165">Overloading</span></span>  
 <span data-ttu-id="c205e-166">Die `Like` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat.</span><span class="sxs-lookup"><span data-stu-id="c205e-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="c205e-167">Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten.</span><span class="sxs-lookup"><span data-stu-id="c205e-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="c205e-168">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c205e-168">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c205e-169">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c205e-169">Example</span></span>  
 <span data-ttu-id="c205e-170">Dieses Beispiel verwendet die `Like` Operator zum Vergleichen von Zeichenfolgen mit verschiedenen Mustern.</span><span class="sxs-lookup"><span data-stu-id="c205e-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="c205e-171">Die Ergebnisse werden in einem `Boolean` Variable, der angibt, ob jede Zeichenfolge dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="c205e-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="c205e-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c205e-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="c205e-173">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c205e-173">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="c205e-174">Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c205e-174">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="c205e-175">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="c205e-175">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="c205e-176">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c205e-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="c205e-177">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c205e-177">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="c205e-178">Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster</span><span class="sxs-lookup"><span data-stu-id="c205e-178">How to: Match a String against a Pattern</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
