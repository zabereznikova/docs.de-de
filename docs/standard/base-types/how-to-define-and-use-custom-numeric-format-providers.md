---
title: "Gewusst wie: Definieren und Verwenden von benutzerdefinierten numerischen Formatanbietern | Microsoft Docs"
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
  - "Benutzerdefinierte Formatzeichenfolgen"
  - "Benutzerdefinierte numerische Formatzeichenfolgen"
  - "Anzeigen von Datums- und Uhrzeitdaten"
  - "Formatanbieter [.NET Framework]"
  - "Formatieren [.NET Framework], Zahlen"
  - "Zahlenformatierung [.NET Framework]"
  - "Zahlen [.NET Framework], Benutzerdefinierte numerische Formatzeichenfolgen"
  - "Numerische Formatzeichenfolgen [.NET Framework]"
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Definieren und Verwenden von benutzerdefinierten numerischen Formatanbietern
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] bietet umfangreiche Steuerungsmöglichkeiten über die Zeichenfolgendarstellung numerischer Werte.  Folgende Features zur Anpassung des Formats numerischer Werte werden unterstützt:  
  
-   Standardmäßige Zahlenformatzeichenfolgen, die einen Satz vordefinierter Formate für die Konvertierung von Zahlen in die entsprechende Zeichenfolgendarstellung bereitstellen.  Sie können sie mit einer beliebigen numerischen Formatierungsmethode \(z. B. <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName>\) verwenden, die über einen `format`\-Parameter verfügt.  Ausführliche Informationen finden Sie unter [Standardmäßige Zahlenformatzeichenfolgen](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Benutzerdefinierte Zahlenformatzeichenfolgen, die eine Reihe von Symbolen bereitstellen, die zur Festlegung benutzerdefinierter Zahlenformatbezeichner kombiniert werden können.  Sie können außerdem mit einer beliebigen numerischen Formatierungsmethode \(z. B. <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName>\) verwendet werden, die über einen `format`\-Parameter verfügt.  Ausführliche Informationen finden Sie unter [Benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Benutzerdefiniertes <xref:System.Globalization.CultureInfo>\-Objekt oder <xref:System.Globalization.NumberFormatInfo>\-Objekt zur Definition der Symbole und Formatierungsmuster, die zur Anzeige der Zeichenfolgendarstellungen numerischer Werte verwendet werden.  Sie können sie mit einer beliebigen numerischen Formatierungsmethode \(z. B. <xref:System.Int32.ToString%2A>\) verwenden, die über einen `provider`\-Parameter verfügt.  Normalerweise wird der `provider`\-Parameter verwendet, um eine kulturabhängige Formatierung anzugeben.  
  
 In einigen Fällen \(z. B. wenn in einer Anwendung eine formatierte Kontonummer, eine ID oder eine Postleitzahl angezeigt werden soll\) sind diese drei Techniken nicht geeignet.  Über [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] können Sie auch ein Formatierungsobjekt festlegen, das weder ein <xref:System.Globalization.CultureInfo>\-Objekt noch ein <xref:System.Globalization.NumberFormatInfo>\-Objekt darstellt. Auf diese Weise wird bestimmt, wie ein numerischer Wert formatiert wird.  Dieses Thema enthält schrittweise Anleitungen zur Implementierung eines solchen Objekts und umfasst ein Beispiel zur Formatierung von Telefonnummern.  
  
### So definieren Sie einen benutzerdefinierten Formatanbieter  
  
1.  Definieren Sie eine Klasse, durch die die <xref:System.IFormatProvider>\-Schnittstelle und die <xref:System.ICustomFormatter>\-Schnittstelle implementiert wird.  
  
2.  Implementieren Sie die <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName>\-Methode.  <xref:System.IFormatProvider.GetFormat%2A> ist eine Rückrufmethode, die von der Formatierungsmethode \(z. B. der [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\-Methode\) aufgerufen wird, um das Objekt abzurufen, das tatsächlich für die Ausführung der benutzerdefinierten Formatierung zuständig ist.  Eine typische Implementierung von <xref:System.IFormatProvider.GetFormat%2A> übernimmt folgende Aufgaben:  
  
    1.  Bestimmt, ob das als Methodenparameter übergebene <xref:System.Type>\-Objekt eine <xref:System.ICustomFormatter>\-Schnittstelle darstellt.  
  
    2.  Wenn der Parameter die <xref:System.ICustomFormatter>\-Schnittstelle darstellt, gibt <xref:System.IFormatProvider.GetFormat%2A> ein Objekt  zurück, durch das die <xref:System.ICustomFormatter>\-Schnittstelle implementiert wird, die für die benutzerdefinierte Formatierung zuständig ist.  Das benutzerdefinierte Formatierungsobjekt gibt normalerweise sich selbst zurück.  
  
    3.  Wenn der Parameter keine <xref:System.ICustomFormatter>\-Schnittstelle darstellt, gibt <xref:System.IFormatProvider.GetFormat%2A> den Wert `null` zurück.  
  
3.  Implementieren Sie die <xref:System.ICustomFormatter.Format%2A>\-Methode.  Diese Methode wird von der [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\-Methode aufgerufen und ist für die Rückgabe der Zeichenfolgendarstellung einer Zahl zuständig.  Das Implementieren der Methode umfasst normalerweise folgende Schritte:  
  
    1.  Indem Sie den `provider`\-Parameter überprüfen, können Sie optional feststellen, ob die Methode zur Bereitstellung von Formatierungsdiensten berechtigt ist.  Zur Formatierung von Objekten, die sowohl <xref:System.IFormatProvider> als auch <xref:System.ICustomFormatter> implementieren, muss auch der `provider`\-Parameter auf Übereinstimmung mit dem aktuellen Formatierungsobjekt getestet werden.  
  
    2.  Bestimmen Sie, ob das Formatierungsobjekt benutzerdefinierte Formatbezeichner unterstützen soll. \(Beispielweise, kann möglicherweise Formatbezeichner "N" sein, d eine US\-Telefonnummer in NANP\-Format ausgegeben werden soll, und "I" Ausgabe im ITU\-T Recommendation E.123\-Formats an.\) Wenn Formatbezeichner verwendet werden, sollte die Methode den spezifischen Formatbezeichner behandeln.  Er wird an die Methode im `format`\-Parameter übergeben.  Wenn kein Bezeichner vorhanden ist, lautet der Wert des `format`\-Parameters <xref:System.String.Empty?displayProperty=fullName>.  
  
    3.  Rufen Sie den numerischen Wert ab, der als `arg`\-Parameter an die Methode übergeben wurde.  Führen Sie alle Bearbeitungsschritte aus, die zur Konvertierung in die entsprechende Zeichenfolgendarstellung erforderlich sind.  
  
    4.  Lassen Sie die Zeichenfolgendarstellung des `arg`\-Parameters zurückgeben.  
  
### So verwenden Sie ein benutzerdefiniertes numerisches Formatierungsobjekt  
  
1.  Erstellen Sie eine neue Instanz der benutzerdefinierten Formatierungsklasse.  
  
2.  Rufen Sie die [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\-Formatierungsmethode auf, und übergeben Sie das benutzerdefinierte Formatierungsobjekt, den Formatbezeichner \(oder <xref:System.String.Empty?displayProperty=fullName>, falls keiner verwendet wird\) und den zu formatierenden numerischen Wert an die Methode.  
  
## Beispiel  
 Im folgenden Beispiel wird ein benutzerdefinierter numerischer Formatanbieter, der mit dem Namen `TelephoneFormatter`, der eine Zahl konvertiert, die eine US\-Telefonnummer in das entsprechende NANP\- oder E.123\-Format konvertiert wird darstellt.  Die Methode behandelt zwei Formatbezeichner: "N" \(zur Ausgabe des NANP\-Formats\) und "I" \(zur Ausgabe des internationalen E.123\-Formats\).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Der benutzerdefinierte numerische Formatanbieter kann nur in Verbindung mit der [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\-Methode verwendet werden.  Die übrigen Überladungen numerischer Formatierungsmethoden \(z. B. `ToString`\), die über einen Parameter vom Typ <xref:System.IFormatProvider> verfügen, übergeben alle die <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName>\-Implementierung eines <xref:System.Type>\-Objekts, das den <xref:System.Globalization.NumberFormatInfo>\-Typ darstellt.  Im Gegenzug wird erwartet, dass die Methode ein <xref:System.Globalization.NumberFormatInfo>\-Objekt zurückgibt.  Andernfalls wird der benutzerdefinierte numerische Formatanbieter ignoriert und stattdessen das <xref:System.Globalization.NumberFormatInfo>\-Objekt für die aktuelle Kultur verwendet.  Im Beispiel wird mithilfe der `TelephoneFormatter.GetFormat`\-Methode überprüft, ob die Methode unzulässigerweise an eine numerische Formatierungsmethode übergeben wurde. Dazu wird der Methodenparameter überprüft und `null` zurückgegeben, wenn er einen anderen Typ als <xref:System.ICustomFormatter> aufweist.  
  
 Wenn ein benutzerdefinierter numerischer Formatanbieter eine Reihe von Formatbezeichnern unterstützt, sollten Sie ein Standardverhalten für den Fall vorsehen, dass im Formatelement, das im [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\-Methodenaufruf verwendet wird, kein Formatbezeichner angegeben ist.  Im Beispiel entspricht "N" dem Standardformatbezeichner.  Dadurch kann eine Zahl in eine formatierte Telefonnummer konvertiert werden, indem ein expliziter Formatbezeichner angegeben wird.  Im folgenden Beispiel wird ein solcher Methodenaufruf veranschaulicht.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Die Konvertierung kann jedoch auch stattfinden, wenn kein Formatbezeichner vorhanden ist.  Im folgenden Beispiel wird ein solcher Methodenaufruf veranschaulicht.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Wenn kein Standardformatzeichner festgelegt wurde, sollte die Implementierung der <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName>\-Methode etwa folgenden Code enthalten, damit von .NET Framework eine Formatierung bereitgestellt werden kann, die von Ihrem Code ansonsten nicht unterstützt wird.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 In diesem Beispiel dient die Methode, durch die <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName> implementiert wird, als Rückrufmethode für die [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName>\-Methode.  Folglich wird der `formatProvider`\-Parameter daraufhin überprüft, ob er einen Verweis auf das aktuelle `TelephoneFormatter`\-Objekt enthält.  Die Methode kann jedoch auch direkt über den Code aufgerufen werden.  In diesem Fall können Sie den `formatProvider`\-Parameter verwenden, um ein <xref:System.Globalization.CultureInfo>\-Objekt oder ein <xref:System.Globalization.NumberFormatInfo>\-Objekt bereitzustellen, das kulturabhängige Formatierungsinformationen liefert.  
  
## Kompilieren des Codes  
 Kompilieren Sie den Code über csc.exe oder vb.exe in der Befehlszeile.  Um den Code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)