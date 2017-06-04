---
title: "Optionen f&#252;r regul&#228;re Ausdr&#252;cke | Microsoft Docs"
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
  - "reguläre Ausdrücke, Optionen"
  - "Optionen-Konstrukte"
  - "Reguläre Ausdrücke von .NET Framework, Optionen"
  - "Inlineoptionskonstrukte"
  - "Optionenparameter"
ms.assetid: c82dc689-7e82-4767-a18d-cd24ce5f05e9
caps.latest.revision: 27
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 27
---
# Optionen f&#252;r regul&#228;re Ausdr&#252;cke
<a name="Top"></a>Standardmäßig Vergleich einer Eingabezeichenfolge mit irgendwelchen Literalzeichen in einem Muster eines regulären Ausdrucks wird die Groß-/Kleinschreibung beachtet, Leerstellen in einem Muster eines regulären Ausdrucks werden als Literale Leerstellenzeichen interpretiert, und Erfassungsgruppen in einem regulären Ausdruck werden implizit sowie explizit benannt. Sie können diese und andere Aspekte des Standardverhaltens regulärer Ausdrücke ändern, indem Sie Optionen für reguläre Ausdrücke angeben. Diese Optionen, die in der folgenden Tabelle aufgeführt sind, können inline als Teil des Musters für reguläre Ausdrücke enthalten sein, oder sie können für einen <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>-Klassenkonstruktor oder eine statische Musterabgleichsmethode als <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Enumerationswert angegeben werden.  
  
