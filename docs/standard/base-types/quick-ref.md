---
title: "Sprachelemente für reguläre Ausdrücke – Kurzübersicht"
description: "Sprachelemente für reguläre Ausdrücke – Kurzübersicht"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8c5dee8c-7bc7-4e6e-aff1-986965c4d98e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a6644fc2431beafa2128287eeac73bd598ee304a
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expression-language---quick-reference"></a>Sprachelemente für reguläre Ausdrücke – Kurzübersicht

Reguläre Ausdrücke sind Muster, für die das Modul für reguläre Ausdrücke eine Entsprechung im Eingabetext sucht. Muster können aus einem oder mehr Zeichenliteralen, Operatoren oder Konstrukten bestehen. Eine kurze Einführung finden Sie unter [Reguläre Ausdrücke in .NET](regular-expressions.md). 

Jeder Abschnitt dieser Kurzübersicht enthält eine bestimmte Kategorie von Zeichen, Operatoren oder Konstrukten, mit denen Sie reguläre Ausdrücke definieren können: 

* [Escapezeichen](#character-escapes)

* [Zeichenklassen](#character-classes)
      
* [Anchor](#anchors)
    
* [Gruppierungskonstrukte](#grouping-constructs)
      
* [Quantifizierer](#quantifiers)
    
* [Rückverweiskonstrukte](#backreference-constructs)
      
* [Alternierungskonstrukte](#alternation-constructs)
     
* [Ersetzungen](#substitutions)
      
* [Optionen für reguläre Ausdrücke](#regular-expression-options)
      
* [Verschiedene Konstrukte](#miscellaneous-constructs)

Diese Informationen stehen in zwei weiteren Formaten zur Verfügung, damit Sie sie zum Nachschlagen herunterladen und ausdrucken können: 

* [Download im Word-Format (DOCX)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)
    
* [Download im PDF-Format (PDF)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)
    
## <a name="character-escapes"></a>Escapezeichen

Der umgekehrte Schrägstrich (\) in einem regulären Ausdruck gibt an, dass es sich bei dem darauf folgenden Zeichen um ein Sonderzeichen handelt (wie in der folgenden Tabelle gezeigt) oder dass das Zeichen als solches interpretiert werden soll. Weitere Informationen finden Sie unter [Escapezeichen in regulären Ausdrücken](escapes.md). 

Escapezeichen | Beschreibung | Muster | Übereinstimmungen
----------------- | ----------- | ------- | -------
**\a** | Entspricht einem Klingelzeichen (Warnsignal) \u0007. | `\a` | "\u0007" in "Fehler!" + '\u0007'
**\b** | Entspricht in einer Zeichenklasse einem Rücktastenzeichen \u0008. | `[\b]{3,}` | "\b\b\b\b" in "\b\b\b\b"
**\t** | Entspricht einem Tabstoppzeichen \u0009. | `(\w+)\t` | "Element1\t", "Element2\t" in "Element1\tElement2\t"
**\r** | Entspricht einem Wagenrücklaufzeichen \u000D. (**\r** entspricht nicht dem Zeilenumbruchzeichen **\n**.) | `\r\n(\w+)` | "\r\nDies" in "\r\nDies sind\nzwei Zeilen."
**\v** | Entspricht einem vertikalen Tabstoppzeichen \u000B. | `[\v]{2,}` | "\v\v\v" in "\v\v\v"
**\f** | Entspricht einem Seitenvorschubzeichen \u000C. | `[\f]{2,}` | "\f\f\f" in "\f\f\f" 
**\n** | Entspricht einer neuen Zeile \u000A. | `\r\n(\w+)` | "\r\nDies" in "\r\nDies sind\nzwei Zeilen."
**\e** | Entspricht einem Escapezeichen \u001B. | `\e` | "\x001B" in "\x001B"
**\**_nnn_ | Verwendet die oktale Darstellung, um ein Zeichen anzugeben (*nnn* besteht aus zwei oder drei Ziffern). | `\w\040\w` | "a b", "c d" in "a bc d"
**\x**_nn_ | Verwendet die hexadezimale Darstellung, um ein Zeichen anzugeben (*nn* besteht genau aus zwei Ziffern). | `\w\x20\w` | "a b", "c d" in "a bc d"
**\c**_X_ oder **\c**_x_ | Entspricht dem durch *X* oder *x* angegebenen ASCII-Steuerzeichen, wobei *X* oder *x* der Buchstabe des Steuerzeichens ist. | `\cC` | "\x0003" in "\x0003" (Strg-C) 
**\u**_nnnn_ | Entspricht einem Unicode-Zeichen in hexadezimaler Darstellung (genau vier Stellen, dargestellt durch *nnnn*). | `\w\u0020\w` | "a b", "c d" in "a bc d"
**\\** | Entspricht dem angegebenen Zeichen, wenn darauf ein Zeichen folgt, das in dieser und anderen Tabellen in diesem Thema nicht als Escapezeichen erkannt wird. Beispielsweise ist __\*__ identisch mit **\x2A**, und **\.** entspricht **\x2E**. Hierdurch kann das Modul für reguläre Ausdrücke Sprachelemente (z.B. `*` oder `?`) und Zeichenliterale (dargestellt durch `\*` oder `\?)`) unterscheiden. | `\d+[\+-x\*]\d+` | "2+2" und "3*9" in "(2+2) * 3*9"
 
## <a name="character-classes"></a>Zeichenklassen

Eine Zeichenklasse entspricht einer beliebigen Reihe von Zeichen. Zeichenklassen verwenden die in der folgenden Tabelle aufgeführten Sprachelemente. Weitere Informationen finden Sie unter [Zeichenklassen in regulären Ausdrücken](classes.md).

Zeichenklasse | Beschreibung | Muster | Übereinstimmungen
--------------- | ----------- | ------- | ------- 
__[__*Zeichengruppe*__]__ | Entspricht einem beliebigen einzelnen Zeichen in „Zeichengruppe“. Bei der Entsprechung wird standardmäßig die Groß- und Kleinschreibung berücksichtigt. | `[ae]` | "a" in "grau", "a", "e" in "Sahne"
__[^__*Zeichengruppe*__]__ | Negation: Entspricht jedem beliebigen einzelnen Zeichen, das nicht in *Zeichengruppe* enthalten ist. Standardmäßig wird bei Zeichen in *Zeichengruppe* die Groß-/Kleinschreibung beachtet. | `[^aei]` |  "r", "g", "n" in "ringen"
__[__*erstes-letztes*__]__ | Zeichenbereich: Entspricht jedem beliebigen einzelnen Zeichen im Bereich von *erstes* bis *letztes*. | `[A-Z]` | "A", "B" in "AB123"
**.** | Platzhalterzeichen: Entspricht jedem beliebigen einzelnen Zeichen außer \n. Damit es einem Punkt als Literalzeichen entspricht ("." oder  \u002E), muss ihm ein Escapezeichen (\.) vorangestellt werden. | `a.e` |  "abe" in "Rabe", "ate" in "Kate"
__\p{__*name*__}__ | Entspricht jedem beliebigen Zeichen, das sich in der allgemeinen Unicode-Kategorie oder einem durch *name* angegebenen benannten Block befindet. | `\p{Lu}`, `\p{IsCyrillic}` | "C", "L" in "City Lights", "?", "?" in "??em"
__\P{__*name*__}__ | Entspricht jedem beliebigen Zeichen, das sich nicht in der allgemeinen Unicode-Kategorie oder einem durch *name* angegebenen benannten Block befindet. | `\P{Lu}`, `\P{IsCyrillic}` |` "i", "t", "y" in "City", "e", "m" in "??em"
**\w** | Entspricht einem beliebigen Wortzeichen. | `\w` | "I", "D", "A", "1", "3" in "ID A1.3" 
**\W** | Entspricht einem beliebigen Nichtwortzeichen. | `\W` | " ", "." in "ID A1.3"
**\s** | Entspricht einem beliebigen Leerraumzeichen. | `\w\s` | "D " in "ID A1.3"
**\S** | Entspricht einem beliebigen Nicht-Leerraumzeichen. | `\s\S` | " _" in "int __ctr" 
**\d** | Entspricht einer beliebigen Dezimalziffer. | `\d` | "4" in "4 = IV" 
**\D** | Entspricht einem beliebigen Zeichen, das keine Dezimalziffer ist. | `\D` | " ", "=", " ", "I", "V" in "4 = IV" 

## <a name="anchors"></a>Anchor

Anchor oder atomare Assertionen mit einer Breite von Null bewirken, dass, in Abhängigkeit von der Position in der Zeichenfolge, eine Entsprechung gefunden oder nicht gefunden wird. Sie bewirken jedoch nicht, dass das Modul die Zeichenfolge durchläuft oder Zeichen verwendet. Die Metazeichen in der folgenden Tabelle sind Anchor. Weitere Informationen finden Sie unter [Anker in regulären Ausdrücken](anchors.md).

Assertion | Beschreibung | Muster | Übereinstimmungen
--------- | ----------- | ------- | ------- 
**^** | Der Vergleich muss am Anfang der Zeichenfolge oder Zeile beginnen. | `^\d{3}` | "901" in "901-333-"
**$** | Der Abgleich muss am Ende der Zeichenfolge oder vor **\n** am Ende der Zeile oder Zeichenfolge erfolgen. | `-\d{3}$` | "-333" in "-901-333"
**\A** | Der Vergleich muss am Beginn der Zeichenfolge erfolgen. | `\A\d{3}` | "901" in "901-333-"
**\Z** | Die Übereinstimmung muss am Ende der Zeichenfolge oder vor **\n** am Ende der Zeichenfolge vorliegen. | `-\d{3}\Z` | "-333" in "-901-333"
**\z** | Der Vergleich muss am Ende der Zeichenfolge erfolgen. | `-\d{3}\z` | "-333" in "-901-333"
**\G** | Der Vergleich muss an dem Punkt erfolgen, an dem der vorherige Vergleich beendet wurde. | `\G\(\d\)` | "(1)", "(3)", "(5)" in "(1)(3)(5)[7]&#40;9)"
**\b** | Die Übereinstimmung muss an einer Begrenzung zwischen einem **\w** (alphanumerisch) und einem **\W** (nicht alphanumerisch) vorliegen. | `\b\w+\s\w+\b` | "dem demnach", "dem dem" in "dem demnach dem dem" 
**\B** | Die Übereinstimmung darf nicht an einer **\b**-Begrenzung erfolgen. | `\Bend\w*\b` | "ends", "ender" in "end sendet endete sender"

## <a name="grouping-constructs"></a>Gruppierungskonstrukte

Gruppierungskonstrukte grenzen Teilausdrücke eines regulären Ausdrucks ab und zeichnen gewöhnlich Teilzeichenfolgen einer Eingabezeichenfolge auf. Gruppierungskonstrukte verwenden die Sprachelemente in der folgenden Tabelle. Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

Gruppierungskonstrukt | Beschreibung | Muster | Übereinstimmungen
------------------ | ----------- | ------- | ------- 
**(**_teilausdruck_**)** | Zeichnet den übereinstimmenden Teilausdruck auf und weist diesem eine einsbasierte Ordinalzahl zu. | `(\w)\1` | "aa" in "paarweise"
**(?**<name> _teilausdruck_**)** | Zeichnet den übereinstimmenden Teilausdruck in einer benannten Gruppe auf. | `(?<double>\w)\k<double>` | "aa" in "paarweise"
**(?**<name1-name2> _teilausdruck_**)** | Definiert eine Ausgleichsgruppendefinition. Weitere Informationen finden Sie im Abschnitt [Ausgleichen von Gruppendefinitionen](grouping.md#balancing-group-definitions) unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md). | `(((?'Open'\()[^\(\)]*)+((?'Close-Open'\))[^\(\)]*)+)*(?(Open)(?!))$` | "((1-3)*(3-1))" in "3+2^((1-3)*(3-1))"
**(?**: teilausdruck**)** | Definiert eine Nicht-Erfassungsgruppe. | `Write(?:Line)?` | "WriteLine" in "Console.WriteLine()", "Write" in "Console.Write(value)"
**(?imnsx-imnsx**: _teilausdruck_**)** | Aktiviert oder deaktiviert die angegebenen Optionen in _teilausdruck_. Weitere Informationen finden Sie unter [Optionen für reguläre Ausdrücke](options.md). | `A\d{2}(?i:\w+)\b` | "A12xl", "A12XL" in "A12xl A12XL a12xl"
**(?**= _teilausdruck_**)** | Positive Lookaheadassertion mit einer Breite von Null. | `\w+(?=\.)` | "is", "ren" und "weg" in "Er isst. Der Hund rennt. Die Sonne ist weg."
**(?!** _teilausdruck_**)** | Negative Lookaheadassertion mit einer Breite von Null. | `\b(?!un)\w+\b` | "sicher", "mischt" in "unsicher sicher unter mischt"
**(?**<= _teilausdruck_**)** | Positive Lookbehindassertion mit einer Breite von Null. | `(?<=19)\d{2}\b` | "99", "50", "05" in "1851 1999 1950 1905 2003"
**(?**<! _teilausdruck_**)** | Negative Lookbehindassertion mit einer Breite von Null. | `(?<!19)\d{2}\b` | "51", "03" in "1851 1999 1950 1905 2003"
**(?**> _teilausdruck_**)** | Nicht zurückverfolgender ("gieriger") Teilausdruck. | `[13579](?>A+B+)` | "1ABB", "3ABB", and "5AB" in "1ABB 3ABBC 5AB 5AC"

## <a name="quantifiers"></a>Quantifizierer

Quantifizierer geben an, wie viele Instanzen des vorherigen Elements (bei dem es sich um ein Zeichen, eine Gruppe oder eine Zeichenklasse handeln kann) in der Eingabezeichenfolge vorhanden sein müssen, damit eine Entsprechung gefunden wird. Quantifizierer verwenden die Sprachelemente in der folgenden Tabelle. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](quantifiers.md).

Quantifizierer | Beschreibung | Muster | Übereinstimmungen
---------- | ----------- | ------- | -------
__*__ | Entspricht dem vorangehenden Element nicht oder mehrmals. | `\d*\.\d` | ".0", "19.9", "219.9"
**+** | Entspricht dem vorangehenden Element einmal oder mehrmals. | `"be+"` | "bei" in beim"", "be" in "bei"
**?** | Entspricht dem vorangehenden Element nicht oder einmal. | `"rai?n"` | "ran", "rain"
**{**_n_**}** | Entspricht dem vorangehenden Element genau *n*-mal. | `",\d{3}"` | ",043" in "1,043.6", ",876", ",543" und ",210" in "9,876,543,210"
**{**_n_,**}** | Entspricht dem vorangehenden Element mindestens *n*-mal. | `"\d{2,}"` | "166", "29", "1930"
**{**_n_,_m_**}** | Entspricht dem vorangehenden Element mindestens *n*-, höchstens jedoch *m*-mal. | `"\d{3,5}"` | "166", "17668"; "19302" in "193024"
__*?__ | Entspricht dem vorangehenden Element nicht oder mehrmals, jedoch so wenige Male wie möglich. | `\d*?\.\d` | ".0", "19.9", "219.9"
**+?** | Entspricht dem vorangehenden Element ein- oder mehrmals, jedoch so wenige Male wie möglich. | `"be+?"` | "be" in "beim", "be" in "bei"
**??** | Entspricht dem vorangehenden Element nicht oder einmal, jedoch so wenige Male wie möglich. | `"rai??n"` | "ran", "rain"
**{**_n_**}?** | Entspricht dem vorangehenden Element genau *n*-mal. | `",\d{3}?"` | ",043" in "1,043.6", ",876", ",543" und ",210" in "9,876,543,210"
**{**_n_,**}?** | Entspricht dem vorangehenden Element mindestens *n*-mal, jedoch so wenige Male wie möglich. | `"\d{2,}?"` | "166", "29", "1930"
**{**_n_,_m_**}?** | Entspricht dem vorangehenden Element zwischen *n*- und *m*-mal, jedoch so wenige Male wie möglich. | `"\d{3,5}?"` | "166", "17668"; "193", "024" in "193024"

## <a name="backreference-constructs"></a>Rückverweiskonstrukte

Ein Rückverweis ermöglicht es, einen zuvor gefundenen Teilausdruck später im gleichen regulären Ausdruck zu identifizieren. In der folgenden Tabelle sind die Rückverweiskonstrukte aufgeführt, die von regulären .NET Framework-Ausdrücken unterstützt werden. Weitere Informationen finden Sie unter [Rückverweiskonstrukte in regulären Ausdrücken](backreference.md).

Rückverweiskonstrukt | Beschreibung | Muster | Übereinstimmungen
----------------------- | ----------- | ------- | -------
**\**_Nummer_ | Rückverweis. Entspricht dem Wert eines nummerierten Teilausdrucks. | `(\w)\1    ` | "ee" in "beseelt"
**\k<**_name_**>** | Benannter Rückverweis. Entspricht dem Wert eines benannten Ausdrucks. | `(?<char>\w)\k<char>` | "ee" in "beseelt"

## <a name="alternation-constructs"></a>Alternierungskonstrukte

Alternierungskonstrukte ändern einen regulären Ausdruck, um entweder/oder-Vergleiche zuzulassen. Diese Konstrukte verwenden die Sprachelemente in der folgenden Tabelle. Weitere Informationen finden Sie unter [Alternierungskonstrukte in regulären Ausdrücken](alternation.md).

Alternierungskonstrukt | Beschreibung | Muster | Übereinstimmungen
--------------------- | ----------- | ------- | ------- 
**&#124;** | Entspricht jedem beliebigen durch einen senkrechten Strich (*&#124;) getrennten Element. | `th(e*&#124;is*&#124;at)` | "the", "this" in "This is the day. "
__(?(__*ausdruck*__)__*ja*__&#124;__*nein*__)__ | Entspricht *ja*, wenn das von *ausdruck* angegebene Muster für reguläre Ausdrücke übereinstimmt. Andernfalls entspricht es dem optionalen *nein*. *ausdruck* wird als Assertion mit einer Breite von Null interpretiert. | `(?(A)A\d{2}\b*&#124;\b\d{3}\b)` | "A10", "910" in "A10 C103 910"
**(?(**_name_**)**_ja_&#124;_nein_**)** | Entspricht *ja*, wenn *name*, eine benannte oder nummerierte Erfassungsgruppe, eine Übereinstimmung aufweist. Andernfalls entspricht es dem optionalen *nein*. | `(?<quoted>")?(?,(quoted).+?"*&#124;\S+\s)` | Hund.jpg, "Yiska spielt.jpg" in "Hund.jpg "Yiska spielt.jpg""

## <a name="substitutions"></a>Ersetzungen

Ersetzungen sind Sprachelemente regulärer Ausdrücke, die in Ersetzungsmustern unterstützt werden. Weitere Informationen finden Sie unter [Ersetzungen in regulären Ausdrücken](substitutions.md). Die Metazeichen in der folgenden Tabelle sind atomare Assertionen mit einer Breite von Null.

Zeichen | Beschreibung | Muster | Ersetzungsmuster | Eingabezeichenfolge | Ergebniszeichenfolge
--------- | ----------- | ------- | ------------------- | ------------ | ------------- 
**$**_zahl_ | Ersetzt die untergeordnete Zeichenfolge, die dem Wert *zahl* einer Gruppe entspricht. | `\b(\w+)(\s)(\w+)\b` | `$3$2$1` | "one two" | "two one"
**${**_name_**}** | Ersetzt die untergeordnete Zeichenfolge, die dem Wert *name* der benannten Gruppe entspricht. | `\b(?<word1>\w+)(\s)(?<word2>\w+)\b` | `${word2} ${word1}` | "one two" | "two one"
**$$** | Ersetzt ein "$"-Literal. | `\b(\d+)\s?USD` | `$$$1` | "103 USD" | "$103"
**$&** | Ersetzt eine Kopie der gesamten Entsprechung. | `\$?\d*\.?\d+` | `**$&**` | "$1.30" | "**$1.30**"
**$`** | Ersetzt den gesamten Text der Eingabezeichenfolge vor der Entsprechung. | `B+` | `$`` | "AABBCC" | "AAAACC"
**$'** | Ersetzt den gesamten Text der Eingabezeichenfolge nach der Entsprechung. | `B+` | `$'` | "AABBCC" | "AACCCC"
**$+** | Ersetzt die zuletzt erfasste Gruppe. | `B+(C+)` | `$+` | "AABBCCDD" | "AACCDD"
**$_** | Ersetzt die gesamte Eingabezeichenfolge. | `B+` | `$_` | "AABBCC" | "AAAABBCCCC"

## <a name="regular-expression-options"></a>Optionen für reguläre Ausdrücke

Sie können Optionen angeben, die steuern, wie das Modul für reguläre Ausdrücke ein Muster des regulären Ausdrucks interpretiert. Viele dieser Optionen können entweder inline (im Muster des regulären Ausdrucks) oder als eine oder mehrere `RegexOptions`-Konstanten angegeben werden. Diese Kurzübersicht enthält nur Inlineoptionen. Weitere Informationen zu Inline- und `RegexOptions`-Optionen finden Sie im Artikel [Optionen für reguläre Ausdrücke](options.md). 

Sie können eine Inlineoption auf zwei Arten angeben:

* Mit **(?imnsx-imnsx)**, einem der verschiedenen Konstrukte, bei dem ein Minuszeichen (-) vor einer Option oder einem Optionensatz diese Optionen deaktiviert. Zum Beispiel aktiviert **(?i-mn)** Übereinstimmungen ohne Berücksichtigung der Groß-/Kleinschreibung (i), deaktiviert den Mehrzeilenmodus (**m**) und deaktiviert unbenannte Gruppenerfassungen (**n**). Die Option gilt für das Muster des regulären Ausdrucks ab dem Punkt, an dem die Option definiert ist, und ist entweder bis zum Ende des Musters oder bis zu dem Punkt gültig, an dem ein anderes Konstrukt die Option umkehrt.

* Mit dem Gruppierungskonstrukt **(?imnsx-imnsx:**_teilausdruck_**)**, das Optionen nur für die angegebene Gruppe definiert.

Das .NET-Modul für reguläre Ausdrücke unterstützt die folgenden Inlineoptionen.

Option | Beschreibung | Muster | Übereinstimmungen
------ | ----------- | ------- | ------- 
**i** | Groß-/Kleinschreibung bei der Suche ignorieren | **\b(?i)a(?-i)a\w+\b** | "Aale" und "Aasblumen" in "Aale essen Aasblumen roh" 
**m** | Mehrzeilenmodus verwenden. **^** und **$** entsprechen dem Anfang und Ende einer Zeile anstatt dem Anfang und Ende einer Zeichenfolge. | Ein Beispiel finden Sie im Abschnitt „Mehrzeilenmodus“ unter [Optionen für reguläre Ausdrücke](options.md). | 
**n*** | Unbenannte Gruppen nicht erfassen | Ein Beispiel finden Sie im Abschnitt „Nur explizite Erfassungen“ unter [Optionen für reguläre Ausdrücke](options.md). | 
**s** | Einzeilenmodus verwenden | Ein Beispiel finden Sie im Abschnitt „Einzeilenmodus“ unter [Optionen für reguläre Ausdrücke](options.md). | 
**x** | Leerraum ohne Escapezeichen im Muster eines regulären Ausdrucks ignorieren | **\b(?x) \d+ \s \w+** | "1 Erdferkel", "2 Katzen" in "1 Erdferkel 2 Katzen IV Zenturionen" 

##<a name="miscellaneous-constructs"></a>Verschiedene Konstrukte

Verschiedene Konstrukte ändern Muster von regulären Ausdrücken oder stellen Informationen darüber bereit. In der folgenden Tabelle sind die verschiedenen Konstrukte aufgeführt, die von .NET unterstützt werden. Weitere Informationen finden Sie unter [Verschiedene Konstrukte in regulären Ausdrücken](miscellaneous.md).

Konstrukt | Definition | Beispiel
--------- | ---------- | ------- 
**(?imnsx-imnsx)** | Aktiviert oder deaktiviert Optionen wie die Groß-/Kleinschreibung mitten in einem Muster. Weitere Informationen finden Sie unter [Optionen für reguläre Ausdrücke](options.md). | `\bA(?i)b\w+\b` entspricht "ABA", "Able" in "ABA Able Act"
**(?#** _kommentar_**)** | Inlinekommentar. Der Kommentar endet bei der ersten schließenden Klammer. | `\bA(?#` entspricht Wörtern beginnend mit `A)\w+\b`
**#** [bis Zeilenende] | X‑Modus-Kommentar. Der Kommentar beginnt bei einem # ohne Escapezeichen und reicht bis zum Ende der Zeile. | `(?x)\bA\w+\b#` entspricht Wörtern beginnend mit `A`

## <a name="see-also"></a>Siehe auch




[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[Regex](xref:System.Text.RegularExpressions.Regex)

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Das Objektmodell für reguläre Ausdrücke](object-model.md)

[Beispiele für reguläre Ausdrücke](regex-examples.md)

[Download im Word-Format (DOCX)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)
    
[Download im PDF-Format (PDF)](http://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)

