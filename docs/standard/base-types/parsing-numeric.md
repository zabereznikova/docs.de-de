---
title: Analysieren von numerischen Zeichenfolgen in .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, numeric strings
- numeric strings
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c9bb58b0d7b45ca197653742844be01ac3bbe41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-numeric-strings-in-net"></a>Analysieren von numerischen Zeichenfolgen in NET
Alle numerischen Typen weisen zwei statische Analysemethoden auf, `Parse` und `TryParse`, mit denen Sie die Zeichenfolgendarstellung einer Zahl in einen numerischen Typ konvertieren können. Mit diesen Methoden können Sie Zeichenfolgen analysieren, die mithilfe der Formatzeichenfolgen erstellt wurden, die unter [Standardformatzeichenfolgen für Zahlen](../../../docs/standard/base-types/standard-numeric-format-strings.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md) dokumentiert sind. In der Standardeinstellung können die Methoden `Parse` und `TryParse` Zeichenfolgen, die nur Vorkommastellen enthalten, erfolgreich in ganzzahlige Werte konvertieren. Sie können Zeichenfolgen, die Vor- und Nachkommastellen, Gruppentrennzeichen und ein Dezimaltrennzeichen enthalten, erfolgreich in Gleitkommawerte konvertieren. Die `Parse`-Methode löst eine Ausnahme aus, wenn der Vorgang einen Fehler verursacht, wohingegen die `TryParse`-Methode `false` zurückgibt.  
  
## <a name="parsing-and-format-providers"></a>Analyse und Formatanbieter  
 In der Regel unterscheiden sich die Zeichenfolgendarstellungen numerischer Werte je nach Kultur. Elemente numerischer Zeichenfolgen wie Währungssymbole, Gruppentrennzeichen (oder Tausendertrennzeichen) und Dezimaltrennzeichen variieren alle je nach Kultur. Analysemethoden verwenden entweder implizit oder explizit einen Formatanbieter, der diese kulturspezifischen Variationen erkennt. Wenn keine Formatanbieter in einem Aufruf angegeben wird die `Parse` oder `TryParse` -Methode, die Formatanbieter, der der aktuellen Threadkultur zugeordnet (die <xref:System.Globalization.NumberFormatInfo> zurückgegebenes Objekt die <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=nameWithType> Eigenschaft) verwendet wird.  
  
 Ein Formatanbieter dargestellte ein <xref:System.IFormatProvider> Implementierung. Diese Schnittstelle verfügt über einen einzelnen Member, die <xref:System.IFormatProvider.GetFormat%2A> -Methode, deren einziger Parameter ist ein <xref:System.Type> -Objekt, das den Typ der zu formatierende darstellt. Diese Methode gibt das Objekt mit den Formatierungsinformationen zurück. .NET unterstützt die folgenden beiden <xref:System.IFormatProvider> Implementierungen für die Analyse von numerischer Zeichenfolgen:  
  
-   Ein <xref:System.Globalization.CultureInfo> Objekt, dessen <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=nameWithType> Methode gibt ein <xref:System.Globalization.NumberFormatInfo> Objekt, das kulturspezifische Formatierungsinformationen bereitstellt.  
  