|RegexOptions-Member|Inlinezeichen|Effekt|  
|-------------------------|----------------------|------------|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Nicht verfügbar|Standardverfahren verwenden. Weitere Informationen finden Sie unter [Standardoptionen](#Default).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`i`|Groß-/Kleinschreibung bei der Suche ignorieren Weitere Informationen finden Sie unter [Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung](#Case).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`m`|Verwenden Sie den Mehrzeilenmodus, in dem `^` und `$` dem Anfang und dem Ende jeder Zeile (und nicht dem Anfang und dem Ende der Eingabezeichenfolge) entsprechen. Weitere Informationen finden Sie unter [Mehrzeilenmodus](#Multiline).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`s`|Verwenden Sie Einzeilenmodus, in dem der Punkt (.) den einzelnen Zeichen entspricht (anstatt allen Zeichen mit Ausnahme von `\n`). Weitere Informationen finden Sie unter [Einzeilenmodus](#Singleline).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`n`|Unbenannte Gruppen nicht erfassen Die einzigen gültigen Erfassungen explizit benannte oder nummerierte Gruppen in der Form `(?<` *Namen* `>` *Teilausdruck*`)`. Weitere Informationen finden Sie unter [Nur explizite Erfassungen](#Explicit).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Nicht verfügbar|Kompiliert den regulären Ausdruck in eine Assembly. Weitere Informationen hierzu finden Sie unter [Kompilierte reguläre Ausdrücke](#Compiled).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|`x`|Schließt Leerstellen ohne Escapezeichen vom Muster aus und aktiviert Kommentare nach einem Nummernzeichen (`#`). Weitere Informationen finden Sie unter [Leerzeichen ignorieren](#Whitespace).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Nicht verfügbar|Ändert die Suchrichtung. Die Suche wird von rechts nach links und nicht von links nach rechts durchgeführt. Weitere Informationen finden Sie unter [Rechts-nach-Links-Modus](#RightToLeft).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Nicht verfügbar|ECMAScript-kompatibles Verhalten für den Ausdruck aktivieren. Weitere Informationen finden Sie unter [ECMAScript-Vergleichsverhalten](#ECMAScript).|  
|<xref:System.Text.RegularExpressions.RegexOptions>|Nicht verfügbar|Ignoriert kulturelle Unterschiede in der Sprache. Weitere Informationen finden Sie unter [Vergleiche mit der invarianten Kultur](#Invariant).|  
  
## <a name="specifying-the-options"></a>Angeben der Optionen  
 Sie können Optionen für reguläre Ausdrücke mit einer von drei Methoden angeben:  
  
-   In der `options` Parameter ein <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> -Klassenkonstruktors oder einer statischen (`Shared` in Visual Basic) Mustervergleichsmethode, z. B. <xref:System.Text.RegularExpressions.Regex.%23ctor%28System.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> oder <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>. Die `options` Parameter ist eine bitweise OR-Kombination von <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> -Enumerationswerte.  
  
     Wenn Optionen angegeben werden, um eine <xref:System.Text.RegularExpressions.Regex> Instanz mithilfe der `options` -Parameters eines Klassenkonstruktors, sind die Optionen zugewiesen sind die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Eigenschaft. Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Eigenschaft gibt jedoch keine Inlineoptionen des eigentlichen Musters für reguläre Ausdrücke wieder.  
  
     Dies wird im folgenden Beispiel veranschaulicht. Er verwendet die `options` Parameter von der <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> -Methode Kleinschreibung aktivieren und Musterleerstellen ignoriert, wenn Wörter identifiziert werden, die mit dem Buchstaben "d" beginnen.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#6)]
     [!code-vb[Conceptual.Regex.Language.Options#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#6)]  
  
-   Durch das Übernehmen von Inlineoptionen in einem Muster eines regulären Ausdrucks mit der Syntax `(?imnsx-imnsx)`. Die Option gilt für das Muster ab dem Punkt, an dem die Option definiert wird, bis zum Ende des Musters oder zu dem Punkt, an dem die Definition der Option von einer anderen Inlineoption aufgehoben wird. Beachten Sie, dass die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Eigenschaft einer <xref:System.Text.RegularExpressions.Regex>-Instanz diese Inlineoptionen nicht wiedergibt. Weitere Informationen finden Sie unter der [verschiedene Konstrukte](../../../docs/standard/base-types/miscellaneous-constructs-in-regular-expressions.md) Thema.  
  
     Dies wird im folgenden Beispiel veranschaulicht. Dabei werden Inlineoptionen verwendet, um Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung zu ermöglichen und das Ignorieren von Leerzeichenmustern zu aktivieren, wenn Wörter identifiziert werden, die mit dem Buchstaben "d" beginnen.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#7)]
     [!code-vb[Conceptual.Regex.Language.Options#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#7)]  
  
-   Erstellen Sie durch das Übernehmen von Inlineoptionen in einem bestimmten Gruppierungskonstrukt in einem Muster eines regulären Ausdrucks mit der Syntax `(?imnsx-imnsx:` *Teilausdruck*`)`. Kein Vorzeichen vor einer Gruppe von Optionen aktiviert diese Optionen. Ein Minuszeichen deaktiviert sie. (`?` ist ein fester Bestandteil der Syntax des Sprachkonstrukts, der immer erforderlich ist, unabhängig davon, ob Optionen aktiviert oder deaktiviert sind.) Die Option wird nur auf diese Gruppe angewendet. Weitere Informationen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
     Dies wird im folgenden Beispiel veranschaulicht. Dabei werden Inlineoptionen in einem Gruppierungskonstrukt verwendet, um Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung zu ermöglichen und das Ignorieren von Leerzeichenmustern zu aktivieren, wenn Wörter identifiziert werden, die mit dem Buchstaben "d" beginnen.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
     [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]  
  
 Wenn Optionen inline angegeben sind, deaktiviert ein Minuszeichen (`-`) vor einer Option oder einer Gruppe von Optionen diese Optionen. Zum Beispiel das Inlinekonstrukt `(?ix-ms)` Schaltet die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> und <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> -Option und deaktiviert die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> und <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Optionen. Alle Optionen für reguläre Ausdrücke sind standardmäßig deaktiviert.  
  
> [!NOTE]
>  Wenn die Optionen für reguläre Ausdrücke im `options`-Parameter eines Konstruktors oder Methodenaufrufs im Konflikt mit den Optionen stehen, die inline in einem Muster eines regulären Ausdrucks angegeben wurden, werden die Inlineoptionen verwendet.  
  
 Die folgenden fünf Optionen für reguläre Ausdrücke können sowohl mit dem options-Parameter als auch inline festgelegt werden:  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
 Die folgenden fünf Optionen für reguläre Ausdrücke können mit dem `options`-Parameter, jedoch nicht inline festgelegt werden:  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
-   <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>  
  
## <a name="determining-the-options"></a>Ermitteln der Optionen  
 Sie können ermitteln, welche Optionen für ein <xref:System.Text.RegularExpressions.Regex>-Objekt bei seiner Instanziierung bereitgestellt wurden, indem Sie den Wert der schreibgeschützten <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=fullName>-Eigenschaft abrufen. Diese Eigenschaft ist besonders nützlich zum Ermitteln der Optionen, die für einen kompilierten regulären Ausdruck erstellt, indem definiert die <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName> Methode.  
  
 Um das Vorhandensein einer anderen Option als <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> zu prüfen, führen Sie eine AND-Operation mit dem Wert der <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=fullName>-Eigenschaft und dem <xref:System.Text.RegularExpressions.RegexOptions>-Wert aus, für den Sie sich interessieren. Anschließend testen Sie, ob das Ergebnis diesem <xref:System.Text.RegularExpressions.RegexOptions>-Wert entspricht. Im folgenden Beispiel wird getestet, ob die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option festgelegt wurde.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#19)]
 [!code-vb[Conceptual.Regex.Language.Options#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#19)]  
  
 Testen <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, zu bestimmen, ob der Wert des der <xref:System.Text.RegularExpressions.Regex.Options%2A?displayProperty=fullName> -Eigenschaft entspricht <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/determine1.cs#20)]
 [!code-vb[Conceptual.Regex.Language.Options#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/determine1.vb#20)]  
  
 In den folgenden Abschnitten sind die Optionen aufgeführt, die von regulären .NET Framework-Ausdrücken unterstützt werden.  
  
<a name="Default"></a>   
## <a name="default-options"></a>Standardoptionen  
 Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option gibt an, dass keine Optionen angegeben wurden, und das Modul für reguläre Ausdrücke verwendet sein Standardverhalten. Hierzu gehören folgende Elemente:  
  
-   Das Muster wird kanonisch und nicht als regulärer ECMAScript-Ausdruck interpretiert.  
  
-   Das Muster eines regulären Ausdrucks wird von links nach rechts mit der Eingabezeichenfolge verglichen.  
  
-   Bei Vergleichen wird die Groß-/Kleinschreibung berücksichtigt.  
  
-   Die Sprachelemente `^` und `$` finden eine Entsprechung für den Anfang und das Ende der Eingabezeichenfolge.  
  
-   Das `.`-Sprachelement findet eine Entsprechung für jedes Zeichen außer `\n`.  
  
-   Alle Leerstellen in einem Muster eines regulären Ausdrucks werden als literale Leerzeichen interpretiert.  
  
-   Die Konventionen der aktuellen Kultur werden zum Vergleichen des Musters mit der Eingabezeichenfolge verwendet.  
  
-   Erfassungsgruppen im Muster eines regulären Ausdrucks sind implizit und explizit.  
  
> [!NOTE]
>  Die Option <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> besitzt keine Inlineentsprechung. Wenn reguläre Ausdrucksoptionen inline übernommen werden, wird das Standardverhalten auf optionsweiser Basis durch Deaktivieren einer bestimmten Option wiederhergestellt. `(?i)` aktiviert z. B. Vergleiche, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, und `(?-i)` stellt das Standardverhalten mit Beachtung der Groß-/Kleinschreibung wieder her.  
  
 Da die Option <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> das Standardverhalten des Moduls für reguläre Ausdrücke darstellt, wird sie selten explizit in einem Methodenaufruf angegeben. Stattdessen wird ein Konstruktor oder eine statische Mustervergleichsmethode ohne `options`-Parameter aufgerufen.  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Case"></a>   
## <a name="case-insensitive-matching"></a>Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung  
 Die <xref:System.Text.RegularExpressions.RegexOptions> -Option oder die `i` Inlineoption stellt die Kleinschreibung bereit. Standardmäßig werden die Groß-/Kleinschreibungskonventionen der aktuellen Kultur verwendet.  
  
 Im folgenden Beispiel wird das Muster eines regulären Ausdrucks `\bthe\w*\b` definiert, das eine Entsprechung für alle Wörter findet, die mit "the" beginnen. Da der erste Aufruf der <xref:System.Text.RegularExpressions.Regex.Match%2A> -Methode Vergleich standardmäßig die Groß-/Kleinschreibung beachtet, die Ausgabe an, dass die Zeichenfolge "The", die am Anfang des Satzes keine Übereinstimmung gefunden wurde. Eine Entsprechung wird gefunden, wenn die <xref:System.Text.RegularExpressions.Regex.Match%2A>-Methode mit der Einstellung <xref:System.Text.RegularExpressions.RegexOptions> für die Optionen aufgerufen wird.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case1.cs#1)]
 [!code-vb[Conceptual.Regex.Language.Options#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case1.vb#1)]  
  
 Im folgenden Beispiel wird das Muster eines regulären Ausdrucks aus dem vorherigen Beispiel so geändert, dass Inlineoptionen anstelle des `options`-Parameters verwendet werden, um einen Vergleich ohne Berücksichtigung von Groß- und Kleinschreibung bereitzustellen. Das erste Muster definiert die Option zum Ignorieren der Groß-/Kleinschreibung in einem Gruppierungskonstrukt, das in der Zeichenfolge "the" nur für den Buchstaben "t" gilt. Da das Optionskonstrukt am Anfang des Musters auftritt, wendet das zweite Muster die Option zur Missachtung der Groß-/Kleinschreibung auf den gesamten regulären Ausdruck an.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/case2.cs#2)]
 [!code-vb[Conceptual.Regex.Language.Options#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/case2.vb#2)]  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Multiline"></a>   
## <a name="multiline-mode"></a>Mehrzeilenmodus  
 Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> -Option oder die `m` Inlineoption aktiviert das Modul für reguläre Ausdrücke, die Behandlung einer Eingabezeichenfolge, die aus mehreren Zeilen besteht. Ändert die Bedeutung der Sprachelemente `^` und `$`, sodass sie jeweils dem Anfang und dem Ende einer Zeile und nicht nur dem Anfang und dem Ende der Eingabezeichenfolge entsprechen.  
  
 Standardmäßig findet `$` nur eine Entsprechung für das Ende der Eingabezeichenfolge. Bei Angabe der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option, entspricht diese entweder das Zeilenumbruchzeichen (`\n`) oder dem Ende der Eingabezeichenfolge. Sie entspricht jedoch nicht der Kombination aus Wagenrücklauf- und Zeilenvorschubzeichen. Um erfolgreich eine Entsprechung für sie zu finden, verwenden Sie den Teilausdruck `\r?$` statt nur `$`.  
  
 Im folgenden Beispiel werden die Namen und Ergebnisse von Bowlern extrahiert und fügt diese einer <xref:System.Collections.Generic.SortedList%602> Auflistung, die sie in absteigender Reihenfolge sortiert.</TKey, TValue> Die <xref:System.Text.RegularExpressions.Regex.Matches%2A>-Methode wird zweimal aufgerufen. Im ersten Methodenaufruf ist der reguläre Ausdruck `^(\w+)\s(\d+)$`. Es werden keine Optionen festgelegt. Wie die Ausgabe zeigt, werden keine Übereinstimmungen gefunden, da das Modul für reguläre Ausdrücke das Eingabemuster nicht mit dem Anfang und dem Ende der Eingabezeichenfolge vergleichen kann. Im zweiten Methodenaufruf wird der reguläre Ausdruck in `^(\w+)\s(\d+)\r?$` geändert, und die Optionen werden auf <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> festgelegt. Wie die Ausgabe zeigt, werden die Namen und Ergebnisse erfolgreich abgeglichen, und die Ergebnisse werden in absteigender Reihenfolge angezeigt.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline1.cs#3)]
 [!code-vb[Conceptual.Regex.Language.Options#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline1.vb#3)]  
  
 Das Muster für reguläre Ausdrücke `^(\w+)\s(\d+)\r*$` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Am Anfang der Zeile beginnen.|  
|`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`(\d+)`|Entsprechung für mindestens eine Dezimalstelle finden. Dies ist die zweite Erfassungsgruppe.|  
|`\r?`|Entspricht null oder mehr Wagenrücklaufzeichen.|  
|`$`|Ende am Ende der Zeile.|  
  
 Das folgende Beispiel entspricht dem vorherigen, abgesehen davon, dass zum Festlegen der Mehrzeilenoption die Inlineoption `(?m)` verwendet wird.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/multiline2.cs#4)]
 [!code-vb[Conceptual.Regex.Language.Options#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/multiline2.vb#4)]  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Singleline"></a>   
## <a name="single-line-mode"></a>Einzeilenmodus  
 Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> -Option oder die `s` Inlineoption bewirkt, dass das Modul für reguläre Ausdrücke, die Eingabezeichenfolge so behandelt, als ob sie aus einer einzigen Zeile besteht. Es wird das Verhalten des Sprachelements Punkt (`.`) geändert, sodass dieser jedem Zeichen entspricht, anstatt jedem Zeichen außer dem Zeilenumbruchzeichen `\n` oder \u000A.  
  
 Im folgende Beispiel wird veranschaulicht, wie das Verhalten von der `.` -Sprachelements ändert, wenn Sie verwenden die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option. Der reguläre `^.+`-Ausdruck beginnt am Anfang der Zeichenfolge und stimmt mit jedem Zeichen überein. Standardmäßig endet die Übereinstimmung am Ende der ersten Zeile. Das Muster für den regulären Ausdruck stimmt mit dem Wagenrücklaufzeichen (`\r` oder "\u000D"), jedoch nicht mit `\n` überein. Da die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option die gesamte Eingabezeichenfolge als einzelne Zeile interpretiert, es entspricht jedem Zeichen in der Eingabezeichenfolge, einschließlich `\n`.  
  
 [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
 [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
 Das folgende Beispiel entspricht dem vorherigen, abgesehen davon, dass zum Aktivieren der Einzelzeilenoption die Inlineoption `(?s)` verwendet wird.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/singleline1.cs#5)]
 [!code-vb[Conceptual.Regex.Language.Options#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/singleline1.vb#5)]  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Explicit"></a>   
## <a name="explicit-captures-only"></a>Nur explizite Erfassungen.  
 Standardmäßig werden Erfassungsgruppen durch die Verwendung von Klammern im Muster eines regulären Ausdrucks definiert. Benannte Gruppen werden ein Name zugewiesen oder einer Zahl von der `(?<` *Namen*`>`*Teilausdruck* `)` -Sprachoption, wohingegen auf unbenannte Gruppen über den Index zugegriffen werden. Im <xref:System.Text.RegularExpressions.GroupCollection>-Objekt gehen unbenannte Gruppen benannten Gruppen voraus.  
  
 Gruppierungskonstrukte werden häufig nur verwendet, um Quantifizierer für mehrere Sprachelemente zu übernehmen, und die erfassten Teilzeichenfolgen sind nicht von Bedeutung. Wenn beispielsweise der reguläre Ausdruck wie folgt lautet:  
  
```  
\b\(?((\w+),?\s?)+[\.!?]\)?  
```  
  
 und nur dazu dienen soll, Sätze mit einem Punkt, Ausrufezeichen oder Fragezeichen am Ende aus einem Dokument zu extrahieren, ist nur der resultierende Satz von Interesse (der durch das <xref:System.Text.RegularExpressions.Match>-Objekt dargestellt wird). Die einzelnen Wörter in der Auflistung sind irrelevant.  
  
 Erfassungsgruppen, die anschließend nicht verwendet werden, können speicherintensiv sein, da das Modul für reguläre Ausdrücke sowohl das <xref:System.Text.RegularExpressions.GroupCollection>- als auch das <xref:System.Text.RegularExpressions.CaptureCollection>-Sammlungsobjekt auffüllen muss. Als Alternative können Sie entweder mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option oder der `n` Inlineoption verwenden, um anzugeben, dass die einzigen gültigen Erfassungen explizit benannte oder nummerierte Gruppen, die durch gekennzeichnet sind die `(?<` *Namen* `>` *Teilausdruck* `)` erstellen.  
  
 Das folgende Beispiel zeigt Informationen zu den Übereinstimmungen an, die vom Muster für reguläre Ausdrücke `\b\(?((\w+),?\s?)+[\.!?]\)?` zurückgegeben werden, wenn die <xref:System.Text.RegularExpressions.Regex.Match%2A>-Methode mit und ohne die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option aufgerufen wird. Wie die Ausgabe des ersten Methodenaufrufs zeigt, füllt das Modul für reguläre Ausdrücke das <xref:System.Text.RegularExpressions.GroupCollection>-Sammlungsobjekt und das <xref:System.Text.RegularExpressions.CaptureCollection>-Sammlungsobjekt vollständig mit Informationen zu erfassten Teilzeichenfolgen auf. Da die zweite Methode aufgerufen wird, mit `options` festgelegt <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, werden keine Informationen zu Gruppen erfasst.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit1.cs#9)]
 [!code-vb[Conceptual.Regex.Language.Options#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit1.vb#9)]  
  
 Das Muster eines regulären Ausdrucks`\b\(?((?>\w+),?\s?)+[\.!?]\)?` ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Bei einer Wortgrenze beginnen.|  
|`\(?`|Sucht nach einer Übereinstimmung mit null oder einem Vorkommen der öffnenden Klammer ("(").|  
|`(?>\w+),?`|Sucht nach einer Übereinstimmung mit einem oder mehreren Wortzeichen gefolgt von keinem oder einem Komma. Bei übereinstimmenden Wortzeichen findet keine Rückverfolgung statt.|  
|`\s?`|Sucht nach einer Übereinstimmung mit keinem oder einem Leerzeichen.|  
|`((\w+),?\s?)+`|Entspricht der Kombination von mindestens einem Wortzeichen gefolgt von keinem oder einem Komma und keinem oder einem Leerzeichen (ein- oder mehrfach).|  
|`[\.!?]\)?`|Entspricht jedem der drei Interpunktionszeichen, gefolgt von keiner oder einer schließenden Klammer (")").|  
  
 Sie können auch das `(?n)`-Inlineelement verwenden, um automatische Aufzeichnungen zu unterdrücken. Das folgende Beispiel ändert das vorherige Muster für reguläre Ausdrücke, verwenden Sie die `(?n)` Inlineelement statt der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit2.cs#10)]
 [!code-vb[Conceptual.Regex.Language.Options#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit2.vb#10)]  
  
 Abschließend können Sie mit dem Inlinegruppenelement `(?n:)` automatische Erfassungen gruppenweise unterdrücken. Im folgenden Beispiel wird das vorherige Muster geändert, sodass unbenannte Erfassungen in der äußeren Gruppe `((?>\w+),?\s?)` unterdrückt werden. Beachten Sie, dass dadurch auch unbenannte Erfassungen in der inneren Gruppe unterdrückt werden.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/explicit3.cs#11)]
 [!code-vb[Conceptual.Regex.Language.Options#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/explicit3.vb#11)]  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Compiled"></a>   
## <a name="compiled-regular-expressions"></a>Kompilierte reguläre Ausdrücke  
 Standardmäßig werden reguläre Ausdrücke in .NET Framework interpretiert. Wenn ein <xref:System.Text.RegularExpressions.Regex>-Objekt instanziiert oder eine statische <xref:System.Text.RegularExpressions.Regex>-Methode aufgerufen wird, wird das Muster für reguläre Ausdrücke in einen Satz benutzerdefinierter Opcodes analysiert, und ein Interpreter führt den regulären Ausdruck mithilfe dieser Opcodes aus. Dabei wird ein Kompromiss eingegangen: Der Aufwand für die Initialisierung des Moduls für reguläre Ausdrücke wird auf Kosten der Laufzeitleistung minimiert.  
  
 Sie können kompilierte statt interpretierter regulärer Ausdrücke mit der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option verwenden. Wenn in diesem Fall ein Muster an das Modul für reguläre Ausdrücke übergeben wird, wird es in einen Satz von Opcodes aufgeschlüsselt und dann nach MSIL (Microsoft Intermediate Language) konvertiert, sodass es direkt an die Common Language Runtime übergeben werden kann. Kompilierte reguläre Ausdrücke maximieren die Laufzeitleistung auf Kosten der Initialisierungszeit.  
  
> [!NOTE]
>  Ein regulärer Ausdruck kann nur kompiliert werden die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Wert der `options` Parameter ein <xref:System.Text.RegularExpressions.Regex> -Klassenkonstruktor oder eine statische Mustervergleichsmethode. Es besteht keine Verfügbarkeit als Inlineoption.  
  
 Sie können kompilierte reguläre Ausdrücke in Aufrufen von statischen regulären Ausdrücken und solchen für Instanzen verwenden. In statischen regulären Ausdrücken die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option wird zum Übergeben der `options` Parameter des Mustervergleichs-Methode des regulären Ausdrucks. In regulären Ausdrücken Instanz erfolgt eine Übergabe an das `options` Parameter von der <xref:System.Text.RegularExpressions.Regex> Klassenkonstruktor. In beiden Fällen führt dies zu einer besseren Leistung.  
  
 Diese Verbesserung der Leistung tritt jedoch nur unter den folgenden Bedingungen auf:  
  
-   Ein <xref:System.Text.RegularExpressions.Regex>-Objekt, das einen bestimmten regulären Ausdruck darstellt, wird in mehreren Aufrufen regulärer Ausdrucksmuster-Vergleichsmethoden verwendet.  
  
-   Das <xref:System.Text.RegularExpressions.Regex>-Objekt darf den Gültigkeitsbereich nicht verlassen, daher kann es wiederverwendet werden.  
  
-   Ein statischer regulärer Ausdruck wird in mehreren Aufrufen regulärer Ausdrucksmustervergleichsmethoden verwendet. (Die Leistungsverbesserung ist möglich, da reguläre in statischen Methodenaufrufen verwendete Ausdrücke vom Modul für reguläre Ausdrücke zwischengespeichert werden.)  
  
> [!NOTE]
>  Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Option nicht in Beziehung zu den <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=fullName> Methode, die eine zweckgebundene Assembly erstellt, die vordefinierte kompilierte reguläre Ausdrücke enthält.  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Whitespace"></a>   
## <a name="ignore-white-space"></a>Leerstellen ignorieren  
 Standardmäßig werden Leerstellen in einem Muster eines regulären Ausdrucks interpretiert. Das Modul für reguläre Ausdrücke sucht dann nach einem entsprechenden Leerstellenzeichen in der Eingabezeichenfolge. Daher der reguläre Ausdruck "`\b\w+\s`"und"`\b\w+` " entspricht in etwa äquivalente reguläre Ausdrücke. Außerdem wird das Nummernzeichen (#), wenn es in einem Muster eines regulären Ausdrucks gefunden wird, als Literalzeichen interpretiert und nach einer Übereinstimmung gesucht.  
  
 Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> -Option oder die `x` Inlineoption ändert dieses Standardverhalten wie folgt:  
  
-   Leerstellen ohne Escapezeichen im Muster eines regulären Ausdrucks werden ignoriert. Um Teil eines Musters eines regulären Ausdrucks zu sein, müssen Leerstellenzeichen mit Escapezeichen versehen werden (z. B. `\s` oder "`\` ").  
  
-   Das Nummernzeichen (#) wird als Anfang eines Kommentars interpretiert, nicht als Literalzeichen. Der gesamte Text im Muster eines regulären Ausdrucks vom Zeichen "#" bis zum Ende der Zeichenfolge wird als Kommentar interpretiert.  
  
 In den folgenden Fällen werden Leerzeichen in regulären Ausdrücken jedoch nicht ignoriert, auch wenn Sie die Option <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> verwenden:  
  
-   Leerzeichen in einer Zeichenklasse werden stets literal interpretiert. Der reguläre Ausdruck `[ .,;:]` findet z. B. ein einzelnes Leerstellenzeichen, Punkt, Komma, Semikolon oder einen Doppelpunkt.  
  
-   White space isn't allowed within a bracketed quantifier, such as `{`*n*`}`, `{`*n*`,}`, and `{`*n*`,`*m*`}`. Das Muster eines regulären Ausdrucks `\d{1. 3}` findet z. B. keine Übereinstimmung mit Ziffernsequenzen von einer bis zu drei Ziffern, da es ein Leerzeichen enthält.  
  
-   Leerzeichen sind in Zeichenfolgen, die Sprachelemente einleiten, nicht zulässig. Beispiel:  
  
    -   Das Sprachelement `(?:` *Teilausdruck* `)` stellt eine nicht erfassende Gruppe dar und die `(?:` Teil des Elements darf keine eingebetteten Leerzeichen. Das Muster `(? :` *Teilausdruck* `)` löst ein <xref:System.ArgumentException> zur Laufzeit, da das Modul für reguläre Ausdrücke das Muster und das Muster nicht analysieren kann `( ?:` *Teilausdruck* `)` keine Übereinstimmung mit *Teilausdruck*.  
  
    -   Das Sprachelement `\p{` *Namen*`}`, die stellt einer Unicode-Kategorie oder einem benannten Block, dürfen keine eingebettete Leerzeichen in den `\p{` Teil des Elements. Falls Sie trotzdem ein Leerzeichen einfügen, löst das Element zur Laufzeit eine <xref:System.ArgumentException> aus.  
  
 Durch das Aktivieren dieser Option werden reguläre Ausdrücke vereinfacht, die oft schwierig zu analysieren und zu verstehen sind. Dadurch wird Lesbarkeit verbessert, und es wird möglich, einen regulären Ausdruck zu dokumentieren.  
  
 Im folgenden Beispiel wird das folgende Muster des regulären Ausdrucks definiert:  
  
 `\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.`  
  
 Dieses Muster ist dem im Abschnitt [Nur explizite Erfassungen](#Explicit) definierten Muster ähnlich, außer dass mithilfe der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option Leerzeichen im Muster ignoriert werden.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace1.cs#12)]
 [!code-vb[Conceptual.Regex.Language.Options#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace1.vb#12)]  
  
 Im folgenden Beispiel wird die Inlineoption `(?x)` verwendet, um Leerzeichen im Muster zu ignorieren.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/whitespace2.cs#13)]
 [!code-vb[Conceptual.Regex.Language.Options#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/whitespace2.vb#13)]  
  
 [Zurück zum Anfang](#Top)  
  
<a name="RightToLeft"></a>   
## <a name="right-to-left-mode"></a>Modus "von rechts nach links"  
 Standardmäßig sucht das Modul für reguläre Ausdrücke von links nach rechts. Sie können mit der Option <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> die Suchrichtung umkehren. Die Suche startet automatisch bei der Position des letzten Zeichens der Zeichenfolge. Bei Mustervergleichsmethoden, die einen Parameter für die Anfangsposition enthalten, wie z.B. <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.Int32%29?displayProperty=fullName>, ist die Anfangsposition der Index der am weitesten rechts stehenden Zeichenposition, bei der die Suche beginnt.  
  
> [!NOTE]
>  Für rechts-nach-links-Mustermodus ist nur verfügbar der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Wert der `options` Parameter ein <xref:System.Text.RegularExpressions.Regex> Klassenkonstruktors oder einer statischen Mustervergleichsmethode. Es besteht keine Verfügbarkeit als Inlineoption.  
  
 Die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option ändert nur die Suchrichtung; sie interpretiert das Muster für reguläre Ausdrücke nicht von rechts nach links. Der reguläre Ausdruck `\bb\w+\s` findet z. B. eine Entsprechung für Wörter, die mit dem Buchstaben "b" beginnen und von einem Leerstellenzeichen gefolgt sind. Im folgenden Beispiel besteht die Eingabezeichenfolge aus drei Wörtern, die ein oder mehrere "b"-Zeichen enthalten. Das erste Wort beginnt mit "b", das zweite endet mit "b", und das dritte enthält zwei "b"-Zeichen im Wortinnern. Wie die Ausgabe des Beispiels zeigt, stimmt nur das erste Wort mit dem Muster des regulären Ausdrucks überein.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft1.cs#17)]
 [!code-vb[Conceptual.Regex.Language.Options#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft1.vb#17)]  
  
 Beachten Sie, dass die Lookaheadassertion (das `(?=` *Teilausdruck* `)` Sprachelement) und die Lookbehindassertion (das `(?<=` *Teilausdruck* `)` Sprachelement) Richtung nicht ändern. Die Lookaheadassertionen prüfen nach rechts, die Lookbehindassertionen nach links. Der reguläre Ausdruck `(?<=\d{1,2}\s)\w+,?\s\d{4}` testet z. B. mithilfe der Lookbehindassertion auf ein Datum, das einem Monatsnamen vorausgeht. Der reguläre Ausdruck gleicht dann Monat und Jahr ab. Informationen zu Lookahead- und Lookbehindassertionen finden Sie unter [Gruppierungskonstrukte](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 [!code-csharp[Conceptual.Regex.Language.Options#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/righttoleft2.cs#18)]
 [!code-vb[Conceptual.Regex.Language.Options#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/righttoleft2.vb#18)]  
  
 Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`(?<=\d{1,2}\s)`|Dem Anfang der Übereinstimmung müssen eine oder zwei von einem Leerzeichen gefolgte Dezimalstellen vorangestellt sein.|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`,?`|Entspricht keinem oder einem Kommazeichen.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`\d{4}`|Entsprechung für vier Dezimalstellen finden.|  
  
 [Zurück zum Anfang](#Top)  
  
<a name="ECMAScript"></a>   
## <a name="ecmascript-matching-behavior"></a>ECMAScript-Vergleichsverhalten  
 Standardmäßig verwendet das Modul für reguläre Ausdrücke das kanonische Verhalten, wenn ein Muster eines regulären Ausdrucks mit dem Eingabetext verglichen wird. Sie können jedoch das Modul für reguläre Ausdrücke anweisen, das ECMAScript-Vergleichsverhalten zu verwenden, indem Sie die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option angeben.  
  
> [!NOTE]
>  ECMAScript-kompatibles Verhalten ist nur verfügbar der <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Wert der `options` Parameter ein <xref:System.Text.RegularExpressions.Regex> Klassenkonstruktors oder einer statischen Mustervergleichsmethode. Es besteht keine Verfügbarkeit als Inlineoption.  
  
 Die Option <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> kann nur mit den Optionen <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> und <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> kombiniert werden. Die Verwendung einer anderen Option in einem regulären Ausdruck führt zu einer <xref:System.ArgumentOutOfRangeException>.  
  
 Das Verhalten von ECMAScript und kanonischen regulären Ausdrücke unterscheidet sich in drei Bereichen: Zeichenklassensyntax, bei Selbstverweisen von Erfassungsgruppen sowie bei der Interpretation von Oktalwerten und Rückverweisen.  
  
-   Zeichenklassensyntax. Da kanonische reguläre Ausdrücke im Gegensatz zu ECMAScript Unicode unterstützen, weisen Zeichenklassen in ECMAScript eine beschränktere Syntax auf, und einige Zeichenklassensprachelemente haben eine andere Bedeutung. ECMAScript unterstützt z. B. keine Sprachelemente wie die Kategorie- oder Blockelemente `\p` und `\P` von Unicode. Entsprechend ist das `\w`-Element, das einem Wortzeichen entspricht, äquivalent zur `[a-zA-Z_0-9]`-Zeichenklasse beim Verwenden von ECMAScript bzw. äquivalent zu `[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]` beim Verwenden des kanonischen Verhaltens. Weitere Informationen finden Sie unter [Zeichenklassen](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).  
  
     Im folgenden Beispiel wird der Unterschied zwischen kanonischen und ECMAScript-Mustervergleichen veranschaulicht. Dabei wird ein regulärer Ausdruck, `\b(\w+\s*)+`, definiert, der eine Entsprechung für Wörter findet, denen Leerstellenzeichen folgen. Die Eingabe besteht aus zwei Zeichenfolgen, einer mit dem lateinischen Zeichensatz und einer mit dem kyrillischen Zeichensatz. Wie die Ausgabe zeigt, findet der Aufruf der <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>-Methode, die den ECMAScript-Abgleich verwendet, keine Entsprechung für die kyrillischen Wörter, wohingegen der Methodenaufruf, der einen kanonischen Vergleich verwendet, eine Entsprechung für diese Wörter findet.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript1.cs#16)]
     [!code-vb[Conceptual.Regex.Language.Options#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript1.vb#16)]  
  
-   Auf sich selbst verweisende Erfassungsgruppen. Eine Aufzeichnungsklasse für einen regulären Ausdruck mit einem Rückverweis auf sich selbst muss mit jeder Aufzeichnungsiteration aktualisiert werden. Wie das folgende Beispiel zeigt, aktiviert diese Funktion den regulären Ausdruck `((a+)(\1) ?)+`, um eine Entsprechung für die Eingabezeichenfolge " aa aaaa aaaaaa " zu finden, wenn ECMAScript verwendet wird, jedoch nicht, wenn kanonische Vergleiche verwendet werden.  
  
     [!code-csharp[Conceptual.Regex.Language.Options#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/ecmascript2.cs#21)]
     [!code-vb[Conceptual.Regex.Language.Options#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/ecmascript2.vb#21)]  
  
     Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle definiert:  
  
    |Muster|Beschreibung|  
    |-------------|-----------------|  
    |(a+)|Entspricht einem oder mehreren Vorkommen des Buchstabens "a". Dies ist die zweite Erfassungsgruppe.|  
    |(\1)|Entspricht der Teilzeichenfolge, die von der ersten Erfassungsgruppe erfasst wurde. Dies ist die dritte Erfassungsgruppe.|  
    |?|Entspricht keinem oder einem Leerzeichen.|  
    |((a+)(\1) ?)+|Entspricht mindestens einem "a", ein- oder mehrmals gefolgt von einer Zeichenfolge, die der ersten Erfassungsgruppe entspricht, und keinem oder mehr Leerzeichen. Dies ist die erste Erfassungsgruppe.|  
  
-   Auflösung von Zweideutigkeiten zwischen Oktalescapezeichen und Rückverweisen. Die folgende Tabelle fasst die Unterschiede zwischen der Oktal- und der Rückverweisinterpretation durch kanonische reguläre Ausdrücke und reguläre ECMAScript-Ausdrücke zusammen.  
  
    |Regulärer Ausdruck|Kanonisches Verhalten|ECMAScript-Verhalten|  
    |------------------------|------------------------|-------------------------|  
    |`\0` gefolgt von 0 bis 2 Oktalziffern|Als Oktalwert interpretieren. Zum Beispiel wird `\044` immer als Oktalwert interpretiert und bedeutet "$".|Gleiches Verhalten.|  
    |`\` gefolgt von einer Ziffer zwischen 1 und 9 ohne nachfolgende Dezimalziffern|Als Rückverweis interpretieren. Zum Beispiel bedeutet `\9` immer Rückverweis 9, auch wenn keine Erfassungsgruppe 9 vorhanden ist. Wenn die Erfassungsgruppe nicht vorhanden ist, löst Parser für den regulären Ausdruck eine <xref:System.ArgumentException>.|Wenn eine Erfassungsgruppe einer einzigen Dezimalziffer vorhanden ist, wird ein Rückverweis auf diese Ziffer ausgeführt. Andernfalls wird der Wert als Literal interpretiert.|  
    |`\` gefolgt von einer Ziffer zwischen 1 und 9 mit nachfolgenden Dezimalziffern|Ziffern als Dezimalwert interpretieren. Wenn diese Erfassungsgruppe vorhanden ist, wird der Ausdruck als Rückverweis interpretiert.<br /><br /> Ansonsten werden die vorangestellten Oktalziffern bis zur Oktalzahl 377 interpretiert. Das bedeutet, dass nur die unteren 8 Bits des Werts berücksichtigt werden. Verbleibende Ziffern als Literale interpretieren. Beispiel: Wenn im Ausdruck `\3000` die Erfassungsgruppe 300 vorhanden ist, wird der Ausdruck als Rückverweis 300 interpretiert. Wenn die Erfassungsgruppe 300 nicht vorhanden ist, wird er als Oktalzahl 300 gefolgt von 0 interpretiert.|Als Rückverweis interpretieren, indem so viele Ziffern wie möglich in einen Dezimalwert konvertiert werden, der auf eine Erfassung verweisen kann. Wenn keine Ziffern konvertiert werden können, wird der Ausdruck als Oktalzahl unter Verwendung der ersten Oktalziffern bis zu Oktalzahl 377 interpretiert, und die restlichen Ziffern werden als Literale interpretiert.|  
  
 [Zurück zum Anfang](#Top)  
  
<a name="Invariant"></a>   
## <a name="comparison-using-the-invariant-culture"></a>Vergleiche mit der invarianten Kultur  
 Standardmäßig verwendet das Modul für reguläre Ausdrücke bei Vergleichen ohne Berücksichtigung der Groß- und Kleinschreibung die Groß-/Kleinschreibungskonventionen der aktuellen Kultur, um äquivalente Groß- und Kleinbuchstaben zu ermitteln.  
  
 Dieses Verhalten ist jedoch für einige Typen von Vergleichen unerwünscht, insbesondere wenn Benutzereingaben mit Namen von Systemressourcen wie Kennwörtern, Dateien oder URLs verglichen werden. Dieser Prozess wird anhand des folgenden Szenarios veranschaulicht. Der Code ist dazu gedacht, um Zugriff auf jede Ressource zu blockieren, deren URL vorangestellt **FILE://**. Der reguläre Ausdruck sucht nach einer Übereinstimmung ohne Beachtung der Groß-/Kleinschreibung mit der Zeichenfolge unter Verwendung des regulären Ausdrucks `$FILE://`. Wenn die aktuelle Systemkultur jedoch "tr-TR (Türkisch-Türkei)" ist, ist "I" nicht der entsprechende Großbuchstabe zu "i". Daher ist der Aufruf von der <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> -Methode gibt `false`, und Zugriff auf die Datei zulässig ist.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#14)]
 [!code-vb[Conceptual.Regex.Language.Options#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#14)]  
  
> [!NOTE]
>  Weitere Informationen zu Zeichenfolgenvergleichen, bei denen die Groß-/Kleinschreibung beachtet wird und die die invariante Kultur verwenden, finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../../../docs/standard/base-types/best-practices-strings.md).  
  
 Statt die Vergleiche der aktuellen Kultur zu verwenden, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, können Sie die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>-Option angeben, um kulturelle Unterschiede in der Sprache zu ignorieren und die Konventionen der nicht varianten Kultur zu verwenden.  
  
> [!NOTE]
>  Vergleiche mit der invarianten Kultur sind nur möglich, indem die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> Wert der `options` Parameter ein <xref:System.Text.RegularExpressions.Regex> Klassenkonstruktors oder einer statischen Mustervergleichsmethode. Es besteht keine Verfügbarkeit als Inlineoption.  
  
 Das folgende Beispiel ist mit dem vorherigen Beispiel identisch, abgesehen davon, dass die statische <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName>-Methode mit Optionen aufgerufen wird, die <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> enthalten. Auch wenn die aktuelle Kultur auf "Türkisch (Türkei)" gesetzt ist, kann das Modul für reguläre Ausdrücke "FILE" und "file" erfolgreich zuordnen und den Zugriff auf die Dateiressource blockieren.  
  
 [!code-csharp[Conceptual.Regex.Language.Options#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/culture1.cs#15)]
 [!code-vb[Conceptual.Regex.Language.Options#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/culture1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)