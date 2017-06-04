---
title: "Analysieren von numerischen Zeichenfolgen in .NET Framework | Microsoft Docs"
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
  - "Analysieren von Zeichenfolgen, Numerische Zeichenfolgen"
  - "Numerische Zeichenfolgen"
  - "Enumerationen [.NET Framework-Profilerstellung], Analysieren von Zeichenfolgen"
  - "Basistypen, Analysieren von Zeichenfolgen"
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Analysieren von numerischen Zeichenfolgen in .NET Framework
Alle numerischen Typen weisen zwei statische Analysemethoden auf: `Parse` und `TryParse`. Diese können Sie verwenden, um die Zeichenfolgendarstellung einer Zahl in einen numerischen Typ zu konvertieren.  Diese Methoden ermöglichen es Ihnen, Zeichenfolgen zu analysieren, die mithilfe der in [Standardmäßige Zahlenformatzeichenfolgen](../../../docs/standard/base-types/standard-numeric-format-strings.md) und [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md) dokumentierten Formatzeichenfolgen erstellt wurden.  Standardmäßig können die `TryParse`\-Methode und die `Parse`\-Methode nur Zeichenfolgen, die ganzzahlige Dezimalziffern enthalten, erfolgreich in ganzzahlige Werte konvertieren.  Die Methoden können erfolgreich Zeichenfolgen in Gleitkommawerte konvertieren, die ganzzahlige und Bruchdezimalziffern, Gruppentrennzeichen und ein Dezimaltrennzeichen enthalten.  Die `Parse`\-Methode löst eine Ausnahme aus, wenn der Vorgang fehlschlägt, während die `TryParse`\-Methode `false` zurückgibt.  
  
## Analysieren und Formatanbieter  
 Normalerweise unterscheiden sich die Zeichenfolgendarstellungen numerischer Werte nach Kultur.  Elemente numerischer Zeichenfolgen wie Währungssymbole, Gruppentrennzeichen \(oder Tausendertrennzeichen\) und Dezimaltrennzeichen allen variieren je nach Kultur.  Analysemethoden verwenden entweder implizit oder explizit einen Formatanbieter, der diese kulturspezifische Variationen erkennt.  Wenn in einem Aufruf der `TryParse`\-Methode oder der `Parse`\-Methode kein Formatanbieter angegeben ist, wird der Formatanbieter verwendet, der der aktuellen Threadkultur zugeordnet ist \(das <xref:System.Globalization.NumberFormatInfo>\-Objekt, das von der <xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird\).  
  
 Ein Formatanbieter wird durch eine <xref:System.IFormatProvider>\-Implementierung dargestellt.  Diese Schnittstelle verfügt über einen einzelnen Member – die <xref:System.IFormatProvider.GetFormat%2A>\-Methode, deren einziger Parameter ein <xref:System.Type>\-Objekt ist, das den zu formatierenden Typ darstellt.  Diese Methode gibt das Objekt zurück, das Formatierungsinformationen bereitstellt.  .NET Framework unterstützt die folgenden zwei <xref:System.IFormatProvider>\-Implementierungen für das Analysieren von numerischen Zeichenfolgen:  
  
-   Ein <xref:System.Globalization.CultureInfo>\-Objekt, dessen <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=fullName>\-Methode ein <xref:System.Globalization.NumberFormatInfo>\-Objekt zurückgibt, das kulturspezifische Formatierungsinformationen bereitstellt.  
  
-   Ein <xref:System.Globalization.NumberFormatInfo>\-Objekt, dessen <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=fullName>\-Methode sich selbst zurückgibt.  
  
 Im folgenden Beispiel wird versucht, jede Zeichenfolge in einem Array in einen <xref:System.Double>\-Wert zu konvertieren.  Zunächst wird versucht, die Zeichenfolge mithilfe eines Formatanbieters zu analysieren, der die Konventionen der Kultur Englisch \(USA\) darstellt.  Wenn dieser Vorgang eine <xref:System.FormatException> auslöst, wird versucht, die Zeichenfolge mithilfe eines Formatanbieters zu analysieren, der die Konventionen der Kultur Französisch \(Frankreich\) darstellt.  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## Analysieren und NumberStyles\-Werte  
 Welche Formatelemente \(z. B. Leerräume, Gruppentrennzeichen und Dezimaltrennzeichen\) vom Analysevorgang behandelt werden können, wird durch einen <xref:System.Globalization.NumberStyles>\-Enumerationswert definiert.  Standardmäßig werden Zeichenfolgen, die ganzzahlige Werte darstellen, mithilfe des <xref:System.Globalization.NumberStyles?displayProperty=fullName>\-Werts analysiert, der nur numerische Ziffern, vorangestellte und nachfolgende Leerraumzeichen und ein führendes Zeichen zulässt.  Zeichenfolgen, die Gleitkommawerte darstellen, werden mithilfe einer Kombination des <xref:System.Globalization.NumberStyles?displayProperty=fullName>\-Werts und des <xref:System.Globalization.NumberStyles?displayProperty=fullName>\-Werts analysiert. Dieses kombinierte Format lässt Dezimalziffern zusammen mit führenden und nachgestellten Leerraumzeichen, einem führenden Zeichen, einem Dezimaltrennzeichen, einem Gruppentrennzeichen und einem Exponenten zu.  Wenn Sie eine Überladung der `Parse`\-Methode bzw. der `TryParse`\-Methode aufrufen, die einen Parameter vom Typ <xref:System.Globalization.NumberStyles> enthält, und mindestens ein <xref:System.Globalization.NumberStyles>\-Flag festlegen, können Sie steuern, welche Formatelemente in der Zeichenfolge vorhanden sein dürfen, damit der Analysevorgang erfolgreich ausgeführt werden kann.  
  
 Beispielsweise kann eine Zeichenfolge, die ein Gruppentrennzeichen enthält, nicht in einen <xref:System.Int32>\-Wert konvertiert werden, indem die <xref:System.Int32.Parse%28System.String%29?displayProperty=fullName>\-Methode.  Allerdings schlägt die Konvertierung, wenn Sie das <xref:System.Globalization.NumberStyles?displayProperty=fullName>\-Flag verwenden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  Im Analysevorgang werden immer die Formatierungskonventionen einer bestimmten Kultur verwendet.  Wenn Sie kein <xref:System.Globalization.CultureInfo>\-Objekt bzw. <xref:System.Globalization.NumberFormatInfo>\-Objekt übergeben, um eine Kultur anzugeben, wird die dem aktuellen Thread zugeordnete Kultur verwendet.  
  
 In der folgenden Tabelle werden die Member der <xref:System.Globalization.NumberStyles>\-Enumeration aufgeführt und ihre Auswirkungen auf den Analysevorgang beschrieben.  
  
