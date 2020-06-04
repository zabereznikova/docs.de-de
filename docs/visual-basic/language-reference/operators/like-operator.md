---
title: Like-Operator
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
ms.openlocfilehash: 4279d90c74c80403146448a8ba5a6051ec9d12f6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401554"
---
# <a name="like-operator-visual-basic"></a><span data-ttu-id="98c23-102">Like-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98c23-102">Like Operator (Visual Basic)</span></span>
<span data-ttu-id="98c23-103">Vergleicht eine Zeichenfolge mit einem Muster.</span><span class="sxs-lookup"><span data-stu-id="98c23-103">Compares a string against a pattern.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="98c23-104">Der `Like` -Operator wird derzeit nicht in .net Core-und .NET Standard-Projekten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98c23-104">The `Like` operator is currently not supported in .NET Core and .NET Standard projects.</span></span>

## <a name="syntax"></a><span data-ttu-id="98c23-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="98c23-105">Syntax</span></span>  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a><span data-ttu-id="98c23-106">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="98c23-106">Parts</span></span>  
 `result`  
 <span data-ttu-id="98c23-107">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98c23-107">Required.</span></span> <span data-ttu-id="98c23-108">Eine beliebige `Boolean` Variable.</span><span class="sxs-lookup"><span data-stu-id="98c23-108">Any `Boolean` variable.</span></span> <span data-ttu-id="98c23-109">Das Ergebnis ist ein `Boolean` Wert, der angibt, ob der `string` die erfüllt `pattern` .</span><span class="sxs-lookup"><span data-stu-id="98c23-109">The result is a `Boolean` value indicating whether or not the `string` satisfies the `pattern`.</span></span>  
  
 `string`  
 <span data-ttu-id="98c23-110">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98c23-110">Required.</span></span> <span data-ttu-id="98c23-111">Beliebiger `String` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="98c23-111">Any `String` expression.</span></span>  
  
 `pattern`  
 <span data-ttu-id="98c23-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98c23-112">Required.</span></span> <span data-ttu-id="98c23-113">Jeder `String` Ausdruck, der den in "Anmerkungen" beschriebenen Muster Vergleichs Konventionen entspricht.</span><span class="sxs-lookup"><span data-stu-id="98c23-113">Any `String` expression conforming to the pattern-matching conventions described in "Remarks."</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98c23-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="98c23-114">Remarks</span></span>  
 <span data-ttu-id="98c23-115">Wenn der Wert in `string` dem in enthaltenen Muster entspricht `pattern` , `result` ist `True` .</span><span class="sxs-lookup"><span data-stu-id="98c23-115">If the value in `string` satisfies the pattern contained in `pattern`, `result` is `True`.</span></span> <span data-ttu-id="98c23-116">Wenn die Zeichenfolge das Muster nicht erfüllt, `result` ist `False` .</span><span class="sxs-lookup"><span data-stu-id="98c23-116">If the string does not satisfy the pattern, `result` is `False`.</span></span> <span data-ttu-id="98c23-117">Wenn sowohl `string` als auch `pattern` leere Zeichen folgen sind, ist das Ergebnis `True` .</span><span class="sxs-lookup"><span data-stu-id="98c23-117">If both `string` and `pattern` are empty strings, the result is `True`.</span></span>  
  
## <a name="comparison-method"></a><span data-ttu-id="98c23-118">Vergleichsmethode</span><span class="sxs-lookup"><span data-stu-id="98c23-118">Comparison Method</span></span>  
 <span data-ttu-id="98c23-119">Das Verhalten des- `Like` Operators hängt von der [Option Compare-Anweisung](../statements/option-compare-statement.md)ab.</span><span class="sxs-lookup"><span data-stu-id="98c23-119">The behavior of the `Like` operator depends on the [Option Compare Statement](../statements/option-compare-statement.md).</span></span> <span data-ttu-id="98c23-120">Die standardmäßige Zeichen folgen Vergleichsmethode für jede Quelldatei ist `Option Compare Binary` .</span><span class="sxs-lookup"><span data-stu-id="98c23-120">The default string comparison method for each source file is `Option Compare Binary`.</span></span>  
  
