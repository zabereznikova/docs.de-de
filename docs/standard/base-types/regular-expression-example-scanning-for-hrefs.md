---
title: "Beispiel für reguläre Ausdrücke: Suchen nach HREFs"
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
- searching with regular expressions, examples
- parsing text with regular expressions, examples
- regular expressions, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- pattern-matching with regular expressions, examples
ms.assetid: fae2c15b-7adf-4b15-b118-58eb3906994f
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2bc9db7317c7a73f70a2cb83322b8b3a4c3771b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="regular-expression-example-scanning-for-hrefs"></a><span data-ttu-id="a4c0f-102">Beispiel für reguläre Ausdrücke: Suchen nach HREFs</span><span class="sxs-lookup"><span data-stu-id="a4c0f-102">Regular Expression Example: Scanning for HREFs</span></span>
<span data-ttu-id="a4c0f-103">Im folgenden Beispiel wird eine Eingabezeichenfolge durchsucht, und es werden alle href="..."-Werte und ihre Positionen in der Zeichenfolge angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-103">The following example searches an input string and displays all the href="…" values and their locations in the string.</span></span>  
  
## <a name="the-regex-object"></a><span data-ttu-id="a4c0f-104">Das Regex-Objekt</span><span class="sxs-lookup"><span data-stu-id="a4c0f-104">The Regex Object</span></span>  
 <span data-ttu-id="a4c0f-105">Da die `DumpHRefs` Methode kann mehrmals von Benutzercode aufgerufen werden, verwendet der `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-105">Because the `DumpHRefs` method can be called multiple times from user code, it uses the `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a4c0f-106">Dies ermöglicht das Modul für reguläre Ausdrücke den regulären Ausdruck zwischengespeichert und vermeidet den zusätzlichen Aufwand Instanziierung eines neuen <xref:System.Text.RegularExpressions.Regex> Objekt jedes Mal die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-106">This enables the regular expression engine to cache the regular expression and avoids the overhead of instantiating a new <xref:System.Text.RegularExpressions.Regex> object each time the method is called.</span></span> <span data-ttu-id="a4c0f-107">Ein <xref:System.Text.RegularExpressions.Match> Objekt wird dann verwendet, um alle Übereinstimmungen in der Zeichenfolge durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-107">A <xref:System.Text.RegularExpressions.Match> object is then used to iterate through all matches in the string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#1)]
 [!code-vb[RegularExpressions.Examples.HREF#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#1)]  
  
 <span data-ttu-id="a4c0f-108">Im folgenden Beispiel wird ein Aufruf der `DumpHRefs`-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-108">The following example then illustrates a call to the `DumpHRefs` method.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.HREF#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.HREF/cs/example.cs#2)]
 [!code-vb[RegularExpressions.Examples.HREF#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.HREF/vb/example.vb#2)]  
  
 <span data-ttu-id="a4c0f-109">Das Muster für reguläre Ausdrücke `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` wird entsprechend der folgenden Tabelle interpretiert:</span><span class="sxs-lookup"><span data-stu-id="a4c0f-109">The regular expression pattern `href\s*=\s*(?:["'](?<1>[^"']*)["']|(?<1>\S+))` is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="a4c0f-110">Muster</span><span class="sxs-lookup"><span data-stu-id="a4c0f-110">Pattern</span></span>|<span data-ttu-id="a4c0f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4c0f-111">Description</span></span>|  
|-------------|-----------------|  
|`href`|<span data-ttu-id="a4c0f-112">Sucht nach der Literalzeichenfolge „href“.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-112">Match the literal string "href".</span></span> <span data-ttu-id="a4c0f-113">Die Groß- und Kleinschreibung wird bei der Übereinstimmung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-113">The match is case-insensitive.</span></span>|  
|`\s*`|<span data-ttu-id="a4c0f-114">Sucht nach 0 (null) oder mehr Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-114">Match zero or more white-space characters.</span></span>|  
|`=`|<span data-ttu-id="a4c0f-115">Übereinstimmung mit dem Gleichheitszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-115">Match the equals sign.</span></span>|  
|`\s*`|<span data-ttu-id="a4c0f-116">Sucht nach 0 (null) oder mehr Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-116">Match zero or more white-space characters.</span></span>|  
|`(?:["'](?<1>[^"']*)"&#124;(?<1>\S+))`|<span data-ttu-id="a4c0f-117">Übereinstimmung für einen der folgenden ohne erneute Zuordnen des Ergebnisses einer erfassten Gruppe:</span><span class="sxs-lookup"><span data-stu-id="a4c0f-117">Match one of the following without assigning the result to a captured group:</span></span><br /><br /> <span data-ttu-id="a4c0f-118">– Ein Anführungszeichen oder ein Apostroph, gefolgt von keinem oder mehreren Vorkommen beliebiger Zeichen als ein Anführungszeichen oder Apostroph, gefolgt von einem Anführungszeichen oder Apostroph.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-118">-   A quotation mark or apostrophe, followed by zero or more occurrences of any character other than a quotation mark or apostrophe, followed by a quotation mark or apostrophe.</span></span> <span data-ttu-id="a4c0f-119">Die Gruppe namens `1` ist in diesem Muster enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-119">The group named `1` is included in this pattern.</span></span><br /><span data-ttu-id="a4c0f-120">-Eine oder mehrere nicht-Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-120">-   One or more non-white-space characters.</span></span> <span data-ttu-id="a4c0f-121">Die Gruppe namens `1` ist in diesem Muster enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-121">The group named `1` is included in this pattern.</span></span>|  
|`(?<1>[^"']*)`|<span data-ttu-id="a4c0f-122">Weist der Erfassungsgruppe namens `1` null oder mehr Vorkommen eines beliebigen Zeichens außer Anführungszeichen oder Apostroph zu.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-122">Assign zero or more occurrences of any character other than a quotation mark or apostrophe to the capturing group named `1`.</span></span>|  
|`"(?<1>\S+)`|<span data-ttu-id="a4c0f-123">Weist der Erfassungsgruppe namens `1` ein oder mehr Nicht-Leerzeichen zu.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-123">Assign one or more non-white-space characters to the capturing group named `1`.</span></span>|  
  
## <a name="match-result-class"></a><span data-ttu-id="a4c0f-124">Abgleichsergebnisklasse</span><span class="sxs-lookup"><span data-stu-id="a4c0f-124">Match Result Class</span></span>  
 <span data-ttu-id="a4c0f-125">Die Ergebnisse einer Suche werden gespeichert, der <xref:System.Text.RegularExpressions.Match> Klasse, die Zugriff auf alle Teilzeichenfolgen, die von der Suche extrahierten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-125">The results of a search are stored in the <xref:System.Text.RegularExpressions.Match> class, which provides access to all the substrings extracted by the search.</span></span> <span data-ttu-id="a4c0f-126">Auch gespeichert wird, die Zeichenfolge, die zu durchsuchenden und den regulären Ausdruck verwendeten ADO.NET-Anbieter ab, sodass sie aufrufen können die <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> aufzurufende Methode durchführen, eine andere Suche starten, in denen der letzte beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-126">It also remembers the string being searched and the regular expression being used, so it can call the <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> method to perform another search starting where the last one ended.</span></span>  
  
## <a name="explicitly-named-captures"></a><span data-ttu-id="a4c0f-127">Explizit benannte Erfassungen</span><span class="sxs-lookup"><span data-stu-id="a4c0f-127">Explicitly Named Captures</span></span>  
 <span data-ttu-id="a4c0f-128">In herkömmlichen regulären Ausdrücken werden Klammern für die Erfassung automatisch nach der Reihenfolge durchnummeriert.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-128">In traditional regular expressions, capturing parentheses are automatically numbered sequentially.</span></span> <span data-ttu-id="a4c0f-129">Daraus ergeben sich zwei Probleme.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-129">This leads to two problems.</span></span> <span data-ttu-id="a4c0f-130">Zum einen muss nach dem Einfügen oder Entfernen von Klammern jeglicher Code, der auf die nummerierten Klammern verweist, der neuen Nummerierung entsprechend umgeschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-130">First, if a regular expression is modified by inserting or removing a set of parentheses, all code that refers to the numbered captures must be rewritten to reflect the new numbering.</span></span> <span data-ttu-id="a4c0f-131">Zweitens werden häufig unterschiedliche Klammerpaare verwendet, um zwei Alternativausdrücke für eine Übereinstimmung zu erhalten. Dadurch wird es schwierig festzustellen, durch welchen der beiden Ausdrücke das Ergebnis zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-131">Second, because different sets of parentheses often are used to provide two alternative expressions for an acceptable match, it might be difficult to determine which of the two expressions actually returned a result.</span></span>  
  
 <span data-ttu-id="a4c0f-132">Um diese Probleme zu behandeln die <xref:System.Text.RegularExpressions.Regex> Klasse unterstützt die Syntax `(?<name>…)` zum Aufzeichnen einer Übereinstimmung in einer angegebenen Slot (das Einschubfach mit einer Zeichenfolge oder eine ganze Zahl namens; Ganzzahlen schneller wiederhergestellt werden können).</span><span class="sxs-lookup"><span data-stu-id="a4c0f-132">To address these problems, the <xref:System.Text.RegularExpressions.Regex> class supports the syntax `(?<name>…)` for capturing a match into a specified slot (the slot can be named using a string or an integer; integers can be recalled more quickly).</span></span> <span data-ttu-id="a4c0f-133">Damit können alle Suchergebnisse für dieselbe Zeichenfolge an denselben Ort geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-133">Thus, alternative matches for the same string all can be directed to the same place.</span></span> <span data-ttu-id="a4c0f-134">Im Fall eines Konflikts ist das zuletzt im Slot gespeicherte Suchergebnis gültig.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-134">In case of a conflict, the last match dropped into a slot is the successful match.</span></span> <span data-ttu-id="a4c0f-135">(Eine vollständige Liste mehrerer Übereinstimmungen für einen einzelnen Slot steht jedoch zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a4c0f-135">(However, a complete list of multiple matches for a single slot is available.</span></span> <span data-ttu-id="a4c0f-136">Finden Sie unter der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> -Auflistung.)</span><span class="sxs-lookup"><span data-stu-id="a4c0f-136">See the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> collection for details.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4c0f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4c0f-137">See Also</span></span>  
 [<span data-ttu-id="a4c0f-138">Reguläre Ausdrücke von .NET</span><span class="sxs-lookup"><span data-stu-id="a4c0f-138">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