|NumberStyles\-Wert|Auswirkung auf die zu analysierende Zeichenfolge|  
|------------------------|------------------------------------------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Nur numerische Ziffern sind zulässig.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Das Dezimaltrennzeichen und Bruchziffern sind zulässig.  Für ganzzahlige Werte ist nur 0 \(null\) als Dezimalstelle zulässig.  Die gültigen Dezimaltrennzeichen werden von der <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=fullName>\-Eigenschaft oder der <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=fullName>\-Eigenschaft bestimmt.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Das Zeichen "e" oder "E" kann verwendet werden, um die Exponentialschreibweise anzugeben.  Weitere Informationen finden Sie unter <xref:System.Globalization.NumberStyles>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Führender Leerraum ist zulässig.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Nachgestellter Leerraum ist zulässig.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Numerischen Ziffern kann ein Plus\- oder Minuszeichen vorangestellt sein.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Numerischen Ziffern kann ein Plus\- oder Minuszeichen nachgestellt sein.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Zur Angabe von negativen Werten können Klammern verwendet werden.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Das Gruppentrennzeichen ist zulässig.  Das Gruppentrennzeichen wird von der <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=fullName>\-Eigenschaft oder der <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=fullName>\-Eigenschaft bestimmt.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Das Währungssymbol ist zulässig.  Das Währungssymbol wird von der <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=fullName>\-Eigenschaft definiert.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Die zu analysierende Zeichenfolge wird als Hexadezimalzahl interpretiert.  Enthalten sein können die Hexadezimalziffern 0\-9, A\-F und a\-f.  Dieses Flag kann nur zur Analyse ganzzahliger Werte verwendet werden.|  
  
 Außerdem stellt die <xref:System.Globalization.NumberStyles>\-Enumeration die folgenden zusammengesetzten Formate bereit, die mehrere <xref:System.Globalization.NumberStyles>\-Flags umfassen.  
  
|Zusammengesetzter NumberStyles\-Wert|Enthaltene Member|  
|------------------------------------------|-----------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Enthält die Formate <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> und <xref:System.Globalization.NumberStyles?displayProperty=fullName>.  Dies ist das Standardformat für die Analyse von ganzzahligen Werten.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Enthält die Formate <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> und <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Enthält die Formate <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> und <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Enthält alle Formate mit Ausnahme von <xref:System.Globalization.NumberStyles?displayProperty=fullName> und <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Enthält alle Formate mit Ausnahme von <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|Enthält die Formate <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> und <xref:System.Globalization.NumberStyles?displayProperty=fullName>.|  
  
## Analysieren und Unicode\-Ziffern  
 Der Unicode\-Standard definiert Codepunkte für Ziffern in verschiedenen Schreibsystemen.  Beispielsweise stellen die Codepunkte von U\+0030 bis U\+0039 die grundlegenden lateinischen Ziffern 0 bis 9 dar, Codepunkte von U\+09E6 bis U\+09EF stellen die Bangla\-Ziffern 0 bis 9 dar, und Codepunkte von U\+FF10 bis U\+FF19 stellen die vollbreiten Ziffern 0 bis 9 dar.  Allerdings sind die einzigen numerischen Ziffern, die von Analysemethoden erkannt werden, die grundlegenden lateinischen Ziffern 0\-9 mit Codepunkten von U\+0030 bis U\+0039.  Wenn einer numerischen Analysemethode eine Zeichenfolge übergeben wird, die andere Ziffern enthält, löst die Methode eine <xref:System.FormatException> aus.  
  
 Im folgenden Beispiel wird die <xref:System.Int32.Parse%2A?displayProperty=fullName>\-Methode zum Analysieren von Zeichenfolgen verwendet, die aus Ziffern verschiedener Schreibsysteme bestehen.  Die Ausgabe im Beispiel zeigt, ist der Versuch, die grundlegenden lateinischen Ziffern zu analysieren, der Versuch, die vollbreiten, die arabisch\-indischen Ziffern und Bangla\-Ziffern zu analysieren schlägt fehl.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## Siehe auch  
 <xref:System.Globalization.NumberStyles>   
 [Analysieren von Zeichenfolgen](../../../docs/standard/base-types/parsing-strings.md)   
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)