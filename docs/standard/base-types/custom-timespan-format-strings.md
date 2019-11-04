---
title: 'Benutzerdefinierte TimeSpan-Formatzeichenfolgen: .NET'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, custom time interval
- format strings
- formatting [.NET Framework], time interval
- custom time interval format strings
- formatting [.NET Framework], time
- custom TimeSpan format strings
ms.assetid: a63ebf55-7269-416b-b4f5-286f6c03bf0e
ms.openlocfilehash: f38ea3a1e2d687044f862e5d6c0a78c6c12965d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126556"
---
# <a name="custom-timespan-format-strings"></a>Benutzerdefinierte TimeSpan-Formatzeichenfolgen

Eine <xref:System.TimeSpan>-Formatzeichenfolge definiert die aus einem Formatierungsvorgang resultierende Zeichenfolgendarstellung eines <xref:System.TimeSpan>-Werts. Eine benutzerdefinierte Formatzeichenfolge besteht aus einem oder mehreren benutzerdefinierten <xref:System.TimeSpan>-Formatbezeichnern und einer beliebigen Anzahl von Literalzeichen. Alle Zeichenfolgen, bei denen es sich nicht um [standardmäßige TimeSpan-Formatzeichenfolgen](standard-timespan-format-strings.md) handelt, werden als benutzerdefinierte <xref:System.TimeSpan>-Formatzeichenfolgen interpretiert.

