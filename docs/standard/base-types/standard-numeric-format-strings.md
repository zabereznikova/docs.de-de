---
title: "Standardm&#228;&#223;ige Zahlenformatzeichenfolgen | Microsoft Docs"
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
  - "Formatbezeichner, Numerisch"
  - "Formatbezeichner, Standardformatzeichenfolgen für Zahlen"
  - "Formatzeichenfolgen"
  - "Formatieren [.NET Framework], Zahlen"
  - "Formatieren von Zahlen [.NET Framework]"
  - "Zahlen [.NET Framework], Formatierung"
  - "Numerische Formatzeichenfolgen [.NET Framework]"
  - "Standardformatzeichenfolgen, Numerisch"
  - "Standardformatzeichenfolgen für Zahlen"
ms.assetid: 580e57eb-ac47-4ffd-bccd-3a1637c2f467
caps.latest.revision: 99
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 95
---
# Standardm&#228;&#223;ige Zahlenformatzeichenfolgen
Standardformatzeichenfolgen für Zahlen werden für die Formatierung allgemeiner numerischer Typen verwendet. Eine Standardformatzeichenfolge für Zahlen besitzt das Format `Axx`, wobei:  
  
-   `A` ist ein einzelnes alphabetisches Zeichen, das als *Formatbezeichner* bezeichnet wird. Jede Zahlenformatzeichenfolge, die mehr als ein alphabetisches Zeichen \(einschließlich Leerzeichen\) enthält, wird als benutzerdefinierte Zahlenformatzeichenfolge interpretiert. Weitere Informationen finden Sie unter [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   `xx` ist eine optionale ganze Zahl, die als *Genauigkeitsangabe* bezeichnet wird. Die Genauigkeitsangabe reicht von 0 bis 99 und wirkt sich auf die Anzahl der Ziffern im Ergebnis aus. Beachten Sie, dass die Genauigkeitsangabe die Anzahl der Ziffern in der Zeichenfolgendarstellung einer Zahl steuert. Die Zahl selbst wird nicht gerundet. Verwenden Sie für einen Rundungsvorgang die <xref:System.Math.Ceiling%2A?displayProperty=fullName>\-, <xref:System.Math.Floor%2A?displayProperty=fullName>\- oder <xref:System.Math.Round%2A?displayProperty=fullName>\-Methode.  
  
     Wenn *Genauigkeitsangabe* die Anzahl von Dezimalstellen in der Ergebniszeichenfolge steuert, entsprechen Ergebniszeichenfolgen Zahlen, die von null weg gerundet werden \(d. h., es wird <xref:System.MidpointRounding?displayProperty=fullName> verwendet\).  
  
 Standardmäßige numerische Formatzeichenfolgen werden von einigen Überladungen der `ToString`\-Methode aller numerischen Typen unterstützt. Sie können z. B. eine numerische Formatzeichenfolge an die <xref:System.Int32.ToString%28System.String%29>\-Methode und <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29>\-Methode des <xref:System.Int32>\-Typs übergeben. Standardmäßige numerische Formatzeichenfolgen werden auch von der .NET Framework\-Funktion für die [kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md) unterstützt, die von einigen `Write`\-Methoden und `WriteLine`\-Methoden der <xref:System.Console>\-Klasse und der <xref:System.IO.StreamWriter>\-Klasse, der <xref:System.String.Format%2A?displayProperty=fullName>\-Methode und der <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=fullName>\-Methode verwendet wird. Die Funktion für kombinierte Formatierung ermöglicht es Ihnen, die Zeichenfolgendarstellung mehrerer Datenelemente in eine einzelne Zeichenfolge einzuschließen, die Feldbreite anzugeben und die Zahlen in einem Feld auszurichten. Weitere Informationen finden Sie unter [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md).  
  
> [!TIP]
>  Sie können das [Hilfsprogramm zur Formatierung](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d) herunterladen. Dies ist eine Anwendung, mit der Sie Formatzeichenfolgen auf numerische Werte oder Datums\- und Uhrzeitwerte anwenden und die Ergebniszeichenfolge anzeigen können.  
  
<a name="table"></a> Die folgenden Tabelle beschreibt die standardmäßigen Zahlenformatbezeichner und zeigt eine Beispielausgabe an, die von den einzelnen Formatbezeichnern erstellt wird. Weitere Informationen über das Verwenden von numerischen Standardformatzeichenfolgen finden Sie im Abschnitt [Hinweise](#NotesStandardFormatting). Der Abschnitt [Beispiel](#example) enthält eine umfassende Abbildung ihrer Verwendung.  
  
|Formatbezeichner|Name|Beschreibung|Beispiele|  
|----------------------|----------|------------------|---------------|  
|"C" oder "c"|Währung|Ergebnis: Währungswert.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der Dezimalstellen.<br /><br /> Standardmäßige Genauigkeitsangabe: Definiert von <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=fullName>.<br /><br /> Weitere Informationen finden Sie unter [Der Währungsformatbezeichner "C"](#CFormatString).|123.456 \("C", en\-US\) \-\> $123.46<br /><br /> 123.456 \("C", fr\-FR\) \-\> 123,46 €<br /><br /> 123.456 \("C", ja\-JP\) \-\> ¥123<br /><br /> \-123.456 \("C3", en\-US\) \-\> \($123.456\)<br /><br /> \-123.456 \("C3", fr\-FR\) \-\> \-123,456 €<br /><br /> \-123.456 \("C3", ja\-JP\) \-\> \-¥123.456|  
|"D" oder "d"|Decimal|Ergebnis: Ganzzahlige Ziffern mit optionalem Minuszeichen.<br /><br /> Unterstützt von: Nur ganzzahlige Typen.<br /><br /> Genauigkeitsangabe: Mindestanzahl von Ziffern.<br /><br /> Standardmäßige Genauigkeitsangabe: Mindestanzahl von erforderlichen Ziffern.<br /><br /> Weitere Informationen finden Sie unter [Der Dezimalformatbezeichner "D"](#DFormatString).|1234 \("D"\) \-\> 1234<br /><br /> \-1234 \("D6"\) \-\> \-001234|  
|"E" oder "e"|Exponential \(wissenschaftlich\)|Ergebnis: Exponentialschreibweise.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der Dezimalstellen.<br /><br /> Standardmäßige Genauigkeitsangabe: 6.<br /><br /> Weitere Informationen finden Sie unter [Der Exponentialformatbezeichner "E"](#EFormatString).|1052.0329112756 \("E", en\-US\) \-\> 1.052033E\+003<br /><br /> 1052.0329112756 \("e", fr\-FR\) \-\> 1,052033e\+003<br /><br /> \-1052.0329112756 \("e2", en\-US\) \-\> \-1.05e\+003<br /><br /> \-1052.0329112756 \("E2", fr\_FR\) \-\> \-1,05E\+003|  
|"F" oder "f"|Festkomma|Ergebnis: Ganze Zahlen und Dezimalzahlen mit optionalem Minuszeichen.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der Dezimalstellen.<br /><br /> Standardmäßige Genauigkeitsangabe: Definiert von <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=fullName>.<br /><br /> Weitere Informationen finden Sie unter [Der Festkommaformatbezeichner "F"](#FFormatString).|1234.567 \("F", en\-US\) \-\> 1234.57<br /><br /> 1234.567 \("F", de\-DE\) \-\> 1234,57<br /><br /> 1234 \("F1", en\-US\) \-\> 1234.0<br /><br /> 1234 \("F1", de\-DE\) \-\> 1234,0<br /><br /> \-1234.56 \("F4", en\-US\) \-\> \-1234.5600<br /><br /> \-1234.56 \("F4", de\-DE\) \-\> \-1234,5600|  
|"G" oder "g"|Allgemein|Ergebnis: Die kompakteste Festkomma\- oder wissenschaftliche Notation.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: Anzahl der signifikanten Stellen.<br /><br /> Standardmäßige Genauigkeitsangabe: Abhängig vom numerischen Typ.<br /><br /> Weitere Informationen finden Sie unter [Der allgemeine Formatbezeichner "G"](#GFormatString).|\-123.456 \("G", en\-US\) \-\> \-123.456<br /><br /> \-123.456 \("G", sv\-SE\) \-\> \-123,456<br /><br /> 123.4546 \("G4", en\-US\) \-\> 123.5<br /><br /> 123.4546 \("G4", sv\-SE\) \-\> 123,5<br /><br /> \-1.234567890e\-25 \("G", en\-US\) \-\> \-1.23456789E\-25<br /><br /> \-1.234567890e\-25 \("G", sv\-SE\) \-\> \-1,23456789E\-25|  
|"N" oder "n"|Nummer|Ergebnis: Ganze Zahlen und Dezimalzahlen, Gruppentrennzeichen und ein Dezimaltrennzeichen mit optionalem Minuszeichen.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: gewünschte Anzahl der Dezimalstellen.<br /><br /> Standardmäßige Genauigkeitsangabe: Definiert von <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=fullName>.<br /><br /> Weitere Informationen finden Sie unter [Der numerische Formatbezeichner "N"](#NFormatString).|1234.567 \("N", en\-US\) \-\> 1,234.57<br /><br /> 1234.567 \("N", ru\-RU\) \-\> 1 234,57<br /><br /> 1234 \("N1", en\-US\) \-\> 1,234.0<br /><br /> 1234 \("N1", ru\-RU\) \-\> 1 234,0<br /><br /> \-1234.56 \("N3", en\-US\) \-\> \-1,234.560<br /><br /> \-1234.56 \("N3", ru\-RU\) \-\> \-1 234,560|  
|"P" oder "p"|Prozent|Ergebnis: Die Zahl multipliziert mit 100 und mit einem Prozentzeichen versehen.<br /><br /> Unterstützt von: Alle numerischen Typen.<br /><br /> Genauigkeitsangabe: gewünschte Anzahl der Dezimalstellen.<br /><br /> Standardmäßige Genauigkeitsangabe: Definiert von <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A?displayProperty=fullName>.<br /><br /> Weitere Informationen finden Sie unter [Der Prozentformatbezeichner "P"](#PFormatString).|1 \("P", en\-US\) \-\> 100.00 %<br /><br /> 1 \("P", fr\-FR\) \-\> 100,00 %<br /><br /> \-0.39678 \("P1", en\-US\) \-\> \-39.7 %<br /><br /> \-0.39678 \("P1", fr\-FR\) \-\> \-39,7 %|  
|"R" oder "r"|Schleife|Ergebnis: Eine Zeichenfolge, die eine Schleife zu einem identischen Wert ausführen kann.<br /><br /> Unterstützt von: <xref:System.Single>, <xref:System.Double> und <xref:System.Numerics.BigInteger>.<br /><br /> Genauigkeitsangabe: Wird ignoriert.<br /><br /> Weitere Informationen finden Sie unter [Der Schleifenformatbezeichner "R"](#RFormatString).|123456789.12345678 \("R"\) \-\> 123456789.12345678<br /><br /> \-1234567890.12345678 \("R"\) \-\> \-1234567890.1234567|  
|"X" oder "x"|Hexadezimal|Ergebnis: Eine Hexadezimalzeichenfolge.<br /><br /> Unterstützt von: Nur ganzzahlige Typen.<br /><br /> Genauigkeitsangabe: Anzahl von Ziffern in der Ergebniszeichenfolge.<br /><br /> Weitere Informationen finden Sie unter [Der Hexadezimal\-Formatbezeichner "X"](#XFormatString).|255 \("X"\) \-\> FF<br /><br /> \-1 \("x"\) \-\> ff<br /><br /> 255 \("x4"\) \-\> 00ff<br /><br /> \-1 \("X4"\) \-\> 00FF|  
|Jedes andere einzelne Zeichen|Unbekannter Bezeichner|Ergebnis: Löst zur Laufzeit eine <xref:System.FormatException> aus.||  
  
<a name="Using"></a>   
## Verwenden von numerischen Standardformatzeichenfolgen  
 Eine numerische Standardformatzeichenfolge kann verwendet werden, um die Formatierung eines numerischen Werts wie folgt zu definieren:  
  
-   Die Zeichenfolge kann an eine Überladung der `ToString`\-Methode übergeben werden, die über einen `format`\-Parameter verfügt. Im folgenden Beispiel wird ein numerischer Wert in der aktuellen Kultur \(en\-US\) als Währungszeichenfolge formatiert.  
  
     [!code-cpp[Formatting.Numeric.Standard#10](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#10)]
     [!code-csharp[Formatting.Numeric.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#10)]
     [!code-vb[Formatting.Numeric.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#10)]  
  
-   Die Zeichenfolge kann als `formatString`\-Argument in einem Formatelement angegeben werden, das beispielsweise mit den Methoden <xref:System.String.Format%2A?displayProperty=fullName>, <xref:System.Console.WriteLine%2A?displayProperty=fullName> und <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=fullName> verwendet wird. Weitere Informationen finden Sie unter [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md). Im folgenden Beispiel wird ein Währungswert mit einem Formatelement in eine Zeichenfolge eingefügt.  
  
     [!code-cpp[Formatting.Numeric.Standard#11](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#11)]
     [!code-csharp[Formatting.Numeric.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#11)]
     [!code-vb[Formatting.Numeric.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#11)]  
  
     Optional können Sie ein `alignment`\-Argument bereitstellen, um die Breite des numerischen Felds anzugeben und festzulegen, ob sein Wert rechts\- oder linksbündig ausgerichtet ist. Im folgenden Beispiel wird ein Währungswert in einem 28\-stelligen Feld linksbündig und ein Währungswert in einem 14\-stelligen Feld rechtsbündig ausgerichtet.  
  
     [!code-cpp[Formatting.Numeric.Standard#12](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/standardusage1.cpp#12)]
     [!code-csharp[Formatting.Numeric.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/standardusage1.cs#12)]
     [!code-vb[Formatting.Numeric.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/standardusage1.vb#12)]  
  
 Die folgenden Abschnitte enthalten ausführliche Informationen zu den einzelnen numerischen Standardformatzeichenfolgen.  
  
<a name="CFormatString"></a>   
## Der Währungsformatbezeichner "C"  
 Mit dem Währungsformatbezeichner "C" wird eine Zahl in eine Zeichenfolge konvertiert, die einen Währungswert darstellt. Die Genauigkeitsangabe gibt die gewünschte Anzahl von Dezimalstellen in der Ergebniszeichenfolge an. Wenn die Genauigkeitsangabe fehlt, wird die Standardgenauigkeit von der <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A?displayProperty=fullName>\-Eigenschaft definiert.  
  
 Wenn der zu formatierende Wert mehr als die angegebene oder die standardmäßige Anzahl von Dezimalstellen aufweist, wird der Bruchwert in der Ergebniszeichenfolge gerundet. Wenn der Wert rechts von der Anzahl angegebener Dezimalstellen 5 oder größer ist, wird die letzte Ziffer in der Ergebniszeichenfolge in positiver Richtung gerundet.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. In der folgenden Tabelle sind die <xref:System.Globalization.NumberFormatInfo>\-Eigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern%2A>|Definiert die Platzierung des Währungssymbols für positive Werte.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A>|Definiert die Platzierung des Währungssymbols für negative Werte und gibt an, ob das Minuszeichen durch Klammern oder durch die <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>\-Eigenschaft dargestellt wird.|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert das verwendete Minuszeichen, wenn <xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern%2A> angibt, dass keine Klammern verwendet werden.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A>|Definiert das Währungssymbol.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits%2A>|Definiert die Standardanzahl von Dezimalstellen in einem Währungswert. Dieser Wert kann mit der Genauigkeitsangabe überschrieben werden.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A>|Definiert die Zeichenfolge, die ganze Zahlen und Dezimalzahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A>|Definiert die Zeichenfolge, die Gruppen von ganzen Zahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes%2A>|Definiert die Anzahl von ganzzahligen Ziffern, die in einer Gruppe angezeigt werden.|  
  
 Im folgenden Beispiel wird ein <xref:System.Double>\-Wert mit dem Währungsformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#1)]
 [!code-csharp[Formatting.Numeric.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#1)]
 [!code-vb[Formatting.Numeric.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#1)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="DFormatString"></a>   
## Der Dezimalformatbezeichner "D"  
 Der Dezimalformatbezeichner "D" konvertiert Zahl wird in eine Zeichenfolge aus Dezimalzahlen \(0\-9\), der ein Minuszeichen vorangestellt wird, wenn es sich um eine negative Zahl handelt. Dieses Format wird nur bei ganzzahligen Typen unterstützt.  
  
 Die Genauigkeitsangabe gibt die gewünschte Mindestanzahl von Ziffern für die resultierende Zeichenfolge an. Bei Bedarf werden links von der Zahl Nullen ergänzt, um die durch die Genauigkeitsangabe bestimmte Anzahl von Ziffern zu erstellen. Bei fehlender Genauigkeitsangabe wird standardmäßig der zur Darstellung der ganzen Zahl ohne führende Nullen erforderliche Minimalwert zugrunde gelegt.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. Wie die folgende Tabelle zeigt, wirkt sich eine einzelne Eigenschaft auf die Formatierung der Ergebniszeichenfolge aus.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.|  
  
 Im folgenden Beispiel wird ein <xref:System.Int32>\-Wert mit dem Dezimalformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#2)]
 [!code-csharp[Formatting.Numeric.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#2)]
 [!code-vb[Formatting.Numeric.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#2)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="EFormatString"></a>   
## Der Exponentialformatbezeichner "E"  
 Der Exponentialformatbezeichner "E" konvertiert eine Zahl in eine Zeichenfolge, die folgende Form aufweist: "\-d.ddd…E\+ddd" oder "\-d.ddd…e\+ddd". Jedes "d" in der Zeichenfolge steht dabei für eine Ziffer \(0\-9\). Die Zeichenfolge beginnt mit einem Minuszeichen, wenn die Zahl negativ ist. Es steht immer genau eine Ziffer vor dem Dezimaltrennzeichen.  
  
 Die Genauigkeitsangabe gibt die gewünschte Anzahl von Ziffern nach dem Dezimaltrennzeichen an. Wenn die Genauigkeitsangabe fehlt, werden als Standard sechs Ziffern nach dem Dezimaltrennzeichen angegeben.  
  
 Die Groß\- oder Kleinschreibung des Formatbezeichners gibt an, ob dem Exponenten ein "E" oder ein "e" vorangestellt wird. Der Exponent besteht immer aus einem Plus\- oder Minuszeichen und mindestens drei Ziffern. Der Exponent wird ggf. durch Nullen ergänzt, um diesem Mindestwert zu entsprechen.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. In der folgenden Tabelle sind die <xref:System.Globalization.NumberFormatInfo>\-Eigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl sowohl für den Koeffizienten als auch für den Exponenten negativ ist.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Definiert die Zeichenfolge, die die ganzzahlige Ziffer von Dezimalstellen im Koeffizienten trennt.|  
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Definiert die Zeichenfolge, die angibt, dass ein Exponent positiv ist.|  
  
 Im folgenden Beispiel wird ein <xref:System.Double>\-Wert mit dem Exponentialformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#3)]
 [!code-csharp[Formatting.Numeric.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#3)]
 [!code-vb[Formatting.Numeric.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#3)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="FFormatString"></a>   
## Der Festkommaformatbezeichner "F"  
 Der Festkommaformatbezeichner "F" konvertiert eine Zahl in eine Zeichenfolge, die folgende Form aufweist: "\-ddd.ddd…". Jedes "d" steht dabei für eine Ziffer \(0\-9\). Die Zeichenfolge beginnt mit einem Minuszeichen, wenn die Zahl negativ ist.  
  
 Die Genauigkeitsangabe gibt die gewünschte Anzahl von Dezimalstellen an. Bei fehlender Genauigkeitsangabe wird die numerische Genauigkeit von der <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=fullName>\-Eigenschaft angegeben.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. In der folgenden Tabelle sind die Eigenschaften des <xref:System.Globalization.NumberFormatInfo>\-Objekts aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Definiert die Standardanzahl von Dezimalzahlen. Dieser Wert kann mit der Genauigkeitsangabe überschrieben werden.|  
  
 Im folgenden Beispiel wird ein <xref:System.Double>\-Wert und ein <xref:System.Int32>\-Wert mit dem Festkommaformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#4](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#4)]
 [!code-csharp[Formatting.Numeric.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#4)]
 [!code-vb[Formatting.Numeric.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#4)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="GFormatString"></a>   
## Der allgemeine Formatbezeichner "G"  
 Der allgemeine Formatbezeichner "G" konvertiert eine Zahl abhängig vom ihrem Typ und dem Vorhandensein einer Genauigkeitsangabe in eine möglichst kompakte Festkomma\- oder wissenschaftliche Notation. Die Genauigkeitsangabe definiert die maximale Anzahl von signifikanten Stellen, die in der Ergebniszeichenfolge angezeigt werden können. Wenn die Genauigkeitsangabe fehlt oder 0 \(null\) ist, wird die Standardgenauigkeit über den Typ der Zahl festgelegt \(siehe folgende Tabelle\).  
  
|Numerischer Typ|Standardgenauigkeit|  
|---------------------|-------------------------|  
|<xref:System.Byte> oder <xref:System.SByte>|3 Stellen|  
|<xref:System.Int16> oder <xref:System.UInt16>|5 Stellen|  
|<xref:System.Int32> oder <xref:System.UInt32>|10 Stellen|  
|<xref:System.Int64>|19 Stellen|  
|<xref:System.UInt64>|20 Stellen|  
|<xref:System.Numerics.BigInteger>|50 Stellen|  
|<xref:System.Single>|7 Stellen|  
|<xref:System.Double>|15 Stellen|  
|<xref:System.Decimal>|29 Stellen|  
  
 Die Festkommanotation wird verwendet, wenn der Exponent, der sich durch Ausdrücken der Zahl in wissenschaftlicher Notation ergibt, größer als –5 und kleiner als die Genauigkeitsangabe ist. Andernfalls wird die wissenschaftliche Notation verwendet. Das Ergebnis enthält ggf. ein Dezimaltrennzeichen. Nachfolgende Nullen nach dem Dezimaltrennzeichen werden weggelassen. Wenn die Genauigkeitsangabe vorhanden ist und die Anzahl der signifikanten Ziffern im Ergebnis die angegebene Genauigkeit übersteigt, werden die überzähligen nachfolgenden Ziffern durch Rundung entfernt.  
  
 Wenn die Zahl jedoch eine <xref:System.Decimal> ist und kein Genauigkeitsspezifizierer angegeben wurde, wird die Festkommanotation in jedem Fall verwendet und nachfolgende Nullen bleiben erhalten.  
  
 Bei Verwendung der wissenschaftlichen Notation wird dem Exponenten im Ergebnis "E" vorangestellt, wenn der Formatbezeichner "G" ist, oder "e", wenn der Formatbezeichner "g" ist. Der Exponent enthält mindestens zwei Ziffern. Dies stellt einen Unterschied zum wissenschaftlichen Notationsformat dar, das vom exponentiellen Formatbezeichner erzeugt wird und mindestens drei Ziffern im Exponenten verwendet.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. In der folgenden Tabellen sind die <xref:System.Globalization.NumberFormatInfo>\-Eigenschaften aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Definiert die Zeichenfolge, die angibt, dass ein Exponent positiv ist.|  
  
 Im folgenden Beispiel werden gemischte Gleitkommawerte mit dem allgemeinen Formatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#5](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#5)]
 [!code-csharp[Formatting.Numeric.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#5)]
 [!code-vb[Formatting.Numeric.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#5)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="NFormatString"></a>   
## Der numerische Formatbezeichner "N"  
 Der numerische Formatbezeichner \("N"\) konvertiert eine Zahl in eine Zeichenfolge mit dem Format "\-d,ddd,ddd.ddd…", wobei "\-" ggf. ein negatives Zahlensymbol, "d" eine Ziffer \(0\-9\), "'," ein Gruppentrennzeichen und "." ein Dezimaltrennzeichensymbol angibt. Die Genauigkeitsangabe gibt die gewünschte Anzahl von Ziffern nach dem Dezimaltrennzeichen an. Bei fehlender Genauigkeitsangabe wird die Anzahl der Dezimalstellen von der aktuellen <xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A?displayProperty=fullName>\-Eigenschaft definiert.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. In der folgenden Tabellen sind die <xref:System.Globalization.NumberFormatInfo>\-Eigenschaften aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.|  
|<xref:System.Globalization.NumberFormatInfo.NumberNegativePattern%2A>|Definiert das Format von negativen Werten und gibt an, ob das Minuszeichen durch Klammern oder durch die <xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>\-Eigenschaft dargestellt wird.|  
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSizes%2A>|Definiert die Anzahl von ganzzahligen Ziffern, die zwischen Gruppentrennzeichen angezeigt werden.|  
|<xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A>|Definiert die Zeichenfolge, die Gruppen von ganzen Zahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Definiert die Zeichenfolge, die ganze Zahlen und Dezimalzahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalDigits%2A>|Definiert die Standardanzahl von Dezimalzahlen. Dieser Wert kann mit einer Genauigkeitsangabe überschrieben werden.|  
  
 Im folgenden Beispiel werden gemischte Gleitkommawerte mit dem Zahlenformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#6](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#6)]
 [!code-csharp[Formatting.Numeric.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#6)]
 [!code-vb[Formatting.Numeric.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#6)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="PFormatString"></a>   
## Der Prozentformatbezeichner "P"  
 Der Prozentformatbezeichner "P" multipliziert eine Zahl mit 100 und konvertiert sie in eine Zeichenfolge, die einen Prozentsatz darstellt. Die Genauigkeitsangabe gibt die gewünschte Anzahl von Dezimalstellen an. Bei fehlender Genauigkeitsangabe wird die Standardgenauigkeit für Zahlen verwendet, die von der aktuellen <xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>\-Eigenschaft angegeben wird.  
  
 In der folgenden Tabelle sind die <xref:System.Globalization.NumberFormatInfo>\-Eigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.PercentPositivePattern%2A>|Definiert die Platzierung des Prozentsymbols für positive Werte.|  
|<xref:System.Globalization.NumberFormatInfo.PercentNegativePattern%2A>|Definiert die Platzierung des Prozentsymbols sowie des Minuszeichens für negative Werte.|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.|  
|<xref:System.Globalization.NumberFormatInfo.PercentSymbol%2A>|Definiert das Prozentsymbol.|  
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalDigits%2A>|Definiert die Standardanzahl von Dezimalstellen in einem Prozentwert. Dieser Wert kann mit der Genauigkeitsangabe überschrieben werden.|  
|<xref:System.Globalization.NumberFormatInfo.PercentDecimalSeparator%2A>|Definiert die Zeichenfolge, die ganze Zahlen und Dezimalzahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSeparator%2A>|Definiert die Zeichenfolge, die Gruppen von ganzen Zahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.PercentGroupSizes%2A>|Definiert die Anzahl von ganzzahligen Ziffern, die in einer Gruppe angezeigt werden.|  
  
 Im folgenden Beispiel werden gemischte Gleitkommawerte mit dem Prozentformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#7](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#7)]
 [!code-csharp[Formatting.Numeric.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#7)]
 [!code-vb[Formatting.Numeric.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#7)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="RFormatString"></a>   
## Der Schleifenformatbezeichner "R"  
 Der Schleifenformatbezeichner "R" wird verwendet, um sicherzustellen, dass ein in eine Zeichenfolge konvertierter numerischer Wert wieder in denselben numerischen Wert rückkonvertiert wird. Dieses Format wird nur für folgende Typen unterstützt: <xref:System.Single>, <xref:System.Double> und <xref:System.Numerics.BigInteger>.  
  
 Wenn ein <xref:System.Numerics.BigInteger>\-Wert mit diesem Bezeichner formatiert wird, enthält seine Zeichenfolgendarstellung alle signifikanten Stellen im <xref:System.Numerics.BigInteger>\-Wert. Wenn ein <xref:System.Single>\-Wert oder ein <xref:System.Double>\-Wert mit diesem Bezeichner formatiert wird, wird der Wert zuerst mit dem allgemeinen Format getestet, wobei <xref:System.Double> mit einer Genauigkeit von 15 Stellen und <xref:System.Single> mit einer Genauigkeit von 7 Stellen dargestellt wird. Wenn der Wert erfolgreich in den gleichen numerischen Wert rückkonvertiert werden kann, wird er mit dem Bezeichner für das allgemeine Format formatiert. Wenn der Wert jedoch nicht in den gleichen Wert rückkonvertiert werden kann, wird der Wert mit einer Genauigkeit von 17 Ziffern für <xref:System.Double> und 9 Ziffern für <xref:System.Single> formatiert.  
  
 Eine Genauigkeitsangabe kann zwar vorhanden sein, sie wird jedoch ignoriert. Bei diesem Bezeichner hat die Rückkonvertierbarkeit höhere Priorität als die Genauigkeit.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst. In der folgenden Tabellen sind die <xref:System.Globalization.NumberFormatInfo>\-Eigenschaften aufgeführt, die die Formatierung der Ergebniszeichenfolge steuern.  
  
|NumberFormatInfo\-Eigenschaft|Beschreibung|  
|-----------------------------------|------------------|  
|<xref:System.Globalization.NumberFormatInfo.NegativeSign%2A>|Definiert die Zeichenfolge, die angibt, dass eine Zahl negativ ist.|  
|<xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A>|Definiert die Zeichenfolge, die ganze Zahlen von Dezimalzahlen trennt.|  
|<xref:System.Globalization.NumberFormatInfo.PositiveSign%2A>|Definiert die Zeichenfolge, die angibt, dass ein Exponent positiv ist.|  
  
 Im folgenden Beispiel wird <xref:System.Double>\-Werte mit dem Schleifenformatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#8](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#8)]
 [!code-csharp[Formatting.Numeric.Standard#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#8)]
 [!code-vb[Formatting.Numeric.Standard#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#8)]  
  
> [!IMPORTANT]
>  In einigen Fällen werden <xref:System.Double>\-Werte, die mit der Standardformatzeichenfolge für Zahlen "R" formatiert sind, nicht erfolgreich zurückkonvertiert, wenn sie mit dem `/platform:x64`\- oder dem `/platform:anycpu`\-Parameter kompiliert wurden und auf 64\-Bit\-Systemen ausgeführt werden. Weitere Informationen erhalten Sie im folgenden Abschnitt.  
  
 Um das Problem zu umgehen, dass mit der standardmäßigen numerischen Formatierungszeichenfolge "R" formatierte <xref:System.Double>\-Werte bei der Kompilierung mit der `/platform:x64`\-Option oder der `/platform:anycpu`\-Option und bei Ausführung auf 64\-Bit\-Systemen keinen erfolgreichen Roundtrip durchführen, können Sie <xref:System.Double>\-Werte mit der standardmäßigen numerischen Formatierungszeichenfolge "G17" formatieren. Im folgenden Beispiel wird die Formatzeichenfolge "R" mit einem <xref:System.Double>\-Wert verwendet, der nicht erfolgreich zurückkonvertiert wird, und es wird die Formatzeichenfolge "G17" verwendet, um erfolgreich in den ursprünglichen Wert zurückzukonvertieren.  
  
 [!code-csharp[System.Double.ToString#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Double.ToString/cs/roundtripex1.cs#5)]
 [!code-vb[System.Double.ToString#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Double.ToString/vb/roundtripex1.vb#5)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="XFormatString"></a>   
## Der Hexadezimal\-Formatbezeichner "X"  
 Der Hexadezimal\-Formatbezeichner "X" konvertiert eine Zahl in eine Zeichenfolge von Hexadezimalzahlen. Die Schreibweise des Formatbezeichners gibt an, ob Groß\- oder Kleinbuchstaben für Hexadezimalzahlen verwendet werden sollen, die größer als 9 sind. Verwenden Sie z. B. "X" für "ABCDEF", und "x" für "abcdef". Dieses Format wird nur bei ganzzahligen Typen unterstützt.  
  
 Die Genauigkeitsangabe gibt die gewünschte Mindestanzahl von Ziffern für die resultierende Zeichenfolge an. Bei Bedarf werden links von der Zahl Nullen ergänzt, um die durch die Genauigkeitsangabe bestimmte Anzahl von Ziffern zu erstellen.  
  
 Die Ergebniszeichenfolge wird von den Formatierungsinformationen des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts nicht beeinflusst.  
  
 Im folgenden Beispiel wird <xref:System.Int32>\-Werte mit dem Hexadezimal\-Formatbezeichner formatiert.  
  
 [!code-cpp[Formatting.Numeric.Standard#9](../../../samples/snippets/cpp/VS_Snippets_CLR/Formatting.Numeric.Standard/cpp/Standard.cpp#9)]
 [!code-csharp[Formatting.Numeric.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Numeric.Standard/cs/Standard.cs#9)]
 [!code-vb[Formatting.Numeric.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Numeric.Standard/vb/Standard.vb#9)]  
  
 [Zurück zur Tabelle](#table)  
  
<a name="NotesStandardFormatting"></a>   
## Notizen  
  
### Einstellungen der Systemsteuerung  
 Die Einstellungen der **Regions\- und Sprachoptionen** in der Systemsteuerung beeinflussen die durch einen Formatierungsvorgang erstellte Ergebniszeichenfolge. Mithilfe dieser Einstellungen wird das <xref:System.Globalization.NumberFormatInfo>\-Objekt initialisiert, das der aktuellen Threadkultur zugeordnet ist. Sie stellt Werte zur Steuerung der Formatierung bereit. Auf Computern mit anderen Einstellungen werden andere Ergebniszeichenfolgen generiert.  
  
 Wenn der <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29?displayProperty=fullName>\-Constructor verwendet wird, um ein neues <xref:System.Globalization.CultureInfo>\-Objekt zu instantiieren, das dieselbe Kultur repräsentiert wie die aktuelle Systemkultur, werden darüber hinaus alle Anpassungen, die über die Einstellung **Regions\- und Sprachoptionen** in der Systemsteuerung eingerichtet werden, auf das neue <xref:System.Globalization.CultureInfo>\-Objekt angewendet. Sie können den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName>\-Konstruktor verwenden, um ein <xref:System.Globalization.CultureInfo>\-Objekt zu erstellen, das die Anpassungen eines Systems nicht wiedergibt.  
  
### NumberFormatInfo\-Eigenschaften  
 Die Formatierung wird durch die Eigenschaften des aktuellen <xref:System.Globalization.NumberFormatInfo>\-Objekts beeinflusst, das implizit durch die aktuelle Threadkultur oder explizit durch den <xref:System.IFormatProvider>\-Parameter der Methode bereitgestellt wird, die die Formatierung aufruft. Geben Sie ein <xref:System.Globalization.NumberFormatInfo>\-Objekt oder ein <xref:System.Globalization.CultureInfo>\-Objekt für diesen Parameter an.  
  
> [!NOTE]
>  Informationen zum Anpassen der Muster oder Zeichenfolgen, die beim Formatieren der numerischer Werte verwendet werden, finden Sie im Thema zur <xref:System.Globalization.NumberFormatInfo>\-Klasse.  
  
### Ganzzahlige numerische Typen und numerische Gleitkommatypen  
 Einige Beschreibungen standardmäßiger Zahlenformatbezeichner verweisen auf ganzzahlige numerische Typen oder numerische Gleitkommatypen. Die ganzzahligen numerischen Typen sind <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64> und <xref:System.Numerics.BigInteger>. Die numerischen Gleitkommatypen sind <xref:System.Decimal>, <xref:System.Single> und <xref:System.Double>.  
  
### Unendlichkeiten und NaN bei Gleitkommawerten  
 Wenn der Wert eines <xref:System.Single>\-Gleitkommatyps oder eines <xref:System.Double>\-Gleitkommatyps positiv unendlich, negativ unendlich oder keine Zahl \(Not a Number, NaN\) ist, handelt es sich bei der formatierten Zeichenfolge unabhängig von der Formatzeichenfolge um den Wert der entsprechenden <xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol%2A>\-Eigenschaft, <xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol%2A>\-Eigenschaft oder <xref:System.Globalization.NumberFormatInfo.NaNSymbol%2A>\-Eigenschaft, die durch das derzeit gültige <xref:System.Globalization.NumberFormatInfo>\-Objekt angegeben wird.  
  
<a name="example"></a>   
## Beispiel  
 Durch das folgende Beispiel werden mithilfe der Kultur en\-US und allen Standardzahlen\-Formatbezeichnern ein ganzzahliger Wert und ein numerischer Gleitkommawert formatiert. In diesem Beispiel werden zwei bestimmte numerische Typen \(<xref:System.Double> und <xref:System.Int32>\) verwendet. Die Ergebnisse sind jedoch für alle numerischen Basistypen \(<xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Numerics.BigInteger>, <xref:System.Decimal> und <xref:System.Single>\) ähnlich.  
  
 [!code-csharp[system.x.tostring-and-culture#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.X.ToString-and-Culture/cs/xts.cs#1)]
 [!code-vb[system.x.tostring-and-culture#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.X.ToString-and-Culture/vb/xts.vb#1)]  
  
## Siehe auch  
 <xref:System.Globalization.NumberFormatInfo>   
 [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md)   
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)   
 [Gewusst wie: Auffüllen einer Zahl mit führenden Nullen](../../../docs/standard/base-types/how-to-pad-a-number-with-leading-zeros.md)   
 [Beispiel: .NET Framework 4\-Hilfsprogramm zur Formatierung](http://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)   
 [Kombinierte Formatierung](../../../docs/standard/base-types/composite-formatting.md)