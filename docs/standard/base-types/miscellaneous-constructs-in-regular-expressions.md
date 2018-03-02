---
title: "Verschiedene Konstrukte in regulären Ausdrücken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7a7c577c617ca8f40d64548f9f0f2d103c5887e1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a><span data-ttu-id="81aef-102">Verschiedene Konstrukte in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="81aef-102">Miscellaneous Constructs in Regular Expressions</span></span>
<span data-ttu-id="81aef-103">Reguläre Ausdrücke in .NET umfassen drei verschiedene Sprachkonstrukte.</span><span class="sxs-lookup"><span data-stu-id="81aef-103">Regular expressions in .NET include three miscellaneous language constructs.</span></span> <span data-ttu-id="81aef-104">Einer ermöglicht Ihnen das Aktivieren oder Deaktivieren bestimmter Vergleichsoptionen mitten in einem Muster für reguläre Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="81aef-104">One lets you enable or disable particular matching options in the middle of a regular expression pattern.</span></span> <span data-ttu-id="81aef-105">Mithilfe der beiden anderen können Sie Kommentare in einen regulären Ausdruck aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="81aef-105">The remaining two let you include comments in a regular expression.</span></span>  
  
## <a name="inline-options"></a><span data-ttu-id="81aef-106">Inlineoptionen</span><span class="sxs-lookup"><span data-stu-id="81aef-106">Inline Options</span></span>  
 <span data-ttu-id="81aef-107">Sie können bestimmte Mustervergleichsoptionen für einen Teil eines regulären Ausdrucks festlegen oder deaktivieren. Verwenden Sie dazu folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="81aef-107">You can set or disable specific pattern matching options for part of a regular expression by using the syntax</span></span>  
  
```  
(?imnsx-imnsx)  
```  
  
 <span data-ttu-id="81aef-108">Die Optionen, die Sie aktivieren möchten, werden nach dem Fragezeichen aufgeführt, und die Optionen, die Sie deaktivieren möchten, werden nach dem Minuszeichen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="81aef-108">You list the options you want to enable after the question mark, and the options you want to disable after the minus sign.</span></span> <span data-ttu-id="81aef-109">In der folgenden Tabelle sind die einzelnen Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81aef-109">The following table describes each option.</span></span> <span data-ttu-id="81aef-110">Weitere Informationen zu den einzelnen Optionen finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).</span><span class="sxs-lookup"><span data-stu-id="81aef-110">For more information about each option, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
