---
title: Gruppierungskonstrukte in regulären Ausdrücken
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lookbehinds
- regular expressions, grouping constructs
- lookaheads
- .NET Framework regular expressions, grouping constructs
- constructs, grouping
- grouping constructs
ms.assetid: 0fc18634-f590-4062-8d5c-f0b71abe405b
ms.openlocfilehash: 8bf6870e3eb3ef65b498f431cb2b8805eee7ec3c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140110"
---
# <a name="grouping-constructs-in-regular-expressions"></a>Gruppierungskonstrukte in regulären Ausdrücken
Gruppierungskonstrukte grenzen die Teilausdrücke eines regulären Ausdrucks ab und zeichnen die Teilzeichenfolgen einer Eingabezeichenfolge auf. Mit Gruppierungskonstrukten können Sie folgende Schritte ausführen:  
  
- Finden Sie eine Entsprechung für einen Teilausdruck, der in der Eingabezeichenfolge wiederholt wird.  
  
- Wenden Sie einen Quantifizierer auf einen Teilausdruck an, der über mehrere reguläre Ausdruckssprachelemente verfügt. Weitere Informationen zu Quantifizierern finden Sie unter [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
- Schließen Sie einen Teilausdruck in die Zeichenfolge ein, die von den <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> - und <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> -Methoden zurückgegeben wird.  
  
- Rufen Sie einzelne Teilausdrücke aus der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> -Eigenschaft ab, und verarbeiten Sie sie getrennt vom entsprechenden Text als Ganzes.  
  
 Die folgende Tabelle führt die Gruppierungskonstrukte auf, die von der .NET-Engine für reguläre Ausdrücke unterstützt werden, und gibt an, ob sie erfassend oder nicht erfassend sind.  
  
|Gruppierungskonstrukt|Erfassend oder nicht erfassend|  
|------------------------|-------------------------------|  
|[Übereinstimmende Teilausdrücke](#matched_subexpression)|Wird erfasst|  
|[Benannte übereinstimmende Teilausdrücke](#named_matched_subexpression)|Wird erfasst|  
|[Ausgleichen von Gruppendefinitionen](#balancing_group_definition)|Wird erfasst|  
|[Nicht erfassende Gruppen](#noncapturing_group)|Nicht erfassend|  
|[Gruppenoptionen](#group_options)|Nicht erfassend|  
|[Positive Lookaheadassertionen mit einer Breite von Null](#zerowidth_positive_lookahead_assertion)|Nicht erfassend|  
|[Negative Lookaheadassertionen mit einer Breite von Null](#zerowidth_negative_lookahead_assertion)|Nicht erfassend|  
|[Positive Lookbehindassertionen mit einer Breite von Null](#zerowidth_positive_lookbehind_assertion)|Nicht erfassend|  
|[Negative Lookbehindassertionen mit einer Breite von Null](#zerowidth_negative_lookbehind_assertion)|Nicht erfassend|  
|[Nicht zurückverfolgende Teilausdrücke](#nonbacktracking_subexpression)|Nicht erfassend|  
  
 Weitere Informationen zu Gruppen und dem Objektmodell für reguläre Ausdrücke finden Sie unter [Gruppieren von Konstrukten und Objekten für reguläre Ausdrücke](#Objects).  
  
<a name="matched_subexpression"></a>   
## <a name="matched-subexpressions"></a>Übereinstimmende Teilausdrücke  
 Das folgende Gruppierungskonstrukt erfasst einen übereinstimmenden Teilausdruck:  
  
 `(` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges gültiges Muster eines regulären Ausdrucks ist. Erfassungen, die Klammern verwenden, werden automatisch von links nach rechts und mit eins beginnend auf Grundlage der Reihenfolge der öffnenden runden Klammern im regulären Ausdruck aufgezählt. Die Erfassung, die mit 0 gekennzeichnet wird, ist der Text, dem das gesamte Muster für den regulären Ausdruck entspricht.  
  
> [!NOTE]
> Standardmäßig erfasst das Sprachelement `(`*Teilausdruck*`)` den übereinstimmenden Teilausdruck. Wenn der <xref:System.Text.RegularExpressions.RegexOptions> -Parameter einer übereinstimmenden Methode für ein Muster eines regulären Ausdrucks das <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> -Flag enthält oder wenn die `n` -Option auf diesen Teilausdruck angewendet wird (siehe weiter unten in diesem Thema [Gruppenoptionen](#group_options) ), wird der übereinstimmende Teilausdruck jedoch nicht erfasst.  
  
 Für den Zugriff auf erfasste Gruppen gibt es vier Möglichkeiten:  
  
- Indem das Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mit der Syntax `\`*number*verwiesen, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist.  
  
- Indem das benannte Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mit der Syntax `\k<`*name*`>`verwiesen, wobei *name* der Name einer Erfassungsgruppe ist, oder mit `\k<`*number*`>`verwiesen, wobei *number* die Ordinalzahl einer Erfassungsgruppe ist. Eine Erfassungsgruppe weist einen Standardnamen auf, der mit der zugehörigen Ordinalzahl identisch ist. Weitere Informationen finden Sie unter [Benannte übereinstimmende Teilausdrücke](#named_matched_subexpression) weiter unten in diesem Thema.  
  
- Mit der Ersatzsequenz `$`*number* in einem <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> - oder <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> -Methodenaufruf, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist.  
  
- Programmgesteuert durch die Verwendung des <xref:System.Text.RegularExpressions.GroupCollection> -Objekts, das von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Der Member auf der Nullposition in der Auflistung stellt die gesamte Übereinstimmung für einen regulären Ausdruck dar. Jeder nachfolgende Member stellt einen übereinstimmenden Teilausdruck dar. Weitere Informationen finden Sie im Abschnitt [Grouping Constructs and Regular Expression Objects](#Objects) .  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck veranschaulicht, der doppelte Wörter im Text identifiziert. Die zwei Erfassungsgruppen des Musters eines regulären Ausdrucks stellen die zwei Instanzen des doppelten Worts dar. Die zweite Instanz wird erfasst, um die Anfangsposition in der Eingabezeichenfolge zu melden.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/grouping1.cs#1)]
 [!code-vb[RegularExpressions.Language.Grouping#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/grouping1.vb#1)]  
  
 Das Muster für den reguläre Ausdruck lautet folgendermaßen:  
  
`(\w+)\s(\1)\W`  
  
 Die folgende Tabelle zeigt, wie das Muster eines regulären Ausdrucks interpretiert wird.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(\1)`|Suchen Sie nach einer Entsprechung für die Zeichenfolge in der ersten erfassten Gruppe. Dies ist die zweite Erfassungsgruppe. Im Beispiel wird sie einer erfassten Gruppe zugewiesen, damit die Anfangsposition des doppelten Worts von der `Match.Index` -Eigenschaft zurückgegeben wird.|  
|`\W`|Finden Sie eine Entsprechung für ein Nichtwortzeichen, einschließlich Leerzeichen und Interpunktion. Dies verhindert, dass für das Muster eines regulären Ausdrucks eine Entsprechung für ein Wort gefunden wird, das mit dem Wort von der zuerst erfassten Gruppe beginnt.|  
  
<a name="named_matched_subexpression"></a>   
## <a name="named-matched-subexpressions"></a>Benannte übereinstimmende Teilausdrücke  
 Das folgende Gruppierungskonstrukt erfasst einen übereinstimmenden Teilausdruck und ermöglicht den Zugriff nach Name oder Zahl:  
  
`(?<name>subexpression)`  
  
 oder:  
  
`(?'name'subexpression)`  
  
 wobei *name* ein gültiger Gruppenname und *subexpression* ein beliebiges gültiges Muster eines regulären Ausdrucks ist. *name* darf keine Interpunktion enthalten und nicht mit einer Zahl beginnen.  
  
> [!NOTE]
> Wenn der <xref:System.Text.RegularExpressions.RegexOptions> -Parameter einer übereinstimmenden Methode für ein Muster eines regulären Ausdrucks das <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> -Flag enthält oder wenn die `n` -Option auf diesen Teilausdruck angewendet wird (siehe weiter unten in diesem Thema [Gruppenoptionen](#group_options) ), besteht die einzige Möglichkeit zur Erfassung eines Teilausdrucks in der expliziten Benennung von Erfassungsgruppen.  
  
 Sie können wie folgt auf benannte erfasste Gruppen zugreifen:  
  
- Indem das benannte Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mit der Syntax `\k<`*name*`>`verwiesen, wobei *name* der Name des erfassten Teilausdrucks ist.  
  
- Indem das Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mit der Syntax `\`*number*verwiesen, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist. Benannte übereinstimmende Teilausdrücke werden hintereinander von links nach rechts nach übereinstimmenden Teilausdrücken nummeriert.  
  
- Mit der Ersatzsequenz `${`*name*`}` in einem <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> - oder <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> -Methodenaufruf, wobei *name* der Name des erfassten Teilausdrucks ist.  
  
- Mit der Ersatzsequenz `$`*number* in einem <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>- oder <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType>-Methodenaufruf, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist.  
  
- Programmgesteuert durch die Verwendung des <xref:System.Text.RegularExpressions.GroupCollection> -Objekts, das von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Der Member auf der Nullposition in der Auflistung stellt die gesamte Übereinstimmung für einen regulären Ausdruck dar. Jeder nachfolgende Member stellt einen übereinstimmenden Teilausdruck dar. Benannte erfasste Gruppen werden in der Auflistung nach nummerierten erfassten Gruppen gespeichert.  
  
- Programmgesteuert, durch das Bereitstellen des Teilausdrucknamens für den Indexer (in C#) des <xref:System.Text.RegularExpressions.GroupCollection> -Objekts oder seine <xref:System.Text.RegularExpressions.GroupCollection.Item%2A> -Eigenschaft (in Visual Basic).  
  
 Ein einfaches Muster eines regulären Ausdrucks veranschaulicht, wie auf nummerierte (unbenannte) und benannte Gruppen entweder programmgesteuert oder mit der Sprachsyntax für reguläre Ausdrücke verwiesen werden kann. Der reguläre Ausdruck `((?<One>abc)\d+)?(?<Two>xyz)(.*)` generiert die folgenden Erfassungsgruppen nach Nummer und Name. Die erste Erfassungsgruppe (Nummer 0) bezieht sich stets auf das gesamte Muster.  
  
|number|name|Muster|  
|------------|----------|-------------|  
|0|0 (Standardname)|`((?<One>abc)\d+)?(?<Two>xyz)(.*)`|  
|1|1 (Standardname)|`((?<One>abc)\d+)`|  
|2|2 (Standardname)|`(.*)`|  
|3|Eins|`(?<One>abc)`|  
|4|Zwei|`(?<Two>xyz)`|  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck veranschaulicht, der duplizierte Wörter sowie das Wort, das jedem duplizierten Wort direkt folgt, identifiziert. Das Muster eines regulären Ausdrucks definiert zwei benannte Teilausdrücke: `duplicateWord`, der das doppelte Wort darstellt; und `nextWord`, der das Wort darstellt, das auf das doppelte Wort folgt.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/grouping2.cs#2)]
 [!code-vb[RegularExpressions.Language.Grouping#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/grouping2.vb#2)]  
  
 Das Muster für den reguläre Ausdruck lautet folgendermaßen:  
  
`(?<duplicateWord>\w+)\s\k<duplicateWord>\W(?<nextWord>\w+)`  
  
 In der folgenden Tabelle wird gezeigt, wie der reguläre Ausdruck interpretiert wird.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`(?<duplicateWord>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Geben Sie für die Erfassungsgruppe `duplicateWord`als Namen an.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`\k<duplicateWord>`|Suchen Sie nach einer Entsprechung der Zeichenfolge der erfassten Gruppe mit der Bezeichnung `duplicateWord`.|  
|`\W`|Finden Sie eine Entsprechung für ein Nichtwortzeichen, einschließlich Leerzeichen und Interpunktion. Dies verhindert, dass für das Muster eines regulären Ausdrucks eine Entsprechung für ein Wort gefunden wird, das mit dem Wort von der zuerst erfassten Gruppe beginnt.|  
|`(?<nextWord>\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Geben Sie für die Erfassungsgruppe `nextWord`als Namen an.|  
  
 Beachten Sie, dass der Name einer Gruppe in einem regulären Ausdruck wiederholt werden kann. Beispielsweise ist es möglich, dass mehr als eine Gruppe den Namen `digit`trägt, wie im folgenden Beispiel veranschaulicht wird. Im Fall von doppelten Namen wird der Wert des <xref:System.Text.RegularExpressions.Group> -Objekts durch die letzte erfolgreiche Erfassung in der Eingabezeichenfolge bestimmt. Darüber hinaus wird <xref:System.Text.RegularExpressions.CaptureCollection> mit Informationen über jede Erfassung aufgefüllt, wie es der Fall wäre, wenn der Gruppenname nicht dupliziert wäre.  
  
 Im folgenden Beispiel umfasst der reguläre Ausdruck `\D+(?<digit>\d+)\D+(?<digit>\d+)?` zwei Vorkommen einer Gruppe namens `digit`. Die erste mit `digit` benannte Gruppe erfasst ein oder mehrere Ziffernzeichen. Die zweite mit `digit` benannte Gruppe erfasst entweder null oder ein Vorkommen von einem oder mehreren Ziffernzeichen. Wie die Ausgabe des Beispiels zeigt, definiert der Wert dieses Texts, wenn die zweite Erfassungsgruppe erfolgreich mit Text übereinstimmt, den Wert des <xref:System.Text.RegularExpressions.Group> -Objekts. Wenn die zweite Erfassungsgruppe nicht der Eingabezeichenfolge entspricht, definiert der Wert der letzten erfolgreichen Übereinstimmung den Wert des <xref:System.Text.RegularExpressions.Group> -Objekts.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#12](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/duplicate1.cs#12)]
 [!code-vb[RegularExpressions.Language.Grouping#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/duplicate1.vb#12)]  
  
 In der folgenden Tabelle wird gezeigt, wie der reguläre Ausdruck interpretiert wird.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\D+`|Übereinstimmung mit einem oder mehreren Nichtdezimal-Ziffernzeichen.|  
|`(?<digit>\d+)`|Übereinstimmung mit einem oder mehreren Dezimalziffernzeichen. Weisen Sie die Übereinstimmung der Gruppe namens `digit` zu.|  
|`\D+`|Übereinstimmung mit einem oder mehreren Nichtdezimal-Ziffernzeichen.|  
|`(?<digit>\d+)?`|Übereinstimmung mit keinem oder einem Vorkommen mindestens eines Dezimalziffernzeichens. Weisen Sie die Übereinstimmung der Gruppe namens `digit` zu.|  
  
<a name="balancing_group_definition"></a>   
## <a name="balancing-group-definitions"></a>Ausgleichen von Gruppendefinitionen  
 Eine Ausgleichsgruppendefinition löscht die Definition einer zuvor definierten Gruppe und speichert in der aktuellen Gruppe das Intervall zwischen der zuvor definierten Gruppe und der aktuellen Gruppe. Dieses Gruppierungskonstrukt besitzt das folgende Format:  
  
`(?<name1-name2>subexpression)`  
  
 oder:  
  
`(?'name1-name2' subexpression)`
  
 wobei *name1* die aktuelle Gruppe (optional), *name2* eine zuvor definierte Gruppe und *subexpression* ein beliebiges gültiges Muster eines regulären Ausdrucks ist. Die Ausgleichsgruppendefinition löscht die Definition von *name2* und speichert das Intervall zwischen *name2* und *name1* in *name1*. Wenn keine *name2* -Gruppe definiert ist, wird die Übereinstimmung rückwärts verarbeitet. Da durch Löschen der letzten Definition von *name2* die vorherige Definition von *name2*angezeigt wird, kann mithilfe dieses Konstrukts der Erfassungsstapel für die *name2* -Gruppe als Zähler für die Erfassung von geschachtelten Konstrukten, z. B. Anführungszeichen oder öffnende bzw. schließende Klammern, verwendet werden.  
  
 Die Ausgleichsgruppendefinition verwendet *name2* als Stapel. Das Anfangszeichen jedes geschachtelten Konstrukts wird in die Gruppe sowie in die zugehörige <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> -Auflistung eingefügt. Wenn das schließende Zeichen abgeglichen wird, wird das entsprechende öffnende Zeichen aus der Gruppe entfernt, und die <xref:System.Text.RegularExpressions.Group.Captures%2A> -Auflistung wird um eins verringert. Nachdem die öffnenden und schließenden Zeichen aller geschachtelten Konstrukte abgeglichen wurden, ist *name2* leer.  
  
> [!NOTE]
> Nachdem Sie den regulären Ausdruck im folgenden Beispiel geändert haben, sodass er die entsprechenden öffnenden und schließenden Zeichen eines geschachtelten Konstrukts enthält, können Sie diesen zur Behandlung der meisten geschachtelten Konstrukte verwenden, z. B. für mathematische Ausdrücke oder Programmcodezeilen, die mehrere geschachtelte Methodenaufrufe enthalten.  
  
 Das folgende Codebeispiel verwendet eine Ausgleichsgruppendefinition, um in einer Eingabezeichenfolge nach öffnenden und schließenden spitzen Klammern (<>) zu suchen. Im Beispiel werden zwei benannte Gruppen, `Open` und `Close`, definiert, die wie ein Stapel verwendet werden, um übereinstimmende Paare von spitzen Klammern nachzuverfolgen. Jede erfasste öffnende spitze Klammer wird in die Erfassungsauflistung der `Open` -Gruppe eingefügt, und jede erfasste schließende spitze Klammer wird in die Erfassungsauflistung der `Close` -Gruppe eingefügt. Die Ausgleichsgruppendefinition stellt sicher, dass es eine entsprechende schließende spitze Klammer für jede öffnende spitze Klammer gibt. Trifft dies nicht zu, wird das abschließende Teilmuster, `(?(Open)(?!))`, nur ausgewertet, wenn die `Open` -Gruppe nicht leer ist (und wenn alle geschachtelten Konstrukte nicht geschlossen wurden). Wenn das endgültige Teilmuster ausgewertet wird, schlägt die Übereinstimmung fehl, da das `(?!)` Teilmuster eine negative Lookaheadassertion mit einer Breite von 0 (null) ist, die immer fehlschlägt.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/grouping3.cs#3)]
 [!code-vb[RegularExpressions.Language.Grouping#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/grouping3.vb#3)]  
  
 Das Muster des regulären Ausdrucks lautet:  
  
`^[^<>]*(((?'Open'<)[^<>]*)+((?'Close-Open'>)[^<>]*)+)*(?(Open)(?!))$`  
  
 Der reguläre Ausdruck wird wie folgt interpretiert:  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`^`|Starten Sie am Beginn der Zeichenfolge.|  
|`[^<>]*`|Finden Sie eine Entsprechung für null oder mehr Zeichen, die keine linken oder rechten spitzen Klammern sind.|  
|`(?'Open'<)`|Suchen Sie eine Übereinstimmung für ein kleiner als-Zeichen, und weisen Sie es einer Gruppe mit dem Namen `Open`zu.|  
|`[^<>]*`|Finden Sie eine Entsprechung für null oder mehr Zeichen, die keine linken oder rechten spitzen Klammern sind.|  
|`((?'Open'<)[^<>]*)+`|Finden Sie eine Entsprechung für ein oder mehr Vorkommen einer linken spitzen Klammer, gefolgt von null oder mehr Zeichen, die keine linken oder rechten spitzen Klammern sind. Dies ist die zweite Erfassungsgruppe.|  
|`(?'Close-Open'>)`|Finden Sie eine Entsprechung für eine öffnende spitze Klammer, weisen Sie die Teilzeichenfolge zwischen der `Open` -Gruppe und der aktuellen Gruppe der `Close` -Gruppe zu, und löschen Sie die Definition der `Open` -Gruppe.|  
|`[^<>]*`|Finden Sie eine Entsprechung für null oder mehr Vorkommen eines die oft ausgegebene Befehlszeilen  Zeichens, das weder eine linke noch eine rechte spitze Klammern ist.|  
|`((?'Close-Open'>)[^<>]*)+`|Finden Sie eine Entsprechung für ein oder mehr Vorkommen einer rechten spitzen Klammer, gefolgt von einem die oft ausgegebene Befehlszeilen  Zeichen, das weder eine linke noch eine rechte spitze Klammern ist. Wenn Sie die öffnende spitze Klammer zuordnen, weisen Sie die Teilzeichenfolge zwischen der `Open` -Gruppe und der aktuellen Gruppe der `Close` -Gruppe zu, und löschen Sie die Definition der `Open` -Gruppe. Dies ist die dritte Erfassungsgruppe.|  
|`(((?'Open'<)[^<>]*)+((?'Close-Open'>)[^<>]*)+)*`|Finden Sie eine Entsprechung für null oder mehr Vorkommen des folgenden Musters: ein oder mehr Vorkommen einer linken spitzen Klammer, gefolgt von null oder mehr Zeichen, die keine spitzen Klammern sind, gefolgt von einem oder mehr Vorkommen einer rechten spitzen Klammer, gefolgt von null oder mehr Vorkommen von nicht spitzen Klammern. Löschen Sie beim Abgleichen der schließenden spitzen Klammer die Definition der `Open` -Gruppe, und weisen Sie der `Open` -Gruppe die Teilzeichenfolge zwischen der `Close` -Gruppe und der aktuellen Gruppe zu. Dies ist die erste Erfassungsgruppe.|  
|`(?(Open)(?!))`|Wenn die `Open`-Gruppe vorhanden ist und eine leere Zeichenfolge abgeglichen werden kann, geben Sie die Übereinstimmung auf, erhöhen Sie dabei jedoch nicht die Position der Engine für den regulären Ausdruck in der Zeichenfolge. Dies ist eine negative Lookaheadassertion mit einer Breite von Null. Da eine leere Zeichenfolge in einer Eingabezeichenfolge immer implizit vorhanden ist, schlägt diese Übereinstimmung immer fehl. Das Fehlschlagen dieser Übereinstimmung weist darauf hin, dass die spitzen Klammern nicht ausgeglichen sind.|  
|`$`|Entsprechung für das Ende der Eingabezeichenfolge finden.|  
  
 Der abschließende Teilausdruck, `(?(Open)(?!))`, gibt an, ob die Schachtelungskonstrukte in der Eingabezeichenfolge ausgeglichen sind (z. B. ob jeder öffnenden spitzen Klammer eine entsprechende schließende spitze Klammer zugeordnet ist). Dabei wird eine bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe verwendet. Weitere Informationen finden Sie unter [Alternation Constructs](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md). Wenn die `Open`-Gruppe definiert ist, versucht die Engine für reguläre Ausdrücke, eine Entsprechung für den `(?!)`-Teilausdruck in der Eingabezeichenfolge zu finden. Die `Open` -Gruppe sollte nur definiert werden, wenn Schachtelungskonstrukte nicht ausgeglichen sind. Daher sollte das in der Eingabezeichenfolge zu findende Muster immer dazu führen, dass die Übereinstimmung fehlschlägt. In diesem Fall ist `(?!)` eine negative Lookaheadassertion mit einer Breite von Null, die immer fehlschlägt, da eine leere Zeichenfolge immer an der nächsten Position in der Eingabezeichenfolge implizit vorhanden ist.  
  
 Bei diesem Beispiel wertet die Engine des regulären Ausdrucks die Eingabezeichenfolge „\<abc&gt;&lt;mno\<xyz&gt;&gt;“ wie in der folgenden Tabelle angezeigt aus.  
  
|Schritt|Muster|Ergebnis|  
|----------|-------------|------------|  
|1|`^`|Beginnt den Abgleich am Anfang der Eingabezeichenfolge|  
|2|`[^<>]*`|Sucht vor der öffnenden spitzen Klammer nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.|  
|3|`(((?'Open'<)`|Findet eine Entsprechung für die öffnende spitze Klammer in „\<abc>“ und weist sie der `Open`-Gruppe zu.|  
|4|`[^<>]*`|Entspricht "abc".|  
|5|`)+`|"<abc" ist der Wert der zweiten erfassten Gruppe.<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist keine öffnende spitze Klammer. Deshalb führt die Engine für reguläre Ausdrücke keine Schleife zurück zum `(?'Open'<)[^<>]*)`-Teilmuster aus.|  
|6|`((?'Close-Open'>)`|Findet eine Entsprechung für die schließende spitze Klammer in „\<abc>“, weist „abc“ (die Teilzeichenfolge zwischen der `Open`-Gruppe und der schließenden spitzen Klammer) der `Close`-Gruppe zu und löscht den aktuellen Wert („<“) der `Open`-Gruppe, der dann leer bleibt.|  
|7|`[^<>]*`|Sucht nach der schließenden spitzen Klammer nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.|  
|8|`)+`|Der Wert der dritten erfassten Gruppe ist ">".<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist keine schließende spitze Klammer. Deshalb führt die Engine für reguläre Ausdrücke keine Schleife zurück zum `((?'Close-Open'>)[^<>]*)`-Teilmuster aus.|  
|9|`)*`|Der Wert der ersten erfassten Gruppe ist „\<abc>“.<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist eine öffnende spitze Klammer, weshalb die Engine für reguläre Ausdrücke eine Schleife zurück zum `(((?'Open'<)` -Teilmuster ausführt.|  
|10|`(((?'Open'<)`|Findet eine Entsprechung für die öffnende spitze Klammer in „\<mno>“ und weist sie der `Open`-Gruppe zu. Die <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Auflistung verfügt jetzt über einen einzelnen Wert "<".|  
|11|`[^<>]*`|Entspricht "mno".|  
|12|`)+`|"<mno" ist der Wert der zweiten erfassten Gruppe.<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist eine öffnende spitze Klammer, weshalb die Engine für reguläre Ausdrücke eine Schleife zurück zum `(?'Open'<)[^<>]*)`-Teilmuster ausführt.|  
|13|`(((?'Open'<)`|Findet eine Entsprechung für die öffnende spitze Klammer in „\<xyz>“ und weist sie der `Open`-Gruppe zu. Die <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Sammlung der `Open`-Gruppe schließt jetzt zwei Erfassungen ein: die öffnende spitze Klammer von „\<mno>“ und die öffnende spitze Klammer von „\<xyz>“.|  
|14|`[^<>]*`|Entspricht "xyz".|  
|15|`)+`|"<xyz" ist der Wert der zweiten erfassten Gruppe.<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist keine öffnende spitze Klammer. Deshalb führt die Engine für reguläre Ausdrücke keine Schleife zurück zum `(?'Open'<)[^<>]*)`-Teilmuster aus.|  
|16|`((?'Close-Open'>)`|Findet eine Übereinstimmung für die schließende spitze Klammer in „\<xyz>“. „xyz“ weist die Teilzeichenfolge zwischen der `Open` -Gruppe und der schließenden spitzen Klammer der `Close` -Gruppe zu und löscht den aktuellen Wert der `Open` -Gruppe. Der Wert der vorherigen Erfassung (die öffnende spitze Klammer in „\<mno>“) wird zum aktuellen Wert der `Open`-Gruppe. Die <xref:System.Text.RegularExpressions.Group.Captures%2A>-Auflistung der `Open`-Gruppe schließt jetzt eine einzelne Erfassung ein, die öffnende spitze Klammer von „\<xyz>“.|  
|17|`[^<>]*`|Sucht nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.|  
|18|`)+`|Der Wert der dritten erfassten Gruppe ist ">".<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist eine schließende spitze Klammer, weshalb die Engine für reguläre Ausdrücke eine Schleife zurück zum `((?'Close-Open'>)[^<>]*)`-Teilmuster ausführt.|  
|19|`((?'Close-Open'>)`|Findet eine Entsprechung für die abschließende rechte spitze Klammer in „xyz>>“, weist „mno\<xyz>“ (die Teilzeichenfolge zwischen der `Open`-Gruppe und der schließenden spitzen Klammer) der `Close`-Gruppe zu und löscht den aktuellen Wert der `Open`-Gruppe. Die `Open` -Gruppe ist jetzt leer.|  
|20|`[^<>]*`|Sucht nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.|  
|21|`)+`|Der Wert der dritten erfassten Gruppe ist ">".<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist keine schließende spitze Klammer. Deshalb führt die Engine für reguläre Ausdrücke keine Schleife zurück zum `((?'Close-Open'>)[^<>]*)`-Teilmuster aus.|  
|22|`)*`|Der Wert der ersten erfassten Gruppe ist „<mno\<xyz>“.<br /><br /> Das nächste Zeichen in der Eingabezeichenfolge ist keine öffnende spitze Klammer. Deshalb führt die Engine für reguläre Ausdrücke keine Schleife zurück zum `(((?'Open'<)`-Teilmuster aus.|  
|23|`(?(Open)(?!))`|Die `Open` -Gruppe ist nicht definiert, sodass keine Übereinstimmung gesucht wird.|  
|24|`$`|Gleicht das Ende der Eingabezeichenfolge ab.|  
  
<a name="noncapturing_group"></a>   
## <a name="noncapturing-groups"></a>Nicht erfassende Gruppen  
 Das folgende Gruppierungskonstrukt erfasst nicht die Teilzeichenfolge, die zu einem Teilausdruck passt:  
  
`(?:subexpression)`
  
 wobei *Teilausdruck* ein beliebiges gültiges Muster eines regulären Ausdrucks ist. Das nicht erfassende Gruppenkonstrukt wird in der Regel verwendet, wenn ein Quantifizierer auf eine Gruppe angewendet wird, die von der Gruppe erfassten Teilzeichenfolgen jedoch nicht von Interesse sind.  
  
> [!NOTE]
> Wenn ein regulärer Ausdruck geschachtelte Gruppierungskonstrukte einschließt, gilt ein äußeres nicht erfassendes Gruppenkonstrukt nicht für die inneren geschachtelten Gruppenkonstrukte.  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck veranschaulicht, der nicht erfassende Gruppen einschließt. Beachten Sie, dass die Ausgabe keine erfassten Gruppen einschließt.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/noncapture1.cs#5)]
 [!code-vb[RegularExpressions.Language.Grouping#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/noncapture1.vb#5)]  
  
 Der reguläre Ausdruck `(?:\b(?:\w+)\W*)+\.` stimmt mit einem Satz überein, der durch einen Punkt beendet wird. Da sich der reguläre Ausdruck auf Sätze konzentriert und nicht auf einzelne Wörter, werden Gruppierungskonstrukte ausschließlich als Quantifizierer verwendet. Das Muster für reguläre Ausdrücke wird entsprechend der folgenden Tabelle interpretiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(?:\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Weisen Sie einer erfassten Gruppe den entsprechenden Text nicht zu.|  
|`\W*`|Suchen Sie nach einer Übereinstimmung mit null oder mehr Nicht-Wortzeichen.|  
|`(?:\b(?:\w+)\W*)+`|Suchen Sie nach einer Übereinstimmung für das Muster aus einem oder mehreren Wortzeichen, beginnend bei einer Wortgrenze und gefolgt von null oder mehr Nicht-Wortzeichen (ein oder zwei Mal). Weisen Sie einer erfassten Gruppe den entsprechenden Text nicht zu.|  
|`\.`|Entsprechung für einen Punkt finden.|  
  
<a name="group_options"></a>   
## <a name="group-options"></a>Gruppenoptionen  
 Das folgende Gruppierungskonstrukt wendet die angegebenen Optionen in einem Teilausdruck an oder deaktiviert sie:  
  
 `(?imnsx-imnsx:` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges gültiges Muster eines regulären Ausdrucks ist. Beispielsweise aktiviert `(?i-s:)` die Einstellung, dass Groß-/Kleinschreibung nicht beachtet wird, und deaktiviert den Einzeilenmodus. Weitere Informationen zu den möglichen Inlineoptionen finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
> [!NOTE]
> Sie können Optionen angeben, die für einen vollständigen regulären Ausdruck und nicht für einen Teilausdruck gültig sind. Verwenden Sie dazu einen <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> -Klassenkonstruktor oder eine statische Methode. Sie können auch Inlineoptionen angeben, die nach einem bestimmten Punkt in einem regulären Ausdruck gelten. Verwenden Sie dazu das `(?imnsx-imnsx)` -Sprachkonstrukt.  
  
 Das Konstrukt für die Gruppenoptionen ist keine Erfassungsgruppe. Obwohl ein beliebiger Teil einer Zeichenfolge, die von *subexpression* erfasst wird, in der Übereinstimmung enthalten ist, ist sie weder in einer erfassten Gruppe enthalten, noch wird sie dazu verwendet, das <xref:System.Text.RegularExpressions.GroupCollection> -Objekt aufzufüllen.  
  
 Beispiel: Der reguläre Ausdruck `\b(?ix: d \w+)\s` verwendet Inlineoptionen in einem Gruppierungskonstrukt, um die Groß-/Kleinschreibung nicht beachtende Übereinstimmung zu aktivieren und Musterleerstellen beim Identifizieren aller Wörter zu ignorieren, die mit dem Buchstaben „d“ beginnen. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle definiert:  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(?ix: d \w+)`|In diesem Muster wird Übereinstimmung ohne Berücksichtigung von Groß- und Kleinschreibung verwendet, und Leerzeichen werden ignoriert (entspricht dem Buchstaben "d" gefolgt von mindestens einem Wortzeichen).|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
  
 [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
 [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]  
  
<a name="zerowidth_positive_lookahead_assertion"></a>   
## <a name="zero-width-positive-lookahead-assertions"></a>Positive Lookaheadassertionen mit einer Breite von Null  
 Das folgende Gruppierungskonstrukt definiert eine positive Lookaheadassertion mit einer Breite von Null:  
  
 `(?=` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges Muster eines regulären Ausdrucks ist. Damit eine Übereinstimmung erfolgreich ist, muss die Eingabezeichenfolge mit dem regulären Ausdrucksmuster in *subexpression*übereinstimmen, obwohl der übereinstimmende Teilausdruck nicht im Übereinstimmungsergebnis enthalten ist. Eine positive Lookaheadassertion mit einer Breite von Null wird nicht zurückverfolgt.  
  
 In der Regel befindet sich eine positive Lookaheadassertion mit einer Breite von Null am Ende eines Musters eines regulären Ausdrucks. Damit wird eine Teilzeichenfolge definiert, die am Ende einer Zeichenfolge gefunden werden muss, damit eine Übereinstimmung vorliegt, jedoch nicht in der Übereinstimmung enthalten sein soll. Dies ist auch zum Verhindern einer übermäßigen Rückverfolgung nützlich. Sie können eine Lookaheadassertion mit einer Breite von Null verwenden, um sicherzustellen, dass eine bestimmte Erfassungsgruppe mit Text beginnt, der einer Teilmenge des Musters entspricht, das für diese Erfassungsgruppe definiert ist. Wenn z. B. eine Erfassungsgruppe aufeinander folgenden Wortzeichen entspricht, können Sie mit einer positiven Lookaheadassertion mit einer Breite von Null anfordern, dass das erste Zeichen ein alphabetischer Großbuchstabe ist.  
  
 Im folgenden Beispiel wird mithilfe einer positiven Lookaheadassertion mit einer Breite von Null eine Entsprechung für das Wort gesucht, das dem Verb "is" in der Eingabezeichenfolge vorausgeht.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#6](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/lookahead1.cs#6)]
 [!code-vb[RegularExpressions.Language.Grouping#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/lookahead1.vb#6)]  
  
 Der reguläre Ausdruck `\b\w+(?=\sis\b)` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`(?=\sis\b)`|Bestimmen Sie, ob den Wortzeichen ein Leerstellenzeichen und die Zeichenfolge "is" folgt, die bei einer Wortgrenze endet. Trifft dies zu, ist die Übereinstimmung erfolgreich.|  
  
<a name="zerowidth_negative_lookahead_assertion"></a>   
## <a name="zero-width-negative-lookahead-assertions"></a>Negative Lookaheadassertionen mit einer Breite von Null  
 Das folgende Gruppierungskonstrukt definiert eine negative Lookaheadassertion mit einer Breite von Null:  
  
 `(?!` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges Muster eines regulären Ausdrucks ist. Damit die Übereinstimmung erfolgreich ist, darf die Eingabezeichenfolge mit dem regulären Ausdrucksmuster in *subexpression*nicht übereinstimmen, obwohl die übereinstimmende Zeichenfolge nicht im Übereinstimmungsergebnis enthalten ist.  
  
 Eine negative Lookaheadassertion mit einer Breite von Null wird in der Regel entweder am Anfang oder dem Ende eines regulären Ausdrucks verwendet. Am Anfang eines regulären Ausdrucks kann ein bestimmtes Muster definiert werden, das nicht zugewiesen werden soll, wenn der Anfang des regulären Ausdrucks ein ähnliches aber allgemeineres Muster zur Übereinstimmung definiert. In diesem Fall wird dies häufig verwendet, um das Zurückverfolgen einzuschränken. Am Ende eines regulären Ausdrucks kann ein Teilausdruck definiert werden, der am Ende einer Übereinstimmung nicht auftreten darf.  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck definiert, der am Anfang des regulären Ausdrucks eine Lookaheadassertion mit einer Breite von Null verwendet, um eine Entsprechung für Wörter zu finden, die nicht mit "un" beginnen.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#7](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/negativelookahead1.cs#7)]
 [!code-vb[RegularExpressions.Language.Grouping#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/negativelookahead1.vb#7)]  
  
 Der reguläre Ausdruck `\b(?!un)\w+\b` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(?!un)`|Es wird bestimmt, ob die nächsten zwei Zeichen "un" sind. Trifft dies nicht zu, ist eine Übereinstimmung möglich.|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck definiert, der am Ende eine Lookaheadassertion mit einer Breite von Null verwendet, um eine Entsprechung für Wörter zu finden, die nicht mit einem Interpunktionszeichen enden.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#8](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/negativelookahead2.cs#8)]
 [!code-vb[RegularExpressions.Language.Grouping#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/negativelookahead2.vb#8)]  
  
 Der reguläre Ausdruck `\b\w+\b(?!\p{P})` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
|`\p{P})`|Wenn das nächste Zeichen kein Interpunktionszeichen (z. B. ein Punkt oder ein Komma) ist, ist die Übereinstimmung erfolgreich.|  
  
<a name="zerowidth_positive_lookbehind_assertion"></a>   
## <a name="zero-width-positive-lookbehind-assertions"></a>Positive Lookbehindassertionen mit einer Breite von Null  
 Das folgende Gruppierungskonstrukt definiert eine positive Lookbehindassertion mit einer Breite von Null:  
  
 `(?<=` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges Muster eines regulären Ausdrucks ist. Damit eine Übereinstimmung erfolgreich ist, muss der *subexpression* in der Eingabezeichenfolge links von der aktuellen Position auftreten, obwohl `subexpression` nicht im Übereinstimmungsergebnis enthalten ist. Eine positive Lookbehindassertion mit einer Breite von Null wird nicht zurückverfolgt.  
  
 Positive Lookbehindassertionen mit einer Breite von Null werden in der Regel entweder am Anfang oder am Ende von regulären Ausdrücken verwendet. Das Muster, das sie definieren, ist eine Vorbedingung für eine Übereinstimmung, obwohl es kein Teil des Übereinstimmungsergebnisses ist.  
  
 Im folgenden Beispiel wird eine Entsprechung für die letzten zwei Ziffern des Jahres für das 21. Jahrhundert (das heißt, es ist erforderlich, dass die Ziffern "20" der entsprechenden Zeichenfolge vorausgehen) gefunden.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#9](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/lookbehind1.cs#9)]
 [!code-vb[RegularExpressions.Language.Grouping#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/lookbehind1.vb#9)]  
  
 Das Muster für reguläre Ausdrücke `(?<=\b20)\d{2}\b` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\d{2}`|Entsprechung für zwei Dezimalstellen finden.|  
|`(?<=\b20)`|Die Übereinstimmung wird fortgesetzt, wenn den zwei Dezimalstellen die Dezimalstellen "20" bei einer Wortgrenze vorangestellt sind.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Positive Lookbehindassertions mit einer Breite von Null werden auch verwendet, um das Zurückverfolgen einzuschränken, wenn die letzten Zeichen in einer Erfassungsgruppe eine Teilmenge der Zeichen sein müssen, die dem Muster eines regulären Ausdrucks dieser Gruppe entsprechen. Wenn beispielsweise eine Gruppe alle aufeinander folgenden Wortzeichen erfasst, können Sie mit einer positiven Lookaheadassertion mit einer Breite von Null anfordern, dass das letzte Zeichen alphabetisch ist.  
  
<a name="zerowidth_negative_lookbehind_assertion"></a>   
## <a name="zero-width-negative-lookbehind-assertions"></a>Negative Lookbehindassertionen mit einer Breite von Null  
 Das folgende Gruppierungskonstrukt definiert eine negative Lookbehindassertion mit einer Breite von Null:  
  
 `(?<!` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges Muster eines regulären Ausdrucks ist. Damit eine Übereinstimmung erfolgreich ist, darf der *subexpression* nicht in der Eingabezeichenfolge links von der aktuellen Position auftreten. Jede Teilzeichenfolge, die nicht mit `subexpression` übereinstimmt, ist nicht im Übereinstimmungsergebnis enthalten.  
  
 Negative Lookbehindassertionen mit einer Breite von Null werden in der Regel entweder am Anfang oder am Ende von regulären Ausdrücken verwendet. Das Muster, das sie definieren, schließt eine Übereinstimmung in der darauf folgenden Zeichenfolge aus. Sie werden auch verwendet, um die Rückverfolgung einzuschränken, wenn die letzten Zeichen in einer erfassten Gruppe keine Zeichen sein dürfen, die dem Muster eines regulären Ausdrucks dieser Gruppe entsprechen. Wenn beispielsweise eine Gruppe alle aufeinander folgenden Wortzeichen erfasst, können Sie mit einer positiven Lookbehindassertion mit einer Breite von 0 (null) anfordern, dass das letzte Zeichen kein Unterstrich (\_) ist.  
  
 Im folgenden Beispiel wird eine Entsprechung für das Datum eines die oft ausgegebene Befehlszeilen  Wochentags gesucht, der nicht auf das Wochenende (das heißt weder Samstag noch Sonntag) fällt.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#10](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/negativelookbehind1.cs#10)]
 [!code-vb[RegularExpressions.Language.Grouping#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/negativelookbehind1.vb#10)]  
  
 Das Muster für reguläre Ausdrücke `(?<!(Saturday|Sunday) )\b\w+ \d{1,2}, \d{4}\b` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`\w+`|Suchen Sie nach einer Übereinstimmung mit einem oder mehreren Wortzeichen gefolgt von einem Leerzeichen.|  
|`\d{1,2},`|Finden Sie eine Entsprechung für entweder eine oder zwei Dezimalstellen, gefolgt von einem Leerstellenzeichen und einem Komma.|  
|`\d{4}\b`|Finden Sie eine Entsprechung für vier Dezimalstellen, und beenden Sie die Übereinstimmung an einer Wortgrenze.|  
|<code>(?<!(Saturday&#124;Sunday) )</code>|Wenn der Übereinstimmung etwas anderes als die Zeichenfolgen "Samstag" oder "Sonntag" (gefolgt von einem Leerzeichen) vorangestellt wird, ist die Übereinstimmung erfolgreich.|  
  
<a name="nonbacktracking_subexpression"></a>   
## <a name="nonbacktracking-subexpressions"></a>Nicht zurückverfolgende Teilausdrücke  
 Das folgende Gruppierungskonstrukt stellt einen nicht zurückverfolgenden Teilausdruck (auch bekannt als "gieriger" Teilausdruck) dar:  
  
 `(?>` *Teilausdruck* `)`  
  
 wobei *Teilausdruck* ein beliebiges Muster eines regulären Ausdrucks ist.  
  
 Wenn ein regulärer Ausdruck ein optionales oder alternatives übereinstimmendes Muster einschließt und eine Übereinstimmung nicht erfolgreich ist, kann sich die Engine für reguläre Ausdrücke in mehrere Richtungen verzweigen, um eine Entsprechung zwischen einer Eingabezeichenfolge und einem Muster zu finden. Wenn eine Übereinstimmung nach der ersten Verzweigung nicht gefunden wird, kann die Engine für reguläre Ausdrücke den Punkt der ersten Übereinstimmung sichern bzw. den Punkt zurückverfolgen und die Übereinstimmung mithilfe der zweiten Verzweigung durchführen. Dieser Prozess kann fortgesetzt werden, bis alle Verzweigungen versucht wurden.  
  
 Die `(?>`*Teilausdruck*`)` deaktiviert die Rückverfolgung. Die Engine für reguläre Ausdrücke stimmt mit so vielen Zeichen in der Eingabezeichenfolge überein wie möglich. Wenn keine weitere Übereinstimmung möglich ist, findet keine Rückverfolgung statt, um alternative Musterübereinstimmungen zu versuchen. (Das heißt, der Teilausdruck sucht nur Entsprechungen für Zeichenfolgen, zu denen der Teilausdruck allein passen würde. Er versucht nicht, eine Entsprechung für eine Zeichenfolge auf Grundlage des Teilausdrucks und beliebige folgende Teilausdrücke zu finden.)  
  
 Diese Option wird empfohlen, wenn Sie wissen, dass eine Rückverfolgung nicht erfolgreich ist. Indem verhindert wird, dass von der Engine für reguläre Ausdrücke unnötige Suchläufe durchgeführt werden, wird die Leistung verbessert.  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein nicht zurückverfolgender Teilausdruck die Ergebnisse einer Musterübereinstimmung ändert. Der rückverfolgende reguläre Ausdruck findet erfolgreich eine Entsprechung für eine Reihe von Zeichen, die von einem weiteren Vorkommen des gleichen Zeichens bei einer Wortgrenze gefolgt wird. Beim regulären Ausdruck ohne Rückverfolgung ist dies nicht der Fall.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#11](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/nonbacktracking1.cs#11)]
 [!code-vb[RegularExpressions.Language.Grouping#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/nonbacktracking1.vb#11)]  
  
 Der nicht zurückverfolgende reguläre Ausdruck `(?>(\w)\1+).\b` wird entsprechend der folgenden Tabelle definiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`(\w)`|Finden Sie eine Entsprechung für ein einzelnes Wortzeichen, und weisen Sie es der ersten Erfassungsgruppe zu.|  
|`\1+`|Finden Sie mindestens eine Entsprechung für die erste erfasste Teilzeichenfolge.|  
|`.`|Finden Sie eine Entsprechung für ein beliebiges Zeichen.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
|`(?>(\w)\1+)`|Finden Sie eine Entsprechung für ein oder mehrere Vorkommen eines duplizierten Wortzeichens, führen Sie jedoch keine Rückverfolgung aus, um für das letzte Zeichen bei einer Wortgrenze eine Entsprechung zu finden.|  
  
<a name="Objects"></a>   
## <a name="grouping-constructs-and-regular-expression-objects"></a>Gruppieren von Konstrukten und Objekten für reguläre Ausdrücke  
 Teilzeichenfolgen, die von einer Erfassungsgruppe für reguläre Ausdrücke abgeglichen werden, werden durch <xref:System.Text.RegularExpressions.Group?displayProperty=nameWithType> -Objekte dargestellt, die aus dem <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> -Objekt abgerufen werden können, das von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird. Das <xref:System.Text.RegularExpressions.GroupCollection> -Objekt wird folgendermaßen aufgefüllt:  
  
- Das erste <xref:System.Text.RegularExpressions.Group> -Objekt in der Auflistung (das Objekt bei Index 0) stellt die gesamte Übereinstimmung dar.  
  
- Der nächste Satz von <xref:System.Text.RegularExpressions.Group> -Objekten stellt unbenannte (nummerierte) Erfassungsgruppen dar. Sie werden in der Reihenfolge angezeigt, in der sie im regulären Ausdruck definiert sind (von links nach rechts). Die Indexwerte dieser Gruppen reichen von 1 bis zur Anzahl unbenannter Erfassungsgruppen in der Auflistung. (Der Index einer bestimmten Gruppe entspricht seinem nummerierten Rückverweis. Weitere Informationen zu Rückverweisen finden Sie unter [Backreference Constructs](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).)  
  
- Der endgültige Satz von <xref:System.Text.RegularExpressions.Group> -Objekten stellt benannte Erfassungsgruppen dar. Sie werden in der Reihenfolge angezeigt, in der sie im regulären Ausdruck definiert sind (von links nach rechts). Der Indexwert der zuerst benannten Erfassungsgruppe ist um eins größer als der Index der letzten unbenannten Erfassungsgruppe. Wenn es keine unbenannten Erfassungsgruppen im regulären Ausdruck gibt, ist der Indexwert der zuerst benannten Erfassungsgruppe gleich eins.  
  
 Wenn Sie einen Quantifizierer auf eine Erfassungsgruppe anwenden, reflektieren die entsprechenden <xref:System.Text.RegularExpressions.Group> -, <xref:System.Text.RegularExpressions.Capture.Value%2A?displayProperty=nameWithType>- und <xref:System.Text.RegularExpressions.Capture.Index%2A?displayProperty=nameWithType>-Eigenschaften des <xref:System.Text.RegularExpressions.Capture.Length%2A?displayProperty=nameWithType> -Objekts die letzte Teilzeichenfolge, die von einer Erfassungsgruppe erfasst wird. Sie können einen vollständigen Satz von Teilzeichenfolgen abrufen, die von Gruppen erfasst werden, die Quantifizierer vom <xref:System.Text.RegularExpressions.CaptureCollection> -Objekt besitzen, das von der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wird.  
  
 Im folgenden Beispiel wird die Beziehung zwischen den <xref:System.Text.RegularExpressions.Group> - und <xref:System.Text.RegularExpressions.Capture> -Objekten veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/objectmodel1.cs#4)]
 [!code-vb[RegularExpressions.Language.Grouping#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/objectmodel1.vb#4)]  
  
 Das Muster eines regulären Ausdrucks `(\b(\w+)\W+)+` extrahiert einzelne Wörter aus einer Zeichenfolge. Das Muster wird wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|BESCHREIBUNG|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Zusammen bilden diese Zeichen ein Wort. Dies ist die zweite Erfassungsgruppe.|  
|`\W+`|Entsprechung für mindestens ein Nicht-Wortzeichen finden.|  
|`(\b(\w+)\W+)`|Suchen Sie nach einer Übereinstimmung für das Muster aus einem oder mehreren Wortzeichen, gefolgt von einem oder mehreren Nicht-Wortzeichen (ein oder zwei Mal). Dies ist die erste Erfassungsgruppe.|  
  
 Die zweite Erfassungsgruppe stimmt mit jedem Wort des Satzes überein. Die erste Erfassungsgruppe stimmt mit jedem Wort sowie der Interpunktion und dem Leerraum überein, der auf die Worte folgt. Das <xref:System.Text.RegularExpressions.Group> -Objekt, dessen Index 2 ist, stellt Informationen zu dem Text bereit, der mit der zweiten Erfassungsgruppe übereinstimmt. Der vollständige Satz von Wörtern, die von der Erfassungsgruppe erfasst wurden, ist vom <xref:System.Text.RegularExpressions.CaptureCollection> -Objekt verfügbar, das von der <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> -Eigenschaft zurückgegeben wurde.  
  
## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
