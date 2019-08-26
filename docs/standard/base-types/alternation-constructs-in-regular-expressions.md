---
title: Alternierungskonstrukte in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie Alternierungskonstrukte für den bedingten Abgleich in regulären Ausdrücken verwenden können.
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
- .NET Framework regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
author: rpetrusha
ms.author: ronpet
ms.custom: seodec18
ms.openlocfilehash: 560597770d667cf8c7668bf2338ac4bac3eb192f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968573"
---
# <a name="alternation-constructs-in-regular-expressions"></a><span data-ttu-id="c112d-103">Alternierungskonstrukte in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="c112d-103">Alternation Constructs in Regular Expressions</span></span>
<a name="top"></a> <span data-ttu-id="c112d-104">Alternierungskonstrukte ändern einen regulären Ausdruck, um Entweder-Oder-Vergleiche oder eine bedingte Übereinstimmung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="c112d-104">Alternation constructs modify a regular expression to enable either/or or conditional matching.</span></span> <span data-ttu-id="c112d-105">.NET unterstützt drei Alternierungskonstrukte:</span><span class="sxs-lookup"><span data-stu-id="c112d-105">.NET supports three alternation constructs:</span></span>  
  
- [<span data-ttu-id="c112d-106">Musterabgleich mit &#124;</span><span class="sxs-lookup"><span data-stu-id="c112d-106">Pattern matching with &#124;</span></span>](#Either_Or)  
  
- [<span data-ttu-id="c112d-107">Bedingte Übereinstimmung mit (?(Ausdruck)ja&#124;nein)</span><span class="sxs-lookup"><span data-stu-id="c112d-107">Conditional matching with (?(expression)yes&#124;no)</span></span>](#Conditional_Expr)  
  
- [<span data-ttu-id="c112d-108">Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe</span><span class="sxs-lookup"><span data-stu-id="c112d-108">Conditional matching based on a valid captured group</span></span>](#Conditional_Group)  
  
<a name="Either_Or"></a>   
## <a name="pattern-matching-with-124"></a><span data-ttu-id="c112d-109">Musterabgleich mit &#124;</span><span class="sxs-lookup"><span data-stu-id="c112d-109">Pattern Matching with &#124;</span></span>  
 <span data-ttu-id="c112d-110">Sie können das vertikale Balkenzeichen (`|`) für Vergleiche mit einem oder mehreren aus einer Reihe von Mustern verwenden, wobei das `|`-Zeichen als Trennzeichen für die einzelnen Muster dient.</span><span class="sxs-lookup"><span data-stu-id="c112d-110">You can use the vertical bar (`|`) character to match any one of a series of patterns, where the `|` character separates each pattern.</span></span>  
  
 <span data-ttu-id="c112d-111">Wie bei der positiven Zeichenklasse kann das `|` -Zeichen für Vergleiche mit jedem beliebigen Zeichen aus einer Reihe einzelner Zeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c112d-111">Like the positive character class, the `|` character can be used to match any one of a number of single characters.</span></span> <span data-ttu-id="c112d-112">Im folgenden Beispiel wird sowohl eine positive Zeichenklasse als auch ein Entweder-Oder-Mustervergleich mithilfe des `|` -Zeichens verwendet, um Vorkommen der Wörter „gray“ oder „grau“ in einer Zeichenfolge zu finden.</span><span class="sxs-lookup"><span data-stu-id="c112d-112">The following example uses both a positive character class and either/or pattern matching with the `|` character to locate occurrences of the words "gray" or "grey" in a string.</span></span> <span data-ttu-id="c112d-113">In diesem Fall ergibt das `|` -Zeichen einen regulären Ausdruck, der eine ausführlichere Ausgabe bewirkt.</span><span class="sxs-lookup"><span data-stu-id="c112d-113">In this case, the `|` character produces a regular expression that is more verbose.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
 [!code-vb[RegularExpressions.Language.Alternation#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]  
  
 <span data-ttu-id="c112d-114">Der reguläre Ausdruck, der das `|` -Zeichen verwendet, `\bgr(a|e)y\b`, wird wie in der folgenden Tabelle dargestellt interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c112d-114">The regular expression that uses the `|` character, `\bgr(a|e)y\b`, is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c112d-115">Muster</span><span class="sxs-lookup"><span data-stu-id="c112d-115">Pattern</span></span>|<span data-ttu-id="c112d-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c112d-116">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c112d-117">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="c112d-117">Start at a word boundary.</span></span>|  
|`gr`|<span data-ttu-id="c112d-118">Übereinstimmung mit den Zeichen "gr".</span><span class="sxs-lookup"><span data-stu-id="c112d-118">Match the characters "gr".</span></span>|  
|<code>(a&#124;e)</code>|<span data-ttu-id="c112d-119">Übereinstimmung mit entweder "a" oder "e".</span><span class="sxs-lookup"><span data-stu-id="c112d-119">Match either an "a" or an "e".</span></span>|  
|`y\b`|<span data-ttu-id="c112d-120">Übereinstimmung mit "y" an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="c112d-120">Match a "y" on a word boundary.</span></span>|  
  
 <span data-ttu-id="c112d-121">Das `|`-Zeichen kann auch verwendet werden, um einen Entweder-Oder-Vergleich mit mehreren Zeichen oder Teilausdrücken durchzuführen, wobei eine beliebige Kombination von Zeichenliteralen und Sprachelementen für reguläre Ausdrücke enthalten sein kann.</span><span class="sxs-lookup"><span data-stu-id="c112d-121">The `|` character can also be used to perform an either/or match with multiple characters or subexpressions, which can include any combination of character literals and regular expression language elements.</span></span> <span data-ttu-id="c112d-122">(Die Zeichenklasse stellt diese Funktionalität nicht bereit.) Im folgenden Beispiel wird das `|`-Zeichen verwendet, um entweder eine Sozialversicherungsnummer in den USA, also eine neunstellige Zahl mit dem Format *ddd*-*dd*-*dddd*, oder eine Identifikationsnummer des Arbeitgebers in den USA (EIN, Employer Identification Number), also eine neunstellige Zahl mit dem Format *dd*-*ddddddd* zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="c112d-122">(The character class does not provide this functionality.) The following example uses the `|` character to extract either a U.S. Social Security Number (SSN), which is a 9-digit number with the format *ddd*-*dd*-*dddd*, or a U.S. Employer Identification Number (EIN), which is a 9-digit number with the format *dd*-*ddddddd*.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
 [!code-vb[RegularExpressions.Language.Alternation#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  
  
 <span data-ttu-id="c112d-123">Der reguläre Ausdruck `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c112d-123">The regular expression `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c112d-124">Muster</span><span class="sxs-lookup"><span data-stu-id="c112d-124">Pattern</span></span>|<span data-ttu-id="c112d-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c112d-125">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c112d-126">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="c112d-126">Start at a word boundary.</span></span>|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|<span data-ttu-id="c112d-127">Eine der folgenden Varianten muss übereinstimmen: zwei Dezimalstellen gefolgt von einem Bindestrich gefolgt von sieben Dezimalstellen; oder drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="c112d-127">Match either of the following: two decimal digits followed by a hyphen followed by seven decimal digits; or three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\d`|<span data-ttu-id="c112d-128">Der Vergleich endet an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="c112d-128">End the match at a word boundary.</span></span>|  
  
 [<span data-ttu-id="c112d-129">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="c112d-129">Back to top</span></span>](#top)  
  
<a name="Conditional_Expr"></a>   
## <a name="conditional-matching-with-an-expression"></a><span data-ttu-id="c112d-130">Bedingte Übereinstimmung mit einem Ausdruck</span><span class="sxs-lookup"><span data-stu-id="c112d-130">Conditional Matching with an Expression</span></span>  
 <span data-ttu-id="c112d-131">Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es ein ursprüngliches Muster zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="c112d-131">This language element attempts to match one of two patterns depending on whether it can match an initial pattern.</span></span> <span data-ttu-id="c112d-132">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="c112d-132">Its syntax is:</span></span>  
  
 <span data-ttu-id="c112d-133">`(?(` *Ausdruck* `)` *ja* `|` *nein* `)`</span><span class="sxs-lookup"><span data-stu-id="c112d-133">`(?(` *expression* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="c112d-134">wobei *expression* das ursprüngliche zu enstprechende Muster ist. *yes* ist das entsprechende Muster, wenn *expression* zugeordnet ist, und *no* ist das entsprechende optionale Muster, wenn *expression* nicht übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c112d-134">where *expression* is the initial pattern to match, *yes* is the pattern to match if *expression* is matched, and *no* is the optional pattern to match if *expression* is not matched.</span></span> <span data-ttu-id="c112d-135">Die Engine für reguläre Ausdrücke behandelt *Ausdruck* als Assertion mit einer Breite von Null, das heißt, dass die Engine für reguläre Ausdrücke im Eingabestream nicht weitergeführt wird, nachdem sie *Ausdruck* auswertet.</span><span class="sxs-lookup"><span data-stu-id="c112d-135">The regular expression engine treats *expression* as a zero-width assertion; that is, the regular expression engine does not advance in the input stream after it evaluates *expression*.</span></span> <span data-ttu-id="c112d-136">Daher entspricht dieses Konstrukt Folgendem:</span><span class="sxs-lookup"><span data-stu-id="c112d-136">Therefore, this construct is equivalent to the following:</span></span>  
  
 <span data-ttu-id="c112d-137">`(?(?=` *expression* `)` *ja* `|` *nein* `)`</span><span class="sxs-lookup"><span data-stu-id="c112d-137">`(?(?=` *expression* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="c112d-138">wobei `(?=`*Ausdruck*`)` ein Assertionskonstrukt mit einer Breite von null ist.</span><span class="sxs-lookup"><span data-stu-id="c112d-138">where `(?=`*expression*`)` is a zero-width assertion construct.</span></span> <span data-ttu-id="c112d-139">(Weitere Informationen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).) Da die Engine für reguläre Ausdrücke *Ausdruck* als Anker (eine Assertion mit einer Breite von null) interpretiert, muss *Ausdruck* entweder eine Assertion mit einer Breite von null (weitere Informationen finden Sie unter [Anker](../../../docs/standard/base-types/anchors-in-regular-expressions.md)) oder ein Teilausdruck sein, der auch in *a* enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c112d-139">(For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).) Because the regular expression engine interprets *expression* as an anchor (a zero-width assertion), *expression* must either be a zero-width assertion (for more information, see [Anchors](../../../docs/standard/base-types/anchors-in-regular-expressions.md)) or a subexpression that is also contained in *yes*.</span></span> <span data-ttu-id="c112d-140">Andernfalls kann das Muster *ja* nicht zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c112d-140">Otherwise, the *yes* pattern cannot be matched.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c112d-141">Wenn *expression*eine benannte oder nummerierte Erfassungsgruppe ist, wird das Alternierungskonstrukt als Erfassungstest interpretiert. Weitere Informationen finden Sie im nächsten Abschnitt [Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe](#Conditional_Group).</span><span class="sxs-lookup"><span data-stu-id="c112d-141">If *expression*is a named or numbered capturing group, the alternation construct is interpreted as a capture test; for more information, see the next section, [Conditional Matching Based on a Valid Capture Group](#Conditional_Group).</span></span> <span data-ttu-id="c112d-142">Das heißt, dass die Engine für reguläre Ausdrücke nicht versucht, mit der erfassten Teilzeichenfolge übereinzustimmen. Stattdessen wird das Vorhandensein oder Fehlen der Gruppe getestet.</span><span class="sxs-lookup"><span data-stu-id="c112d-142">In other words, the regular expression engine does not attempt to match the captured substring, but instead tests for the presence or absence of the group.</span></span>  
  
 <span data-ttu-id="c112d-143">Das folgende Beispiel ist eine Abwandlung des Beispiels, das im Abschnitt [Entweder-Oder-Musterabgleich mit &#124;](#Either_Or) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c112d-143">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="c112d-144">Es wird die bedingte Übereinstimmung verwendet, um zu ermitteln, ob die ersten drei Zeichen nach einer Wortgrenze zwei Ziffern gefolgt von einem Bindestrich sind.</span><span class="sxs-lookup"><span data-stu-id="c112d-144">It uses conditional matching to determine whether the first three characters after a word boundary are two digits followed by a hyphen.</span></span> <span data-ttu-id="c112d-145">Wenn dies der Fall ist, wird eine Übereinstimmung mit einer Identifikationsnummer des Arbeitgebers in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="c112d-145">If they are, it attempts to match a U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="c112d-146">Wenn dies nicht der Fall ist, wird eine Übereinstimmung mit einer Sozialversicherungsnummer in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="c112d-146">If not, it attempts to match a U.S. Social Security Number (SSN).</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
 [!code-vb[RegularExpressions.Language.Alternation#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]  
  
 <span data-ttu-id="c112d-147">Das Muster für reguläre Ausdrücke `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="c112d-147">The regular expression pattern `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c112d-148">Muster</span><span class="sxs-lookup"><span data-stu-id="c112d-148">Pattern</span></span>|<span data-ttu-id="c112d-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c112d-149">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c112d-150">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="c112d-150">Start at a word boundary.</span></span>|  
|`(?(\d{2}-)`|<span data-ttu-id="c112d-151">Bestimmen, ob die nächsten drei Zeichen aus zwei Ziffern gefolgt von einem Bindestrich bestehen.</span><span class="sxs-lookup"><span data-stu-id="c112d-151">Determine whether the next three characters consist of two digits followed by a hyphen.</span></span>|  
|`\d{2}-\d{7}`|<span data-ttu-id="c112d-152">Wenn das vorherige Muster übereinstimmt, stimmen zwei Ziffern gefolgt von einem Bindestrich gefolgt von sieben Ziffern überein.</span><span class="sxs-lookup"><span data-stu-id="c112d-152">If the previous pattern matches, match two digits followed by a hyphen followed by seven digits.</span></span>|  
|`\d{3}-\d{2}-\d{4}`|<span data-ttu-id="c112d-153">Wenn das vorherige Muster nicht übereinstimmt, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein.</span><span class="sxs-lookup"><span data-stu-id="c112d-153">If the previous pattern does not match, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="c112d-154">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="c112d-154">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="c112d-155">Zurück nach oben</span><span class="sxs-lookup"><span data-stu-id="c112d-155">Back to top</span></span>](#top)  
  
<a name="Conditional_Group"></a>   
## <a name="conditional-matching-based-on-a-valid-captured-group"></a><span data-ttu-id="c112d-156">Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe</span><span class="sxs-lookup"><span data-stu-id="c112d-156">Conditional Matching Based on a Valid Captured Group</span></span>  
 <span data-ttu-id="c112d-157">Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es mit einer angegebenen Erfassungsgruppe übereingestimmt hat.</span><span class="sxs-lookup"><span data-stu-id="c112d-157">This language element attempts to match one of two patterns depending on whether it has matched a specified capturing group.</span></span> <span data-ttu-id="c112d-158">Die Syntax lautet:</span><span class="sxs-lookup"><span data-stu-id="c112d-158">Its syntax is:</span></span>  
  
 <span data-ttu-id="c112d-159">`(?(` *Name* `)` *ja* `|` *nein* `)`</span><span class="sxs-lookup"><span data-stu-id="c112d-159">`(?(` *name* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="c112d-160">oder</span><span class="sxs-lookup"><span data-stu-id="c112d-160">or</span></span>  
  
 <span data-ttu-id="c112d-161">`(?(` *number* `)` *ja* `|` *nein* `)`</span><span class="sxs-lookup"><span data-stu-id="c112d-161">`(?(` *number* `)` *yes* `|` *no* `)`</span></span>  
  
 <span data-ttu-id="c112d-162">, wobei *name* der Name und *number* die Nummer einer Erfassungsgruppe ist. *yes* ist der zu übereinstimmende Ausdruck, wenn *name* oder *number* eine Übereinstimmung aufweist, und *no* ist der optionale zu übereinstimmende Ausdruck, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="c112d-162">where *name* is the name and *number* is the number of a capturing group, *yes* is the expression to match if *name* or *number* has a match, and *no* is the optional expression to match if it does not.</span></span>  
  
 <span data-ttu-id="c112d-163">Wenn *name* nicht dem Namen einer Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, wird das Alternierungskonstrukt, wie im vorherigen Abschnitt erläutert, als Ausdruckstest interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c112d-163">If *name* does not correspond to the name of a capturing group that is used in the regular expression pattern, the alternation construct is interpreted as an expression test, as explained in the previous section.</span></span> <span data-ttu-id="c112d-164">In der Regel bedeutet dies, dass *expression* `false`ergibt.</span><span class="sxs-lookup"><span data-stu-id="c112d-164">Typically, this means that *expression* evaluates to `false`.</span></span> <span data-ttu-id="c112d-165">Wenn *number* keiner nummerierten Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, löst die Engine für reguläre Ausdrücke eine <xref:System.ArgumentException> aus.</span><span class="sxs-lookup"><span data-stu-id="c112d-165">If *number* does not correspond to a numbered capturing group that is used in the regular expression pattern, the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="c112d-166">Das folgende Beispiel ist eine Abwandlung des Beispiels, das im Abschnitt [Entweder-Oder-Musterabgleich mit &#124;](#Either_Or) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c112d-166">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="c112d-167">Es wird eine Erfassungsgruppe mit dem Namen `n2` verwendet, die aus zwei Ziffern gefolgt von einem Bindestrich besteht.</span><span class="sxs-lookup"><span data-stu-id="c112d-167">It uses a capturing group named `n2` that consists of two digits followed by a hyphen.</span></span> <span data-ttu-id="c112d-168">Das Alternierungskonstrukt testet, ob diese Erfassungsgruppe in der Eingabezeichenfolge abgeglichen wurde.</span><span class="sxs-lookup"><span data-stu-id="c112d-168">The alternation construct tests whether this capturing group has been matched in the input string.</span></span> <span data-ttu-id="c112d-169">Wenn dies der Fall ist, versucht das Alternierungskonstrukt, mit den letzten sieben Ziffern einer neunstelligen Identifikationsnummer des Arbeitgebers in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="c112d-169">If it has, the alternation construct attempts to match the last seven digits of a nine-digit U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="c112d-170">Wenn dies nicht der Fall ist, versucht es, mit einer neunstelligen Sozialversicherungsnummer in den USA versucht.</span><span class="sxs-lookup"><span data-stu-id="c112d-170">If it has not, it attempts to match a nine-digit U.S. Social Security Number (SSN).</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
 [!code-vb[RegularExpressions.Language.Alternation#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]  
  
 <span data-ttu-id="c112d-171">Das Muster für reguläre Ausdrücke `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="c112d-171">The regular expression pattern `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="c112d-172">Muster</span><span class="sxs-lookup"><span data-stu-id="c112d-172">Pattern</span></span>|<span data-ttu-id="c112d-173">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c112d-173">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="c112d-174">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="c112d-174">Start at a word boundary.</span></span>|  
|`(?<n2>\d{2}-)?`|<span data-ttu-id="c112d-175">Entspricht 0 (Null) oder einem Vorkommen von zwei Ziffern gefolgt von einem Bindestrich.</span><span class="sxs-lookup"><span data-stu-id="c112d-175">Match zero or one occurrence of two digits followed by a hyphen.</span></span> <span data-ttu-id="c112d-176">Geben Sie für die Erfassungsgruppe `n2`als Namen an.</span><span class="sxs-lookup"><span data-stu-id="c112d-176">Name this capturing group `n2`.</span></span>|  
|`(?(n2)`|<span data-ttu-id="c112d-177">Prüfen, ob `n2` in der Eingabezeichenfolge abgeglichen wurde.</span><span class="sxs-lookup"><span data-stu-id="c112d-177">Test whether `n2` was matched in the input string.</span></span>|  
|`\d{7}`|<span data-ttu-id="c112d-178">Wenn `n2` abgeglichen wurde, stimmen sieben Dezimalstellen überein.</span><span class="sxs-lookup"><span data-stu-id="c112d-178">If `n2` was matched, match seven decimal digits.</span></span>|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|<span data-ttu-id="c112d-179">Wenn `n2` nicht abgeglichen wurde, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein.</span><span class="sxs-lookup"><span data-stu-id="c112d-179">If `n2` was not matched, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="c112d-180">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="c112d-180">Match a word boundary.</span></span>|  
  
 <span data-ttu-id="c112d-181">Eine Variante dieses Beispiels, die eine nummerierte Gruppe statt einer benannten Gruppe verwendet, wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c112d-181">A variation of this example that uses a numbered group instead of a named group is shown in the following example.</span></span> <span data-ttu-id="c112d-182">Das entsprechende Muster des regulären Ausdrucks lautet `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span><span class="sxs-lookup"><span data-stu-id="c112d-182">Its regular expression pattern is `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Alternation#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
 [!code-vb[RegularExpressions.Language.Alternation#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c112d-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c112d-183">See also</span></span>

- [<span data-ttu-id="c112d-184">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="c112d-184">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
