---
title: "Sprachelemente f&#252;r regul&#228;re Ausdr&#252;cke – Kurz&#252;bersicht | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.RegularExpressionBuilder"
helpviewer_keywords: 
  - "Reguläre Ausdrücke von .NET Framework, Sprachelemente"
  - "Spickzettel"
  - "Analysieren von Text mit regulären Ausdrücken, Sprachelemente"
  - "Mustervergleich mit regulären Ausdrücken, Sprachelemente"
  - "regex-Spickzettel"
  - "Reguläre Ausdrücke [.NET Framework]"
  - "Reguläre Ausdrücke, Sprachelemente"
  - "Suchen mit regulären Ausdrücken, Sprachelemente"
ms.assetid: 930653a6-95d2-4697-9d5a-52d11bb6fd4c
caps.latest.revision: 56
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 56
---
# Sprachelemente f&#252;r regul&#228;re Ausdr&#252;cke – Kurz&#252;bersicht
<a name="top"></a> Reguläre Ausdrücke sind Muster, für die das Modul für reguläre Ausdrücke eine Entsprechung im Eingabetext sucht. Muster können aus einem oder mehr Zeichenliteralen, Operatoren oder Konstrukten bestehen.  Eine kurze Einführung finden Sie unter [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md).  
  
 Jeder Abschnitt dieser Kurzübersicht enthält eine bestimmte Kategorie von Zeichen, Operatoren oder Konstrukten, mit denen Sie reguläre Ausdrücke definieren können:  
  
 [Escapezeichen](#character_escapes)  
 [Zeichenklassen](#character_classes)  
 [Anchor](#atomic_zerowidth_assertions)  
 [Gruppierungskonstrukte](#grouping_constructs)  
 [Quantifizierer](#quantifiers)  
 [Rückverweiskonstrukte](#backreference_constructs)  
 [Alternierungskonstrukte](#alternation_constructs)  
 [Ersetzungen](#substitutions)  
 [Optionen für reguläre Ausdrücke](#options)  
 [Verschiedene Konstrukte](#miscellaneous_constructs)  
  
 Diese Informationen stehen in zwei weiteren Formaten zur Verfügung, damit Sie sie zum Nachschlagen herunterladen und ausdrucken können:  
  
 [Download im Word\-Format \(DOCX\)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
[Download im PDF\-Format \(PDF\)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)  
  
<a name="character_escapes"></a>   
## Escapezeichen  
 Der umgekehrte Schrägstrich \(\\\) in einem regulären Ausdruck gibt an, dass es sich bei dem darauf folgenden Zeichen um ein Sonderzeichen \(wie in der folgenden Tabelle angezeigt\) handelt oder dass das Zeichen als solches interpretiert werden soll. Weitere Informationen finden Sie unter [Escapezeichen](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md).  
  
|Escapezeichen|Beschreibung|Muster|Übereinstimmungen|  
|-------------------|------------------|------------|-----------------------|  
|`\a`|Entspricht einem Klingelzeichen \(Warnsignal\) \\u0007.|`\a`|"\\u0007" in "Fehler\!" \+ '\\u0007'|  
|`\b`|Entspricht in einer Zeichenklasse einem Rücktastenzeichen \\u0008.|`[\b]{3,}`|"\\b\\b\\b\\b" in "\\b\\b\\b\\b"|  
|`\t`|Entspricht einem Tabstoppzeichen \\u0009.|`(\w+)\t`|"Element1\\t", "Element2\\t" in "Element1\\tElement2\\t"|  
|`\r`|Entspricht einem Wagenrücklaufzeichen \\u000D. \(`\r` entspricht nicht dem Zeilenumbruchzeichen `\n`.\)|`\r\n(\w+)`|"\\r\\nDies" in "\\r\\nDies sind\\nzwei Zeilen."|  
|`\v`|Entspricht einem vertikalen Tabstoppzeichen \\u000B.|`[\v]{2,}`|"\\v\\v\\v" in "\\v\\v\\v"|  
|`\f`|Entspricht einem Seitenvorschubzeichen \\u000C.|`[\f]{2,}`|"\\f\\f\\f" in "\\f\\f\\f"|  
|`\n`|Entspricht einer neuen Zeile \\u000A.|`\r\n(\w+)`|"\\r\\nDies" in "\\r\\nDies sind\\nzwei Zeilen."|  
|`\e`|Entspricht einem Escapezeichen \\u001B.|`\e`|"\\x001B" in "\\x001B"|  
|`\` *nnn*|Verwendet die oktale Darstellung, um ein Zeichen anzugeben \(*nnn* besteht aus zwei oder drei Ziffern\).|`\w\040\w`|"a b", "c d" in<br /><br /> "a bc d"|  
|`\x` *nn*|Verwendet die hexadezimale Darstellung, um ein Zeichen anzugeben \(*nn* besteht genau aus zwei Ziffern\).|`\w\x20\w`|"a b", "c d" in<br /><br /> "a bc d"|  
|`\c` *X*<br /><br /> `\c` *w*|Entspricht dem durch *X* oder *x* angegebenen ASCII\-Steuerzeichen, wobei *X* oder *x* der Buchstabe des Steuerzeichens ist.|`\cC`|"\\x0003" in "\\x0003" \(Strg\-C\)|  
|`\u` *nnnn*|Entspricht einem Unicode\-Zeichen in hexadezimaler Darstellung \(genau vier Stellen, dargestellt durch *nnnn*\).|`\w\u0020\w`|"a b", "c d" in<br /><br /> "a bc d"|  
|`\`|Entspricht dem angegebenen Zeichen, wenn darauf ein Zeichen folgt, das in dieser und anderen Tabellen in diesem Thema nicht als Escapezeichen erkannt wird. Beispielsweise ist `\*` identisch mit `\x2A` und `\.` entspricht `\x2E`. Hierdurch kann das Modul für reguläre Ausdrücke Sprachelemente \(z. B. \* oder?\) und Zeichenliterale \(dargestellt durch `\*` oder `\?`\) unterscheiden.|`\d+[\+-x\*]\d+`|"2\+2" und "3\*9" in "\(2\+2\) \* 3\*9"|  
  
 [Zurück nach oben](#top)  
  
<a name="character_classes"></a>   
## Zeichenklassen  
 Eine Zeichenklasse entspricht einer beliebigen Reihe von Zeichen. Zeichenklassen verwenden die in der folgenden Tabelle aufgeführten Sprachelemente. Weitere Informationen finden Sie unter [Zeichenklassen](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).  
  
|Zeichenklasse|Beschreibung|Muster|Übereinstimmungen|  
|-------------------|------------------|------------|-----------------------|  
|`[` *character\_group* `]`|Entspricht einem beliebigen einzelnen Zeichen in *character\_group*. Bei der Entsprechung wird standardmäßig die Groß\- und Kleinschreibung berücksichtigt.|`[ae]`|"a" in "wage"<br /><br /> "a", "e" in "klasse"|  
|`[^` *character\_group* `]`|Negation: Entspricht jedem beliebigen einzelnen Zeichen, das nicht in *character\_group* enthalten ist. Standardmäßig wird bei Zeichen in *character\_group* die Groß\-\/Kleinschreibung beachtet.|`[^aei]`|"r", "g", "n" in "ringen"|  
|`[` *first* `-` *last* `]`|Zeichenbereich: Entspricht jedem beliebigen einzelnen Zeichen im Bereich von *first* bis *last*.|`[A-Z]`|"A", "B" in "AB123"|  
|`.`|Platzhalterzeichen: Entspricht jedem beliebigen einzelnen Zeichen außer \\n.<br /><br /> Damit es einem Punkt als Literalzeichen entspricht \("." oder  oder `\u002E`, muss ihm ein Escapezeichen \(`\.`\) vorangestellt werden.|`a.e`|"ade" in "gerade"<br /><br /> "ase" in "klasse"|  
|`\p{` *Name* `}`|Entspricht jedem beliebigen Zeichen, das sich in der allgemeinen Unicode\-Kategorie oder einem von *name* angegebenen benannten Block befindet.|`\p{Lu}`<br /><br /> `\p{IsCyrillic}`|"S", "M" in "Staatliche Museen"<br /><br /> "Д", "Ж" in "ДЖem"|  
|`\P{` *Name* `}`|Entspricht jedem beliebigen Zeichen, das sich nicht in der allgemeinen Unicode\-Kategorie oder einem von *name* angegebenen benannten Block befindet.|`\P{Lu}`<br /><br /> `\P{IsCyrillic}`|"a", "d", "t" in "Stadt"<br /><br /> "e", "m" in "ДЖem"|  
|`\w`|Entspricht einem beliebigen Wortzeichen.|`\w`|"I", "D", "A", "1", "3" in "ID A1.3"|  
|`\W`|Entspricht einem beliebigen Nichtwortzeichen.|`\W`|" ", "." in "ID A1.3"|  
|`\s`|Entspricht einem beliebigen Leerraumzeichen.|`\w\s`|"D " in "ID A1.3"|  
|`\S`|Entspricht einem beliebigen Nicht\-Leerraumzeichen.|`\s\S`|" \_" in "int \_\_ctr"|  
|`\d`|Entspricht einer beliebigen Dezimalziffer.|`\d`|"4" in "4 \= IV"|  
|`\D`|Entspricht einem beliebigen Zeichen, das keine Dezimalziffer ist.|`\D`|" ", "\=", " ", "I", "V" in "4 \= IV"|  
  
 [Zurück nach oben](#top)  
  
<a name="atomic_zerowidth_assertions"></a>   
## Anchor  
 Anchor oder atomare Assertionen mit einer Breite von Null bewirken, dass, in Abhängigkeit von der Position in der Zeichenfolge, eine Entsprechung gefunden oder nicht gefunden wird. Sie bewirken jedoch nicht, dass das Modul die Zeichenfolge durchläuft oder Zeichen verwendet. Die Metazeichen in der folgenden Tabelle sind Anchor. Weitere Informationen finden Sie unter [Anchor](../../../docs/standard/base-types/anchors-in-regular-expressions.md).  
  
|Assertion|Beschreibung|Muster|Übereinstimmungen|  
|---------------|------------------|------------|-----------------------|  
|`^`|Der Vergleich muss am Anfang der Zeichenfolge oder Zeile beginnen.|`^\d{3}`|"901" in<br /><br /> "901\-333\-"|  
|`$`|Der Vergleich muss am Ende der Zeichenfolge oder vor `\n` am Ende der Zeile oder Zeichenfolge erfolgen.|`-\d{3}$`|"\-333" in<br /><br /> "\-901\-333"|  
|`\A`|Der Vergleich muss am Beginn der Zeichenfolge erfolgen.|`\A\d{3}`|"901" in<br /><br /> "901\-333\-"|  
|`\Z`|Der Vergleich muss am Ende der Zeichenfolge oder vor `\n` am Ende der Zeichenfolge erfolgen.|`-\d{3}\Z`|"\-333" in<br /><br /> "\-901\-333"|  
|`\z`|Der Vergleich muss am Ende der Zeichenfolge erfolgen.|`-\d{3}\z`|"\-333" in<br /><br /> "\-901\-333"|  
|`\G`|Der Vergleich muss an dem Punkt erfolgen, an dem der vorherige Vergleich beendet wurde.|`\G\(\d\)`|"\(1\)", "\(3\)", "\(5\)" in "\(1\)\(3\)\(5\)\[7\]\(9\)"|  
|`\b`|Der Vergleich muss an einer Begrenzung zwischen einem `\w` \(alphanumerischen\) und einem `\W` \(nicht alphanumerischen\) Zeichen erfolgen.|`\b\w+\s\w+\b`|"dem demnach", "dem dem" in "dem demnach dem dem"|  
|`\B`|Der Vergleich darf nicht an einer `\b`\-Begrenzung erfolgen.|`\Bend\w*\b`|"ends", "ender" in "end sendet endete sender"|  
  
 [Zurück nach oben](#top)  
  
<a name="grouping_constructs"></a>   
## Gruppierungskonstrukte  
 Gruppierungskonstrukte grenzen Teilausdrücke eines regulären Ausdrucks ab und zeichnen gewöhnlich Teilzeichenfolgen einer Eingabezeichenfolge auf. Gruppierungskonstrukte verwenden die Sprachelemente in der folgenden Tabelle. Weitere Informationen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
|Gruppierungskonstrukt|Beschreibung|Muster|Übereinstimmungen|  
|---------------------------|------------------|------------|-----------------------|  
|`(` *Teilausdruck* `)`|Zeichnet den übereinstimmenden Teilausdruck auf und weist diesem eine einsbasierte Ordinalzahl zu.|`(\w)\1`|"aa" in "paarweise"|  
|`(?<` *name* `>` *subexpression*`)`|Zeichnet den übereinstimmenden Teilausdruck in einer benannten Gruppe auf.|`(?<double>\w)\k<double>`|"aa" in "paarweise"|  
|`(?<` *name1* `-` *name2* `>` *subexpression*`)`|Definiert eine Ausgleichsgruppendefinition. Weitere Informationen finden Sie im Abschnitt „Ausgleichen von Gruppendefinitionen“ in [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).|`(((?'Open'\()[^\(\)]*)+((?'Close-Open'\))[^\(\)]*)+)*(?(Open)(?!))$`|"\(\(1\-3\)\*\(3\-1\)\)" in "3\+2^\(\(1\-3\)\*\(3\-1\)\)"|  
|`(?:` *subexpression*`)`|Definiert eine Nicht\-Erfassungsgruppe.|`Write(?:Line)?`|"WriteLine" in "Console.WriteLine\(\)"<br /><br /> "Write" in "Console.Write\(value\)"|  
|`(?imnsx-imnsx:` *Teilausdruck*`)`|Aktiviert oder deaktiviert die angegebenen Optionen in *subexpression*. Weitere Informationen finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).|`A\d{2}(?i:\w+)\b`|"A12xl", "A12XL" in "A12xl A12XL a12xl"|  
|`(?=` *subexpression*`)`|Positive Lookaheadassertion mit einer Breite von Null.|`\w+(?=\.)`|"is", "ren" und "weg" in "Er isst. Der Hund rennt. Die Sonne ist weg."|  
|`(?!` *subexpression*`)`|Negative Lookaheadassertion mit einer Breite von Null.|`\b(?!un)\w+\b`|"sicher", "mischt" in "unsicher sicher unter mischt"|  
|`(?<=` *subexpression*`)`|Positive Lookbehindassertion mit einer Breite von Null.|`(?<=19)\d{2}\b`|"99", "50", "05" in "1851 1999 1950 1905 2003"|  
|`(?<!` *subexpression*`)`|Negative Lookbehindassertion mit einer Breite von Null.|`(?<!19)\d{2}\b`|"51", "03" in "1851 1999 1950 1905 2003"|  
|`(?>` *subexpression*`)`|Nicht zurückverfolgender \("gieriger"\) Teilausdruck.|`[13579](?>A+B+)`|"1ABB", "3ABB", and "5AB" in "1ABB 3ABBC 5AB 5AC"|  
  
 [Zurück nach oben](#top)  
  
<a name="quantifiers"></a>   
## Quantifizierer  
 Quantifizierer geben an, wie viele Instanzen des vorherigen Elements \(bei dem es sich um ein Zeichen, eine Gruppe oder eine Zeichenklasse handeln kann\) in der Eingabezeichenfolge vorhanden sein müssen, damit eine Entsprechung gefunden wird. Quantifizierer verwenden die Sprachelemente in der folgenden Tabelle. Weitere Informationen finden Sie unter [Quantifizierer](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
|Quantifizierer|Beschreibung|Muster|Übereinstimmungen|  
|--------------------|------------------|------------|-----------------------|  
|`*`|Entspricht dem vorangehenden Element nicht oder mehrmals.|`\d*\.\d`|".0", "19.9", "219.9"|  
|`+`|Entspricht dem vorangehenden Element einmal oder mehrmals.|`"be+"`|"bei" in beim"", "be" in "bei"|  
|`?`|Entspricht dem vorangehenden Element nicht oder einmal.|`"rai?n"`|"ran", "rain"|  
|`{` *n* `}`|Entspricht dem vorangehenden Element genau *n*\-mal.|`",\d{3}"`|",043" in "1,043.6", ",876", ",543" und ",210" in "9,876,543,210"|  
|`{` *n* `,}`|Entspricht dem vorangehenden Element mindestens *n*\-mal.|`"\d{2,}"`|"166", "29", "1930"|  
|`{` *n* `,` *m* `}`|Entspricht dem vorangehenden Element mindestens *n*\-, höchstens jedoch *m*\-mal.|`"\d{3,5}"`|"166", "17668"<br /><br /> "19302" in "193024"|  
|`*?`|Entspricht dem vorangehenden Element nicht oder mehrmals, jedoch so wenige Male wie möglich.|`\d*?\.\d`|".0", "19.9", "219.9"|  
|`+?`|Entspricht dem vorangehenden Element ein\- oder mehrmals, jedoch so wenige Male wie möglich.|`"be+?"`|"be" in "beim", "be" in "bei"|  
|`??`|Entspricht dem vorangehenden Element nicht oder einmal, jedoch so wenige Male wie möglich.|`"rai??n"`|"ran", "rain"|  
|`{` *n* `}?`|Entspricht dem vorangehenden Element genau *n*\-mal.|`",\d{3}?"`|",043" in "1,043.6", ",876", ",543" und ",210" in "9,876,543,210"|  
|`{` *n* `,}?`|Entspricht dem vorangehenden Element mindestens *n*\-mal, jedoch so wenige Male wie möglich.|`"\d{2,}?"`|"166", "29", "1930"|  
|`{` *n* `,` *m* `}?`|Entspricht dem vorangehenden Element zwischen *n*\- und *m*\-mal, jedoch so wenige Male wie möglich.|`"\d{3,5}?"`|"166", "17668"<br /><br /> "193", "024" in "193024"|  
  
 [Zurück nach oben](#top)  
  
<a name="backreference_constructs"></a>   
## Rückverweiskonstrukte  
 Ein Rückverweis ermöglicht es, einen zuvor gefundenen Teilausdruck später im gleichen regulären Ausdruck zu identifizieren. In der folgenden Tabelle sind die Rückverweiskonstrukte aufgeführt, die von regulären .NET Framework\-Ausdrücken unterstützt werden. Weitere Informationen finden Sie unter [Rückverweiskonstrukte](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).  
  
|Rückverweiskonstrukt|Beschreibung|Muster|Übereinstimmungen|  
|--------------------------|------------------|------------|-----------------------|  
|`\` *number*|Rückverweis. Entspricht dem Wert eines nummerierten Teilausdrucks.|`(\w)\1`|"ee" in "beseelt"|  
|`\k<` *Name* `>`|Benannter Rückverweis. Entspricht dem Wert eines benannten Ausdrucks.|`(?<char>\w)\k<char>`|"ee" in "beseelt"|  
  
 [Zurück nach oben](#top)  
  
<a name="alternation_constructs"></a>   
## Alternierungskonstrukte  
 Alternierungskonstrukte ändern einen regulären Ausdruck, um entweder\/oder\-Vergleiche zuzulassen. Diese Konstrukte verwenden die Sprachelemente in der folgenden Tabelle. Weitere Informationen finden Sie unter [Alternierungskonstrukte](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md).  
  
|Alternierungskonstrukt|Beschreibung|Muster|Übereinstimmungen|  
|----------------------------|------------------|------------|-----------------------|  
|`&#124;`|Entspricht jedem beliebigen durch einen senkrechten Strich \(&#124;\) getrennten Element.|`th(e&#124;is&#124;at)`|"the", "this" in "This is the day. "|  
|`(?(` *expression* `)` *ja* `&#124;` *nein* `)`|Entspricht *yes*, wenn das von *expression* angegebene Muster für reguläre Ausdrücke übereinstimmt. Andernfalls entspricht es dem optionalen *no*.*expression* wird als Assertion mit einer Breite von Null interpretiert.|`(?(A)A\d{2}\b&#124;\b\d{3}\b)`|"A10", "910" in "A10 C103 910"|  
|`(?(` *Name* `)` *ja* `&#124;` *nein* `)`|Entspricht *yes*, wenn *name*, eine benannte oder nummerierte Erfassungsgruppe, eine Übereinstimmung aufweist. Andernfalls entspricht es dem optionalen *no*.|`(?<quoted>")?(?(quoted).+?"&#124;\S+\s)`|Hund.jpg, "Yiska spielt.jpg" in "Hund.jpg "Yiska spielt.jpg""|  
  
 [Zurück nach oben](#top)  
  
<a name="substitutions"></a>   
## Ersetzungen  
 Ersetzungen sind Sprachelemente regulärer Ausdrücke, die in Ersetzungsmustern unterstützt werden. Weitere Informationen finden Sie unter [Ersetzungen](../../../docs/standard/base-types/substitutions-in-regular-expressions.md). Die Metazeichen in der folgenden Tabelle sind atomare Assertionen mit einer Breite von Null.  
  
|Zeichen|Beschreibung|Muster|Ersetzungsmuster|Eingabezeichenfolge|Ergebniszeichenfolge|  
|-------------|------------------|------------|----------------------|-------------------------|--------------------------|  
|`$` *number*|Ersetzt die untergeordnete Zeichenfolge, die der *number* einer Gruppe entspricht.|`\b(\w+)(\s)(\w+)\b`|`$3$2$1`|"one two"|"two one"|  
|`${` *Name* `}`|Ersetzt die untergeordnete Zeichenfolge, die dem genannten *name* der Gruppe entspricht.|`\b(?<word1>\w+)(\s)(?<word2>\w+)\b`|`${word2} ${word1}`|"one two"|"two one"|  
|`$$`|Ersetzt ein "$"\-Literal.|`\b(\d+)\s?USD`|`$$$1`|"103 USD"|"$103"|  
|`$&`|Ersetzt eine Kopie der gesamten Entsprechung.|`\$?\d*\.?\d+`|`**$&**`|"$1.30"|"\*\*$1.30\*\*"|  
|`$``|Ersetzt den gesamten Text der Eingabezeichenfolge vor der Entsprechung.|`B+`|`$``|"AABBCC"|"AAAACC"|  
|`$'`|Ersetzt den gesamten Text der Eingabezeichenfolge nach der Entsprechung.|`B+`|`$'`|"AABBCC"|"AACCCC"|  
|`$+`|Ersetzt die zuletzt erfasste Gruppe.|`B+(C+)`|`$+`|"AABBCCDD"|AACCDD|  
|`$_`|Ersetzt die gesamte Eingabezeichenfolge.|`B+`|`$_`|"AABBCC"|"AAAABBCCCC"|  
  
 [Zurück nach oben](#top)  
  
<a name="options"></a>   
## Optionen für reguläre Ausdrücke  
 Sie können Optionen angeben, die steuern, wie das Modul für reguläre Ausdrücke ein Muster des regulären Ausdrucks interpretiert. Viele dieser Optionen können entweder inline \(im Muster des regulären Ausdrucks\) oder als eine oder mehrere <xref:System.Text.RegularExpressions.RegexOptions>\-Konstanten angegeben werden. Diese Kurzübersicht enthält nur Inlineoptionen. Weitere Informationen zu Inlineoptionen und <xref:System.Text.RegularExpressions.RegexOptions>\-Optionen finden Sie im Artikel [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
 Sie können eine Inlineoption auf zwei Arten angeben:  
  
-   Mit `(?imnsx-imnsx)`, einem der [verschiedenen Konstrukte](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md), bei dem ein Minuszeichen \(\-\) vor einer Option oder einem Optionensatz diese Optionen deaktiviert. Zum Beispiel aktiviert `(?i-mn)` Übereinstimmungen ohne Berücksichtigung der Groß\-\/Kleinschreibung \(`i`\), deaktiviert Mehrzeilenmodus \(`m`\) und deaktiviert unbenannte Gruppenerfassungen \(`n`\). Die Option gilt für das Muster des regulären Ausdrucks ab dem Punkt, an dem die Option definiert ist, und ist entweder bis zum Ende des Musters oder bis zu dem Punkt gültig, an dem ein anderes Konstrukt die Option umkehrt.  
  
-   Mit dem [Gruppierungskonstrukt](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md)`(?imnsx-imnsx:`*subexpression*`)`, das die Optionen nur für die angegebene Gruppe definiert.  
  
 Das .NET Framework\-Modul für reguläre Ausdrücke unterstützt die folgenden Inlineoptionen.  
  
|Option|Beschreibung|Muster|Übereinstimmungen|  
|------------|------------------|------------|-----------------------|  
|`i`|Groß\-\/Kleinschreibung bei der Suche ignorieren|`\b(?i)a(?-i)a\w+\b`|"Aale" und "Aasblumen" in "Aale essen Aasblumen roh"|  
|`m`|Mehrzeilenmodus verwenden.`^` und `$` entsprechen dem Anfang und Ende einer Zeile anstatt dem Anfang und Ende einer Zeichenfolge.|Ein Beispiel finden Sie im Abschnitt zum Mehrzeilenmodus in [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).||  
|`n`|Unbenannte Gruppen nicht erfassen|Ein Beispiel finden Sie im Abschnitt zu ausschließlich expliziten Erfassungen in [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).||  
|`s`|Einzeilenmodus verwenden|Ein Beispiel finden Sie im Abschnitt zum Einzeilenmodus in [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).||  
|`x`|Leerraum ohne Escapezeichen im Muster eines regulären Ausdrucks ignorieren|`\b(?x) \d+ \s \w+`|"1 Erdferkel", "2 Katzen" in "1 Erdferkel 2 Katzen IV Zenturionen"|  
  
 [Zurück nach oben](#top)  
  
<a name="miscellaneous_constructs"></a>   
## Verschiedene Konstrukte  
 Verschiedene Konstrukte ändern Muster von regulären Ausdrücken oder stellen Informationen darüber bereit. In der folgenden Tabelle sind die verschiedenen Konstrukte aufgeführt, die von .NET Framework unterstützt werden. Weitere Informationen finden Sie unter [Verschiedene Konstrukte](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md).  
  
|Konstrukt|Definition|Beispiel|  
|---------------|----------------|--------------|  
|`(?imnsx-imnsx)`|Aktiviert oder deaktiviert Optionen wie die Groß\-\/Kleinschreibung mitten in einem Muster. Weitere Informationen finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).|`\bA(?i)b\w+\b` entspricht "ABA", "Able" in "ABA Able Act"|  
|`(?#` *comment*`)`|Inlinekommentar. Der Kommentar endet bei der ersten schließenden Klammer.|`\bA(?#Matches words starting with A)\w+\b`|  
|`#` \[bis Zeilenende\]|X‑Modus\-Kommentar. Der Kommentar beginnt bei einem `#` ohne Escapezeichen und reicht bis zum Ende der Zeile.|`(?x)\bA\w+\b#Matches words starting with A`|  
  
## Siehe auch  
 <xref:System.Text.RegularExpressions?displayProperty=fullName>   
 <xref:System.Text.RegularExpressions.Regex>   
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)   
 [Klassen für reguläre Ausdrücke](../../../docs/standard/base-types/the-regular-expression-object-model.md)   
 [Beispiele für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-examples.md)   
 [Reguläre Ausdrücke – Kurzübersicht \(Download im Word\-Format\)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)   
 [Reguläre Ausdrücke – Kurzübersicht \(Download im PDF\-Format\)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)