## <a name="pattern-options"></a><span data-ttu-id="98c23-121">Muster Optionen</span><span class="sxs-lookup"><span data-stu-id="98c23-121">Pattern Options</span></span>  
 <span data-ttu-id="98c23-122">Der integrierte Musterabgleich bietet ein vielseitiges Tool für Zeichen folgen Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="98c23-122">Built-in pattern matching provides a versatile tool for string comparisons.</span></span> <span data-ttu-id="98c23-123">Die Muster Vergleichs Features ermöglichen es Ihnen, jedes Zeichen in mit `string` einem bestimmten Zeichen, einem Platzhalter Zeichen, einer Zeichen Liste oder einem Zeichenbereich abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="98c23-123">The pattern-matching features allow you to match each character in `string` against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="98c23-124">In der folgenden Tabelle sind die Zeichen aufgeführt, die in zulässig sind `pattern` .</span><span class="sxs-lookup"><span data-stu-id="98c23-124">The following table shows the characters allowed in `pattern` and what they match.</span></span>  
  
|<span data-ttu-id="98c23-125">Zeichen in`pattern`</span><span class="sxs-lookup"><span data-stu-id="98c23-125">Characters in `pattern`</span></span>|<span data-ttu-id="98c23-126">Übereinstimmungen in`string`</span><span class="sxs-lookup"><span data-stu-id="98c23-126">Matches in `string`</span></span>|  
|-----------------------------|-------------------------|  
|`?`|<span data-ttu-id="98c23-127">Ein einzelnes Zeichen</span><span class="sxs-lookup"><span data-stu-id="98c23-127">Any single character</span></span>|  
|`*`|<span data-ttu-id="98c23-128">NULL oder mehr Zeichen</span><span class="sxs-lookup"><span data-stu-id="98c23-128">Zero or more characters</span></span>|  
|`#`|<span data-ttu-id="98c23-129">Eine beliebige einzelne Ziffer (0 – 9)</span><span class="sxs-lookup"><span data-stu-id="98c23-129">Any single digit (0–9)</span></span>|  
|`[charlist]`|<span data-ttu-id="98c23-130">Beliebiges einzelnes Zeichen in`charlist`</span><span class="sxs-lookup"><span data-stu-id="98c23-130">Any single character in `charlist`</span></span>|  
|`[!charlist]`|<span data-ttu-id="98c23-131">Alle einzelnen Zeichen, die nicht in`charlist`</span><span class="sxs-lookup"><span data-stu-id="98c23-131">Any single character not in `charlist`</span></span>|  
  
## <a name="character-lists"></a><span data-ttu-id="98c23-132">Zeichen Listen</span><span class="sxs-lookup"><span data-stu-id="98c23-132">Character Lists</span></span>  
 <span data-ttu-id="98c23-133">Eine Gruppe mit einem oder mehreren Zeichen ( `charlist` ), die in eckige Klammern () eingeschlossen ist, `[ ]` kann verwendet werden, um ein beliebiges einzelnes Zeichen in abzugleichen `string` , und kann nahezu beliebigen Zeichencode enthalten, einschließlich Ziffern.</span><span class="sxs-lookup"><span data-stu-id="98c23-133">A group of one or more characters (`charlist`) enclosed in brackets (`[ ]`) can be used to match any single character in `string` and can include almost any character code, including digits.</span></span>  
  
 <span data-ttu-id="98c23-134">Ein Ausrufezeichen ( `!` ) am Anfang von `charlist` bedeutet, dass eine Abgleich erfolgt, wenn ein beliebiges Zeichen mit Ausnahme der Zeichen in `charlist` gefunden wird `string` .</span><span class="sxs-lookup"><span data-stu-id="98c23-134">An exclamation point (`!`) at the beginning of `charlist` means that a match is made if any character except the characters in `charlist` is found in `string`.</span></span> <span data-ttu-id="98c23-135">Bei Verwendung außerhalb von Klammern entspricht das Ausrufezeichen dem Wert selbst.</span><span class="sxs-lookup"><span data-stu-id="98c23-135">When used outside brackets, the exclamation point matches itself.</span></span>  
  