-   Ein <xref:System.Globalization.NumberFormatInfo> Objekt, dessen <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=nameWithType> Methodenrückgabe selbst.  
  
 Im folgenden Beispiel wird versucht, jede Zeichenfolge in ein Array zu konvertieren einer <xref:System.Double> Wert. Zuerst wird versucht, die Zeichenfolge anhand eines Formatanbieters zu analysieren, der die Konventionen der Kultur „Englisch (USA)“ wiedergibt. Wenn dieser Vorgang löst eine <xref:System.FormatException>, versucht wird, analysiert die Zeichenfolge mit einem Formatanbieter, die die Konventionen der Kultur Französisch (Frankreich) wiedergibt.  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## <a name="parsing-and-numberstyles-values"></a>Analyse und NumberStyles-Werte  
 Style-Elemente (z. B. Leerzeichen, Gruppentrennzeichen und Dezimaltrennzeichen), die der Analysevorgang bewältigt werden definiert, durch eine <xref:System.Globalization.NumberStyles> -Enumerationswert. Standardmäßig werden Zeichenfolgen, die ganzzahlige Werte darstellen analysiert, mithilfe der <xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType> -Wert, der nur numerische Zeichen, führende und nachfolgende Leerzeichen und einem vorangestellten Plus-oder Minuszeichen zulässt. Zeichenfolgen, die Gleitkommawerte darstellen analysiert werden, mithilfe einer Kombination der <xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> Werte; diese kombinierte Format erlaubt Dezimalstellen sowie führende und nachfolgende Leerzeichen, einem vorangestellten Plus-oder Minuszeichen, einem Dezimaltrennzeichen, einer Gruppe als Trennzeichen und einen Exponenten. Durch Aufruf einer Überladung der `Parse` oder `TryParse` Methode, die einen Parameter vom Typ enthält <xref:System.Globalization.NumberStyles> und eine oder mehrere <xref:System.Globalization.NumberStyles> Flags, können Sie steuern, die Style-Elemente, die in der Zeichenfolge für den Analysevorgang vorhanden sein können erfolgreich ausgeführt werden.  
  
 Z. B. in eine Zeichenfolge, ein Gruppentrennzeichen enthält, konvertiert werden kann ein <xref:System.Int32> Wert mithilfe der <xref:System.Int32.Parse%28System.String%29?displayProperty=nameWithType> Methode. Allerdings die Konvertierung erfolgreich ist, wenn Sie verwenden die <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> kennzeichnen, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  Beim Analysevorgang werden immer die Formatierungskonventionen einer bestimmten Kultur verwendet. Wenn Sie keine Kultur durch Übergabe angeben einer <xref:System.Globalization.CultureInfo> oder <xref:System.Globalization.NumberFormatInfo> -Objekt, das den aktuellen Thread zugeordnete Kultur wird verwendet.  
  
 Die folgende Tabelle enthält die Elemente der <xref:System.Globalization.NumberStyles> Enumeration und beschreibt die Auswirkungen, die sie für den Analysevorgang verfügen.  
  
|NumberStyles-Wert|Auswirkung auf die zu analysierende Zeichenfolge|  
|------------------------|---------------------------------------|  
|<xref:System.Globalization.NumberStyles.None?displayProperty=nameWithType>|Nur Ziffern sind zulässig.|  
|<xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>|Das Dezimaltrennzeichen und Nachkommastellen sind zulässig. Für ganzzahlige Werte ist nur 0 (null) als Nachkommastelle zulässig. Gültige Dezimaltrennzeichen werden bestimmt, indem die <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=nameWithType> oder <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=nameWithType> Eigenschaft.|  
|<xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType>|Das Zeichen „e“ oder „E“ kann zum Angeben der Exponentialschreibweise verwendet werden. Finden Sie unter <xref:System.Globalization.NumberStyles> zusätzliche Informationen.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>|Vorangestellte Leerzeichen sind zulässig.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>|Nachfolgende Leerzeichen sind zulässig.|  
|<xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>|Ein positives oder negatives Vorzeichen kann numerischen Zeichen vorangestellt werden.|  
|<xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>|Ein positives oder negatives Vorzeichen kann numerischen Zeichen nachfolgen.|  
|<xref:System.Globalization.NumberStyles.AllowParentheses?displayProperty=nameWithType>|Klammern können zum Festlegen negativer Werte verwendet werden.|  
|<xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType>|Das Gruppentrennzeichen ist zulässig. Das Gruppentrennzeichen richtet sich nach der <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=nameWithType> oder <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=nameWithType> Eigenschaft.|  
|<xref:System.Globalization.NumberStyles.AllowCurrencySymbol?displayProperty=nameWithType>|Das Währungssymbol ist zulässig. Das Währungssymbol wird definiert, indem die <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=nameWithType> Eigenschaft.|  
|<xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>|Die zu analysierende Zeichenfolge wird als Hexadezimalzahl interpretiert. Sie kann die Hexadezimalzeichen 0 bis 9, A bis F und a bis f enthalten. Dieses Flag kann nur für die Analyse ganzzahliger Werte verwendet werden.|  
  
 Darüber hinaus die <xref:System.Globalization.NumberStyles> Enumeration stellt die folgenden zusammengesetzten Formate, die Multiple-include- <xref:System.Globalization.NumberStyles> Flags.  
  
