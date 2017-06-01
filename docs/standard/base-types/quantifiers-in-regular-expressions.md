---
title: "Quantifizierer in regul&#228;ren Ausdr&#252;cken | Microsoft Docs"
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
  - "Reguläre Ausdrücke, Quantifizierer"
  - "Metazeichen, Quantifizierer"
  - "Quantifizierer für minimale Übereinstimmung"
  - "Quantifizierer in regulären Ausdrücken"
  - "Reguläre Ausdrücke von .NET Framework, Quantifizierer"
  - "Quantifizierer"
  - "Verzögerte Quantifizierer"
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Quantifizierer in regul&#228;ren Ausdr&#252;cken
Quantifizierer geben an, wie viele Instanzen eines Zeichens, einer Gruppe oder einer Zeichenklasse in der Eingabe vorhanden sein müssen, damit eine Übereinstimmung festgestellt wird.  In der folgenden Tabelle sind die Quantifizierer aufgeführt, die von .NET Framework unterstützt werden.  
  
|Gieriger Quantifizierer|Träge \(lazy\) Quantifizierer|**Beschreibung**|  
|-----------------------------|-----------------------------------|----------------------|  
|`*`|`*?`|Entsprechung \(nullmal oder mehrere Male\).|  
|`+`|`+?`|Mindestens einmalige Entsprechung.|  
|`?`|`??`|Entsprechung \(null\- oder einmal\).|  
|`{` *n* `}`|`{` *n* `}?`|Übereinstimmung mit Zeiten genau *n* ab.|  
|`{` *n* `,}`|`{` *n* `,}?`|Sucht nach mindestens *n* Zeiten ab.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|Anpassen von *n* in *m* Zeiten aufgeführt.|  
  
 Der Mengen `n` und `m` sind ganzzahlige Konstanten.  Gewöhnlich sind Quantifizierer gierig; durch sie ordnet das Modul für reguläre Ausdrücke so viele Vorkommen bestimmter Muster wie möglich zu.  Das Anhängen des `?`\-Zeichens an einen Quantifizierer macht es träge; es bewirkt, dass das Modul für reguläre Ausdrücke so wenige Vorkommen wie möglich findet.  Eine vollständige Beschreibung des Unterschieds zwischen "gierigen" und "trägen" Quantifizierern finden Sie im Abschnitt [Gierige und träge Quantifizierer](#Greedy) später in diesem Thema.  
  
> [!IMPORTANT]
>  Das Schachteln von Quantifizierern \(z. B. wie durch das Muster eines regulären Ausdrucks `(a*)*`\) kann die Anzahl von Vergleichen, die das Modul für reguläre Ausdrücke ausführen muss, als Exponentialfunktion der Anzahl von Zeichen in der Eingabezeichenfolge erhöhen.  Weitere Informationen zu diesem Verhalten und zu Problemumgehungen finden Sie unter [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## Reguläre Ausdrucksquantifizierer  
 In der folgenden Abschnittsliste sind die Quantifizierer aufgeführt, die von regulären .NET Framework\-Ausdrücken unterstützt werden.  
  
> [!NOTE]
>  Wenn die Zeichen \*, \+?, {, und } im Muster eines regulären Ausdrucks enthalten sind, interpretiert das Modul für reguläre Ausdrücke sie als Quantifizierer oder als Teil von Quantifiziererkonstrukten, sofern sie nicht in einer [Zeichenklasse](../../../docs/standard/base-types/character-classes-in-regular-expressions.md) enthalten sind.  Um diese außerhalb einer Zeichenklasse als Literalzeichen zu interpretieren, müssen Sie sie mit Escapezeichen versehen, indem Sie ihnen einen umgekehrten Schrägstrich voranstellen.  Die Zeichenfolge `\*` in einem Muster eines regulären Ausdrucks wird z. B. als literales Sternchenzeichen \("\*"\) interpretiert.  
  
### Entspricht dem Zeichen nullmal oder mehrere Male: \*  
 Der `*`\-Quantifizierer gleicht das vorausgehende Element nullmal oder häufiger ab.  Sie entspricht dem `{0,}`\-Quantifizierer.  `*` ist ein gieriger Quantifizierer, dessen träge Entsprechung `*?` ist.  
  
 Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  Von den neun Ziffern in der Eingabezeichenfolge stimmen fünf mit dem Muster überein und vier nicht \(`95`, `929`, `9129` und `9919`\).  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`91*`|Entspricht "9" gefolgt von null oder mehr "1"\-Zeichen.|  
|`9*`|Entspricht null oder mehr "9"\-Zeichen.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### Mindestens einmalige Entsprechung: \+  
 Der `+`\-Quantifizierer gleicht das vorausgehende Element mindestens einmal ab.  Ist äquivalent zu `{1,}`.  `+` ist ein gieriger Quantifizierer, dessen träge Entsprechung `+?` ist.  
  
 Der reguläre Ausdruck `\ban+\w*?\b` sucht beispielsweise nach ganzen Wörtern, die mit dem Buchstaben `a` beginnen, auf den mindestens eine Instanz des Buchstaben `n` folgt.  Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  Der reguläre Ausdruck liefert die Wörter `an`, `annual`, `announcement` und `antique` als Ergebnis und erkennt erwartungsgemäß keine Übereinstimmung bei den Wörtern `autumn` und `all`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`an+`|Entspricht "a" gefolgt von mindestens einem "n"\-Zeichen.|  
|`\w*?`|Entspricht einem Wortzeichen nullmal oder mehrere Male, doch so wenig wie möglich.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### Entspricht dem Zeichen null\- oder einmal: ?  
 Der `?`\-Quantifizierer gleicht das vorausgehende Element nullmal oder einmal ab.  Ist äquivalent zu `{0,1}`.  `?` ist ein gieriger Quantifizierer, dessen träge Entsprechung `??` ist.  
  
 Der reguläre Ausdruck `\ban?\b` sucht beispielsweise nach ganzen Wörtern, die mit dem Buchstaben `a` beginnen, auf den keine oder eine Instanz des Buchstaben `n` folgt.  Er sucht also nach den Wörtern `a` und `an`.  Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`an?`|Entspricht "a" gefolgt von null oder einem "n"\-Zeichen.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### Entspricht genau n\-mal dem Zeichen: {n}  
 Der Quantifizierer `{`*n*`}` entspricht *n* Zeiten des vorangehenden Element genau ab, wobei *n* eine ganze Zahl ist.  `{`*n*`}` ist ein gieriger Quantifizierer, dessen Entsprechung verzögerte `{`*n*`}?` ist.  
  
 Der reguläre Ausdruck `\b\d+\,\d{3}\b` sucht beispielsweise nach Übereinstimmungen einer Wortgrenze, auf die mindestens eine Dezimalziffer, drei Dezimalziffern und eine weitere Wortgrenze folgen.  Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`\,`|Entspricht einem Kommazeichen.|  
|`\d{3}`|Entsprechung für drei Dezimalstellen finden.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### Entspricht mindestens n‑mal dem Zeichen: {n,}  
 Der Quantifizierer `{`*n*`,}` entspricht die vorangehenden *n* Zeiten des Elements mindestens ab, wobei *n* eine ganze Zahl ist.  `{`*n*`,}` ist ein gieriger Quantifizierer, dessen Entsprechung verzögerte `{`*n*`}?` ist.  
  
 Der reguläre Ausdruck `\b\d{2,}\b\D+` sucht beispielsweise nach Übereinstimmungen einer Wortgrenze, auf die mindestens zwei Ziffern, eine Wortgrenze und ein weiteres Zeichen folgen, bei dem es sich nicht um eine Ziffer handelt.  Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  Der reguläre Ausdruck liefert kein Ergebnis für den Ausdruck `"7 days"`, da dieser nur eine Dezimalziffer enthält, er erkennt jedoch erfolgreich Übereinstimmungen mit den Ausdrücken `"10 weeks and 300 years"`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\d{2,}`|Entspricht mindestens zwei Dezimalstellen.|  
|`\b`|Entsprechung für eine Wortgrenze finden.|  
|`\D+`|Entspricht mindestens einer nicht dezimalen Stelle.|  
  
### Entspricht dem Zeichen zwischen n\- und m\-mal: {n,m}?  
 Der Quantifizierer `{`*n*`,`*m*`}` entspricht die vorangehenden *n* Zeiten des Elements mindestens, höchstens jedoch *m* Zeiten ab, wobei *n* und *m* ganze Zahlen sind.  `{`*n*`,`*m*`}` ist ein gieriger Quantifizierer, dessen Entsprechung verzögerte `{`*n*`,`*m*`}?` ist.  
  
 Im folgenden Beispiel sucht der reguläre Ausdruck `(00\s){2,4}` beispielsweise nach zwei bis vier Vorkommen zweier 0\-Ziffern, auf die ein Leerzeichen folgt.  Beachten Sie, dass der letzte Abschnitt der Eingabezeichenfolge dieses Muster fünf Mal und nicht maximal vier Mal enthält.  Nur der Anfangsabschnitt dieser Teilzeichenfolge \(bis zum Leerzeichen und dem fünften Nullenpaar\) stimmt mit dem regulären Ausdrucksmuster jedoch überein.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### Entspricht dem Zeichen nullmal oder mehrere Male \(träge Übereinstimmung\): \*?  
 Der `*?`\-Quantifizierer sucht für das vorangehende Element keine oder mehrere Übereinstimmungen, jedoch so wenige wie möglich.  Es handelt sich um das träge Gegenstück des gierigen Quantifizierers `*`.  
  
 Im folgenden Beispiel entspricht der reguläre Ausdruck `\b\w*?oo\w*?\b` allen Wörtern, die die Zeichenfolge `oo` enthalten.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\w*?`|Entspricht null oder mehreren Wortzeichen, aber so wenigen Zeichen wie möglich.|  
|`oo`|Entspricht der Zeichenfolge "oo".|  
|`\w*?`|Entspricht null oder mehreren Wortzeichen, aber so wenigen Zeichen wie möglich.|  
|`\b`|An einer Wortgrenze beenden.|  
  
### Mindestens einmalige Entsprechung \(träge Übereinstimmung\): \+?  
 Der `+?`\-Quantifizierer sucht für das vorangehende Element eine oder mehrere Übereinstimmungen, jedoch so wenige wie möglich.  Es handelt sich um das träge Gegenstück des gierigen Quantifizierers `+`.  
  
 Der reguläre Ausdruck `\b\w+?\b` sucht beispielsweise ein oder mehrere durch Wortgrenzen getrennte Zeichen.  Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### Entspricht dem Zeichen null\- oder einmal \(träge Übereinstimmung\): ??  
 Der `??`\-Quantifizierer sucht für das vorangehende Element keine oder eine Übereinstimmungen, jedoch so wenige wie möglich.  Es handelt sich um das träge Gegenstück des gierigen Quantifizierers `?`.  
  
 Zum Beispiel versucht der reguläre Ausdruck `^\s*(System.)??Console.Write(Line)??\(??`, die Zeichenfolgen "Console.Write" oder "Console.WriteLine" zuzuordnen.  Die Zeichenfolge kann auch "System." vor "Console" enthalten und vor einer öffnenden Klammer stehen.  Die Zeichenfolge muss am Anfang einer Zeile stehen, ihr kann jedoch ein Leerzeichen vorangehen.  Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`^`|Entspricht dem Anfang des Eingabestreams.|  
|`\s*`|Sucht nach 0 \(null\) oder mehr Leerzeichen.|  
|`(System.)??`|Entspricht null oder einem Vorkommen der Zeichenfolge "System.".|  
|`Console.Write`|Übereinstimmung mit der Zeichenfolge "Console.Write".|  
|`(Line)??`|Übereinstimmung mit 0 \(null\) oder einem Vorkommen der Zeichenfolge "Line".|  
|`\(??`|Entspricht null oder einem Vorkommen der öffnenden Klammer.|  
  
### Entspricht genau n\-mal dem Zeichen \(träge Übereinstimmung\): {n}?  
 Der Quantifizierer `{`*n*`}?` entspricht die vorangehenden `n` des Elements Zeiten genau ab, wobei *n* eine ganze Zahl ist.  Es ist die verzögerte Entsprechung des Quantifizierers gierigen `{`*n*`}+`.  
  
 Im folgenden Beispiel wird der reguläre Ausdruck `\b(\w{3,}?\.){2}?\w{3,}?\b` verwendet, um eine Website\-Adresse zu identifizieren.  Es entspricht "www.microsoft.com" und "msdn.microsoft.com", jedoch nicht "mywebsite" oder "mycompany.com".  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(\w{3,}?\.)`|Entspricht mindestens drei Wortzeichen, doch möglichst wenigen Zeichen, gefolgt von einem Punktzeichen.  Dies ist die erste Erfassungsgruppe.|  
|`(\w{3,}?\.){2}?`|Entspricht dem Muster in der ersten zweimal, doch so wenige Male wie möglich.|  
|`\b`|Beendet den Vergleich an einer Wortgrenze.|  
  
### Entspricht mindestens n\-mal dem Zeichen \(träge Übereinstimmung\): {n,}?  
 Der Quantifizierer `{`*n*`,}?` entspricht die vorangehenden `n` Zeiten des Elements mindestens, wobei *n* eine ganze Zahl ist, jedoch so wenige Male wie möglich ab.  Es ist die verzögerte Entsprechung des Quantifizierers gierigen `{`*n*`,}`.  
  
 Im Beispiel für den Quantifizierer `{`*n*`}?` im vorangegangenen Abschnitt für eine Abbildung.  Der reguläre Ausdruck in diesem Beispiel verwendet den Quantifizierer `{`*n*`,}`, um eine Zeichenfolge zu finden, die mindestens drei Zeichen enthält, gefolgt von einem Punkt.  
  
### Entspricht dem Zeichen zwischen n\- und m\-mal \(träge Übereinstimmung\): {n,m}?  
 Der Quantifizierer `{`*n*`,`*m*`}?` entspricht dem vorangehenden Element zwischen `n` und `m` vorkommen, wobei *n* und *m* ganze Zahlen sind, jedoch so wenige Male wie möglich ab.  Es ist die verzögerte Entsprechung des Quantifizierers gierigen `{`*n*`,`*m*`}`.  
  
 Im folgenden Beispiel führt der reguläre Ausdruck `\b[A-Z](../../../amples/snippets/visualbasic/VS_Snippets_Remoting/SoapAttributes1/VB/s.vb){1,10}?[.!?]` zu Übereinstimmungen mit Sätzen, die zwischen einem und zehn Wörtern enthalten.  Er liefert alle Sätze der Eingabezeichenfolge als Ergebnis mit Ausnahme eines Satzes, der 18 Wörter enthält.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`[A-Z]`|Entspricht einem Großbuchstaben von A bis Z.|  
|`(\w*\s+)`|Entspricht null oder mehreren Wortzeichen gefolgt von mindestens einem Leerzeichen.  Dies ist die erste Erfassungsgruppe.|  
|`{1,10}?`|Entspricht dem vorangehenden Muster zwischen ein\- und zehnmal, jedoch so wenige Male wie möglich.|  
|`[.!?]`|Entspricht einem der Interpunktionszeichen ".","\! " oder"?".|  
  
<a name="Greedy"></a>   
## Gierige und träge Quantifizierer  
 Einige Quantifizierer kommen in zwei Versionen vor:  
  
-   Eine gierige Version.  
  
     Ein gieriger Quantifizierer sucht nach so vielen Übereinstimmungen mit dem Element wie möglich.  
  
-   Eine nicht gierige bzw. träge Version.  
  
     Ein nicht gieriger Quantifizierer sucht nach so wenigen Übereinstimmungen mit dem Element wie möglich.  Sie können einen gierigen Quantifizierer in einen faulen Quantifizierer umwandeln, indem Sie  `?` hinzufügen.  
  
 Betrachten Sie z. B. einen sehr einfachen regulären Ausdruck, der die letzten vier Ziffern einer Zahlenfolge, wie z. B. einer Kreditkartennummer, extrahieren soll.  Die Version des regulären Ausdrucks, der den gierigen Quantifizierer `*` verwendet, lautet `\b.*([0-9]{4})\b`.  Wenn eine Zeichenfolge jedoch zwei Zahlen enthält, entspricht der reguläre Ausdruck nur den letzten vier Ziffern der zweiten Zahl \(siehe folgendes Beispiel\).  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 Der reguläre Ausdruck liefert kein Ergebnis für die erste Zahl, da der `*`\-Quantifizierer in der gesamten Zeichenfolge nach so vielen Überereinstimmungen des vorangehenden Elements wie möglich sucht, und daher eine Entsprechung am Ende der Zeichenfolge feststellt.  
  
 Dies ist nicht das gewünschte Verhalten.  Stattdessen können Sie mit dem trägen Quantifizierer `*?` ``  Ziffern aus beiden Zahlen extrahieren \(siehe folgendes Beispiel\).  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 In den meisten Fällen geben reguläre Ausdrücke mit gierigen und trägen Quantifizierern die gleichen Übereinstimmungen zurück.  Normalerweise geben sie unterschiedliche Ergebnisse zurück, wenn sie mit dem Platzhaltermetazeichen \(`.`\) verwendet werden, das einem beliebigen Zeichen entspricht.  
  
## Quantifizierer und leere Übereinstimmungen  
 Die Quantifizierer `*`, `+` und `{`*n*`,`*m*`}` und ihre Entsprechungen verzögerten überprüfen nie nachdem eine leere Übereinstimmung, wenn die Mindestanzahl der Erfassungen gefunden wurde.  Diese Regel verhindert, dass Quantifizierer in Endlosschleifen für leere Übereinstimmungen mit Teilausdrücken eintreten, wenn die maximale Anzahl möglicher Gruppenaufzeichnungen unbegrenzt oder beinahe unbegrenzt ist.  
  
 Beispielsweise zeigt der folgende Code das Ergebnis eines Aufrufs der <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=fullName>\-Methode mit dem Muster eines regulären Ausdrucks `(a?)*` an, das mit keinem oder einem Zeichen "a" keinmal oder mehrmals übereinstimmt.  Beachten Sie, dass die einzelne Erfassungsgruppe jedes "a" sowie <xref:System.String.Empty?displayProperty=fullName> erfasst, aber keine zweite leere Übereinstimmung vorhanden ist, da der Quantifizierer nach der ersten leeren Übereinstimmung die Wiederholung beendet.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 Um den praktischen Unterschied zwischen einer Erfassungsgruppe, die eine minimale und maximale Anzahl von Erfassungen definiert, und einer Erfassungsgruppe anzuzeigen, die eine feste Anzahl von Erfassungen definiert, sollten Sie die Muster eines regulären Ausdrucks `(a\1|(?(1)\1)){0,2}` und `(a\1|(?(1)\1)){2}` berücksichtigen.  Beide reguläre Ausdrücke bestehen aus einer einzelnen Erfassungsgruppe, die entsprechend der folgenden Tabelle definiert ist.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`(a\1`|Entweder Übereinstimmung mit "a" zusammen mit dem Wert der ersten Erfassungsgruppe…|  
|`&#124;(?(1)`|… oder Test, ob die erste Erfassungsgruppe definiert wurde. \(Beachten Sie, dass das `(?(1)`\-Konstrukt keine Erfassungsgruppe definiert.\)|  
|`\1))`|Wenn die erste Erfassungsgruppe vorhanden ist, entspricht sie dem Wert.  Falls die Gruppe nicht vorhanden ist, entspricht die Gruppe <xref:System.String.Empty?displayProperty=fullName>.|  
  
 Der erste reguläre Ausdruck versucht, dieses Muster zwischen null und zweimal abzugleichen, der zweite genau zwei Mal.  Da das erste Muster die Mindestanzahl von Erfassungen mit der ersten Erfassung von <xref:System.String.Empty?displayProperty=fullName> erreicht, wiederholt es keine Versuche, `a\1` zu entsprechen. Der `{0,2}`\-Quantifizierer gestattet nur leere Übereinstimmungen in der letzten Iteration.  Im Gegensatz dazu entspricht der zweite reguläre Ausdruck "a", da er `a\1` ein zweites Mal auswertet. Die minimale Anzahl von Iterationen \(2\) erzwingt eine Wiederholung des Moduls nach einer leeren Übereinstimmung.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## Siehe auch  
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)   
 [Backtracking](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)