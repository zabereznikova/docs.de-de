---
title: "Rückverweiskonstrukte in regulären Ausdrücken"
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
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a884e70f542c2ed7ff63e39cb7eadedf0ef7b4d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="11426-102">Rückverweiskonstrukte in regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="11426-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="11426-103">Rückverweise bieten eine einfache Möglichkeit, ein wiederholtes Zeichen oder eine Teilzeichenfolge innerhalb einer Zeichenfolge zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="11426-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="11426-104">Wenn z.B. die Eingabezeichenfolge mehrere Vorkommen einer beliebigen Teilzeichenfolge enthält, können Sie das erste Vorkommen mit einer Erfassungsgruppe abgleichen und dann mit einem Rückverweis nachfolgende Vorkommen der Teilzeichenfolge abgleichen.</span><span class="sxs-lookup"><span data-stu-id="11426-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11426-105">Eine separate Syntax wird verwendet, um auf benannte und nummerierte Erfassungsgruppen in Ersetzungszeichenfolgen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="11426-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="11426-106">Weitere Informationen finden Sie unter [Substitutions](substitutions-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="11426-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="11426-107">.NET definiert separate Sprachelemente, um auf nummerierte und benannte Erfassungsgruppen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="11426-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="11426-108">Weitere Informationen zum Aufzeichnen von Gruppen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="11426-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="11426-109">Nummerierte Rückverweise</span><span class="sxs-lookup"><span data-stu-id="11426-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="11426-110">Ein nummerierter Rückverweis verwendet die folgende Syntax:</span><span class="sxs-lookup"><span data-stu-id="11426-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="11426-111">`\` *number*</span><span class="sxs-lookup"><span data-stu-id="11426-111">`\` *number*</span></span>  
  
 <span data-ttu-id="11426-112">wobei *Nummer* die Ordnungsposition der Erfassungsgruppe im regulären Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="11426-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="11426-113">`\4` gleicht z.B. den Inhalt der vierten Erfassungsgruppe ab.</span><span class="sxs-lookup"><span data-stu-id="11426-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="11426-114">Wenn *Anzahl* nicht im Muster regulären Ausdrucks definiert ist, tritt ein Analysefehler auf und löst das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="11426-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="11426-115">Beispielsweise ist der reguläre Ausdruck `\b(\w+)\s\1` gültig, da `(\w+)` die erste und einzige Erfassungsgruppe im Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="11426-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="11426-116">Auf der anderen Seite ist `\b(\w+)\s\2` ungültig und löst eine Argumentausnahme aus, da es keine nummerierte Erfassungsgruppe `\2` gibt.</span><span class="sxs-lookup"><span data-stu-id="11426-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span>  
  
 <span data-ttu-id="11426-117">Beachten Sie die Mehrdeutigkeit zwischen oktale Escapesequenz (wie z. B. `\16`) und `\` *Anzahl* Rückverweisen, die die gleiche Notation verwenden.</span><span class="sxs-lookup"><span data-stu-id="11426-117">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="11426-118">Diese Mehrdeutigkeit wird wie folgt aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="11426-118">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="11426-119">Die Ausdrücke `\1` bis `\9` werden immer als Rückverweise und nicht als oktale Codes interpretiert.</span><span class="sxs-lookup"><span data-stu-id="11426-119">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="11426-120">Wenn die erste Ziffer eines mehrziffrigen Ausdrucks 8 oder 9 ist (z.B. `\80` oder `\91`), wird der Ausdruck als Literal interpretiert.</span><span class="sxs-lookup"><span data-stu-id="11426-120">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="11426-121">Ausdrücke aus `\10` und höher werden als Rückverweise betrachtet, wenn ein Rückverweis vorhanden ist, der dieser Nummer entspricht; andernfalls werden sie als oktale Codes interpretiert.</span><span class="sxs-lookup"><span data-stu-id="11426-121">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="11426-122">Wenn ein regulärer Ausdruck einen Rückverweis auf eine nicht definierte Gruppe enthält, tritt ein Analysefehler auf und löst das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="11426-122">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="11426-123">Wenn die Mehrdeutigkeit ein Problem darstellt, können Sie mithilfe der `\k<` *Namen* `>` Notation, die eindeutig ist und nicht mit oktalen Zeichencodes verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="11426-123">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="11426-124">Auf ähnliche Weise sind hexadezimale Codes wie z.B. `\xdd` eindeutig und können nicht mit Rückverweisen verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="11426-124">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="11426-125">Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht.</span><span class="sxs-lookup"><span data-stu-id="11426-125">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="11426-126">Ein regulärer Ausdruck `(\w)\1` wird definiert, der aus den folgenden Elementen besteht.</span><span class="sxs-lookup"><span data-stu-id="11426-126">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="11426-127">Element</span><span class="sxs-lookup"><span data-stu-id="11426-127">Element</span></span>|<span data-ttu-id="11426-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11426-128">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="11426-129">Übereinstimmung mit einem Wortzeichen und dessen Zuweisung zur ersten Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="11426-129">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="11426-130">Übereinstimmung mit dem nächsten Zeichen, das mit dem Wert der ersten Erfassungsgruppe identisch ist.</span><span class="sxs-lookup"><span data-stu-id="11426-130">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="11426-131">Benannte Rückverweise</span><span class="sxs-lookup"><span data-stu-id="11426-131">Named Backreferences</span></span>  
 <span data-ttu-id="11426-132">Ein benannter Rückverweis wird mit der folgenden Syntax definiert:</span><span class="sxs-lookup"><span data-stu-id="11426-132">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="11426-133">`\k<` *Name* `>`</span><span class="sxs-lookup"><span data-stu-id="11426-133">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="11426-134">oder:</span><span class="sxs-lookup"><span data-stu-id="11426-134">or:</span></span>  
  
 <span data-ttu-id="11426-135">`\k'` *name* `'`</span><span class="sxs-lookup"><span data-stu-id="11426-135">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="11426-136">wobei *Name* der Name einer Erfassungsgruppe ist, die im Muster eines regulären Ausdrucks definiert ist.</span><span class="sxs-lookup"><span data-stu-id="11426-136">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="11426-137">Wenn *Namen* nicht im Muster regulären Ausdrucks definiert ist, tritt ein Analysefehler auf und löst das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="11426-137">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="11426-138">Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht.</span><span class="sxs-lookup"><span data-stu-id="11426-138">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="11426-139">Ein regulärer Ausdruck `(?<char>\w)\k<char>` wird definiert, der aus den folgenden Elementen besteht.</span><span class="sxs-lookup"><span data-stu-id="11426-139">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="11426-140">Element</span><span class="sxs-lookup"><span data-stu-id="11426-140">Element</span></span>|<span data-ttu-id="11426-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11426-141">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="11426-142">Übereinstimmung mit einem Wortzeichen, und weisen diese einer Erfassungsgruppe mit dem Namen `char`.</span><span class="sxs-lookup"><span data-stu-id="11426-142">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="11426-143">Das nächste Zeichen, die als Wert des ist, entsprechen den `char` Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="11426-143">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 <span data-ttu-id="11426-144">Beachten Sie, dass *Name* auch die Zeichenfolgendarstellung einer Zahl sein kann.</span><span class="sxs-lookup"><span data-stu-id="11426-144">Note that *name* can also be the string representation of a number.</span></span> <span data-ttu-id="11426-145">Im folgenden Beispiel werden mit dem regulären Ausdruck `(?<2>\w)\k<2>` doppelte Wortzeichen in einer Zeichenfolge gesucht.</span><span class="sxs-lookup"><span data-stu-id="11426-145">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a><span data-ttu-id="11426-146">Übereinstimmende Rückverweise</span><span class="sxs-lookup"><span data-stu-id="11426-146">What Backreferences Match</span></span>  
 <span data-ttu-id="11426-147">Ein Rückverweis bezieht sich auf die aktuellste Definition einer Gruppe (beim Abgleichen von links nach rechts die am weitesten links befindliche Definition).</span><span class="sxs-lookup"><span data-stu-id="11426-147">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="11426-148">Wenn eine Gruppe mehrere Erfassungen durchführt, bezieht sich ein Rückverweis auf die aktuellste Erfassung.</span><span class="sxs-lookup"><span data-stu-id="11426-148">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="11426-149">Das folgende Beispiel enthält ein Muster für reguläre Ausdrücke, `(?<1>a)(?<1>\1b)*`, das die Gruppe namens „\1“ neu definiert.</span><span class="sxs-lookup"><span data-stu-id="11426-149">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="11426-150">Die folgende Tabelle beschreibt jedes Muster im regulären Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="11426-150">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="11426-151">Muster</span><span class="sxs-lookup"><span data-stu-id="11426-151">Pattern</span></span>|<span data-ttu-id="11426-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11426-152">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="11426-153">Übereinstimmung mit den Zeichen "a", und weisen Sie das Ergebnis der Erfassungsgruppe mit dem Namen `1`.</span><span class="sxs-lookup"><span data-stu-id="11426-153">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="11426-154">Übereinstimmung mit 0 oder 1 Vorkommen der Gruppe "mit dem Namen" `1` zusammen mit einem "b", und weisen Sie das Ergebnis der Erfassungsgruppe mit dem Namen `1`.</span><span class="sxs-lookup"><span data-stu-id="11426-154">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="11426-155">Beim Vergleich des regulären Ausdrucks mit der Eingabezeichenfolge („aababb“) führt das Modul für reguläre Ausdrücke die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="11426-155">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="11426-156">Begonnen wird am Anfang der Zeichenfolge, und „a“ wird erfolgreich mit dem Ausdruck `(?<1>a)` abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="11426-156">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="11426-157">Der Wert, der die `1` -Gruppe ist jetzt "a".</span><span class="sxs-lookup"><span data-stu-id="11426-157">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="11426-158">Es wird zum zweiten Zeichen gewechselt, und die Zeichenfolge „ab“ wird erfolgreich mit dem Ausdruck `\1b` bzw. „ab“ abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="11426-158">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="11426-159">Anschließend wird `\1` das Ergebnis „ab“ zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="11426-159">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="11426-160">Es wird zum vierten Zeichen gewechselt.</span><span class="sxs-lookup"><span data-stu-id="11426-160">It advances to the fourth character.</span></span> <span data-ttu-id="11426-161">Der Ausdruck `(?<1>\1b)` muss nullmal oder mehrfach abgeglichen werden, damit er der Zeichenfolge „abb“ mit dem Ausdruck `\1b` entspricht.</span><span class="sxs-lookup"><span data-stu-id="11426-161">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="11426-162">Das Ergebnis „abb“ wird wieder `\1` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="11426-162">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="11426-163">In diesem Beispiel ist `*` ein Schleifenquantifizierer – er wird wiederholt ausgewertet, bis das Modul für reguläre Ausdrücke keine Entsprechung für das Muster finden kann, das es definiert.</span><span class="sxs-lookup"><span data-stu-id="11426-163">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="11426-164">Quantifizierer, die in Schleifen durchlaufen werden, löschen keine Gruppendefinitionen.</span><span class="sxs-lookup"><span data-stu-id="11426-164">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="11426-165">Wurden durch eine Gruppe keine Teilzeichenfolgen gefunden, ist der Rückverweis auf diese Gruppe nicht definiert und führt niemals zu einer Übereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="11426-165">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="11426-166">Dies wird anhand des Musters des regulären Ausdrucks veranschaulicht `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, die wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="11426-166">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="11426-167">Muster</span><span class="sxs-lookup"><span data-stu-id="11426-167">Pattern</span></span>|<span data-ttu-id="11426-168">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11426-168">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="11426-169">Beginnt den Vergleich an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="11426-169">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="11426-170">Übereinstimmung mit zwei Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="11426-170">Match two uppercase letters.</span></span> <span data-ttu-id="11426-171">Dies ist die erste Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="11426-171">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="11426-172">Übereinstimmung mit null oder einem Vorkommen von zwei Dezimalziffern.</span><span class="sxs-lookup"><span data-stu-id="11426-172">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="11426-173">Dies ist die zweite Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="11426-173">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="11426-174">Übereinstimmung mit zwei Großbuchstaben.</span><span class="sxs-lookup"><span data-stu-id="11426-174">Match two uppercase letters.</span></span> <span data-ttu-id="11426-175">Dies ist die dritte Erfassungsgruppe.</span><span class="sxs-lookup"><span data-stu-id="11426-175">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="11426-176">Beendet den Vergleich an einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="11426-176">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="11426-177">Eine Eingabezeichenfolge kann auch dann mit diesem regulären Ausdruck übereinstimmen, wenn die von der zweiten Erfassungsgruppe definierten zwei Dezimalziffern nicht vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="11426-177">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="11426-178">Das folgende Beispiel zeigt, dass trotz Übereinstimmung eine leere Erfassungsgruppe zwischen zwei erfolgreichen Erfassungsgruppen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="11426-178">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="11426-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11426-179">See Also</span></span>  
 [<span data-ttu-id="11426-180">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="11426-180">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
