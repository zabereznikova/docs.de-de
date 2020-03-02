---
title: Quantifizierer in regulären Ausdrücken
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, quantifiers
- metacharacters, quantifiers
- minimal matching quantifiers
- quantifiers in regular expressions
- .NET Framework regular expressions, quantifiers
- quantifiers
- lazy quantifiers
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
ms.openlocfilehash: f1627248cbed0f03c6fb76ce660f9b2bf7764781
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160013"
---
# <a name="quantifiers-in-regular-expressions"></a>Quantifizierer in regulären Ausdrücken
Quantifizierer geben an, wie viele Instanzen eines Zeichens, einer Gruppe oder einer Zeichenklasse in der Eingabe vorhanden sein müssen, damit eine Übereinstimmung gefunden wird.  In der folgenden Tabelle werden die von .NET unterstützten Quantifizierer aufgeführt.  
  
|Gieriger Quantifizierer|Träger Quantifizierer|Beschreibung|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|Übereinstimmung mit null oder mehr Vorkommen.|  
|`+`|`+?`|Übereinstimmung mit einem oder mehr Vorkommen.|  
|`?`|`??`|Übereinstimmung mit null oder einem Vorkommen.|  
|`{` *n* `}`|`{` *n* `}?`|Übereinstimmung mit genau *n* Vorkommen.|  
|`{` *n* `,}`|`{` *n* `,}?`|Übereinstimmung mit mindestens *n* Vorkommen.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|Übereinstimmung mit *n* bis *m* Vorkommen.|  
  
 Die Mengen `n` und `m` sind ganzzahlige Konstanten. Gewöhnlich sind Quantifizierer gierig; durch sie gleicht die Engine für reguläre Ausdrücke so viele Vorkommen bestimmter Muster wie möglich ab. Das Anhängen des `?`-Zeichens an einen Quantifizierer macht es träge; es bewirkt, dass die Engine für reguläre Ausdrücke so wenige Vorkommen wie möglich abgleicht. Eine vollständige Beschreibung des Unterschieds zwischen „gierigen“ und „trägen“ Quantifizierern finden Sie weiter unten in diesem Thema im Abschnitt [Gierige und träge Quantifizierer](#Greedy).  
  
> [!IMPORTANT]
> Das Schachteln von Quantifizierern (z.B. wie durch das Muster für reguläre Ausdrücke `(a*)*`) kann die Anzahl von Vergleichen, die die Engine für reguläre Ausdrücke ausführen muss, als Exponentialfunktion der Anzahl von Zeichen in der Eingabezeichenfolge erhöhen. Weitere Informationen zu diesem Verhalten und zu Problemumgehungen finden Sie unter [Rückverfolgung](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## <a name="regular-expression-quantifiers"></a>Quantifizierer in regulären Ausdrücken  
 In den folgenden Abschnitten werden die Quantifizierer aufgeführt, die in regulären .NET-Ausdrücken unterstützt werden.  
  
> [!NOTE]
> Wenn die Zeichen *, +, ?, { und } im Muster für reguläre Ausdrücke enthalten sind, interpretiert die Engine für reguläre Ausdrücke sie als Quantifizierer oder als Teil von Quantifiziererkonstrukten, sofern sie nicht in einer [Zeichenklasse](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) enthalten sind. Um sie als Literalzeichen außerhalb einer Zeichenklasse zu interpretieren, müssen Sie sie mit Escapezeichen versehen, indem Sie ihnen einen umgekehrten Schrägstrich voranstellen. Die Zeichenfolge `\*` in einem Muster für reguläre Ausdrücke wird z.B. als literales Sternchen („\*“) interpretiert.  
  
### <a name="match-zero-or-more-times-"></a>Übereinstimmung mit null oder mehr Vorkommen: *  
 Der `*`-Quantifizierer gleicht das vorangehende Element nullmal oder häufiger ab. Dies entspricht dem `{0,}`-Quantifizierer. `*` ist ein gieriger Quantifizierer, dessen träges Äquivalent `*?` lautet.  
  
 Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. Von den neun Ziffern in der Eingabezeichenfolge entsprechen fünf dem Muster, bei vier Ziffern (`95`, `929`, `9219` und `9919`) ist das nicht der Fall.  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`91*`|Übereinstimmung mit „9“, gefolgt von null oder mehr Zeichen „1“.|  
|`9*`|Übereinstimmung mit null oder mehr Zeichen „9“.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### <a name="match-one-or-more-times-"></a>Übereinstimmung mit einem oder mehr Vorkommen: +  
 Der `+`-Quantifizierer gleicht das vorangehende Element einmal oder häufiger ab. Er entspricht `{1,}`. `+` ist ein gieriger Quantifizierer, dessen träges Äquivalent `+?` lautet.  
  
 Beispielsweise versucht der reguläre Ausdruck `\ban+\w*?\b` ganze Wörter abzugleichen, die mit dem Buchstaben `a` beginnen, gefolgt von mindestens einer Instanz des Buchstabens `n`. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. Der reguläre Ausdruck gleicht die Wörter `an`, `annual`, `announcement` und `antique` ab und findet richtigerweise keine Übereinstimmung mit `autumn` und `all`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`an+`|Übereinstimmung mit „a“, gefolgt von einem oder mehr Zeichen „n“.|  
|`\w*?`|Gleicht ein Wortzeichen nullmal oder häufiger ab, jedoch so wenige Male wie möglich.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### <a name="match-zero-or-one-time-"></a>Übereinstimmung mit null oder einem Vorkommen: ?  
 Der Quantifizierer `?` gleicht das vorangehende Element null- oder einmal ab. Er entspricht `{0,1}`. `?` ist ein gieriger Quantifizierer, dessen träges Äquivalent `??` lautet.  
  
 Beispielsweise versucht der reguläre Ausdruck `\ban?\b` ganze Wörter abzugleichen, die mit dem Buchstaben `a` beginnen, gefolgt von null oder einer Instanz des Buchstabens `n`. Das heißt, er versucht, die Wörter `a` und `an` abzugleichen. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`an?`|Übereinstimmung mit „a“, gefolgt von null oder einem Zeichen „n“.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### <a name="match-exactly-n-times-n"></a>Übereinstimmung mit genau n Vorkommen: {n}  
 Der `{`*n*`}`-Quantifizierer gleicht das vorangehende Element genau *n* Mal ab, wobei *n* für einen beliebigen Integer steht. `{`*n*`}` ist ein gieriger Quantifizierer, dessen träges Äquivalent `{`*n*`}?` lautet.  
  
 Beispielsweise versucht der reguläre Ausdruck `\b\d+\,\d{3}\b`, eine Wortgrenze, gefolgt von einer oder mehreren Dezimalziffern, gefolgt von drei Dezimalziffern, gefolgt von einer Wortgrenze abzugleichen. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`\,`|Übereinstimmung mit einem Kommazeichen.|  
|`\d{3}`|Entsprechung für drei Dezimalstellen finden.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### <a name="match-at-least-n-times-n"></a>Übereinstimmung mit mindestens n Vorkommen: {n,}  
 Der `{`*n*`,}`-Quantifizierer gleicht das vorangehende Element mindestens *n*-mal ab, wobei *n* für einen beliebigen Integer steht. `{`*n*`,}` ist ein gieriger Quantifizierer, dessen träges Äquivalent `{`*n*`,}?` lautet.  
  
 Beispielsweise versucht der reguläre Ausdruck `\b\d{2,}\b\D+`, eine Wortgrenze, gefolgt von mindestens zwei Ziffern, gefolgt von einer Wortgrenze und einer Nicht-Dezimalziffer abzugleichen. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. Der reguläre Ausdruck kann den Ausdruck `"7 days"` nicht abgleichen, da er nur eine Dezimalziffer enthält, findet aber erfolgreich Übereinstimmungen mit den Phrasen `"10 weeks and 300 years"`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\d{2,}`|Übereinstimmung mit mindestens zwei Dezimalziffern.|  
|`\b`|Übereinstimmung mit einer Wortgrenze.|  
|`\D+`|Übereinstimmung mit mindestens einer Nicht-Dezimalziffer.|  
  
### <a name="match-between-n-and-m-times-nm"></a>Übereinstimmung mit n bis m Vorkommen: {n,m}  
 Der `{`*n*`,`*m*`}`-Quantifizierer gleicht das vorangehende Element mindestens *n* Mal, aber nicht mehr als *m* Mal ab, wobei *n* und *m* Integerwerte sind. `{`*n*`,`*m*`}` ist ein gieriger Quantifizierer, dessen träges Äquivalent `{`*n*`,`*m*`}?` lautet.  
  
 Im folgenden Beispiel versucht der reguläre Ausdruck `(00\s){2,4}`, zwei bis vier Vorkommen zweier 0-Ziffern, gefolgt von einem Leerzeichen, abzugleichen. Beachten Sie, dass der letzte Teil der Eingabezeichenfolge dieses Muster fünfmal enthält und damit das Maximum von vier überschreitet. Allerdings stimmt nur der erste Teil dieser Teilzeichenfolge (bis zum Leerzeichen und fünften Nullpaar) mit dem Muster für reguläre Ausdrücke überein.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a>Übereinstimmung mit null oder mehr Vorkommen (träger Abgleich): *?  
 Der `*?`-Quantifizierer gleicht das vorangehende Element nullmal oder häufiger ab, jedoch so wenige Male wie möglich. Dies ist das träge Gegenstück zum gierigen Quantifizierer `*`.  
  
 Im folgenden Beispiel gleicht der reguläre Ausdruck `\b\w*?oo\w*?\b` alle Wörter ab, die die Zeichenfolge `oo` enthalten.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\w*?`|Übereinstimmung mit null oder mehr Wortzeichen, aber so wenigen Zeichen wie möglich.|  
|`oo`|Übereinstimmung mit der Zeichenfolge „Oo“.|  
|`\w*?`|Übereinstimmung mit null oder mehr Wortzeichen, aber so wenigen Zeichen wie möglich.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### <a name="match-one-or-more-times-lazy-match-"></a>Übereinstimmung mit einem oder mehr Vorkommen (träger Abgleich): +?  
 Der `+?`-Quantifizierer gleicht das vorangehende Element einmal oder häufiger ab, jedoch so wenige Male wie möglich. Dies ist das träge Gegenstück zum gierigen Quantifizierer `+`.  
  
 Beispielsweise gleicht der reguläre Ausdruck `\b\w+?\b` ein oder mehr Zeichen ab, die durch Wortgrenzen getrennt sind. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a>Übereinstimmung mit null oder einem Vorkommen (träger Abgleich): ??  
 Der `??`-Quantifizierer gleicht das vorangehende Element null- oder einmal ab, jedoch so wenige Male wie möglich. Dies ist das träge Gegenstück zum gierigen Quantifizierer `?`.  
  
 Beispielsweise versucht der reguläre Ausdruck `^\s*(System.)??Console.Write(Line)??\(??`, die Zeichenfolgen „Console.Write“ oder „Console.WriteLine“ abzugleichen. Die Zeichenfolge kann auch „System.“ vor „Console“ enthalten und von einer öffnenden Klammer gefolgt sein. Die Zeichenfolge muss sich am Anfang einer Zeile befinden, ihr kann jedoch ein Leerzeichen vorangestellt sein. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Übereinstimmung mit dem Beginn des Eingabestreams.|  
|`\s*`|Sucht nach 0 (null) oder mehr Leerzeichen.|  
|`(System.)??`|Übereinstimmung mit null oder einem Vorkommen der Zeichenfolge „System.“.|  
|`Console.Write`|Übereinstimmung mit der Zeichenfolge „Console.Write“.|  
|`(Line)??`|Übereinstimmung mit null oder einem Vorkommen der Zeichenfolge „Line“.|  
|`\(??`|Übereinstimmung mit null oder einem Vorkommen der öffnenden Klammer.|  
  
### <a name="match-exactly-n-times-lazy-match-n"></a>Übereinstimmung mit genau n Vorkommen (träger Abgleich): {n}?  
 Der `{`*n*`}?`-Quantifizierer gleicht das vorangehende Element genau `n` Mal ab, wobei *n* für eine beliebige ganze Zahl steht. Dies ist das träge Gegenstück zum gierigen Quantifizierer `{`*n*`}`.  
  
 Im folgenden Beispiel wird der reguläre Ausdruck `\b(\w{3,}?\.){2}?\w{3,}?\b` verwendet, um die Adresse einer Website zu identifizieren. Beachten Sie, dass „www.microsoft.com“ und „msdn.microsoft.com“ abgeglichen werden, aber nicht „mywebsite“ oder „mycompany.com“.  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(\w{3,}?\.)`|Übereinstimmung mit mindestens 3 Wortzeichen, aber so wenigen Zeichen wie möglich, gefolgt von einem Punktzeichen. Dies ist die erste Erfassungsgruppe.|  
|`(\w{3,}?\.){2}?`|Übereinstimmung mit zwei Vorkommen im Muster in der ersten Gruppe, jedoch so wenige Male wie möglich.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
  
### <a name="match-at-least-n-times-lazy-match-n"></a>Übereinstimmung mit mindestens n Vorkommen (träger Abgleich): {n,}?  
 Der `{`*n*`,}?`-Qualifizierer gleicht das vorangehende Element mindestens `n` Mal ab, jedoch so wenige Male wie möglich, wobei *n* für einen beliebigen Integer steht. Dies ist das träge Gegenstück zum gierigen Quantifizierer `{`*n*`,}`.  
  
 Eine Veranschaulichung finden Sie im vorherigen Abschnitt im Beispiel für den `{`*n*`}?`-Quantifizierer. Der reguläre Ausdruck in diesem Beispiel verwendet den `{`*n*`,}`-Quantifizierer, um eine Zeichenfolge abzugleichen, die mindestens drei Zeichen umfasst, gefolgt von einem Punkt.  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Übereinstimmung mit n bis m Vorkommen (träger Abgleich): {n,m}?  
 Der `{`*n*`,`*m*`}?`-Quantifizierer gleicht das vorangehende Element `n` bis `m` Mal ab, jedoch so wenige Male wie möglich, wobei *n* und *m* Integerwerte sind. Dies ist das träge Gegenstück zum gierigen Quantifizierer `{`*n*`,`*m*`}`.  
  
 Im folgenden Beispiel gleicht der reguläre Ausdruck `\b[A-Z](\w*?\s*?){1,10}[.!?]` Sätze ab, die zwischen ein und zehn Wörter enthalten. Er gleicht alle Sätze in der Eingabezeichenfolge ab mit Ausnahme eines Satzes, der 18 Wörter enthält.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`[A-Z]`|Übereinstimmung mit einem Großbuchstaben von A bis Z.|  
|`(\w*?\s*?)`|Übereinstimmung mit 0 (null) oder mehr Wortzeichen, gefolgt von einem oder mehreren Leerzeichen, jedoch so wenige wie möglich. Dies ist die erste Erfassungsgruppe.|  
|`{1,10}`|Übereinstimmung mit dem vorhergehenden Muster zwischen 1- und 10-mal.|  
|`[.!?]`|Übereinstimmung mit einem der Interpunktionszeichen „.“, „!“ oder „?“.|  
  
<a name="Greedy"></a>
## <a name="greedy-and-lazy-quantifiers"></a>Gierige und träge Quantifizierer  
 Eine Reihe von Quantifizierern gibt es in zwei Versionen:  
  
- Eine gierige Version.  
  
     Ein gieriger Quantifizierer versucht, ein Element so oft wie möglich abzugleichen.  
  
- Eine nicht gierige (oder träge) Version.  
  
     Ein nicht gieriger Quantifizierer versucht, ein Element so selten wie möglich abzugleichen. Sie können einen gierigen Quantifizierer in einen trägen Quantifizierer umwandeln, indem Sie einfach ein `?` hinzufügen.  
  
 Nehmen Sie einen einfachen regulären Ausdruck, der die letzten vier Ziffern aus einer Zeichenfolge mit Zahlen extrahieren soll, beispielsweise aus einer Kreditkartennummer. Die Version des regulären Ausdrucks, die den gierigen `*`-Quantifizierer verwendet, lautet `\b.*([0-9]{4})\b`. Wenn eine Zeichenfolge zwei Zahlen enthält, gleicht dieser reguläre Ausdruck jedoch nur die letzten vier Ziffern der zweiten Zahl ab, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 Der reguläre Ausdruck kann die erste Zahl nicht abgleichen, da der `*`-Quantifizierer versucht, das vorherige Element so oft wie möglich in der gesamten Zeichenfolge abzugleichen. Daher wird die Übereinstimmung am Ende der Zeichenfolge gefunden.  
  
 Dies entspricht nicht dem gewünschten Verhalten. Stattdessen können Sie den `*?`trägen Quantifizierer verwenden, um Ziffern aus beiden Zahlen zu extrahieren, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 In den meisten Fällen werden von regulären Ausdrücken mit gierigen und trägen Quantifizierern die gleichen Übereinstimmungen zurückgegeben. Im Allgemeinen geben sie unterschiedliche Ergebnisse zurück, wenn sie mit dem Platzhaltermetazeichen (`.`) verwendet werden, das jedes beliebige Zeichen abgleicht.  
  
## <a name="quantifiers-and-empty-matches"></a>Quantifizierer und leere Übereinstimmungen  
 Die Quantifizierer `*`, `+` und `{`*n*`,`*m*`}` sowie ihre trägen Gegenstücke werden nach einer leeren Übereinstimmung nie wiederholt, wenn die Mindestanzahl von Erfassungen gefunden wurde. Diese Regel verhindert, dass Quantifizierer bei leeren Teilausdruckübereinstimmungen in Endlosschleifen geraten, wenn die maximale Anzahl möglicher Gruppenerfassungen unendlich oder nahezu unendlich ist.  
  
 Der folgende Code zeigt z.B. das Ergebnis eines Aufrufs der <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>-Methode mit dem Muster für reguläre Ausdrücke `(a?)*`, bei dem null oder ein Zeichen „a“ nullmal oder häufiger abgeglichen wird. Beachten Sie, dass die einzelne Erfassungsgruppe jedes „a“ sowie <xref:System.String.Empty?displayProperty=nameWithType> abgleicht, dass es aber keine zweite leere Übereinstimmung gibt, weil der Quantifizierer nach der ersten leeren Übereinstimmung nicht mehr wiederholt wird.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 Um den praktischen Unterschied zwischen einer Erfassungsgruppe, die eine Mindest- und eine Höchstzahl von Erfassungen definiert, und einer Erfassungsgruppe zu sehen, die eine feste Anzahl von Erfassungen definiert, betrachten Sie die Muster für reguläre Ausdrücke `(a\1|(?(1)\1)){0,2}` und `(a\1|(?(1)\1)){2}`. Beide reguläre Ausdrücke bestehen aus einer einzelnen Erfassungsgruppe, die wie in der folgenden Tabelle gezeigt definiert ist.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`(a\1`|Entweder „a“ zusammen mit dem Wert der ersten Erfassungsgruppe abgleichen...|  
|<code>&#124;(?(1)</code>|… oder testen, ob die erste Erfassungsgruppe definiert wurde. (Beachten Sie, dass das `(?(1)`-Konstrukt keine Erfassungsgruppe definiert.)|  
|`\1))`|Wenn die erste Erfassungsgruppe vorhanden ist, deren Wert abgleichen. Wenn die Gruppe nicht vorhanden ist, gleicht die Gruppe <xref:System.String.Empty?displayProperty=nameWithType> ab.|  
  
 Der erste reguläre Ausdruck versucht, dieses Muster zwischen null- und zweimal abzugleichen; der zweite Ausdruck genau zweimal. Da das erste Muster die minimale Anzahl von Erfassungen mit der ersten Erfassung von <xref:System.String.Empty?displayProperty=nameWithType> erreicht, wird es nie wiederholt, um `a\1` abzugleichen. Der `{0,2}`-Quantifizierer erlaubt nur leere Übereinstimmungen in der letzten Iteration. Im Gegensatz dazu gleicht der zweite reguläre Ausdruck „a“ ab, weil `a\1` ein zweites Mal ausgewertet wird; die Mindestanzahl von Iterationen (2) zwingt die Engine nach einer leeren Übereinstimmung zur Wiederholung.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
