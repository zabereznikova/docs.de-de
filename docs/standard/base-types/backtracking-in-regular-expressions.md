---
title: Rückverfolgung in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie die Rückverfolgung beim Musterabgleich regulärer Ausdrücke steuern.
ms.date: 11/12/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- .NET Framework regular expressions, backtracking
- alternative matching patterns
- optional matching patterns
- searching with regular expressions, backtracking
- pattern-matching with regular expressions, backtracking
- backtracking
- regular expressions [.NET Framework], backtracking
- strings [.NET Framework], regular expressions
- parsing text with regular expressions, backtracking
ms.assetid: 34df1152-0b22-4a1c-a76c-3c28c47b70d8
ms.openlocfilehash: d9fb976c73891646df60b5329beb09493acbae8a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277803"
---
# <a name="backtracking-in-regular-expressions"></a>Backtracking in regulären Ausdrücken
Eine Rückverfolgung tritt ein, wenn ein Muster eines regulären Ausdrucks optionale [Quantifizierer](quantifiers-in-regular-expressions.md) oder [Alternierungskonstrukte](alternation-constructs-in-regular-expressions.md) enthält und die Engine für reguläre Ausdrücke in einen zuvor gespeicherten Zustand zurückkehrt, um die Suche nach einer Übereinstimmung fortzusetzen. Die Rückverfolgung ist für die Leistungsfähigkeit regulärer Ausdrücke von zentraler Bedeutung. Sie ermöglicht flexible und leistungsstarke Ausdrücke, die höchst komplexen Muster entsprechen können. Diese Leistungsfähigkeit zieht aber auch Nachteile mit sich. Die Rückverfolgung ist häufig der wichtigste Faktor, der sich auf die Leistung der Engine für reguläre Ausdrücke auswirkt. Der Entwickler kann jedoch steuern, wie sich die Engine für reguläre Ausdrücke verhält und wie die Rückverfolgung verwendet wird. In diesem Thema wird erläutert, wie die Rückverfolgung funktioniert und wie sie gesteuert werden kann.  
  
> [!NOTE]
> Bei einer NFA-Engine (Nondeterministic Finite Automaton) wie der .NET-Engine für reguläre Ausdrücke liegt die Verantwortung für die Erstellung effizienter und schneller regulärer Ausdrücke im Allgemeinen beim Entwickler.  