|Zusammengesetzter NumberStyles-Wert|Umfasst folgende Member|  
|----------------------------------|----------------------|  
|<xref:System.Globalization.NumberStyles.Integer?displayProperty=nameWithType>|Enthält die <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, und <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType> Stile. Dies ist der Standardstil für die Analyse ganzzahliger Werte.|  
|<xref:System.Globalization.NumberStyles.Number?displayProperty=nameWithType>|Enthält die <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, und <xref:System.Globalization.NumberStyles.AllowThousands?displayProperty=nameWithType> Stile.|  
|<xref:System.Globalization.NumberStyles.Float?displayProperty=nameWithType>|Enthält die <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowLeadingSign?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowDecimalPoint?displayProperty=nameWithType>, und <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> Stile.|  
|<xref:System.Globalization.NumberStyles.Currency?displayProperty=nameWithType>|Enthält alle Formatvorlagen außer <xref:System.Globalization.NumberStyles.AllowExponent?displayProperty=nameWithType> und <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.Any?displayProperty=nameWithType>|Enthält alle Formatvorlagen außer <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType>.|  
|<xref:System.Globalization.NumberStyles.HexNumber?displayProperty=nameWithType>|Enthält die <xref:System.Globalization.NumberStyles.AllowLeadingWhite?displayProperty=nameWithType>, <xref:System.Globalization.NumberStyles.AllowTrailingWhite?displayProperty=nameWithType>, und <xref:System.Globalization.NumberStyles.AllowHexSpecifier?displayProperty=nameWithType> Stile.|  
  
## <a name="parsing-and-unicode-digits"></a>Analyse und Unicode-Ziffern  
 Der Unicode-Standard definiert Codepunkte für Ziffern in verschiedenen Schreibsystemen. Beispielsweise stehen Codepunkte von U+0030 bis U+0039 für die grundlegenden lateinischen Ziffern 0 bis 9, Codepunkte von U+09E6 bis U+09EF für die Bangla-Ziffern 0 bis 9 und Codepunkte von U+FF10 bis U+FF19 für Ziffern voller Breite von 0 bis 9. Allerdings werden von den Analysemethoden nur die grundlegenden lateinischen Ziffern von 0 bis 9 mit den Codepunkten von U+0030 bis U+0039 erkannt. Wenn eine numerischen Analysemethode eine Zeichenfolge übergeben wird, die andere Ziffern enthält, löst die Methode eine <xref:System.FormatException>.  
  
 Im folgenden Beispiel wird die <xref:System.Int32.Parse%2A?displayProperty=nameWithType> Methode zum Analysieren von Zeichenfolgen, die in unterschiedlichen Schriftsystemen aus Ziffern bestehen. Wie die Ausgabe des Beispiels zeigt, verläuft die Analyse der grundlegenden lateinischen Ziffern erfolgreich, aber der Versuch zum Analysieren der vollbreiten, der arabisch-indischen und der Bangla-Ziffern verursacht einen Fehler.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Globalization.NumberStyles>  
 [Analysieren von Zeichenfolgen](../../../docs/standard/base-types/parsing-strings.md)  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)
