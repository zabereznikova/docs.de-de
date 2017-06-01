---
title: "Verschiedene Konstrukte in regul&#228;ren Ausdr&#252;cken | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Reguläre Ausdrücke von .NET Framework, Verschiedene Konstrukte"
  - "Konstrukte, Verschiedene"
  - "Reguläre Ausdrücke, Verschiedene Konstrukte"
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Verschiedene Konstrukte in regul&#228;ren Ausdr&#252;cken
Reguläre Ausdrücke in .NET Framework schließen drei verschiedene Sprachkonstrukte ein.  Sie können bestimmte Vergleichsoptionen in der Mitte eines Musters für einen regulären Ausdruck aktivieren oder deaktivieren.  Die vebleibenden zwei Elemente ermöglichen das Hinzufügen von Kommentaren in einem regulären Ausdruck.  
  
## Inlineoptionen  
 Mithilfe der Syntax können bestimmte Mustervergleichsoptionen für einen Teil eines regulären Ausdrucks festgelegt oder deaktiviert werden.  
  
```  
(?imnsx-imnsx)  
```  
  
 Sie führen die zu aktivierenden Optionen nach dem Fragezeichen und die zu deaktivierenden Optionen nach dem Minuszeichen auf.  In der folgenden Tabelle sind die einzelnen Optionen beschrieben.  Weitere Informationen zu den einzelnen Optionen finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|`i`|Übereinstimmung ohne Berücksichtigung der Groß\-\/Kleinschreibung.|  
|`m`|Mehrzeilenmodus.|  
|`n`|Nur explizite Erfassungen. \(Klammern fungieren nicht als Erfassungsgruppen.\)|  
|`s`|Einzeilenmodus|  
|`x`|Leerstellen ohne Escapezeichen ignorieren und x\-Modus\-Kommentare zulassen.|  
  
 Irgendeine Änderung in regulären Ausdrucksoptionen, die vom `(?imnsx-imnsx)`\-Konstrukt definiert wurde, bleibt bis zum Ende der einschließenden Gruppe gültig.  
  
> [!NOTE]
>  `(?imnsx-imnsx:` *subexpression* `)`, das die Zuordnung gruppiert, stellt identische Funktionalität für einen Teilausdruck bereit.  Weitere Informationen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 Im folgenden Beispiel werden mit den Optionen `i`, `n` und `x` die Nichtbeachtung von Groß\- und Kleinschreibung und explizite Erfassungen aktiviert. Zudem werden Leerzeichen im Muster des regulären Ausdrucks in der Mitte eines regulären Ausdrucks ignoriert.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 Im Beispiel werden zwei reguläre Ausdrücke definiert.  Das erste Element, `\b(D\w+)\s(d\w+)\b`, entspricht zwei aufeinander folgenden Wörtern, die mit einem großgeschriebenen "D" und einem kleingeschriebenen "d" beginnen.  Der zweite reguläre Ausdruck, `\b(D\w+)(?ixn) \s (d\w+) \b`, verwendet Inlineoptionen, um dieses Muster zu ändern \(siehe Beschreibung in der folgenden Tabelle\).  Ein Vergleich der Ergebnisse bestätigt den Effekt des `(?ixn)`\-Konstrukts.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(D\w+)`|Entspricht einem großen "D" gefolgt von mindestens einem Wortzeichen.  Dies ist die erste Erfassungsgruppe.|  
|`(?ixn)`|Führen Sie von diesem Punkt an keine Vergleiche mit Beachtung von Groß\-\/Kleinschreibung durch, führen Sie nur explizite Erfassungen aus, und ignorieren Sie Leerstellen im Muster eines regulären Ausdrucks.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(d\w+)`|Entspricht einem in Groß\- oder Kleinbuchstaben geschriebenen "d" gefolgt von mindestens einem Wortzeichen.  Diese Gruppe wird nicht erfasst, da die `n` \(explizite Erfassung\)\-Option aktiviert wurde.|  
|`\b`|Entsprechung für eine Wortgrenze finden.|  
  
