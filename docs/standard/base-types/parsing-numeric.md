---
title: Analysieren numerischer Zeichenfolgen in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
ms.openlocfilehash: ac44282a06b2b3710d3a9e5390c7a514c1632c3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127601"
---
# <a name="parsing-numeric-strings-in-net"></a>Analysieren numerischer Zeichenfolgen in .NET
Alle numerischen Typen weisen zwei statische Analysemethoden auf, `Parse` und `TryParse`, mit denen Sie die Zeichenfolgendarstellung einer Zahl in einen numerischen Typ konvertieren können. Mit diesen Methoden können Sie Zeichenfolgen analysieren, die mithilfe der Formatzeichenfolgen erstellt wurden, die unter [Standardformatzeichenfolgen für Zahlen](../../../docs/standard/base-types/standard-numeric-format-strings.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md) dokumentiert sind. In der Standardeinstellung können die Methoden `Parse` und `TryParse` Zeichenfolgen, die nur Vorkommastellen enthalten, erfolgreich in ganzzahlige Werte konvertieren. Sie können Zeichenfolgen, die Vor- und Nachkommastellen, Gruppentrennzeichen und ein Dezimaltrennzeichen enthalten, erfolgreich in Gleitkommawerte konvertieren. Die `Parse`-Methode löst eine Ausnahme aus, wenn der Vorgang einen Fehler verursacht, wohingegen die `TryParse`-Methode `false` zurückgibt.  
  
## <a name="parsing-and-format-providers"></a>Analyse und Formatanbieter  
 In der Regel unterscheiden sich die Zeichenfolgendarstellungen numerischer Werte je nach Kultur. Elemente numerischer Zeichenfolgen wie Währungssymbole, Gruppentrennzeichen (oder Tausendertrennzeichen) und Dezimaltrennzeichen variieren alle je nach Kultur. Analysemethoden verwenden entweder implizit oder explizit einen Formatanbieter, der diese kulturspezifischen Variationen erkennt. Wird in einem Aufruf der `Parse`- oder der `TryParse`-Methode kein Formatanbieter angegeben, so wird der der aktuellen Threadkultur zugeordnete Formatanbieter verwendet (das von der <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebene <xref:System.Globalization.NumberFormatInfo>-Objekt).  
  
 Ein Formatanbieter wird durch eine <xref:System.IFormatProvider>-Implementierung dargestellt. Diese Schnittstelle verfügt über einen einzelnen Member, die <xref:System.IFormatProvider.GetFormat%2A>-Methode, deren einziger Parameter ein <xref:System.Type>-Objekt für den zu formatierenden Typ ist. Diese Methode gibt das Objekt mit den Formatierungsinformationen zurück. .NET unterstützt die folgenden beiden <xref:System.IFormatProvider>-Implementierungen zur Analyse numerischer Zeichenfolgen:  
  
- Ein <xref:System.Globalization.CultureInfo>-Objekt, dessen <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType>-Methode ein <xref:System.Globalization.NumberFormatInfo>-Objekt mit kulturspezifischen Formatierungsinformationen zurückgibt.  
  
- Ein <xref:System.Globalization.NumberFormatInfo> Objekt, dessen <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType>-Methode sich selbst zurückgibt.  
  
 Im folgenden Beispiel wird versucht, jede Zeichenfolge in einem Array in einen <xref:System.Double>-Wert zu konvertieren. Zuerst wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Englisch (USA)“ wiedergibt. Wenn dieser Vorgang eine <xref:System.FormatException> auslöst, wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Französisch (Frankreich)“ darstellt.  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Analyse und NumberStyles-Werte  
 Die Stilelemente (z.B. Leerzeichen, Gruppentrennzeichen und Dezimaltrennzeichen), die der Analysevorgang verarbeiten kann, werden durch einen <xref:System.Globalization.NumberStyles>-Enumerationswert definiert. Standardmäßig werden Zeichenfolgen, die ganzzahlige Werte darstellen, über den <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>-Wert analysiert, der nur Ziffern, vorangestellte und nachfolgende Leerzeichen sowie ein Vorzeichen zulässt. Zeichenfolgen, die Gleitkommawerte darstellen, werden mithilfe einer Kombination der Werte <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> analysiert. Dieser zusammengesetzte Stil lässt Dezimalstellen sowie vorangestellte und nachfolgende Leerzeichen, ein Vorzeichen, ein Dezimaltrennzeichen, ein Gruppentrennzeichen und einen Exponenten zu. Durch den Aufruf einer Überladung der `Parse`- oder der `TryParse`-Methode mit einem Parameter vom Typ <xref:System.Globalization.NumberStyles> und durch Festlegen von <xref:System.Globalization.NumberStyles>-Flags können Sie die Stilelemente steuern, die in der Zeichenfolge vorhanden sein dürfen, damit der Analysevorgang erfolgreich durchgeführt werden kann.  
  
 Beispielsweise kann eine Zeichenfolge, die ein Gruppentrennzeichen enthält, nicht mithilfe der <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType>-Methode in einen <xref:System.Int32>-Wert konvertiert werden. Die Konvertierung ist jedoch erfolgreich, wenn Sie das <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>-Flag verwenden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