|<span data-ttu-id="81aef-111">Option</span><span class="sxs-lookup"><span data-stu-id="81aef-111">Option</span></span>|<span data-ttu-id="81aef-112">description</span><span class="sxs-lookup"><span data-stu-id="81aef-112">Description</span></span>|  
|------------|-----------------|  
|`i`|<span data-ttu-id="81aef-113">Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="81aef-113">Case-insensitive matching.</span></span>|  
|`m`|<span data-ttu-id="81aef-114">Mehrzeilenmodus.</span><span class="sxs-lookup"><span data-stu-id="81aef-114">Multiline mode.</span></span>|  
|`n`|<span data-ttu-id="81aef-115">Nur explizite Erfassungen.</span><span class="sxs-lookup"><span data-stu-id="81aef-115">Explicit captures only.</span></span> <span data-ttu-id="81aef-116">(Klammern fungieren nicht als Erfassungsgruppen.)</span><span class="sxs-lookup"><span data-stu-id="81aef-116">(Parentheses do not act as capturing groups.)</span></span>|  
|`s`|<span data-ttu-id="81aef-117">Einzeilenmodus.</span><span class="sxs-lookup"><span data-stu-id="81aef-117">Single-line mode.</span></span>|  
|`x`|<span data-ttu-id="81aef-118">Leerzeichen ohne Escapezeichen ignorieren und Kommentare im x-Modus zulassen.</span><span class="sxs-lookup"><span data-stu-id="81aef-118">Ignore unescaped white space, and allow x-mode comments.</span></span>|  
  
 <span data-ttu-id="81aef-119">Alle Änderungen in Optionen für reguläre Ausdrücke, die über das Konstrukt `(?imnsx-imnsx)` definiert werden, bleiben bis zum Ende der einschließenden Gruppe gültig.</span><span class="sxs-lookup"><span data-stu-id="81aef-119">Any change in regular expression options defined by the `(?imnsx-imnsx)` construct remains in effect until the end of the enclosing group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81aef-120">Das Gruppierungskonstrukt `(?imnsx-imnsx:`*subexpression*`)` bietet identische Funktionen für einen Teilausdruck.</span><span class="sxs-lookup"><span data-stu-id="81aef-120">The `(?imnsx-imnsx:`*subexpression*`)` grouping construct provides identical functionality for a subexpression.</span></span> <span data-ttu-id="81aef-121">Weitere Informationen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="81aef-121">For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="81aef-122">Im folgenden Beispiel werden die Optionen `i`, `n` und `x` verwendet, um die Groß-/Kleinschreibung zu ignorieren, explizite Erfassungen zu ermöglichen und Leerzeichen im Muster für reguläre Ausdrücke in der Mitte eines regulären Ausdrucks zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="81aef-122">The following example uses the `i`, `n`, and `x` options to enable case insensitivity and explicit captures, and to ignore white space in the regular expression pattern in the middle of a regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 <span data-ttu-id="81aef-123">Im Beispiel werden zwei reguläre Ausdrücke definiert.</span><span class="sxs-lookup"><span data-stu-id="81aef-123">The example defines two regular expressions.</span></span> <span data-ttu-id="81aef-124">Der erste, `\b(D\w+)\s(d\w+)\b`, entspricht zwei aufeinander folgenden Wörtern, die mit dem Großbuchstaben „D“ und dem Kleinbuchstaben „d“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="81aef-124">The first, `\b(D\w+)\s(d\w+)\b`, matches two consecutive words that begin with an uppercase "D" and a lowercase "d".</span></span> <span data-ttu-id="81aef-125">Der zweite reguläre Ausdruck, `\b(D\w+)(?ixn) \s (d\w+) \b`, verwendet Inlineoptionen, um dieses Muster entsprechend der folgenden Tabelle zu ändern.</span><span class="sxs-lookup"><span data-stu-id="81aef-125">The second regular expression, `\b(D\w+)(?ixn) \s (d\w+) \b`, uses inline options to modify this pattern, as described in the following table.</span></span> <span data-ttu-id="81aef-126">Ein Vergleich der Ergebnisse bestätigt den Effekt des `(?ixn)`-Konstrukts.</span><span class="sxs-lookup"><span data-stu-id="81aef-126">A comparison of the results confirms the effect of the `(?ixn)` construct.</span></span>  
  
|<span data-ttu-id="81aef-127">Muster</span><span class="sxs-lookup"><span data-stu-id="81aef-127">Pattern</span></span>|<span data-ttu-id="81aef-128">description</span><span class="sxs-lookup"><span data-stu-id="81aef-128">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="81aef-129">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="81aef-129">Start at a word boundary.</span></span>|  
|`(D\w+)`|<span data-ttu-id="81aef-130">Übereinstimmung mit dem Großbuchstaben „D“, gefolgt von einem oder mehreren Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="81aef-130">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="81aef-131">Dies ist die erste Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="81aef-131">This is the first capture group.</span></span>|  
|`(?ixn)`|<span data-ttu-id="81aef-132">Ab diesem Punkt werden Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung und nur explizite Erfassungen durchgeführt sowie Leerzeichen im Muster für reguläre Ausdrücke ignoriert.</span><span class="sxs-lookup"><span data-stu-id="81aef-132">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`\s`|<span data-ttu-id="81aef-133">Entsprechung für ein Leerraumzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="81aef-133">Match a white-space character.</span></span>|  
|`(d\w+)`|<span data-ttu-id="81aef-134">Übereinstimmung mit dem Groß- oder Kleinbuchstaben „d“, gefolgt von mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="81aef-134">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="81aef-135">Diese Gruppe wird nicht erfasst, da die Option `n` (explizite Erfassung) aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="81aef-135">This group is not captured because the `n` (explicit capture) option was enabled..</span></span>|  
|`\b`|<span data-ttu-id="81aef-136">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="81aef-136">Match a word boundary.</span></span>|  
  