## Inlinekommentar  
 Das Konstrukt `(?#` *comment*`)` können Sie einen Inlinekommentar in einem regulären Ausdruck.  Das Modul für reguläre Ausdrücke verwendet keinen beliebigen Teil des Kommentars im Mustervergleich, obwohl der Kommentar in der Zeichenfolge enthalten ist, die von der <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=fullName>\-Methode zurückgegeben wird.  Der Kommentar endet bei der ersten schließenden Klammer.  
  
 Im folgenden Beispiel wird das erste Muster eines regulären Ausdrucks aus dem Beispiel im vorherigen Abschnitt wiederholt.  Es fügt dem regulären Ausdruck zwei Inlinekommentare hinzu, um anzugeben, ob beim Vergleich die Groß\-\/Kleinschreibung beachtet wird.  Das Muster eines regulären Ausdrucks \(`\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`\) wird folgendermaßen definiert:  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(?# case-sensitive comparison)`|Ein Kommentar.  Dies hat keine Auswirkungen auf das Mustervergleichsverhalten.|  
|`(D\w+)`|Entspricht einem großen "D" gefolgt von mindestens einem Wortzeichen.  Dies ist die erste Erfassungsgruppe.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(?ixn)`|Führen Sie von diesem Punkt an keine Vergleiche mit Beachtung von Groß\-\/Kleinschreibung durch, führen Sie nur explizite Erfassungen aus, und ignorieren Sie Leerstellen im Muster eines regulären Ausdrucks.|  
|`(?#case-insensitive comparison)`|Ein Kommentar.  Dies hat keine Auswirkungen auf das Mustervergleichsverhalten.|  
|`(d\w+)`|Entspricht einem in Groß\- oder Kleinbuchstaben geschriebenen "d" gefolgt von mindestens einem Wortzeichen.  Dies ist die zweite Erfassungsgruppe.|  
|`\b`|Entsprechung für eine Wortgrenze finden.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## Kommentar am Zeilenende  
 Ein Nummernzeichen \(`#`\) markiert einen x\-Modus\-Kommentar, der beim nicht entfernten \#\-Zeichen am Ende des Musters eines regulären Ausdrucks beginnt, und fährt bis zum Ende der Zeile fort.  Um dieses Konstrukt zu verwenden, müssen Sie entweder die `x`\-Option \(durch Inlineoptionen\) aktivieren oder den <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Wert für den `option`\-Parameter angeben, wenn Sie das <xref:System.Text.RegularExpressions.Regex>\-Objekt instanziieren oder eine statische <xref:System.Text.RegularExpressions.Regex>\-Methode aufrufen.  
  
 Das folgende Beispiel veranschaulicht das Konstrukt für Zeilenendkommentare:  Es wird bestimmt, ob eine Zeichenfolge eine zusammengesetzte Formatzeichenfolge ist, die mindestens ein Formatelement einschließt.  In der folgenden Tabelle werden die Konstrukte im Muster für reguläre Ausdrücke beschrieben.  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\{`|Entspricht einer öffnenden geschweiften Klammer.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`(,-*\d+)*`|Entspricht null oder einem Vorkommen eines Kommas gefolgt von einem optionalen Minuszeichen und mindestens einer Dezimalstelle.|  
|`(\:\w{1,4}?)*`|Entspricht null oder einem Vorkommen eines Doppelpunkts gefolgt von einem bis vier \(doch möglichst wenigen\) Leerzeichen.|  
|`(?#case insensitive comparison)`|Ein Inlinekommentar.  Dies hat keine Auswirkungen auf das Mustervergleichsverhalten.|  
|`\}`|Entspricht einer schließenden geschweiften Klammer.|  
|`(?x)`|Aktivieren Sie die Option zum Ignorieren von Musterleerstellen, damit der Kommentar am Zeilenende erkannt wird.|  
|`# Looks for a composite format item.`|Ein Kommentar am Zeilenende.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Anstatt das `(?x)`\-Konstrukt im regulären Ausdruck bereitzustellen, kann der Kommentar auch durch Aufrufen der <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>\-Methode und die Übergabe des <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>\-Enumerationswerts an die Methode erkannt werden.  
  
## Siehe auch  
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)