> Beim Analysevorgang werden immer die Formatierungskonventionen einer bestimmten Kultur verwendet. Wenn Sie keine Kultur durch Übergabe eines <xref:System.Globalization.CultureInfo>- oder <xref:System.Globalization.NumberFormatInfo>-Objekts angeben, wird die dem aktuellen Thread zugeordnete Kultur verwendet.  
  
 Die folgende Tabelle enthält die Member der <xref:System.Globalization.NumberStyles>-Enumeration und beschreibt, wie sich diese auf den Analysevorgang auswirken.  
  
|NumberStyles-Wert|Auswirkung auf die zu analysierende Zeichenfolge|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Nur Ziffern sind zulässig.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Das Dezimaltrennzeichen und Nachkommastellen sind zulässig. Für ganzzahlige Werte ist nur 0 (null) als Nachkommastelle zulässig. Gültige Dezimaltrennzeichen werden mithilfe der <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType>- oder <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType>-Eigenschaft ermittelt.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Das Zeichen „e“ oder „E“ kann zum Angeben der Exponentialschreibweise verwendet werden. Weitere Informationen finden Sie unter <xref:System.Globalization.NumberStyles>.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|Vorangestellte Leerzeichen sind zulässig.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|Nachfolgende Leerzeichen sind zulässig.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Ein positives oder negatives Vorzeichen kann numerischen Zeichen vorangestellt werden.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Ein positives oder negatives Vorzeichen kann numerischen Zeichen nachfolgen.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Klammern können zum Festlegen negativer Werte verwendet werden.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|Das Gruppentrennzeichen ist zulässig. Das Gruppentrennzeichen wird mithilfe der <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType>- oder <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType>-Eigenschaft ermittelt.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|Das Währungssymbol ist zulässig. Das Währungssymbol wird mit der <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType>-Eigenschaft definiert.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|Die zu analysierende Zeichenfolge wird als Hexadezimalzahl interpretiert. Sie kann die Hexadezimalzeichen 0 bis 9, A bis F und a bis f enthalten. Dieses Flag kann nur für die Analyse ganzzahliger Werte verwendet werden.|  
  
 Darüber hinaus stellt die <xref:System.Globalization.NumberStyles>-Enumeration die folgenden zusammengesetzten Stile bereit, die mehrere <xref:System.Globalization.NumberStyles>-Flags umfassen.  
  
|Zusammengesetzter NumberStyles-Wert|Umfasst folgende Member|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Enthält die Stile <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>. Dies ist der Standardstil für die Analyse ganzzahliger Werte.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Enthält die Stile <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Enthält die Stile <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Enthält alle Stile außer <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Enthält alle Stile außer <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Enthält die Stile <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
  
## <a name="parsing-and-unicode-digits"></a>Analyse und Unicode-Ziffern  
 Der Unicode-Standard definiert Codepunkte für Ziffern in verschiedenen Schreibsystemen. Beispielsweise stehen Codepunkte von U+0030 bis U+0039 für die grundlegenden lateinischen Ziffern 0 bis 9, Codepunkte von U+09E6 bis U+09EF für die Bangla-Ziffern 0 bis 9 und Codepunkte von U+FF10 bis U+FF19 für Ziffern voller Breite von 0 bis 9. Allerdings werden von den Analysemethoden nur die grundlegenden lateinischen Ziffern von 0 bis 9 mit den Codepunkten von U+0030 bis U+0039 erkannt. Wenn einer numerischen Analysemethode eine Zeichenfolge übergeben wird, die andere Ziffern enthält, löst die Methode eine <xref:System.FormatException> aus.  
  
 Im folgenden Beispiel wird die <xref:System.Int32.Parse%2A?displayProperty=nameWithType>-Methode zum Analysieren von Zeichenfolgen verwendet, die aus Ziffern unterschiedlicher Schreibsysteme bestehen. Wie die Ausgabe des Beispiels zeigt, verläuft die Analyse der grundlegenden lateinischen Ziffern erfolgreich, aber der Versuch zum Analysieren der vollbreiten, der arabisch-indischen und der Bangla-Ziffern verursacht einen Fehler.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.NumberStyles>
- [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)
- [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)
