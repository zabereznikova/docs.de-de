---
title: Verschiedene Konstrukte in regulären Ausdrücken
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
ms.openlocfilehash: 8ca888074aa757a1bfba786a7bec5928b75b1da2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290408"
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a>Verschiedene Konstrukte in regulären Ausdrücken
Reguläre Ausdrücke in .NET umfassen drei verschiedene Sprachkonstrukte. Einer ermöglicht Ihnen das Aktivieren oder Deaktivieren bestimmter Vergleichsoptionen mitten in einem Muster für reguläre Ausdrücke. Mithilfe der beiden anderen können Sie Kommentare in einen regulären Ausdruck aufnehmen.  
  
## <a name="inline-options"></a>Inlineoptionen  
 Sie können bestimmte Mustervergleichsoptionen für einen Teil eines regulären Ausdrucks festlegen oder deaktivieren. Verwenden Sie dazu folgende Syntax:  
  
`(?imnsx-imnsx)`  
  
 Die Optionen, die Sie aktivieren möchten, werden nach dem Fragezeichen aufgeführt, und die Optionen, die Sie deaktivieren möchten, werden nach dem Minuszeichen eingefügt. In der folgenden Tabelle sind die einzelnen Optionen beschrieben. Weitere Informationen zu den einzelnen Optionen finden Sie unter [Optionen für reguläre Ausdrücke](regular-expression-options.md).  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`i`|Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung.|  
|`m`|Mehrzeilenmodus.|  
|`n`|Nur explizite Erfassungen. (Klammern fungieren nicht als Erfassungsgruppen.)|  
|`s`|Einzeilenmodus.|  
|`x`|Leerzeichen ohne Escapezeichen ignorieren und Kommentare im x-Modus zulassen.|  
  
 Alle Änderungen in Optionen für reguläre Ausdrücke, die über das Konstrukt `(?imnsx-imnsx)` definiert werden, bleiben bis zum Ende der einschließenden Gruppe gültig.  
  
> [!NOTE]
> Das Gruppierungskonstrukt `(?imnsx-imnsx:`*subexpression*`)` bietet identische Funktionen für einen Teilausdruck. Weitere Informationen finden Sie unter [Gruppierungskonstrukte](grouping-constructs-in-regular-expressions.md).  
  
 Im folgenden Beispiel werden die Optionen `i`, `n` und `x` verwendet, um die Groß-/Kleinschreibung zu ignorieren, explizite Erfassungen zu ermöglichen und Leerzeichen im Muster für reguläre Ausdrücke in der Mitte eines regulären Ausdrucks zu ignorieren.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 Im Beispiel werden zwei reguläre Ausdrücke definiert. Der erste, `\b(D\w+)\s(d\w+)\b`, entspricht zwei aufeinander folgenden Wörtern, die mit dem Großbuchstaben „D“ und dem Kleinbuchstaben „d“ beginnen. Der zweite reguläre Ausdruck, `\b(D\w+)(?ixn) \s (d\w+) \b`, verwendet Inlineoptionen, um dieses Muster entsprechend der folgenden Tabelle zu ändern. Ein Vergleich der Ergebnisse bestätigt den Effekt des `(?ixn)`-Konstrukts.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(D\w+)`|Übereinstimmung mit dem Großbuchstaben „D“, gefolgt von einem oder mehreren Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`(?ixn)`|Ab diesem Punkt werden Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung und nur explizite Erfassungen durchgeführt sowie Leerzeichen im Muster für reguläre Ausdrücke ignoriert.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(d\w+)`|Übereinstimmung mit dem Groß- oder Kleinbuchstaben „d“, gefolgt von mindestens einem Wortzeichen. Diese Gruppe wird nicht erfasst, da die Option `n` (explizite Erfassung) aktiviert wurde.|  
|`\b`|Übereinstimmung mit einer Wortgrenze.|  
  