## <a name="inline-comment"></a><span data-ttu-id="81aef-137">Inlinekommentar</span><span class="sxs-lookup"><span data-stu-id="81aef-137">Inline Comment</span></span>  
 <span data-ttu-id="81aef-138">Das Konstrukt `(?#` *comment*`)` ermöglicht das Einfügen eines Inlinekommentars in einen regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="81aef-138">The `(?#` *comment*`)` construct lets you include an inline comment in a regular expression.</span></span> <span data-ttu-id="81aef-139">Die Engine für reguläre Ausdrücke verwendet keinen Teil des Kommentars beim Musterabgleich, obwohl der Kommentar in der von der Methode <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> zurückgegebenen Zeichenfolge enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="81aef-139">The regular expression engine does not use any part of the comment in pattern matching, although the comment is included in the string that is returned by the <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="81aef-140">Der Kommentar endet bei der ersten schließenden Klammer.</span><span class="sxs-lookup"><span data-stu-id="81aef-140">The comment ends at the first closing parenthesis.</span></span>  
  
 <span data-ttu-id="81aef-141">Im folgenden Beispiel wird das erste Muster für reguläre Ausdrücke aus dem Beispiel im vorherigen Abschnitt wiederholt.</span><span class="sxs-lookup"><span data-stu-id="81aef-141">The following example repeats the first regular expression pattern from the example in the previous section.</span></span> <span data-ttu-id="81aef-142">Dem regulären Ausdruck werden zwei Inlinekommentare hinzugefügt, um anzugeben, ob beim Vergleich die Groß-/Kleinschreibung berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="81aef-142">It adds two inline comments to the regular expression to indicate whether the comparison is case-sensitive.</span></span> <span data-ttu-id="81aef-143">Das Muster für reguläre Ausdrücke, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, ist wie folgt definiert.</span><span class="sxs-lookup"><span data-stu-id="81aef-143">The regular expression pattern, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, is defined as follows.</span></span>  
  
|<span data-ttu-id="81aef-144">Muster</span><span class="sxs-lookup"><span data-stu-id="81aef-144">Pattern</span></span>|<span data-ttu-id="81aef-145">description</span><span class="sxs-lookup"><span data-stu-id="81aef-145">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="81aef-146">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="81aef-146">Start at a word boundary.</span></span>|  
|`(?# case-sensitive comparison)`|<span data-ttu-id="81aef-147">Ein Kommentar.</span><span class="sxs-lookup"><span data-stu-id="81aef-147">A comment.</span></span> <span data-ttu-id="81aef-148">Dieser wirkt sich nicht auf das Verhalten des Mustervergleichs aus.</span><span class="sxs-lookup"><span data-stu-id="81aef-148">It does not affect pattern-matching behavior.</span></span>|  
|`(D\w+)`|<span data-ttu-id="81aef-149">Übereinstimmung mit dem Großbuchstaben „D“, gefolgt von einem oder mehreren Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="81aef-149">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="81aef-150">Dies ist die erste Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="81aef-150">This is the first capturing group.</span></span>|  
|`\s`|<span data-ttu-id="81aef-151">Entsprechung für ein Leerraumzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="81aef-151">Match a white-space character.</span></span>|  
|`(?ixn)`|<span data-ttu-id="81aef-152">Ab diesem Punkt werden Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung und nur explizite Erfassungen durchgeführt sowie Leerzeichen im Muster für reguläre Ausdrücke ignoriert.</span><span class="sxs-lookup"><span data-stu-id="81aef-152">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`(?#case-insensitive comparison)`|<span data-ttu-id="81aef-153">Ein Kommentar.</span><span class="sxs-lookup"><span data-stu-id="81aef-153">A comment.</span></span> <span data-ttu-id="81aef-154">Dieser wirkt sich nicht auf das Verhalten des Mustervergleichs aus.</span><span class="sxs-lookup"><span data-stu-id="81aef-154">It does not affect pattern-matching behavior.</span></span>|  
|`(d\w+)`|<span data-ttu-id="81aef-155">Übereinstimmung mit dem Groß- oder Kleinbuchstaben „d“, gefolgt von mindestens einem Wortzeichen.</span><span class="sxs-lookup"><span data-stu-id="81aef-155">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="81aef-156">Dies ist die zweite Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="81aef-156">This is the second capture group.</span></span>|  
|`\b`|<span data-ttu-id="81aef-157">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="81aef-157">Match a word boundary.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a><span data-ttu-id="81aef-158">Zeilenendekommentar</span><span class="sxs-lookup"><span data-stu-id="81aef-158">End-of-Line Comment</span></span>  
 <span data-ttu-id="81aef-159">Ein Nummernzeichen (`#`) markiert einen x-Modus-Kommentar, der bei dem nicht durch Escapezeichen formatierten #-Zeichen am Ende des Musters für reguläre Ausdrücke beginnt und bis zum Zeilenende fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="81aef-159">A number sign (`#`)marks an x-mode comment, which starts at the unescaped # character at the end of the regular expression pattern and continues until the end of the line.</span></span> <span data-ttu-id="81aef-160">Um dieses Konstrukt zu verwenden, müssen Sie entweder die `x`-Option (durch Inlineoptionen) aktivieren oder beim Instanziieren des <xref:System.Text.RegularExpressions.Regex>-Objekts bzw. beim Aufrufen einer statischen <xref:System.Text.RegularExpressions.Regex>-Methode den Wert <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> an den `option`-Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="81aef-160">To use this construct, you must either enable the `x` option (through inline options) or supply the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> value to the `option` parameter when instantiating the <xref:System.Text.RegularExpressions.Regex> object or calling a static <xref:System.Text.RegularExpressions.Regex> method.</span></span>  
  
 <span data-ttu-id="81aef-161">Das folgende Beispiel veranschaulicht das Konstrukt für Zeilenendekommentare.</span><span class="sxs-lookup"><span data-stu-id="81aef-161">The following example illustrates the end-of-line comment construct.</span></span> <span data-ttu-id="81aef-162">Dabei wird bestimmt, ob es sich bei einer Zeichenfolge um eine zusammengesetzte Formatzeichenfolge handelt, die mindestens ein Formatelement einschließt.</span><span class="sxs-lookup"><span data-stu-id="81aef-162">It determines whether a string is a composite format string that includes at least one format item.</span></span> <span data-ttu-id="81aef-163">Die folgende Tabelle beschreibt die Konstrukte im Muster für reguläre Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="81aef-163">The following table describes the constructs in the regular expression pattern:</span></span>  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|<span data-ttu-id="81aef-164">Muster</span><span class="sxs-lookup"><span data-stu-id="81aef-164">Pattern</span></span>|<span data-ttu-id="81aef-165">description</span><span class="sxs-lookup"><span data-stu-id="81aef-165">Description</span></span>|  