## <a name="linear-comparison-without-backtracking"></a>Linearer Vergleich ohne Rückverfolgung  
 Wenn das Muster eines regulären Ausdrucks nicht über optionale Quantifizierer oder Alternierungskonstrukte verfügt, wird die Engine für reguläre Ausdrücke zeitlich linear ausgeführt. Das heißt, nachdem die Engine für reguläre Ausdrücke dem ersten Sprachelement im Muster Text in der Eingabezeichenfolge zugeordnet hat, wird versucht, das nächste Sprachelement im Muster dem nächsten Zeichen oder der nächsten Zeichengruppe in der Eingabezeichenfolge zuzuordnen. Dies wird fortgesetzt, bis die Übereinstimmung erfolgreich ausgeführt wurde oder fehlschlägt. In beiden Fällen wechselt die Engine für reguläre Ausdrücke immer je ein Zeichen in der Eingabezeichenfolge weiter.  
  
 Dies wird im folgenden Beispiel veranschaulicht. Der reguläre Ausdruck `e{2}\w\b` sucht nach zwei Vorkommen des Buchstabens "e", gefolgt von einem beliebigen Wortzeichen, wiederum gefolgt von einer Wortgrenze.  
  
 [!code-csharp[Conceptual.RegularExpressions.Backtracking#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/cs/backtracking1.cs#1)]
 [!code-vb[Conceptual.RegularExpressions.Backtracking#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/vb/backtracking1.vb#1)]  
  
 Obwohl dieser reguläre Ausdruck den Quantifizierer `{2}`einschließt, wird er auf lineare Weise ausgewertet. Die Engine für reguläre Ausdrücke wird nicht zurückverfolgt, da `{2}` kein optionaler Quantifizierer ist, sondern eine genaue Zahl angibt und keine variable Anzahl von Übereinstimmungen des vorherigen Teilausdrucks. Daher versucht die Engine für reguläre Ausdrücke, eine Übereinstimmung des regulären Ausdrucksmusters mit der Eingabezeichenfolge wie in der folgenden Tabelle dargestellt zu finden.  
  
|Vorgang|Position im Muster|Position in der Zeichenfolge|Ergebnis|  
|---------------|-------------------------|------------------------|------------|  
|1|e|"needing a reed" (Index 0)|Keine Übereinstimmung.|  
|2|e|"eeding a reed" (Index 1)|Mögliche Übereinstimmung.|  
|3|e{2}|"eding a reed" (Index 2)|Mögliche Übereinstimmung.|  
|4|\w|"ding a reed" (Index 3)|Mögliche Übereinstimmung.|  
|5|\b|"ing a reed" (Index 4)|Mögliche Übereinstimmung schlägt fehl.|  
|6|e|"eding a reed" (Index 2)|Mögliche Übereinstimmung.|  
|7|e{2}|"ding a reed" (Index 3)|Mögliche Übereinstimmung schlägt fehl.|  
|8|e|"ding a reed" (Index 3)|Übereinstimmung schlägt fehl.|  
|9|e|"ing a reed" (Index 4)|Keine Übereinstimmung.|  
|10|e|"ng a reed" (Index 5)|Keine Übereinstimmung.|  
|11|e|"g a reed" (Index 6)|Keine Übereinstimmung.|  
|12|e|" a reed" (Index 7)|Keine Übereinstimmung.|  
|13|e|"a reed" (Index 8)|Keine Übereinstimmung.|  
|14|e|" reed" (Index 9)|Keine Übereinstimmung.|  
|15|e|"a reed" (Index 10)|Keine Übereinstimmung|  
|16|e|"eed" (Index 11)|Mögliche Übereinstimmung.|  
|17|e{2}|"ed" (Index 12)|Mögliche Übereinstimmung.|  
|18|\w|"d" (Index 13)|Mögliche Übereinstimmung.|  
|19|\b|"" (Index 14)|Übereinstimmung.|  
  
 Wenn das Muster eines regulären Ausdrucks keine optionalen Quantifizierer oder Alternierungskonstrukte enthält, entspricht die maximale Anzahl von Vergleichen, die für die Übereinstimmung des regulären Ausdrucksmusters mit der Eingabezeichenfolge erforderlich sind, ungefähr der Anzahl der Zeichen in der Eingabezeichenfolge. In diesem Fall verwendet die Engine für reguläre Ausdrücke 19 Vergleiche, um mögliche Übereinstimmungen in dieser Zeichenfolge mit 13 Zeichen zu identifizieren.  Mit anderen Worten, die Engine für reguläre Ausdrücke wird zeitlich annähernd linear ausgeführt, wenn sie keine optionalen Quantifizierer oder Alternierungskonstrukte enthält.

## <a name="backtracking-with-optional-quantifiers-or-alternation-constructs"></a>Rückverfolgung mit optionalen Quantifizierern oder Alternierungskonstrukten  
 Wenn ein regulärer Ausdruck optionale Quantifizierer oder Alternierungskonstrukte enthält, erfolgt die Auswertung der Eingabezeichenfolge nicht mehr linear. Mustervergleiche mit einer NFA-Engine werden durch die Sprachelemente im regulären Ausdruck und nicht durch die Zeichen gesteuert, für die in der Eingabezeichenfolge Übereinstimmungen gefunden werden sollen. Daher versucht die Engine für reguläre Ausdrücke, vollständige Übereinstimmungen für die optionalen oder alternativen Teilausdrücke zu finden. Wenn zum nächsten Sprachelement im Teilausdruck gewechselt und keine Übereinstimmung gefunden wird, kann die Engine für reguläre Ausdrücke einen Teil der erfolgreichen Übereinstimmung aufgeben und zu einem zuvor gespeicherten Zustand zurückkehren, um eine Übereinstimmung des gesamten regulären Ausdrucks mit der Eingabezeichenfolge zu erzielen. Dieses Zurückkehren zu einem zuvor gespeicherten Zustand, um eine Übereinstimmung zu finden, wird als Rückverfolgung bezeichnet.  
  
 Als Beispiel dient das reguläre Ausdrucksmuster `.*(es)`, das mit den Zeichen "es" und allen vorangestellten Zeichen übereinstimmt. Wenn die Eingabezeichenfolge "Essential services are provided by regular expressions." lautet, wird die gesamte Zeichenfolge bis einschließlich der Zeichen "es" im Wort "expressions" nach einer Übereinstimmung mit dem Muster durchsucht.  
  
 [!code-csharp[Conceptual.RegularExpressions.Backtracking#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/cs/backtracking2.cs#2)]
 [!code-vb[Conceptual.RegularExpressions.Backtracking#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/vb/backtracking2.vb#2)]  
  
 Hierzu verwendet die Engine für reguläre Ausdrücke das Zurückverfolgen wie folgt:  
  
- Die gesamte Eingabezeichenfolge wird auf Übereinstimmung mit `.*` (Übereinstimmung mit keinem, einem oder mehreren Vorkommen beliebiger Zeichen) geprüft.  
  
- Es wird versucht, eine Übereinstimmung mit "e" im Muster des regulären Ausdrucks zu finden. Die Eingabezeichenfolge weist jedoch keine weiteren Zeichen für eine Übereinstimmung auf.  
  
- Es wird eine Rückverfolgung zur letzten erfolgreichen Übereinstimmung ausgeführt ("Essential services are provided by regular expressions") und versucht, eine Übereinstimmung von "e" mit dem Punkt am Satzende zu finden. Die Übereinstimmung schlägt fehl.  
  
- Die Rückverfolgung zu einer vorherigen erfolgreichen Übereinstimmung wird um je ein Zeichen fortgesetzt, bis die vorläufige übereinstimmende Teilzeichenfolge "Essential services are provided by regular expr" lautet. Anschließend wird das "e" im Muster mit dem zweiten "e" in "expressions" verglichen, und es wird eine Übereinstimmung gefunden.  
  
- Das "s" im Muster wird mit dem "s" verglichen, das dem übereinstimmenden Zeichen "e" folgt (das erste "s" in"expressions"). Die Übereinstimmung ist erfolgreich.  
  
 Bei einer Rückverfolgung erfordert das Abgleichen des regulären Ausdrucksmusters mit der Eingabezeichenfolge, die 55 Zeichen lang ist, 67 Vergleichsoperationen. Wenn das Muster eines regulären Ausdrucks ein einzelnes Alternierungskonstrukt oder einen einzelnen optionalen Quantifizierer enthält, ist die Anzahl der zum Abgleichen eines Musters erforderlichen Vergleichsoperationen im Allgemeinen mehr als doppelt so hoch wie die Anzahl der Zeichen in der Eingabezeichenfolge.

## <a name="backtracking-with-nested-optional-quantifiers"></a>Rückverfolgung mit geschachtelten optionalen Quantifizierern  
 Die Anzahl der für den Abgleich mit einem regulären Ausdrucksmuster erforderlichen Vergleichsoperationen kann sich exponentiell erhöhen, wenn das Muster viele Alternierungskonstrukte bzw. geschachtelte Alternierungskonstrukte oder, wie es am häufigsten vorkommt, geschachtelte optionale Quantifizierer enthält. Beispielsweise ist das reguläre Ausdrucksmuster `^(a+)+$` darauf ausgelegt, eine Übereinstimmung mit einer vollständigen Zeichenfolge zu finden, die mindestens ein "a" enthält. Das Beispiel stellt zwei Eingabezeichenfolgen mit identischer Länge bereit. Aber nur die erste Zeichenfolge stimmt mit dem Muster überein. Die <xref:System.Diagnostics.Stopwatch?displayProperty=nameWithType> -Klasse wird verwendet, um zu bestimmen, wie lange die Vergleichsoperation dauert.  
  
 [!code-csharp[Conceptual.RegularExpressions.Backtracking#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/cs/backtracking3.cs#3)]
 [!code-vb[Conceptual.RegularExpressions.Backtracking#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/vb/backtracking3.vb#3)]  
  
 Wie die Ausgabe des Beispiels zeigt, brauchte die Engine für reguläre Ausdrücke zum Bestimmen, dass eine Eingabezeichenfolge nicht mit dem Muster übereinstimmt, etwa doppelt so lang wie für die Ermittlung einer übereinstimmenden Zeichenfolge. Dies liegt daran, dass eine fehlgeschlagene Übereinstimmung immer den ungünstigsten Fall darstellt. Die Engine für reguläre Ausdrücke muss den regulären Ausdruck verwenden, um allen möglichen Pfaden durch die Daten zu folgen, bevor es feststellen kann, ob die Übereinstimmung fehlschlägt. Durch die geschachtelten Klammern werden viele zusätzliche Pfade durch die Daten erstellt. Die Engine für reguläre Ausdrücke stellt fest, dass die zweite Zeichenfolge nicht mit dem Muster übereinstimmt, indem wie folgt vorgegangen wird:  
  
- Das Modul überprüft, ob es sich am Anfang der Zeichenfolge befindet, und vergleicht dann die ersten fünf Zeichen in der Zeichenfolge mit dem Muster `a+`. Anschließend wird sichergestellt, dass keine weiteren Gruppen des Zeichens "a" in der Zeichenfolge vorhanden sind. Schließlich wird das Ende der Zeichenfolge überprüft. Da ein zusätzliches Zeichen in der Zeichenfolge verbleibt, schlägt die Übereinstimmung fehl. Diese fehlgeschlagene Suche nach Übereinstimmung erfordert 9 Vergleiche. Die Engine für reguläre Ausdrücke speichert darüber hinaus Zustandsinformationen aus den Übereinstimmungen von "a" (hier bezeichnet als Übereinstimmung 1), "aa" (Übereinstimmung 2), "aaa" (Übereinstimmung 3) und "aaaa" (Übereinstimmung 4).  
  
- Das Modul kehrt zur zuvor gespeicherten Übereinstimmung 4 zurück. Es wird ermittelt, dass ein zusätzliches Zeichen "a" vorhanden ist, das einer zusätzlichen Erfassungsgruppe zugewiesen werden soll. Schließlich wird das Ende der Zeichenfolge überprüft. Da ein zusätzliches Zeichen in der Zeichenfolge verbleibt, schlägt die Übereinstimmung fehl. Diese fehlgeschlagene Suche nach Übereinstimmung erfordert 4 Vergleiche. Bisher wurden insgesamt 13 Vergleiche ausgeführt.  
  
- Das Modul kehrt zur zuvor gespeicherten Übereinstimmung 3 zurück. Es wird ermittelt, dass zwei zusätzliche "a"-Zeichen vorhanden sind, die einer zusätzlichen Erfassungsgruppe zugewiesen werden sollen. Allerdings schlägt die Überprüfung des Zeichenfolgenendes fehl. Anschließend kehrt das Modul zur Übereinstimmung 3 zurück und versucht, die zwei zusätzlichen "a"-Zeichen in zwei zusätzlichen Erfassungsgruppen abzugleichen. Die Überprüfung des Zeichenfolgenendes schlägt weiterhin fehl. Diese fehlgeschlagenen Übereinstimmungen erfordern 12 Vergleiche. Bisher wurden insgesamt 25 Vergleiche ausgeführt.  
  
 Der Vergleich der Eingabezeichenfolge mit dem regulären Ausdruck wird auf diese Weise fortgesetzt, bis die Engine für reguläre Ausdrücke alle möglichen Übereinstimmungskombinationen durchlaufen hat und dann feststellt, dass keine Übereinstimmung vorhanden ist. Aufgrund der geschachtelten Quantifizierer handelt es sich bei diesem Vergleich um O(2<sup>n</sup>) oder einen exponentiellen Vorgang, wobei *n* für die Anzahl von Zeichen in der Eingabezeichenfolge steht. Dies bedeutet, dass im ungünstigsten Fall für eine Eingabezeichenfolge von 30 Zeichen etwa 1.073.741.824 Vergleiche und für eine Eingabezeichenfolge von 40 Zeichen ungefähr 1.099.511.627.776 Vergleiche erforderlich sind. Wenn Sie Zeichenfolgen mit dieser oder sogar einer größeren Länge verwenden, kann die Ausführung von Methoden mit regulären Ausdrücken erhebliche Zeit in Anspruch nehmen, wenn diese Eingaben verarbeiten, die nicht mit dem regulären Ausdrucksmuster übereinstimmen.

## <a name="controlling-backtracking"></a>Steuern der Rückverfolgung  
 Mithilfe der Rückverfolgung können Sie leistungsstarke, flexible reguläre Ausdrücke erstellen. Wie allerdings im vorangegangenen Abschnitt erläutert, sind diese Vorteile u. U. mit einer inakzeptabel schlechten Leistung verknüpft. Um eine übermäßige Rückverfolgung zu verhindern, sollten Sie ein Timeoutintervall definieren, wenn Sie ein <xref:System.Text.RegularExpressions.Regex> -Objekt instanziieren oder eine statische Methode für Übereinstimmungen mit regulären Ausdrücken aufrufen. Dies wird im nächsten Abschnitt erläutert. Darüber hinaus unterstützt .NET drei Sprachelemente für reguläre Ausdrücke, die das Zurückverfolgen einschränken oder unterdrücken und komplexe reguläre Ausdrücke bei nur wenigen oder gar keinen Leistungseinbußen unterstützen: [atomische Gruppen](#atomic-groups), [Lookbehindassertionen](#lookbehind-assertions) und [Lookaheadassertionen](#lookahead-assertions). Weitere Informationen zu den einzelnen Sprachelementen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping-constructs-in-regular-expressions.md).  

### <a name="defining-a-time-out-interval"></a>Definieren eines Timeoutintervalls  
 Ab .NET Framework 4.5 können Sie einen Timeoutwert für das längste Intervall festlegen, innerhalb dessen die Engine für reguläre Ausdrücke nach einer einzelnen Übereinstimmung sucht, bevor der Versuch abgebrochen und eine Ausnahme vom Typ <xref:System.Text.RegularExpressions.RegexMatchTimeoutException> ausgelöst wird. Sie geben das Timeoutintervall an, indem Sie einen <xref:System.TimeSpan> -Wert für den <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29> -Konstruktor für reguläre Ausdrucksinstanzen bereitstellen. Außerdem weist jede statische Methode für Musterübereinstimmungen eine Überladung mit einem <xref:System.TimeSpan> -Parameter auf, der es Ihnen ermöglicht, einen Timeoutwert anzugeben. Standardmäßig wird das Timeoutintervall auf <xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout?displayProperty=nameWithType> festgelegt, und die Engine für reguläre Ausdrücke gibt kein Timeout zurück.  
  
> [!IMPORTANT]
> Es wird empfohlen, immer ein Timeoutintervall festzulegen, wenn ein regulärer Ausdruck auf Rückverfolgung angewiesen ist.  
  
 Eine <xref:System.Text.RegularExpressions.RegexMatchTimeoutException>-Ausnahme gibt an, dass die Engine für reguläre Ausdrücke keine Übereinstimmung innerhalb des angegebenen Timeoutintervalls finden konnte. Allerdings gibt sie nicht an, warum die Ausnahme ausgelöst wurde. Der Grund kann eine übermäßige Rückverfolgung sein. Es ist jedoch auch möglich, dass das Timeoutintervall angesichts der Systembelastung zum Zeitpunkt, als die Ausnahme ausgelöst wurde, zu niedrig festgelegt wurde. Wenn Sie die Ausnahme behandeln, können Sie entweder weitere Übereinstimmungen mit der Eingabezeichenfolge abbrechen oder das Timeoutintervall erhöhen und den Vergleichsvorgang erneut ausführen.  
  
 Im folgenden Code wird beispielsweise der <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%2CSystem.TimeSpan%29> -Konstruktor aufgerufen, um ein <xref:System.Text.RegularExpressions.Regex> -Objekt mit einem Timeoutwert von einer Sekunde zu instanziieren. Das Muster des regulären Ausdrucks `(a+)+$`, das mit mindestens einer Sequenz von einem oder mehreren "a"-Zeichen am Ende einer Zeile übereinstimmt, unterliegt übermäßiger Rückverfolgung. Wenn <xref:System.Text.RegularExpressions.RegexMatchTimeoutException> ausgelöst wird, wird der Timeoutwert im Beispiel bis zu einem maximalen Intervall von drei Sekunden erhöht. Danach wird der Versuch, das Muster abzugleichen, abgebrochen.  
  
 [!code-csharp[System.Text.RegularExpressions.Regex.ctor#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.text.regularexpressions.regex.ctor/cs/ctor1.cs#1)]
 [!code-vb[System.Text.RegularExpressions.Regex.ctor#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.text.regularexpressions.regex.ctor/vb/ctor1.vb#1)]  

### <a name="atomic-groups"></a>Atomische Gruppen
 Das Sprachelement `(?>` *Teilausdruck* `)` unterdrückt die Rückverfolgung in einem Teilausdruck. Sobald eine Übereinstimmung gefunden wurde, wird kein Teil der Übereinstimmung für die nachfolgende Rückverfolgung aufgegeben. Beispielsweise gibt `\d*` im Muster `(?>\w*\d*)1`, wenn für `1` keine Übereinstimmung gefunden wird, keine Übereinstimmung auf, selbst wenn dies bedeutet, dass für `1` eine erfolgreiche Übereinstimmung möglich ist. Atomische Gruppen sind nützlich, um die mit fehlgeschlagenen Übereinstimmungen zusammenhängenden Leistungsprobleme zu vermeiden.
  
 Das folgende Beispiel zeigt, wie das Unterdrücken der Rückverfolgung bei Verwendung von geschachtelten Quantifizierern die Leistung verbessert. Es wird gemessen, wie viel Zeit die Engine für reguläre Ausdrücke benötigt, um zu ermitteln, dass eine Eingabezeichenfolge nicht mit zwei regulären Ausdrücken übereinstimmt. Der erste reguläre Ausdruck verwendet die Rückverfolgung, um eine Übereinstimmung mit einer Zeichenfolge zu finden, in der Folgendes ein Mal oder mehrmals vorkommt: eine oder mehrere hexadezimale Ziffern, gefolgt von einem Doppelpunkt, gefolgt von einer oder mehreren hexadezimalen Ziffern, gefolgt von zwei Doppelpunkten. Der zweite reguläre Ausdruck ist mit dem ersten identisch, mit der Ausnahme, dass dieser die Rückverfolgung deaktiviert. Wie die Ausgabe im Beispiel zeigt, ist die Leistungsverbesserung durch das Deaktivieren der Rückverfolgung signifikant.  
  
 [!code-csharp[Conceptual.RegularExpressions.Backtracking#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/cs/backtracking4.cs#4)]
 [!code-vb[Conceptual.RegularExpressions.Backtracking#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/vb/backtracking4.vb#4)]  

### <a name="lookbehind-assertions"></a>Lookbehindassertionen  
 .NET enthält zwei Sprachelemente, `(?<=`*Teilausdruck*`)` und `(?<!`*Teilausdruck*`)`, die mit dem bzw. den vorherigen Zeichen in der Eingabezeichenfolge übereinstimmen. Beide Sprachelemente sind Assertionen mit einer Breite von 0. Das heißt, sie bestimmen ohne Vorlaufen oder Rückverfolgung, ob eine Übereinstimmung des oder der Zeichen unmittelbar vor dem aktuellen Zeichen mit *Teilausdruck*vorliegt.  
  
 `(?<=` *Teilausdruck* `)` ist eine positive Lookbehindassertion. Das heißt, das oder die Zeichen vor der aktuellen Position muss bzw. müssen mit *Teilausdruck* übereinstimmen. `(?<!`*Teilausdruck*`)` ist eine negative Lookbehindassertion. Das heißt, das oder die Zeichen vor der aktuellen Position muss bzw. müssen nicht mit *Teilausdruck*übereinstimmen. Positive und negative Lookbehindassertionen sind besonders hilfreich, wenn *Teilausdruck* eine Teilmenge des vorherigen Teilausdrucks ist.  
  
 Im folgenden Beispiel werden zwei äquivalente reguläre Ausdrucksmuster verwendet, die den Benutzernamen in einer E-Mail-Adresse überprüfen. Aufgrund übermäßiger Rückverfolgung tritt beim ersten Muster eine schlechte Leistung auf. Das zweite Muster ist eine Änderung des ersten regulären Ausdrucks, indem ein geschachtelter Quantifizierer durch eine positive Lookbehindassertion ersetzt wird. In der Beispielausgabe wird die Ausführungszeit der <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> -Methode angezeigt.  
  
 [!code-csharp[Conceptual.RegularExpressions.Backtracking#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/cs/backtracking5.cs#5)]
 [!code-vb[Conceptual.RegularExpressions.Backtracking#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/vb/backtracking5.vb#5)]  
  
 Das erste Muster für reguläre Ausdrücke `^[0-9A-Z]([-.\w]*[0-9A-Z])*@`ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.|  
|`[0-9A-Z]`|Übereinstimmung mit einem alphanumerischen Zeichen. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> -Methode mit der <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> -Option aufgerufen wird.|  
|`[-.\w]*`|Übereinstimmung mit keinem, einem oder mehreren Vorkommen eines Bindestrichs, eines Punkts oder eines Wortzeichens.|  
|`[0-9A-Z]`|Übereinstimmung mit einem alphanumerischen Zeichen.|  
|`([-.\w]*[0-9A-Z])*`|Übereinstimmung mit keinem oder mehreren Vorkommen der Kombination aus keinem oder mehreren Bindestrichen, Punkten oder Wortzeichen, gefolgt von einem alphanumerischen Zeichen. Dies ist die erste Erfassungsgruppe.|  
|`@`|Übereinstimmung mit einem \@-Zeichen.|  
  
 Das zweite Muster für reguläre Ausdrücke `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@`verwendet eine positive Lookbehindassertion. Das Muster wird wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.|  
|`[0-9A-Z]`|Übereinstimmung mit einem alphanumerischen Zeichen. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> -Methode mit der <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> -Option aufgerufen wird.|  
|`[-.\w]*`|Übereinstimmung mit keinem oder mehreren Vorkommen eines Bindestrichs, eines Punkts oder eines Wortzeichens.|  
|`(?<=[0-9A-Z])`|Überprüfung des letzten übereinstimmenden Zeichens und Fortsetzen des Abgleichs, wenn es sich um ein alphanumerisches Zeichen handelt. Beachten Sie, dass alphanumerische Zeichen eine Teilmenge des Satzes sind, der aus Punkten, Bindestrichen und allen Wortzeichen besteht.|  
|`@`|Übereinstimmung mit einem \@-Zeichen.|  

### <a name="lookahead-assertions"></a>Lookaheadassertionen  
 .NET enthält zwei Sprachelemente, `(?=`*Teilausdruck*`)` und `(?!`*Teilausdruck*`)`, die mit dem bzw. den nächsten Zeichen in der Eingabezeichenfolge übereinstimmen. Beide Sprachelemente sind Assertionen mit einer Breite von 0. Das heißt, sie bestimmen ohne Vorlaufen oder Rückverfolgung, ob eine Übereinstimmung des oder der Zeichen unmittelbar nach dem aktuellen Zeichen mit *Teilausdruck*vorliegt.  
  
 `(?=` *Teilausdruck* `)` ist eine positive Lookaheadassertion. Das heißt, das oder die Zeichen nach der aktuellen Position muss bzw. müssen mit *Teilausdruck* übereinstimmen. `(?!`*Teilausdruck*`)` ist eine negative Lookaheadassertion. Das heißt, das oder die Zeichen nach der aktuellen Position muss bzw. müssen nicht mit *Teilausdruck*übereinstimmen. Positive und negative Lookaheadassertionen sind besonders hilfreich, wenn *Teilausdruck* eine Teilmenge des nächsten Teilausdrucks ist.  
  
 Im folgenden Beispiel werden zwei äquivalente Muster für reguläre Ausdrücke verwendet, die einen vollqualifizierten Typnamen überprüfen. Aufgrund übermäßiger Rückverfolgung tritt beim ersten Muster eine schlechte Leistung auf. Das zweite Muster ist eine Änderung des ersten regulären Ausdrucks, indem ein geschachtelter Quantifizierer durch eine positive Lookaheadassertion ersetzt wird. In der Beispielausgabe wird die Ausführungszeit der <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> -Methode angezeigt.  
  
 [!code-csharp[Conceptual.RegularExpressions.Backtracking#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/cs/backtracking6.cs#6)]
 [!code-vb[Conceptual.RegularExpressions.Backtracking#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.backtracking/vb/backtracking6.vb#6)]  
  
 Das erste Muster für reguläre Ausdrücke `^(([A-Z]\w*)+\.)*[A-Z]\w*$`ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.|  
|`([A-Z]\w*)+\.`|Übereinstimmung mit einem Buchstaben (A-Z), gefolgt von keinem oder mehreren Wortzeichen (einmaliges oder mehrmaliges Vorkommen), gefolgt von einem Punkt. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> -Methode mit der <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> -Option aufgerufen wird.|  
|`(([A-Z]\w*)+\.)*`|Keine oder mehrmalige Übereinstimmung mit dem vorherigen Muster.|  
|`[A-Z]\w*`|Übereinstimmung mit einem Buchstaben, gefolgt von keinem oder mehreren Wortzeichen.|  
|`$`|Ende des Abgleichs am Ende der Eingabezeichenfolge.|  
  
 Das zweite Muster für reguläre Ausdrücke `^((?=[A-Z])\w+\.)*[A-Z]\w*$`verwendet eine positive Lookaheadassertion. Das Muster wird wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.|  
|`(?=[A-Z])`|Lookahead zum ersten Zeichen und die Suche nach Übereinstimmungen fortsetzen, wenn es sich um einen Buchstaben (A-Z) handelt. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> -Methode mit der <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> -Option aufgerufen wird.|  
|`\w+\.`|Übereinstimmung mit einem oder mehreren Wortzeichen, gefolgt von einem Punkt.|  
|`((?=[A-Z])\w+\.)*`|Übereinstimmung mit dem Muster aus einem oder mehreren Wortzeichen, gefolgt von keinem oder mehreren Vorkommen eines Punkts. Das erste Wortzeichen muss ein Buchstabe sein.|  
|`[A-Z]\w*`|Übereinstimmung mit einem Buchstaben, gefolgt von keinem oder mehreren Wortzeichen.|  
|`$`|Ende des Abgleichs am Ende der Eingabezeichenfolge.|  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET](regular-expressions.md)
- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
- [Quantifizierer](quantifiers-in-regular-expressions.md)
- [Alternierungskonstrukte](alternation-constructs-in-regular-expressions.md)
- [Grouping Constructs](grouping-constructs-in-regular-expressions.md)