## <a name="inline-comment"></a>Inlinekommentar  
 Das Konstrukt `(?#` *Kommentar*`)` ermöglicht das Einfügen eines Inlinekommentars in einen regulären Ausdruck. Die Engine für reguläre Ausdrücke verwendet keinen Teil des Kommentars beim Musterabgleich, obwohl der Kommentar in der von der Methode <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> zurückgegebenen Zeichenfolge enthalten ist. Der Kommentar endet bei der ersten schließenden Klammer.  
  
 Im folgenden Beispiel wird das erste Muster für reguläre Ausdrücke aus dem Beispiel im vorherigen Abschnitt wiederholt. Dem regulären Ausdruck werden zwei Inlinekommentare hinzugefügt, um anzugeben, ob beim Vergleich die Groß-/Kleinschreibung berücksichtigt wird. Das Muster für reguläre Ausdrücke, `\b((?# case-sensitive comparison)D\w+)\s(?ixn)((?#case-insensitive comparison)d\w+)\b`, ist wie folgt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(?# case-sensitive comparison)`|Ein Kommentar. Dieser wirkt sich nicht auf das Verhalten des Mustervergleichs aus.|  
|`(D\w+)`|Übereinstimmung mit dem Großbuchstaben „D“, gefolgt von einem oder mehreren Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(?ixn)`|Ab diesem Punkt werden Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung und nur explizite Erfassungen durchgeführt sowie Leerzeichen im Muster für reguläre Ausdrücke ignoriert.|  
|`(?#case-insensitive comparison)`|Ein Kommentar. Dieser wirkt sich nicht auf das Verhalten des Mustervergleichs aus.|  
|`(d\w+)`|Übereinstimmung mit dem Groß- oder Kleinbuchstaben „d“, gefolgt von mindestens einem Wortzeichen. Dies ist die zweite Erfassungsgruppe.|  
|`\b`|Übereinstimmung mit einer Wortgrenze.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a>Zeilenendekommentar  
 Ein Nummernzeichen (`#`) markiert einen x-Modus-Kommentar, der bei dem nicht durch Escapezeichen formatierten #-Zeichen am Ende des Musters für reguläre Ausdrücke beginnt und bis zum Zeilenende fortgesetzt wird. Um dieses Konstrukt zu verwenden, müssen Sie entweder die `x`-Option (durch Inlineoptionen) aktivieren oder beim Instanziieren des <xref:System.Text.RegularExpressions.Regex>-Objekts bzw. beim Aufrufen einer statischen <xref:System.Text.RegularExpressions.Regex>-Methode den Wert <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> an den `option`-Parameter übergeben.  
  
 Das folgende Beispiel veranschaulicht das Konstrukt für Zeilenendekommentare. Dabei wird bestimmt, ob es sich bei einer Zeichenfolge um eine zusammengesetzte Formatzeichenfolge handelt, die mindestens ein Formatelement einschließt. Die folgende Tabelle beschreibt die Konstrukte im Muster für reguläre Ausdrücke:  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\{`|Übereinstimmung mit einer öffnenden geschweiften Klammer.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`(,-*\d+)*`|Übereinstimmung mit keinem oder einem Vorkommen eines Kommas, gefolgt von einem optionalen Minuszeichen, gefolgt von mindestens einer Dezimalzahl.|  
|`(\:\w{1,4}?)*`|Übereinstimmung mit keinem oder einem Doppelpunkt, gefolgt von einem bis vier Leerzeichen (jedoch so wenigen wie möglich).|  
|`\}`|Übereinstimmung mit einer schließenden geschweiften Klammer.|  
|`(?x)`|Aktivieren der Option zum Ignorieren von Leerzeichen im Muster, sodass der Zeilenendekommentar erkannt wird.|  
|`# Looks for a composite format item.`|Ein Zeilenendekommentar.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Anstelle der Bereitstellung des `(?x)`-Konstrukts im regulären Ausdruck hätte der Kommentar auch erkannt werden können, indem die <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType>-Methode aufgerufen und der <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType>-Enumerationswert übergeben wird.  
  
## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