> [!IMPORTANT]
> Die benutzerdefinierten <xref:System.TimeSpan>-Formatbezeichner enthalten keine Platzhalter für Trennzeichensymbole, z.B. die Symbole, durch die Tage von Stunden, Stunden von Minuten oder Sekunden von Sekundenbruchteilen getrennt werden. Diese Symbole müssen stattdessen als Zeichenfolgenliterale in die benutzerdefinierte Formatzeichenfolge eingeschlossen werden. Beispielsweise definiert `"dd\.hh\:mm"` einen Punkt (.) als Trennzeichen zwischen Tagen und Stunden und einen Doppelpunkt (:) als Trennzeichen zwischen Stunden und Minuten.
>
> Benutzerdefinierte <xref:System.TimeSpan>-Formatbezeichner enthalten auch kein Vorzeichensymbol, das Ihnen ermöglicht, zwischen den negativen und positiven Zeitabständen zu unterscheiden. Um ein Vorzeichensymbol hinzuzufügen, müssen Sie eine Formatzeichenfolge mit bedingter Logik erstellen. Der Abschnitt [Andere Zeichen](#other-characters) enthält ein Beispiel.

Die Zeichenfolgendarstellungen von <xref:System.TimeSpan>-Werten werden durch Aufrufe der Überladungen der <xref:System.TimeSpan.ToString%2A?displayProperty=nameWithType>-Methode und durch Methoden, die die kombinierte Formatierung unterstützen (z. B. <xref:System.String.Format%2A?displayProperty=nameWithType>), erzeugt. Weitere Informationen finden Sie unter [Formatieren von Typen](formatting-types.md) und [Zusammengesetzte Formatierung](composite-formatting.md). Das folgende Beispiel veranschaulicht die Verwendung von benutzerdefinierten Formatzeichenfolgen bei Formatierungsvorgängen.

[!code-csharp[Conceptual.TimeSpan.Custom#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customformatexample1.cs#1)]
[!code-vb[Conceptual.TimeSpan.Custom#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customformatexample1.vb#1)]

Benutzerdefinierte <xref:System.TimeSpan>-Formatzeichenfolgen werden auch von der <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>-Methode und <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode verwendet, um das erforderliche Format von Eingabezeichenfolgen für Analysevorgänge zu definieren. (Beim Analysieren wird die Zeichenfolgendarstellung eines Werts in diesen Wert konvertiert.) Das folgende Beispiel veranschaulicht die Verwendung von Standardformatzeichenfolgen bei Analysevorgängen.

[!code-csharp[Conceptual.TimeSpan.Custom#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customparseexample1.cs#2)]
[!code-vb[Conceptual.TimeSpan.Custom#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customparseexample1.vb#2)]

<a name="table"></a> In der folgenden Tabelle werden die benutzerdefinierten Formatbezeichner für Datum und Uhrzeit beschrieben.

| Formatbezeichner | BESCHREIBUNG | Beispiel |
|----------------------|-----------------|-------------|
|"d", "%d"|Die Anzahl ganzer Tage im Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „d“](#dSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%d` --> "6"<br /><br /> `d\.hh\:mm` --> "6.14:32"|
|"dd"-"dddddddd"|Die Anzahl ganzer Tage im Zeitintervall, bei Bedarf mit führenden Nullen aufgefüllt.<br /><br /> Weitere Informationen finden Sie unter: [Die benutzerdefinierten Formatbezeichner „dd“ bis „dddddddd“](#ddSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `ddd` --> "006"<br /><br /> `dd\.hh\:mm` --> "06.14:32"|
|"h", "%h"|Die Anzahl ganzer Stunden im Zeitintervall, die nicht als Teil von Tagen gezählt werden. Einstellige Stundenangaben weisen keine führende 0 auf.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „h“](#hSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `%h` --> "14"<br /><br /> `hh\:mm` --> "14:32"|
|"hh"|Die Anzahl ganzer Stunden im Zeitintervall, die nicht als Teil von Tagen gezählt werden. Einstellige Stundenangaben weisen eine führende 0 auf.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „hh“](#hhSpecifier).|`new TimeSpan(6, 14, 32, 17, 685):`<br /><br /> `hh` --> "14"<br /><br /> `new TimeSpan(6, 8, 32, 17, 685):`<br /><br /> `hh` --> 08|
|"m", "%m"|Die Anzahl ganzer Minuten im Zeitintervall, die nicht als Teil von Stunden oder Tagen gezählt werden. Einstellige Minutenangaben weisen keine führende 0 auf.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „m“](#mSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `%m` --> "8"<br /><br /> `h\:m` --> "14:8"|
|"mm"|Die Anzahl ganzer Minuten im Zeitintervall, die nicht als Teil von Stunden oder Tagen gezählt werden. Einstellige Minutenangaben weisen eine führende 0 auf.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „mm“](#mmSpecifier).|`new TimeSpan(6, 14, 8, 17, 685):`<br /><br /> `mm` --> "08"<br /><br /> `new TimeSpan(6, 8, 5, 17, 685):`<br /><br /> `d\.hh\:mm\:ss` --> 6.08:05:17|
|"s", "%s"|Die Anzahl ganzer Sekunden im Zeitintervall, die nicht als Teil von Stunden, Tagen oder Minuten gezählt werden. Einstellige Sekundenangaben weisen keine führende 0 auf.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „s“](#sSpecifier).|`TimeSpan.FromSeconds(12.965)`:<br /><br /> `%s` --> 12<br /><br /> `s\.fff` --> 12.965|
|"ss"|Die Anzahl ganzer Sekunden im Zeitintervall, die nicht als Teil von Stunden, Tagen oder Minuten gezählt werden.  Einstellige Sekundenangaben weisen eine führende 0 auf.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „ss“](#ssSpecifier).|`TimeSpan.FromSeconds(6.965)`:<br /><br /> `ss` --> 06<br /><br /> `ss\.fff` --> 06.965|
|"f", "%f"|Die Zehntelsekunden in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „f“](#fSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `f` --> 8<br /><br /> `ss\.f` --> 06.8|
|"ff"|Die Hundertstelsekunden in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „ff“](#ffSpecifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `ff` --> 89<br /><br /> `ss\.ff` --> 06.89|
|"fff"|Die Millisekunden in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „fff“](#f3Specifier).|`TimeSpan.FromSeconds(6.895)`:<br /><br /> `fff` --> 895<br /><br /> `ss\.fff` --> 06.895|
|"ffff"|Die Zehntausendstelsekunden in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „ffff“](#f4Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffff` --> 8954<br /><br /> `ss\.ffff` --> 06.8954|
|"fffff"|Die Hunderttausendstelsekunden in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „fffff“](#f5Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffff` --> 89543<br /><br /> `ss\.fffff` --> 06.89543|
|"ffffff"|Die Millionstelsekunden in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „ffffff“](#f6Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `ffffff` --> 895432<br /><br /> `ss\.ffffff` --> 06.895432|
|"fffffff"|Die Zehnmillionstelsekunden (oder Sekundenbruchteile) in einem Zeitintervall.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „fffffff“](#f7Specifier).|`TimeSpan.Parse("0:0:6.8954321")`:<br /><br /> `fffffff` --> 8954321<br /><br /> `ss\.fffffff` --> 06.8954321|
|"F", "%F"|Die Zehntelsekunden in einem Zeitintervall. Es wird nichts angezeigt, wenn die Ziffer 0 (null) ist.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „F“](#F_Specifier).|`TimeSpan.Parse("00:00:06.32")`:<br /><br /> `%F`: 3<br /><br /> `TimeSpan.Parse("0:0:3.091")`:<br /><br /> `ss\.F`: 03.|
|"FF"|Die Hundertstelsekunden in einem Zeitintervall. Nachkommanullen oder zwei Nullstellen nach dem Komma werden nicht eingeschlossen.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „FF“](#FF_Specifier).|`TimeSpan.Parse("00:00:06.329")`:<br /><br /> `FF`: 32<br /><br /> `TimeSpan.Parse("0:0:3.101")`:<br /><br /> `ss\.FF`: 03.1|
|"FFF"|Die Millisekunden in einem Zeitintervall. Nachkommanullen werden nicht eingeschlossen.<br /><br /> Weitere Informationen finden Sie unter:|`TimeSpan.Parse("00:00:06.3291")`:<br /><br /> `FFF`: 329<br /><br /> `TimeSpan.Parse("0:0:3.1009")`:<br /><br /> `ss\.FFF`: 03.1|
|"FFFF"|Die Zehntausendstelsekunden in einem Zeitintervall. Nachkommanullen werden nicht eingeschlossen.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „FFFF“](#F4_Specifier).|`TimeSpan.Parse("00:00:06.32917")`:<br /><br /> `FFFFF`: 3291<br /><br /> `TimeSpan.Parse("0:0:3.10009")`:<br /><br /> `ss\.FFFF`: 03.1|
|"FFFFF"|Die Hunderttausendstelsekunden in einem Zeitintervall. Nachkommanullen werden nicht eingeschlossen.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „FFFFF“](#F5_Specifier).|`TimeSpan.Parse("00:00:06.329179")`:<br /><br /> `FFFFF`: 32917<br /><br /> `TimeSpan.Parse("0:0:3.100009")`:<br /><br /> `ss\.FFFFF`: 03.1|
|"FFFFFF"|Die Millionstelsekunden in einem Zeitintervall. Nachkommanullen werden nicht angezeigt.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „FFFFFF“](#F6_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 329179<br /><br /> `TimeSpan.Parse("0:0:3.1000009")`:<br /><br /> `ss\.FFFFFF`: 03.1|
|"FFFFFFF"|Die Zehnmillionstelsekunden in einem Zeitintervall. Nachkommanullen oder sieben Nullstellen werden nicht angezeigt.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Formatbezeichner „FFFFFFF“](#F7_Specifier).|`TimeSpan.Parse("00:00:06.3291791")`:<br /><br /> `FFFFFF`: 3291791<br /><br /> `TimeSpan.Parse("0:0:3.1900000")`:<br /><br /> `ss\.FFFFFF`: 03.19|
|'*Zeichenfolge*'|Trennzeichen für Literalzeichenfolge.<br /><br /> Weitere Informationen finden Sie unter: [Andere Zeichen](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh':'mm':'ss` --> "14:32:17"|
|&#92;|Das Escapezeichen.<br /><br /> Weitere Informationen finden Sie unter: [Andere Zeichen](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|
|Jedes andere Zeichen|Alle anderen Zeichen ohne Escapezeichen werden als benutzerdefinierte Formatbezeichner interpretiert.<br /><br /> Weitere Informationen: [Andere Zeichen](#other-characters).|`new TimeSpan(14, 32, 17):`<br /><br /> `hh\:mm\:ss` --> "14:32:17"|

## <a name="dSpecifier"></a> Der benutzerdefinierte Formatbezeichner „d“

Der benutzerdefinierte Formatbezeichner "d" gibt den Wert der <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Tage im Zeitintervall darstellt. Er gibt auch dann die volle Anzahl von Tagen in einem <xref:System.TimeSpan>-Wert aus, wenn der Wert aus mehreren Ziffern besteht. Wenn der Wert der <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>-Eigenschaft 0 (null) ist, gibt der Bezeichner "0" aus.

Wenn der benutzerdefinierte Formatbezeichner „d“ allein verwendet wird, geben Sie „%d“ an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#3)]
[!code-vb[Conceptual.TimeSpan.Custom#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#3)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "d".

[!code-csharp[Conceptual.TimeSpan.Custom#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#4)]
[!code-vb[Conceptual.TimeSpan.Custom#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#4)]

[Zurück zur Tabelle](#table)

## <a name="ddSpecifier"></a> Die benutzerdefinierten Formatbezeichner „dd“ bis „dddddddd“

Die benutzerdefinierten Formatbezeichner "dd", "ddd", "dddd", "ddddd", "dddddd", "ddddddd" und "dddddddd" geben den Wert der <xref:System.TimeSpan.Days%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Tage im Zeitintervall darstellt.

Die Ausgabezeichenfolge enthält eine Mindestanzahl von Ziffern, die durch die Anzahl der d-Zeichen im Formatbezeichner angegeben wird, und wird bei Bedarf mit führenden Nullen aufgefüllt. Wenn die Ziffern in der Anzahl von Tagen die Anzahl der "d"-Zeichen im Formatbezeichner überschreiten, wird die volle Anzahl von Tagen in der Ergebniszeichenfolge ausgegeben.

Im folgenden Beispiel werden diese Formatbezeichner verwendet, um die Zeichenfolgendarstellung von zwei <xref:System.TimeSpan>-Werten anzuzeigen. Der Wert der Tageskomponente des ersten Zeitintervalls ist 0 (null), der Wert der Tageskomponente des zweiten Zeitintervalls 365.

[!code-csharp[Conceptual.TimeSpan.Custom#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#5)]
[!code-vb[Conceptual.TimeSpan.Custom#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#5)]

[Zurück zur Tabelle](#table)

## <a name="hSpecifier"></a> Der benutzerdefinierte Formatbezeichner „h“

Der benutzerdefinierte Formatbezeichner „h“ gibt den Wert der <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Stunden im Zeitintervall darstellt, die nicht als Teil der Tageskomponente gezählt werden. Er gibt einen einstelligen Zeichenfolgenwert zurück, wenn der Wert der <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>-Eigenschaft zwischen 0 und 9 liegt, und einen zweistelligen Zeichenfolgenwert, wenn der Wert der <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>-Eigenschaft zwischen 10 und 23 liegt.

Wenn der benutzerdefinierte Formatbezeichner „h“ allein verwendet wird, geben Sie „%h“ an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "%h" verwenden, wenn die numerische Zeichenfolge als Anzahl von Stunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#8](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#8)]
[!code-vb[Conceptual.TimeSpan.Custom#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#8)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "h".

[!code-csharp[Conceptual.TimeSpan.Custom#7](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#7)]
[!code-vb[Conceptual.TimeSpan.Custom#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#7)]

[Zurück zur Tabelle](#table)

## <a name="hhSpecifier"></a> Der benutzerdefinierte Formatbezeichner „hh“

Der benutzerdefinierte Formatbezeichner „hh“ gibt den Wert der <xref:System.TimeSpan.Hours%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Stunden im Zeitintervall darstellt, die nicht als Teil der Tageskomponente gezählt werden. Für Werte zwischen 0 und 9 enthält die Ausgabezeichenfolge eine führende Null.

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "hh" verwenden, wenn die numerische Zeichenfolge als Anzahl von Stunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#9](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#9)]
[!code-vb[Conceptual.TimeSpan.Custom#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#9)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "hh".

[!code-csharp[Conceptual.TimeSpan.Custom#10](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#10)]
[!code-vb[Conceptual.TimeSpan.Custom#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#10)]

[Zurück zur Tabelle](#table)

## <a name="mSpecifier"></a> Der benutzerdefinierte Formatbezeichner „m“

Der benutzerdefinierte Formatbezeichner „m“ gibt den Wert der <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Minuten im Zeitintervall darstellt, die nicht als Teil der Tageskomponente gezählt werden. Er gibt einen einstelligen Zeichenfolgenwert zurück, wenn der Wert der <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>-Eigenschaft zwischen 0 und 9 liegt, und einen zweistelligen Zeichenfolgenwert, wenn der Wert der <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>-Eigenschaft zwischen 10 und 59 liegt.

Wenn der benutzerdefinierte Formatbezeichner „m“ allein verwendet wird, geben Sie „%m“ an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#6)]
[!code-vb[Conceptual.TimeSpan.Custom#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#6)]

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "%m" verwenden, wenn die numerische Zeichenfolge als Anzahl von Minuten interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#11](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#11)]
[!code-vb[Conceptual.TimeSpan.Custom#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#11)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "m".

[!code-csharp[Conceptual.TimeSpan.Custom#12](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#12)]
[!code-vb[Conceptual.TimeSpan.Custom#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#12)]

[Zurück zur Tabelle](#table)

## <a name="mmSpecifier"></a> Der benutzerdefinierte Formatbezeichner „mm“

Der benutzerdefinierte Formatbezeichner „mm“ gibt den Wert der <xref:System.TimeSpan.Minutes%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Minuten im Zeitintervall darstellt, die nicht als Teil der Stunden- oder Tageskomponente gezählt werden. Für Werte zwischen 0 und 9 enthält die Ausgabezeichenfolge eine führende Null.

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "mm" verwenden, wenn die numerische Zeichenfolge als Anzahl von Minuten interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#13](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#13)]
[!code-vb[Conceptual.TimeSpan.Custom#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#13)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "mm".

[!code-csharp[Conceptual.TimeSpan.Custom#14](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#14)]
[!code-vb[Conceptual.TimeSpan.Custom#14](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#14)]

[Zurück zur Tabelle](#table)

## <a name="sSpecifier"></a> Der benutzerdefinierte Formatbezeichner „s“

Der benutzerdefinierte Formatbezeichner „s“ gibt den Wert der <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Sekunden im Zeitintervall darstellt, die nicht als Teil der Stunden-, Tages- oder Minutenkomponente gezählt werden. Er gibt einen einstelligen Zeichenfolgenwert zurück, wenn der Wert der <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>-Eigenschaft zwischen 0 und 9 liegt, und einen zweistelligen Zeichenfolgenwert, wenn der Wert der <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>-Eigenschaft zwischen 10 und 59 liegt.

Wenn der benutzerdefinierte Formatbezeichner „s“ allein verwendet wird, geben Sie „%s“ an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#15](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#15)]
[!code-vb[Conceptual.TimeSpan.Custom#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#15)]

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "%s" verwenden, wenn die numerische Zeichenfolge als Anzahl von Sekunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#17](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#17)]
[!code-vb[Conceptual.TimeSpan.Custom#17](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#17)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "s".

[!code-csharp[Conceptual.TimeSpan.Custom#16](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#16)]
[!code-vb[Conceptual.TimeSpan.Custom#16](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#16)]

[Zurück zur Tabelle](#table)

## <a name="ssSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ss“

Der benutzerdefinierte Formatbezeichner „ss“ gibt den Wert der <xref:System.TimeSpan.Seconds%2A?displayProperty=nameWithType>-Eigenschaft aus, der die Anzahl ganzer Sekunden im Zeitintervall darstellt, die nicht als Teil der Stunden-, Tages- oder Minutenkomponente gezählt werden. Für Werte zwischen 0 und 9 enthält die Ausgabezeichenfolge eine führende Null.

Normalerweise wird eine Eingabezeichenfolge, die nur eine Zahl enthält, bei einem Analysevorgang als Anzahl von Tagen interpretiert. Sie können stattdessen den benutzerdefinierten Formatbezeichner "ss" verwenden, wenn die numerische Zeichenfolge als Anzahl von Sekunden interpretiert werden soll. Dies wird im folgenden Beispiel veranschaulicht.

[!code-csharp[Conceptual.TimeSpan.Custom#18](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#18)]
[!code-vb[Conceptual.TimeSpan.Custom#18](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#18)]

Das folgende Beispiel veranschaulicht die Verwendung des benutzerdefinierten Formatbezeichners "ss".

[!code-csharp[Conceptual.TimeSpan.Custom#19](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/customexamples1.cs#19)]
[!code-vb[Conceptual.TimeSpan.Custom#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/customexamples1.vb#19)]

[Zurück zur Tabelle](#table)

## <a name="fSpecifier"></a> Der benutzerdefinierte Formatbezeichner „f“

Der benutzerdefinierte Formatbezeichner "f" gibt die Zehntelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau eine Dezimalstelle enthalten.

Wenn der benutzerdefinierte Formatbezeichner „f“ allein verwendet wird, geben Sie „%f“ an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "f" verwendet, um die Zehntelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. „f“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="ffSpecifier"></a> Der benutzerdefinierte Formatbezeichner „ff“

Der benutzerdefinierte Formatbezeichner "ff" gibt die Hundertstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau zwei Dezimalstellen enthalten.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "ff" verwendet, um die Hundertstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. „ff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="f3Specifier"></a> Der benutzerdefinierte Formatbezeichner „fff“

Der benutzerdefinierte Formatbezeichner "fff" (mit drei "f"-Zeichen) gibt die Millisekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau drei Dezimalstellen enthalten.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "fff" verwendet, um die Millisekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. „fff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="f4Specifier"></a> Der benutzerdefinierte Formatbezeichner „ffff“

Der benutzerdefinierte Formatbezeichner "ffff" (mit vier "f"-Zeichen) gibt die Zehntausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau vier Dezimalstellen enthalten.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "ffff" verwendet, um die Zehntausendstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. „ffff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="f5Specifier"></a> Der benutzerdefinierte Formatbezeichner „fffff“

Der benutzerdefinierte Formatbezeichner "fffff" (mit fünf "f"-Zeichen) gibt die Hunderttausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau fünf Dezimalstellen enthalten.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "ffff" verwendet, um die Hunderttausendstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. „fffff“ wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner „s“ kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="f6Specifier"></a> Der benutzerdefinierte Formatbezeichner „ffffff“

Der benutzerdefinierte Formatbezeichner "ffffff" (mit sechs "f"-Zeichen) gibt die Millionstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau sechs Dezimalstellen enthalten.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "ffffff" verwendet, um die Millionstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Er wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner "s" kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="f7Specifier"></a> Der benutzerdefinierte Formatbezeichner „fffffff“

Der benutzerdefinierte Formatbezeichner "fffffff" (mit sieben "f"-Zeichen) gibt die Zehnmillionstelsekunden (oder Sekundenbruchteile) in einem Zeitintervall aus. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, muss die Eingabezeichenfolge genau sieben Dezimalstellen enthalten.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "fffffff" verwendet, um die Sekundenbruchteile in einem <xref:System.TimeSpan>-Wert anzuzeigen. Er wird zuerst als einziger Formatbezeichner verwendet und dann in einer benutzerdefinierten Formatzeichenfolge mit dem Bezeichner "s" kombiniert.

[!code-csharp[Conceptual.TimeSpan.Custom#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/fspecifiers1.cs#20)]
[!code-vb[Conceptual.TimeSpan.Custom#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/fspecifiers1.vb#20)]

[Zurück zur Tabelle](#table)

## <a name="F_Specifier"></a> Der benutzerdefinierte Formatbezeichner „F“

Der benutzerdefinierte Formatbezeichner "F" gibt die Zehntelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn der Wert der Zehntelsekunden des Zeitintervalls 0 (null) ist, wird er nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der Zehntelsekundenstelle optional.

Wenn der benutzerdefinierte Formatbezeichner „F“ allein verwendet wird, geben Sie „%F“ an, damit er nicht fälschlich als Standardformatzeichenfolge interpretiert wird.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "F" verwendet, um die Zehntelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#21)]
[!code-vb[Conceptual.TimeSpan.Custom#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#21)]

[Zurück zur Tabelle](#table)

## <a name="FF_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FF“

Der benutzerdefinierte Formatbezeichner "FF" gibt die Hundertstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der Zehntel- und Hundertstelsekundenstelle optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "FF" verwendet, um die Hundertstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#22](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#22)]
[!code-vb[Conceptual.TimeSpan.Custom#22](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#22)]

[Zurück zur Tabelle](#table)

## <a name="F3_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFF“

Der benutzerdefinierte Formatbezeichner "FFF" (mit drei "F"-Zeichen) gibt die Millisekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der Zehntel-, Hundertstel- und Tausendstelsekundenstelle optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "FFF" verwendet, um die Tausendstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#23](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#23)]
[!code-vb[Conceptual.TimeSpan.Custom#23](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#23)]

[Zurück zur Tabelle](#table)

## <a name="F4_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFF“

Der benutzerdefinierte Formatbezeichner "FFFF" (mit vier "F"-Zeichen) gibt die Zehntausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der Zehntel-, Hundertstel-, Tausendstel- und Zehntausendstelsekundenstelle optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "FFFF" verwendet, um die Zehntausendstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Der benutzerdefinierte Formatbezeichner "FFFF" wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#24](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#24)]
[!code-vb[Conceptual.TimeSpan.Custom#24](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#24)]

[Zurück zur Tabelle](#table)

## <a name="F5_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFF" (mit fünf "F"-Zeichen) gibt die Hunderttausendstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der Zehntel-, Hundertstel-, Tausendstel-, Zehntausendstel- und Hunderttausendstelsekundenstelle optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "FFFFF" verwendet, um die Hunderttausendstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Der benutzerdefinierte Formatbezeichner "FFFFF" wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#25](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#25)]
[!code-vb[Conceptual.TimeSpan.Custom#25](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#25)]

[Zurück zur Tabelle](#table)

## <a name="F6_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFF" (mit sechs "F"-Zeichen) gibt die Millionstelsekunden in einem Zeitintervall aus. Bei einem Formatierungsvorgang werden die restlichen Dezimalstellen abgeschnitten. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der Zehntel-, Hundertstel-, Tausendstel-, Zehntausendstel-, Hunderttausendstel- und Millionstelsekundenstelle optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "FFFFFF" verwendet, um die Millionstelsekunden in einem <xref:System.TimeSpan>-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#26](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#26)]
[!code-vb[Conceptual.TimeSpan.Custom#26](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#26)]

[Zurück zur Tabelle](#table)

## <a name="F7_Specifier"></a> Der benutzerdefinierte Formatbezeichner „FFFFFFF“

Der benutzerdefinierte Formatbezeichner "FFFFFFF" (mit sieben "F"-Zeichen) gibt die Zehnmillionstelsekunden (oder Sekundenbruchteile) in einem Zeitintervall aus. Wenn Nachkommanullen vorhanden sind, werden sie nicht in die Ergebniszeichenfolge eingeschlossen. Bei einem Analysevorgang, bei dem die <xref:System.TimeSpan.ParseExact%2A?displayProperty=nameWithType>- oder <xref:System.TimeSpan.TryParseExact%2A?displayProperty=nameWithType>-Methode aufgerufen wird, ist das Vorhandensein der sieben Dezimalstellen in der Eingabezeichenfolge optional.

Im folgenden Beispiel wird der benutzerdefinierte Formatbezeichner "FFFFFFF" verwendet, um die Sekundenbruchteile in einem <xref:System.TimeSpan>-Wert anzuzeigen. Dieser benutzerdefinierte Formatbezeichner wird auch für einen Analysevorgang verwendet.

[!code-csharp[Conceptual.TimeSpan.Custom#27](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/f_specifiers1.cs#27)]
[!code-vb[Conceptual.TimeSpan.Custom#27](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/f_specifiers1.vb#27)]

[Zurück zur Tabelle](#table)

## <a name="other-characters"></a>Andere Zeichen.

Alle anderen Zeichen ohne Escapezeichen in einer Formatzeichenfolge (einschließlich Leerzeichen) werden als benutzerdefinierte Formatbezeichner interpretiert. In den meisten Fällen führt das Vorhandensein eines anderen Zeichens ohne Escapezeichen zu einer <xref:System.FormatException>.

Zum Einschließen von Literalzeichen in eine Formatzeichenfolge stehen zwei Methoden zur Verfügung:

- Schließen Sie das Literalzeichen in einfache Anführungszeichen ein (Trennzeichen für Literalzeichenfolgen).

- Stellen Sie dem Literalzeichen einen umgekehrten Schrägstrich („\\“) voran, der als Escapezeichen interpretiert wird. In C# muss die Formatzeichenfolge folglich @-quoted entsprechen, oder dem Literalzeichen muss ein zusätzlicher umgekehrter Schrägstrich vorangestellt werden.

  In einigen Fällen müssen Sie möglicherweise bedingte Logik verwenden, um ein Literal mit Escapezeichen einer Formatzeichenfolge hinzuzufügen. Im folgenden Beispiel wird bedingte Logik verwendet, um ein Vorzeichensymbol für negative Zeitintervalle hinzuzufügen.

  [!code-csharp[Conceptual.TimeSpan.Custom#29](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/negativevalues1.cs#29)]
  [!code-vb[Conceptual.TimeSpan.Custom#29](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/negativevalues1.vb#29)]

.NET definiert keine Grammatik für Trennzeichen in Zeitintervallen. Dies bedeutet, dass die Trennzeichen zwischen Tagen und Stunden, Stunden und Minuten, Minuten und Sekunden und Sekunden und Sekundenbruchteilen in einer Formatzeichenfolge als Zeichenliterale behandelt werden müssen.

Im folgenden Beispiel werden sowohl das Escapezeichen als auch einfache Anführungszeichen verwendet, um eine benutzerdefinierte Formatzeichenfolge mit dem Wort "Minuten" in der Ausgabezeichenfolge zu definieren.

[!code-csharp[Conceptual.TimeSpan.Custom#28](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.timespan.custom/cs/literal1.cs#28)]
[!code-vb[Conceptual.TimeSpan.Custom#28](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.timespan.custom/vb/literal1.vb#28)]

[Zurück zur Tabelle](#table)

## <a name="see-also"></a>Siehe auch

- [Formatierung von Typen](formatting-types.md)
- [TimeSpan-Standardformatzeichenfolgen](standard-timespan-format-strings.md)