|-------------|-----------------|  
|`\{`|<span data-ttu-id="81aef-166">Übereinstimmung mit einer öffnenden geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="81aef-166">Match an opening brace.</span></span>|  
|`\d+`|<span data-ttu-id="81aef-167">Entsprechung für mindestens eine Dezimalstelle finden.</span><span class="sxs-lookup"><span data-stu-id="81aef-167">Match one or more decimal digits.</span></span>|  
|`(,-*\d+)*`|<span data-ttu-id="81aef-168">Übereinstimmung mit keinem oder einem Vorkommen eines Kommas, gefolgt von einem optionalen Minuszeichen, gefolgt von mindestens einer Dezimalzahl.</span><span class="sxs-lookup"><span data-stu-id="81aef-168">Match zero or one occurrence of a comma, followed by an optional minus sign, followed by one or more decimal digits.</span></span>|  
|`(\:\w{1,4}?)*`|<span data-ttu-id="81aef-169">Übereinstimmung mit keinem oder einem Doppelpunkt, gefolgt von einem bis vier Leerzeichen (jedoch so wenigen wie möglich).</span><span class="sxs-lookup"><span data-stu-id="81aef-169">Match zero or one occurrence of a colon, followed by one to four, but as few as possible, white-space characters.</span></span>|  
|`(?#case insensitive comparison)`|<span data-ttu-id="81aef-170">Ein Inlinekommentar.</span><span class="sxs-lookup"><span data-stu-id="81aef-170">An inline comment.</span></span> <span data-ttu-id="81aef-171">Wirkt sich nicht auf das Verhalten zum Musterabgleich aus.</span><span class="sxs-lookup"><span data-stu-id="81aef-171">It has no effect on pattern-matching behavior.</span></span>|  
|`\}`|<span data-ttu-id="81aef-172">Übereinstimmung mit einer schließenden geschweiften Klammer.</span><span class="sxs-lookup"><span data-stu-id="81aef-172">Match a closing brace.</span></span>|  
|`(?x)`|<span data-ttu-id="81aef-173">Aktivieren der Option zum Ignorieren von Leerzeichen im Muster, sodass der Zeilenendekommentar erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="81aef-173">Enable the ignore pattern white-space option so that the end-of-line comment will be recognized.</span></span>|  
|`# Looks for a composite format item.`|<span data-ttu-id="81aef-174">Ein Zeilenendekommentar.</span><span class="sxs-lookup"><span data-stu-id="81aef-174">An end-of-line comment.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 <span data-ttu-id="81aef-175">Anstelle der Bereitstellung des `(?x)`-Konstrukts im regulären Ausdruck hätte der Kommentar auch erkannt werden können, indem die <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>-Methode aufgerufen und der <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>-Enumerationswert übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="81aef-175">Note that, instead of providing the `(?x)` construct in the regular expression, the comment could also have been recognized by calling the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method and passing it the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> enumeration value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aef-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81aef-176">See Also</span></span>  
 [<span data-ttu-id="81aef-177">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="81aef-177">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
