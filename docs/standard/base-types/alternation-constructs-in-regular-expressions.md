---
title: Alternierungskonstrukte in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie Alternierungskonstrukte für den bedingten Abgleich in regulären Ausdrücken verwenden können.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- either/or matching
- alternative matching patterns
- regular expressions, alternation constructs
- alternation constructs
- optional matching patterns
- constructs, alternation
- .NET regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
ms.openlocfilehash: 0a1b46443d5cd9f8a19f4cfb9f9b07a5e33e719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714691"
---
# <a name="alternation-constructs-in-regular-expressions"></a><span data-ttu-id="55ba7-103">Alternierungskonstrukte in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="55ba7-103">Alternation Constructs in Regular Expressions</span></span>

<span data-ttu-id="55ba7-104">Alternierungskonstrukte ändern einen regulären Ausdruck, um Entweder-Oder-Vergleiche oder eine bedingte Übereinstimmung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-104">Alternation constructs modify a regular expression to enable either/or or conditional matching.</span></span> <span data-ttu-id="55ba7-105">.NET unterstützt drei Alternierungskonstrukte:</span><span class="sxs-lookup"><span data-stu-id="55ba7-105">.NET supports three alternation constructs:</span></span>

- [<span data-ttu-id="55ba7-106">Musterabgleich mit &#124;</span><span class="sxs-lookup"><span data-stu-id="55ba7-106">Pattern matching with &#124;</span></span>](#Either_Or)
- [<span data-ttu-id="55ba7-107">Bedingte Übereinstimmung mit (?(Ausdruck)ja&#124;nein)</span><span class="sxs-lookup"><span data-stu-id="55ba7-107">Conditional matching with (?(expression)yes&#124;no)</span></span>](#Conditional_Expr)
- [<span data-ttu-id="55ba7-108">Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe</span><span class="sxs-lookup"><span data-stu-id="55ba7-108">Conditional matching based on a valid captured group</span></span>](#Conditional_Group)

<a name="Either_Or"></a>

## <a name="pattern-matching-with-124"></a><span data-ttu-id="55ba7-109">Musterabgleich mit &#124;</span><span class="sxs-lookup"><span data-stu-id="55ba7-109">Pattern Matching with &#124;</span></span>

<span data-ttu-id="55ba7-110">Sie können das vertikale Balkenzeichen (`|`) für Vergleiche mit einem oder mehreren aus einer Reihe von Mustern verwenden, wobei das `|`-Zeichen als Trennzeichen für die einzelnen Muster dient.</span><span class="sxs-lookup"><span data-stu-id="55ba7-110">You can use the vertical bar (`|`) character to match any one of a series of patterns, where the `|` character separates each pattern.</span></span>

<span data-ttu-id="55ba7-111">Wie bei der positiven Zeichenklasse kann das `|` -Zeichen für Vergleiche mit jedem beliebigen Zeichen aus einer Reihe einzelner Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55ba7-111">Like the positive character class, the `|` character can be used to match any one of a number of single characters.</span></span> <span data-ttu-id="55ba7-112">Im folgenden Beispiel wird sowohl eine positive Zeichenklasse als auch ein Entweder-Oder-Mustervergleich mithilfe des `|` -Zeichens verwendet, um Vorkommen der Wörter „gray“ oder „grau“ in einer Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="55ba7-112">The following example uses both a positive character class and either/or pattern matching with the `|` character to locate occurrences of the words "gray" or "grey" in a string.</span></span> <span data-ttu-id="55ba7-113">In diesem Fall ergibt das `|` -Zeichen einen regulären Ausdruck, der eine ausführlichere Ausgabe bewirkt.</span><span class="sxs-lookup"><span data-stu-id="55ba7-113">In this case, the `|` character produces a regular expression that is more verbose.</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#1](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
[!code-vb[RegularExpressions.Language.Alternation#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]

<span data-ttu-id="55ba7-114">Der reguläre Ausdruck `\bgr(a|e)y\b`, der das `|`-Zeichen verwendet, wird entsprechend der Darstellung in der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="55ba7-114">The regular expression that uses the `|` character, `\bgr(a|e)y\b`, is interpreted as shown in the following table:</span></span>

|<span data-ttu-id="55ba7-115">Muster</span><span class="sxs-lookup"><span data-stu-id="55ba7-115">Pattern</span></span>|<span data-ttu-id="55ba7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55ba7-116">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="55ba7-117">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-117">Start at a word boundary.</span></span>|  
|`gr`|<span data-ttu-id="55ba7-118">Übereinstimmung mit den Zeichen "gr".</span><span class="sxs-lookup"><span data-stu-id="55ba7-118">Match the characters "gr".</span></span>|  
|<code>(a&#124;e)</code>|<span data-ttu-id="55ba7-119">Übereinstimmung mit entweder "a" oder "e".</span><span class="sxs-lookup"><span data-stu-id="55ba7-119">Match either an "a" or an "e".</span></span>|  
|`y\b`|<span data-ttu-id="55ba7-120">Übereinstimmung mit "y" an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="55ba7-120">Match a "y" on a word boundary.</span></span>|  

<span data-ttu-id="55ba7-121">Das `|`-Zeichen kann auch verwendet werden, um einen Entweder-Oder-Vergleich mit mehreren Zeichen oder Teilausdrücken durchzuführen, wobei eine beliebige Kombination von Zeichenliteralen und Sprachelementen für reguläre Ausdrücke enthalten sein kann.</span><span class="sxs-lookup"><span data-stu-id="55ba7-121">The `|` character can also be used to perform an either/or match with multiple characters or subexpressions, which can include any combination of character literals and regular expression language elements.</span></span> <span data-ttu-id="55ba7-122">(Die Zeichenklasse stellt diese Funktionalität nicht bereit.) Im folgenden Beispiel wird das `|`-Zeichen verwendet, um entweder eine Sozialversicherungsnummer in den USA, also eine neunstellige Zahl mit dem Format *ddd*-*dd*-*dddd*, oder eine Identifikationsnummer des Arbeitgebers in den USA (EIN, Employer Identification Number), also eine neunstellige Zahl mit dem Format *dd*-*ddddddd* zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="55ba7-122">(The character class does not provide this functionality.) The following example uses the `|` character to extract either a U.S. Social Security Number (SSN), which is a 9-digit number with the format *ddd*-*dd*-*dddd*, or a U.S. Employer Identification Number (EIN), which is a 9-digit number with the format *dd*-*ddddddd*.</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#2](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
[!code-vb[RegularExpressions.Language.Alternation#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  

<span data-ttu-id="55ba7-123">Der reguläre Ausdruck `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="55ba7-123">The regular expression `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table:</span></span>
  
|<span data-ttu-id="55ba7-124">Muster</span><span class="sxs-lookup"><span data-stu-id="55ba7-124">Pattern</span></span>|<span data-ttu-id="55ba7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55ba7-125">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="55ba7-126">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-126">Start at a word boundary.</span></span>|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|<span data-ttu-id="55ba7-127">Eine der folgenden Varianten muss übereinstimmen: zwei Dezimalstellen gefolgt von einem Bindestrich gefolgt von sieben Dezimalstellen; oder drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-127">Match either of the following: two decimal digits followed by a hyphen followed by seven decimal digits; or three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="55ba7-128">Der Vergleich endet an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="55ba7-128">End the match at a word boundary.</span></span>|  
  
<a name="Conditional_Expr"></a>

## <a name="conditional-matching-with-an-expression"></a><span data-ttu-id="55ba7-129">Bedingte Übereinstimmung mit einem Ausdruck</span><span class="sxs-lookup"><span data-stu-id="55ba7-129">Conditional matching with an expression</span></span>

<span data-ttu-id="55ba7-130">Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es ein ursprüngliches Muster zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="55ba7-130">This language element attempts to match one of two patterns depending on whether it can match an initial pattern.</span></span> <span data-ttu-id="55ba7-131">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="55ba7-131">Its syntax is:</span></span>  

<span data-ttu-id="55ba7-132">`(?(` *expression* `)` *yes* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="55ba7-132">`(?(` *expression* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="55ba7-133">wobei *expression* das ursprüngliche zu enstprechende Muster ist. *yes* ist das entsprechende Muster, wenn *expression* zugeordnet ist, und *no* ist das entsprechende optionale Muster, wenn *expression* nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="55ba7-133">where *expression* is the initial pattern to match, *yes* is the pattern to match if *expression* is matched, and *no* is the optional pattern to match if *expression* is not matched.</span></span> <span data-ttu-id="55ba7-134">Die Engine für reguläre Ausdrücke behandelt *Ausdruck* als Assertion mit einer Breite von Null, das heißt, dass die Engine für reguläre Ausdrücke im Eingabestream nicht weitergeführt wird, nachdem sie *Ausdruck* auswertet.</span><span class="sxs-lookup"><span data-stu-id="55ba7-134">The regular expression engine treats *expression* as a zero-width assertion; that is, the regular expression engine does not advance in the input stream after it evaluates *expression*.</span></span> <span data-ttu-id="55ba7-135">Daher entspricht dieses Konstrukt Folgendem:</span><span class="sxs-lookup"><span data-stu-id="55ba7-135">Therefore, this construct is equivalent to the following:</span></span>

<span data-ttu-id="55ba7-136">`(?(?=` *expression* `)` *yes* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="55ba7-136">`(?(?=` *expression* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="55ba7-137">wobei `(?=`*Ausdruck*`)` ein Assertionskonstrukt mit einer Breite von null ist.</span><span class="sxs-lookup"><span data-stu-id="55ba7-137">where `(?=`*expression*`)` is a zero-width assertion construct.</span></span> <span data-ttu-id="55ba7-138">(Weitere Informationen finden Sie unter [Gruppierungskonstrukte](grouping-constructs-in-regular-expressions.md).) Da die Engine für reguläre Ausdrücke *Ausdruck* als Anker (eine Assertion mit einer Breite von null) interpretiert, muss *Ausdruck* entweder eine Assertion mit einer Breite von null (weitere Informationen finden Sie unter [Anker](anchors-in-regular-expressions.md)) oder ein Teilausdruck sein, der auch in *a* enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="55ba7-138">(For more information, see [Grouping Constructs](grouping-constructs-in-regular-expressions.md).) Because the regular expression engine interprets *expression* as an anchor (a zero-width assertion), *expression* must either be a zero-width assertion (for more information, see [Anchors](anchors-in-regular-expressions.md)) or a subexpression that is also contained in *yes*.</span></span> <span data-ttu-id="55ba7-139">Andernfalls kann das Muster *yes* nicht zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="55ba7-139">Otherwise, the *yes* pattern cannot be matched.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55ba7-140">Wenn *expression* eine benannte oder nummerierte Erfassungsgruppe ist, wird das Alternierungskonstrukt als Erfassungstest interpretiert. Weitere Informationen finden Sie im nächsten Abschnitt [Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe](#Conditional_Group).</span><span class="sxs-lookup"><span data-stu-id="55ba7-140">If *expression* is a named or numbered capturing group, the alternation construct is interpreted as a capture test; for more information, see the next section, [Conditional Matching Based on a Valid Capture Group](#Conditional_Group).</span></span> <span data-ttu-id="55ba7-141">Das heißt, dass die Engine für reguläre Ausdrücke nicht versucht, mit der erfassten Teilzeichenfolge übereinzustimmen. Stattdessen wird das Vorhandensein oder Fehlen der Gruppe getestet.</span><span class="sxs-lookup"><span data-stu-id="55ba7-141">In other words, the regular expression engine does not attempt to match the captured substring, but instead tests for the presence or absence of the group.</span></span>  
  
<span data-ttu-id="55ba7-142">Das folgende Beispiel ist eine Abwandlung des Beispiels, das im Abschnitt [Entweder-Oder-Musterabgleich mit &#124;](#Either_Or) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="55ba7-142">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="55ba7-143">Es wird die bedingte Übereinstimmung verwendet, um zu ermitteln, ob die ersten drei Zeichen nach einer Wortgrenze zwei Ziffern gefolgt von einem Bindestrich sind.</span><span class="sxs-lookup"><span data-stu-id="55ba7-143">It uses conditional matching to determine whether the first three characters after a word boundary are two digits followed by a hyphen.</span></span> <span data-ttu-id="55ba7-144">Wenn dies der Fall ist, wird eine Übereinstimmung mit einer Identifikationsnummer des Arbeitgebers in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="55ba7-144">If they are, it attempts to match a U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="55ba7-145">Wenn dies nicht der Fall ist, wird eine Übereinstimmung mit einer Sozialversicherungsnummer in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="55ba7-145">If not, it attempts to match a U.S. Social Security Number (SSN).</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#3](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
[!code-vb[RegularExpressions.Language.Alternation#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]

<span data-ttu-id="55ba7-146">Das Muster für reguläre Ausdrücke `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="55ba7-146">The regular expression pattern `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table:</span></span>

|<span data-ttu-id="55ba7-147">Muster</span><span class="sxs-lookup"><span data-stu-id="55ba7-147">Pattern</span></span>|<span data-ttu-id="55ba7-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55ba7-148">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="55ba7-149">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-149">Start at a word boundary.</span></span>|  
|`(?(\d{2}-)`|<span data-ttu-id="55ba7-150">Bestimmen, ob die nächsten drei Zeichen aus zwei Ziffern gefolgt von einem Bindestrich bestehen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-150">Determine whether the next three characters consist of two digits followed by a hyphen.</span></span>|  
|`\d{2}-\d{7}`|<span data-ttu-id="55ba7-151">Wenn das vorherige Muster übereinstimmt, stimmen zwei Ziffern gefolgt von einem Bindestrich gefolgt von sieben Ziffern überein.</span><span class="sxs-lookup"><span data-stu-id="55ba7-151">If the previous pattern matches, match two digits followed by a hyphen followed by seven digits.</span></span>|  
|`\d{3}-\d{2}-\d{4}`|<span data-ttu-id="55ba7-152">Wenn das vorherige Muster nicht übereinstimmt, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein.</span><span class="sxs-lookup"><span data-stu-id="55ba7-152">If the previous pattern does not match, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="55ba7-153">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="55ba7-153">Match a word boundary.</span></span>|  

<a name="Conditional_Group"></a>

## <a name="conditional-matching-based-on-a-valid-captured-group"></a><span data-ttu-id="55ba7-154">Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe</span><span class="sxs-lookup"><span data-stu-id="55ba7-154">Conditional matching based on a valid captured group</span></span>

<span data-ttu-id="55ba7-155">Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es mit einer angegebenen Erfassungsgruppe übereingestimmt hat.</span><span class="sxs-lookup"><span data-stu-id="55ba7-155">This language element attempts to match one of two patterns depending on whether it has matched a specified capturing group.</span></span> <span data-ttu-id="55ba7-156">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="55ba7-156">Its syntax is:</span></span>

<span data-ttu-id="55ba7-157">`(?(` *name* `)` *yes* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="55ba7-157">`(?(` *name* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="55ba7-158">oder</span><span class="sxs-lookup"><span data-stu-id="55ba7-158">or</span></span>

<span data-ttu-id="55ba7-159">`(?(` *number* `)` *yes* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="55ba7-159">`(?(` *number* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="55ba7-160">, wobei *name* der Name und *number* die Nummer einer Erfassungsgruppe ist. *yes* ist der zu übereinstimmende Ausdruck, wenn *name* oder *number* eine Übereinstimmung aufweist, und *no* ist der optionale zu übereinstimmende Ausdruck, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="55ba7-160">where *name* is the name and *number* is the number of a capturing group, *yes* is the expression to match if *name* or *number* has a match, and *no* is the optional expression to match if it does not.</span></span>

<span data-ttu-id="55ba7-161">Wenn *name* nicht dem Namen einer Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, wird das Alternierungskonstrukt, wie im vorherigen Abschnitt erläutert, als Ausdruckstest interpretiert.</span><span class="sxs-lookup"><span data-stu-id="55ba7-161">If *name* does not correspond to the name of a capturing group that is used in the regular expression pattern, the alternation construct is interpreted as an expression test, as explained in the previous section.</span></span> <span data-ttu-id="55ba7-162">In der Regel bedeutet dies, dass *expression*`false`ergibt.</span><span class="sxs-lookup"><span data-stu-id="55ba7-162">Typically, this means that *expression* evaluates to `false`.</span></span> <span data-ttu-id="55ba7-163">Wenn *number* keiner nummerierten Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, löst die Engine für reguläre Ausdrücke eine <xref:System.ArgumentException> aus.</span><span class="sxs-lookup"><span data-stu-id="55ba7-163">If *number* does not correspond to a numbered capturing group that is used in the regular expression pattern, the regular expression engine throws an <xref:System.ArgumentException>.</span></span>

<span data-ttu-id="55ba7-164">Das folgende Beispiel ist eine Abwandlung des Beispiels, das im Abschnitt [Entweder-Oder-Musterabgleich mit &#124;](#Either_Or) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="55ba7-164">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="55ba7-165">Es wird eine Erfassungsgruppe mit dem Namen `n2` verwendet, die aus zwei Ziffern gefolgt von einem Bindestrich besteht.</span><span class="sxs-lookup"><span data-stu-id="55ba7-165">It uses a capturing group named `n2` that consists of two digits followed by a hyphen.</span></span> <span data-ttu-id="55ba7-166">Das Alternierungskonstrukt testet, ob diese Erfassungsgruppe in der Eingabezeichenfolge abgeglichen wurde.</span><span class="sxs-lookup"><span data-stu-id="55ba7-166">The alternation construct tests whether this capturing group has been matched in the input string.</span></span> <span data-ttu-id="55ba7-167">Wenn dies der Fall ist, versucht das Alternierungskonstrukt, mit den letzten sieben Ziffern einer neunstelligen Identifikationsnummer des Arbeitgebers in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="55ba7-167">If it has, the alternation construct attempts to match the last seven digits of a nine-digit U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="55ba7-168">Wenn dies nicht der Fall ist, versucht es, mit einer neunstelligen Sozialversicherungsnummer in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="55ba7-168">If it has not, it attempts to match a nine-digit U.S. Social Security Number (SSN).</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#4](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
[!code-vb[RegularExpressions.Language.Alternation#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]

<span data-ttu-id="55ba7-169">Das Muster für reguläre Ausdrücke `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="55ba7-169">The regular expression pattern `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table:</span></span>

|<span data-ttu-id="55ba7-170">Muster</span><span class="sxs-lookup"><span data-stu-id="55ba7-170">Pattern</span></span>|<span data-ttu-id="55ba7-171">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55ba7-171">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="55ba7-172">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="55ba7-172">Start at a word boundary.</span></span>|  
|`(?<n2>\d{2}-)?`|<span data-ttu-id="55ba7-173">Entspricht 0 (Null) oder einem Vorkommen von zwei Ziffern gefolgt von einem Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="55ba7-173">Match zero or one occurrence of two digits followed by a hyphen.</span></span> <span data-ttu-id="55ba7-174">Geben Sie für die Erfassungsgruppe `n2` als Namen an.</span><span class="sxs-lookup"><span data-stu-id="55ba7-174">Name this capturing group `n2`.</span></span>|  
|`(?(n2)`|<span data-ttu-id="55ba7-175">Prüfen, ob `n2` in der Eingabezeichenfolge abgeglichen wurde.</span><span class="sxs-lookup"><span data-stu-id="55ba7-175">Test whether `n2` was matched in the input string.</span></span>|  
|`\d{7}`|<span data-ttu-id="55ba7-176">Wenn `n2` abgeglichen wurde, stimmen sieben Dezimalstellen überein.</span><span class="sxs-lookup"><span data-stu-id="55ba7-176">If `n2` was matched, match seven decimal digits.</span></span>|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|<span data-ttu-id="55ba7-177">Wenn `n2` nicht abgeglichen wurde, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein.</span><span class="sxs-lookup"><span data-stu-id="55ba7-177">If `n2` was not matched, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="55ba7-178">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="55ba7-178">Match a word boundary.</span></span>|  

<span data-ttu-id="55ba7-179">Eine Variante dieses Beispiels, die eine nummerierte Gruppe statt einer benannten Gruppe verwendet, wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="55ba7-179">A variation of this example that uses a numbered group instead of a named group is shown in the following example.</span></span> <span data-ttu-id="55ba7-180">Das entsprechende Muster des regulären Ausdrucks lautet `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span><span class="sxs-lookup"><span data-stu-id="55ba7-180">Its regular expression pattern is `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#5](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
[!code-vb[RegularExpressions.Language.Alternation#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]

## <a name="see-also"></a><span data-ttu-id="55ba7-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55ba7-181">See also</span></span>

- [<span data-ttu-id="55ba7-182">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="55ba7-182">Regular Expression Language - Quick Reference</span></span>](regular-expression-language-quick-reference.md)