## <a name="special-characters"></a><span data-ttu-id="98c23-136">Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="98c23-136">Special Characters</span></span>  
 <span data-ttu-id="98c23-137">Zum Abgleichen der Sonderzeichen Left eckige Klammer ( `[` ), Fragezeichen ( `?` ), Nummern Zeichen ( `#` ) und Sternchen ( `*` ), schließen Sie Sie in eckige Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="98c23-137">To match the special characters left bracket (`[`), question mark (`?`), number sign (`#`), and asterisk (`*`), enclose them in brackets.</span></span> <span data-ttu-id="98c23-138">Die rechte eckige Klammer ( `]` ) kann nicht innerhalb einer Gruppe verwendet werden, um sich selbst abzugleichen, Sie kann jedoch außerhalb einer Gruppe als einzelnes Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98c23-138">The right bracket (`]`) cannot be used within a group to match itself, but it can be used outside a group as an individual character.</span></span>  
  
 <span data-ttu-id="98c23-139">Die Zeichenfolge `[]` wird als Zeichenfolge der Länge 0 (NULL `""` ) betrachtet.</span><span class="sxs-lookup"><span data-stu-id="98c23-139">The character sequence `[]` is considered a zero-length string (`""`).</span></span> <span data-ttu-id="98c23-140">Sie kann jedoch nicht Teil einer Zeichen Liste sein, die in eckige Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="98c23-140">However, it cannot be part of a character list enclosed in brackets.</span></span> <span data-ttu-id="98c23-141">Wenn Sie überprüfen möchten, ob eine Position in `string` mindestens eine Zeichen Gruppe oder kein Zeichen enthält, können Sie Sie `Like` zweimal verwenden.</span><span class="sxs-lookup"><span data-stu-id="98c23-141">If you want to check whether a position in `string` contains one of a group of characters or no character at all, you can use `Like` twice.</span></span> <span data-ttu-id="98c23-142">Ein Beispiel finden Sie unter Gewusst [wie: Vergleichen einer Zeichenfolge mit einem Muster](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="98c23-142">For an example, see [How to: Match a String against a Pattern](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).</span></span>  
  
## <a name="character-ranges"></a><span data-ttu-id="98c23-143">Zeichen Bereiche</span><span class="sxs-lookup"><span data-stu-id="98c23-143">Character Ranges</span></span>  
 <span data-ttu-id="98c23-144">Durch die Verwendung eines Bindestrichs ( `–` ) zum Trennen der unteren und oberen Begrenzungen des Bereichs `charlist` kann einen Zeichenbereich angeben.</span><span class="sxs-lookup"><span data-stu-id="98c23-144">By using a hyphen (`–`) to separate the lower and upper bounds of the range, `charlist` can specify a range of characters.</span></span> <span data-ttu-id="98c23-145">Beispielsweise `[A–Z]` ergibt eine Übereinstimmung, wenn die entsprechende Zeichenposition in ein `string` beliebiges Zeichen innerhalb des Bereichs `A` – enthält `Z` und `[!H–L]` eine Übereinstimmung ergibt, wenn die entsprechende Zeichenposition ein Zeichen außerhalb des Bereichs `H` – enthält `L` .</span><span class="sxs-lookup"><span data-stu-id="98c23-145">For example, `[A–Z]` results in a match if the corresponding character position in `string` contains any character within the range `A`–`Z`, and `[!H–L]` results in a match if the corresponding character position contains any character outside the range `H`–`L`.</span></span>  
  
 <span data-ttu-id="98c23-146">Wenn Sie einen Zeichenbereich angeben, müssen Sie in aufsteigender Sortierreihenfolge angezeigt werden, d. h. von der niedrigsten zur höchsten.</span><span class="sxs-lookup"><span data-stu-id="98c23-146">When you specify a range of characters, they must appear in ascending sort order, that is, from lowest to highest.</span></span> <span data-ttu-id="98c23-147">Daher `[A–Z]` ist ein gültiges Muster, aber `[Z–A]` nicht.</span><span class="sxs-lookup"><span data-stu-id="98c23-147">Thus, `[A–Z]` is a valid pattern, but `[Z–A]` is not.</span></span>  
  
### <a name="multiple-character-ranges"></a><span data-ttu-id="98c23-148">Mehrere Zeichen Bereiche</span><span class="sxs-lookup"><span data-stu-id="98c23-148">Multiple Character Ranges</span></span>  
 <span data-ttu-id="98c23-149">Wenn Sie mehrere Bereiche für dieselbe Zeichenposition angeben möchten, platzieren Sie Sie ohne Trennzeichen in denselben Klammern.</span><span class="sxs-lookup"><span data-stu-id="98c23-149">To specify multiple ranges for the same character position, put them within the same brackets without delimiters.</span></span> <span data-ttu-id="98c23-150">Beispielsweise `[A–CX–Z]` ergibt eine Übereinstimmung, wenn die entsprechende Zeichenposition in ein `string` beliebiges Zeichen innerhalb des Bereichs `A` – `C` oder des Bereichs `X` – enthält `Z` .</span><span class="sxs-lookup"><span data-stu-id="98c23-150">For example, `[A–CX–Z]` results in a match if the corresponding character position in `string` contains any character within either the range `A`–`C` or the range `X`–`Z`.</span></span>  
  
### <a name="usage-of-the-hyphen"></a><span data-ttu-id="98c23-151">Verwendung des Bindestrichs</span><span class="sxs-lookup"><span data-stu-id="98c23-151">Usage of the Hyphen</span></span>  
 <span data-ttu-id="98c23-152">Ein Bindestrich ( `–` ) kann entweder am Anfang (nach einem Ausrufezeichen, falls vorhanden) oder am Ende von angezeigt werden `charlist` , um sich selbst abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="98c23-152">A hyphen (`–`) can appear either at the beginning (after an exclamation point, if any) or at the end of `charlist` to match itself.</span></span> <span data-ttu-id="98c23-153">An einem beliebigen anderen Speicherort identifiziert der Bindestrich einen Zeichenbereich, der durch die Zeichen auf beiden Seiten des Bindestrichs getrennt ist.</span><span class="sxs-lookup"><span data-stu-id="98c23-153">In any other location, the hyphen identifies a range of characters delimited by the characters on either side of the hyphen.</span></span>  
  
## <a name="collating-sequence"></a><span data-ttu-id="98c23-154">Sortierreihenfolge</span><span class="sxs-lookup"><span data-stu-id="98c23-154">Collating Sequence</span></span>  
 <span data-ttu-id="98c23-155">Die Bedeutung eines bestimmten Bereichs hängt von der Zeichenfolge zur Laufzeit ab, wie von bestimmt, `Option Compare` und der Gebiets Schema Einstellung des Systems, auf dem der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="98c23-155">The meaning of a specified range depends on the character ordering at run time, as determined by `Option Compare` and the locale setting of the system the code is running on.</span></span> <span data-ttu-id="98c23-156">Bei `Option Compare Binary` entspricht der Bereich `[A–E]` `A` ,, `B` `C` , `D` und `E` .</span><span class="sxs-lookup"><span data-stu-id="98c23-156">With `Option Compare Binary`, the range `[A–E]` matches `A`, `B`, `C`, `D`, and `E`.</span></span> <span data-ttu-id="98c23-157">Mit entspricht,,,,, `Option Compare Text` `[A–E]` `A` `a` `À` `à` `B` `b` , `C` , `c` , `D` , `d` , `E` und `e` .</span><span class="sxs-lookup"><span data-stu-id="98c23-157">With `Option Compare Text`, `[A–E]` matches `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, and `e`.</span></span> <span data-ttu-id="98c23-158">Der Bereich entspricht nicht `Ê` oder, `ê` weil Zeichen in der Sortierreihenfolge nach Zeichen mit Zeichen mit Zeichen versehen sind.</span><span class="sxs-lookup"><span data-stu-id="98c23-158">The range does not match `Ê` or `ê` because accented characters collate after unaccented characters in the sort order.</span></span>  
  
## <a name="digraph-characters"></a><span data-ttu-id="98c23-159">Digraph-Zeichen</span><span class="sxs-lookup"><span data-stu-id="98c23-159">Digraph Characters</span></span>  
 <span data-ttu-id="98c23-160">In einigen Sprachen gibt es alphabetische Zeichen, die zwei separate Zeichen darstellen.</span><span class="sxs-lookup"><span data-stu-id="98c23-160">In some languages, there are alphabetic characters that represent two separate characters.</span></span> <span data-ttu-id="98c23-161">Beispielsweise verwenden mehrere Sprachen das Zeichen `æ` , um die Zeichen darzustellen, `a` und `e` Wenn Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="98c23-161">For example, several languages use the character `æ` to represent the characters `a` and `e` when they appear together.</span></span> <span data-ttu-id="98c23-162">Der `Like` -Operator erkennt, dass das einzelne Digraph-Zeichen und die beiden einzelnen Zeichen gleichwertig sind.</span><span class="sxs-lookup"><span data-stu-id="98c23-162">The `Like` operator recognizes that the single digraph character and the two individual characters are equivalent.</span></span>  
  
 <span data-ttu-id="98c23-163">Wenn eine Sprache, die ein Digraph-Zeichen verwendet, in den Gebiets Schema Einstellungen des Systems angegeben ist, wird ein Vorkommen des einzelnen Digraph-Zeichens in `pattern` oder mit `string` der entsprechenden 2-Zeichen-Sequenz in der anderen Zeichenfolge übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="98c23-163">When a language that uses a digraph character is specified in the system locale settings, an occurrence of the single digraph character in either `pattern` or `string` matches the equivalent two-character sequence in the other string.</span></span> <span data-ttu-id="98c23-164">Ebenso entspricht ein Digraph-Zeichen in `pattern` Klammern (selbst, in einer Liste oder in einem Bereich) der entsprechenden zweistelligen Sequenz in `string` .</span><span class="sxs-lookup"><span data-stu-id="98c23-164">Similarly, a digraph character in `pattern` enclosed in brackets (by itself, in a list, or in a range) matches the equivalent two-character sequence in `string`.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="98c23-165">Überladen</span><span class="sxs-lookup"><span data-stu-id="98c23-165">Overloading</span></span>  
 <span data-ttu-id="98c23-166">Der `Like` Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.</span><span class="sxs-lookup"><span data-stu-id="98c23-166">The `Like` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="98c23-167">Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen.</span><span class="sxs-lookup"><span data-stu-id="98c23-167">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="98c23-168">Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="98c23-168">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98c23-169">Beispiel</span><span class="sxs-lookup"><span data-stu-id="98c23-169">Example</span></span>  
 <span data-ttu-id="98c23-170">In diesem Beispiel wird der- `Like` Operator zum Vergleichen von Zeichen folgen mit verschiedenen Mustern verwendet.</span><span class="sxs-lookup"><span data-stu-id="98c23-170">This example uses the `Like` operator to compare strings to various patterns.</span></span> <span data-ttu-id="98c23-171">Die Ergebnisse werden in eine `Boolean` Variable umgewandelt, die angibt, ob jede Zeichenfolge dem Muster entspricht.</span><span class="sxs-lookup"><span data-stu-id="98c23-171">The results go into a `Boolean` variable indicating whether each string satisfies the pattern.</span></span>  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="98c23-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98c23-172">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [<span data-ttu-id="98c23-173">Vergleichs Operatoren</span><span class="sxs-lookup"><span data-stu-id="98c23-173">Comparison Operators</span></span>](comparison-operators.md)
- [<span data-ttu-id="98c23-174">Operatorrangfolge in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="98c23-174">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="98c23-175">Nach Funktionalität sortierte Operatoren</span><span class="sxs-lookup"><span data-stu-id="98c23-175">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="98c23-176">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="98c23-176">Option Compare Statement</span></span>](../statements/option-compare-statement.md)
- [<span data-ttu-id="98c23-177">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="98c23-177">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="98c23-178">Vorgehensweise: Vergleichen einer Zeichenfolge mit einem Muster</span><span class="sxs-lookup"><span data-stu-id="98c23-178">How to: Match a String against a Pattern</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
