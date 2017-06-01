---
title: "R&#252;ckverweiskonstrukte in regul&#228;ren Ausdr&#252;cken | Microsoft Docs"
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
  - "Reguläre Ausdrücke von .NET Framework, Rückverweiskonstrukte"
  - "Rückverweise"
  - "Konstrukte, Rückverweis"
  - "Reguläre Ausdrücke, Rückverweiskonstrukte"
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# R&#252;ckverweiskonstrukte in regul&#228;ren Ausdr&#252;cken
Rückverweise bieten eine zweckmäßige Möglichkeit, ein wiederholtes Zeichen oder eine Teilzeichenfolge innerhalb einer Zeichenfolge zu identifizieren.  Wenn die Eingabezeichenfolge beispielsweise mehrere Vorkommen einer beliebigen Teilzeichenfolge enthält, können Sie das erste Vorkommen mit einer Erfassungsgruppe abgleichen und anschließend die nachfolgenden Vorkommen der Teilzeichenfolge mithilfe eines Rückverweises abgleichen.  
  
> [!NOTE]
>  Eine separate Syntax wird verwendet, um auf benannte und nummerierte Erfassungsgruppen in Ersetzungszeichenfolgen zu verweisen.  Weitere Informationen finden Sie unter [Ersetzungen](../../../docs/standard/base-types/substitutions-in-regular-expressions.md).  
  
 .NET Framework definiert separate Sprachelemente, um auf nummerierte und benannte Erfassungsgruppen zu verweisen.  Weitere Informationen zu Erfassungsgruppen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## Nummerierte Rückverweise  
 Ein nummerierter Rückverweis verwendet die folgende Syntax:  
  
 `\` *number*  
  
 wobei *number* die Ordinalposition der Erfassungsgruppe im regulären Ausdruck ist.  Beispielsweise stimmt `\4` mit dem Inhalt der vierten Erfassungsgruppe überein.  Wenn *number* nicht im Muster eines regulären Ausdruck definiert ist, tritt ein Analysefehler auf, und das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException> ausgelöst.  Der reguläre Ausdruck `\b(\w+)\s\1` ist z. B. gültig, da `(\w+)` die erste und einzige Erfassungsgruppe im Ausdruck ist.  Andererseits ist `\b(\w+)\s\2` ungültig und löst eine Argumentausnahme aus, da keine Erfassungsgruppe mit der Nummer `\2` vorhanden ist.  
  
 Beachten Sie die Mehrdeutigkeit zwischen Umschaltcodes Oktalformat \(wie `\16`\) und Rückverweisen `\`*number*, die die gleiche Notation verwenden.  Diese Mehrdeutigkeit wird folgendermaßen aufgelöst:  
  
-   Die Ausdrücke "`\1`" bis "`\9`" werden immer als Rückverweise und nicht als oktale Codes interpretiert.  
  
-   Wenn die erste Ziffer eines multidigit\-Ausdrucks 8 oder 9 ist \(z. B. `\80` oder `\91`\), wird der Ausdruck als Literal interpretiert.  
  
-   Ausdrücke von `\10` und größer werden als Rückverweise betrachtet, wenn es einen Rückverweis gibt, der dieser Zahl entspricht; andernfalls werden sie als oktale Codes interpretiert.  
  
-   Enthält ein regulärer Ausdruck einen Rückverweis auf eine nicht definierte Gruppennummer, tritt ein Analysefehler auf, und das Modul für reguläre Ausdrücke löst eine <xref:System.ArgumentException> aus.  
  
 Wenn die Mehrdeutigkeit ein Problem ist, können Sie die Notation `\k<`*name*`>` verwenden, um eindeutig ist und nicht mit oktalen Zeichencodes verwechselt werden kann.  Auf ähnliche Weise sind hexadezimale Codes wie `\xdd` unzweideutig und können nicht mit Rückverweisen verwechselt werden.  
  
 Im folgenden Beispiel befinden sich doppelte Wortzeichen in einer Zeichenfolge.  Ein regulärer Ausdruck \(`(\w)\1`\) wird definiert, der aus den folgenden Elementen besteht.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`(\w)`|Entspricht einem Wortzeichen und weist es der ersten Erfassungsgruppe zu.|  
|`\1`|Entspricht dem nächsten Zeichen, das mit dem Wert der ersten Erfassungsgruppe identisch ist.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## Benannte Rückverweise  
 Ein benannter Rückverweis wird mit der folgenden Syntax definiert:  
  
 `\k<` *name* `>`  
  
 oder:  
  
 `\k'` *name* `'`  
  
 wobei *name* den Namen einer Erfassungsgruppe ist, die im Muster eines regulären Ausdruck definiert ist.  Wenn *name* nicht im Muster eines regulären Ausdruck definiert ist, tritt ein Analysefehler auf, und das Modul für reguläre Ausdrücke eine <xref:System.ArgumentException> ausgelöst.  
  
 Im folgenden Beispiel befinden sich doppelte Wortzeichen in einer Zeichenfolge.  Ein regulärer Ausdruck \(`(?<char>\w)\k<char>`\) wird definiert, der aus den folgenden Elementen besteht.  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`(?<char>\w)`|Entspricht einem Wortzeichen und weist es einer Erfassungsgruppe mit dem Namen `char` zu.|  
|`\k<char>`|Entspricht dem nächsten Zeichen, das mit dem Wert der `char`\-Erfassungsgruppe identisch ist.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 Beachten Sie, dass *name* die Zeichenfolgendarstellung einer Zahl auch sein kann.  Im folgenden Beispiel wird der reguläre Ausdruck `(?<2>\w)\k<2>` verwendet, um doppelte Wortzeichen in einer Zeichenfolge zu finden.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## Übereinstimmende Rückverweise  
 Ein Rückverweis bezieht sich immer auf die aktuellste Definition einer Gruppe \(die Definition, die bei der Suche von links nach rechts am weitesten links steht\).  Wenn durch eine Gruppe mehrere Übereinstimmungen gefunden werden, bezieht sich ein Rückverweis auf die aktuellste Erfassung.  
  
 Das folgende Beispiel enthält ein Muster eines regulären Ausdrucks, `(?<1>a)(?<1>\1b)*`, das die benannte \\1\-Gruppe neu definiert.  In der folgenden Tabelle wird jedes Muster im regulären Ausdruck beschrieben.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`(?<1>a)`|Entspricht dem Zeichen "a" und weist das Ergebnis der Erfassungsgruppe mit der Bezeichnung `1` zu.|  
|`(?<1>\1b)*`|Vergleichen Sie 0 oder 1 Vorkommen der Gruppe mit dem Namen `1` zusammen mit einem "b", und weisen Sie das Ergebnis der Erfassungsgruppe mit dem Namen `1` zu.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 Beim Vergleich des regulären Ausdrucks mit der Eingabezeichenfolge \("aababb"\) führt das Modul für reguläre Ausdrücke die folgenden Vorgänge aus:  
  
1.  Begonnen wird am Anfang der Zeichenfolge, und "a" wird mit dem Ausdruck `(?<1>a)` abgeglichen.  Der Wert der `1`\-Gruppe ist nun ein "a".  
  
2.  Es wird zum zweiten Zeichen gewechselt, und die Zeichenfolge "ab" wird erfolgreich mit dem Ausdruck `\1b` oder "ab" abgeglichen.  Anschließend wird das Ergebnis \("ab\)" `\1` zugewiesen.  
  
3.  Es wird zum vierten Zeichen gewechselt.  Der Ausdruck `(?<1>\1b)` muss nullmal oder mehrfach abgeglichen werden, damit er der Zeichenfolge "abb" mit dem Ausdruck `\1b` entspricht.  Das Ergebnis \("abb"\) wird wieder `\1` zugewiesen.  
  
 In diesem Beispiel ist `*` ein Schleifenquantifizierer – er wird laufend ausgewertet, bis das Modul für reguläre Ausdrücke keine Entsprechung für das Muster finden kann, das es definiert.  Quantifizierer, die in Schleifen durchlaufen werden, löschen keine Gruppendefinitionen.  
  
 Wurden durch eine Gruppe keine Teilzeichenfolgen gefunden, ist der Rückverweis auf diese Gruppe nicht definiert und führt niemals zu einem Suchergebnis.  Dies wird durch das Muster eines regulären Ausdrucks, `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, veranschaulicht, der folgendermaßen definiert wird:  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|Beginnt den Vergleich an einer Wortgrenze.|  
|`(\p{Lu}{2})`|Entspricht zwei Großbuchstaben.  Dies ist die erste Erfassungsgruppe.|  
|`(\d{2})?`|Entspricht null oder einem Vorkommen von zwei Dezimalstellen.  Dies ist die zweite Erfassungsgruppe.|  
|`(\p{Lu}{2})`|Entspricht zwei Großbuchstaben.  Dies ist die dritte Erfassungsgruppe.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
  
 Eine Eingabezeichenfolge kann mit diesem regulären Ausdruck übereinstimmen, auch wenn die zwei Dezimalstellen, die von der zweiten Erfassungsgruppe definiert werden, nicht vorhanden sind.  Das folgende Beispiel zeigt, dass trotz einer Übereinstimmung eine leere Erfassungsgruppe zwischen zwei erfolgreichen Erfassungsgruppen gefunden wird.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## Siehe auch  
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)