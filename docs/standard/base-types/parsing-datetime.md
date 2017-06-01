---
title: "Analysieren von Zeichenfolgen f&#252;r Datum und Uhrzeit in .NET Framework | Microsoft Docs"
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
  - "Basistypen, Analysieren von Zeichenfolgen"
  - "Datum- und Uhrzeitzeichenfolgen"
  - "DateTime-Objekt"
  - "Enumerationen [.NET Framework], Analysieren von Zeichenfolgen"
  - "ParseExact-Methode"
  - "Analysieren von Zeichenfolgen, Datum- und Uhrzeitzeichenfolgen"
  - "Uhrzeitzeichenfolgen"
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# Analysieren von Zeichenfolgen f&#252;r Datum und Uhrzeit in .NET Framework
Analysemethoden konvertieren die Zeichenfolgendarstellung eines Datums und einer Uhrzeit in ein entsprechendes <xref:System.DateTime>\-Objekt.  Die <xref:System.DateTime.Parse%2A>\-Methode und die <xref:System.DateTime.TryParse%2A>\-Methode konvertieren alle gemeinsamen Darstellungen eines Datums und einer Uhrzeit.  Die <xref:System.DateTime.ParseExact%2A>\-Methode und die <xref:System.DateTime.TryParseExact%2A>\-Methode konvertieren eine Zeichenfolgendarstellung, die genau mit dem von einer Formatzeichenfolge für Datum und Uhrzeit angegebenen Muster übereinstimmt. \(Entsprechende Informationen finden Sie in den Themen zu [Standardformatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) und zu [benutzerdefinierten Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).\)  
  
 Die Verarbeitung wird durch die Eigenschaften eines Formatanbieters beeinflusst, der Informationen wie die Trennzeichen für Datumsangaben und Zeitangaben sowie die Namen von Monaten, Tagen und Zeiträumen bereitstellt.  Der Formatanbieter ist das aktuelle <xref:System.Globalization.DateTimeFormatInfo>\-Objekt, das implizit durch die aktuelle Threadkultur oder explizit durch den <xref:System.IFormatProvider>\-Parameter einer Analysemethode bereitgestellt wird.  Geben Sie für den <xref:System.IFormatProvider>\-Parameter ein <xref:System.Globalization.CultureInfo>\-Objekt an, das eine Kultur oder ein <xref:System.Globalization.DateTimeFormatInfo>\-Objekt darstellt.  
  
 Die Zeichenfolgendarstellung eines zu verarbeitenden Datums muss den Monat und zumindest einen Tag oder ein Jahr enthalten.  Die Zeichenfolgendarstellung einer Uhrzeit muss die Stunde und zumindest die Minuten oder den AM\/PM\-Indikator enthalten.  Bei der Verarbeitung werden jedoch Standardwerte für weggelassene Komponenten bereitgestellt, sofern dies möglich ist.  Für ein fehlendes Datum wird standardmäßig das aktuelle Datum angegeben, für ein fehlendes Jahr das aktuelle Jahr und für einen fehlenden Tag eines Monats der erste Tag des Monats. Für eine fehlende Uhrzeit wird standardmäßig Mitternacht angegeben.  
  
 Falls die Zeichenfolgendarstellung nur eine Uhrzeit angibt, wird bei der Verarbeitung ein <xref:System.DateTime>\-Objekt zurückgegeben, dessen Eigenschaften <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> und <xref:System.DateTime.Day%2A> auf die entsprechenden Werte der <xref:System.DateTime.Today%2A>\-Eigenschaft festgelegt sind.  Ist jedoch die <xref:System.Globalization.DateTimeStyles>\-Konstante in der Analysemethode angegeben, werden die Eigenschaften für Jahr, Monat und Tag auf den Wert `1` festgelegt.  
  
 Außer einer Datums\- und Uhrzeitkomponente kann die Zeichenfolgendarstellung eines Datums oder einer Uhrzeit auch einen Offset umfassen, der angibt, inwieweit die Uhrzeit von der koordinierten Weltzeit \(Coordinated Universal Time, UTC\) abweicht.  So definiert zum Beispiel die Zeichenfolge "2\/14\/2007 5:32:00 \-7:00" eine Uhrzeit, die sieben Stunden vor der koordinierten Weltzeit \(UTC\) liegt.  Falls ein Offset in der Zeichenfolgendarstellung einer Uhrzeit weggelassen wurde, wird bei der Verarbeitung ein <xref:System.DateTime>\-Objekt zurückgegeben, dessen <xref:System.DateTime.Kind%2A>\-Eigenschaft auf <xref:System.DateTimeKind?displayProperty=fullName> festgelegt ist.  Wenn ein Offset angegeben ist, wird bei der Verarbeitung ein <xref:System.DateTime>\-Objekt zurückgegeben, dessen <xref:System.DateTime.Kind%2A>\-Eigenschaft auf <xref:System.DateTimeKind> festgelegt und dessen Wert an die lokale Zeitzone des Computers angepasst ist.  Sie können dieses Verhalten ändern, indem Sie gemeinsam mit der Analysemethode eine <xref:System.Globalization.DateTimeStyles>\-Konstante verwenden.  
  
 Mit dem Formatanbieter werden auch mehrdeutige numerische Daten interpretiert.  So ist beispielsweise nicht eindeutig, bei welchen Komponenten des durch die Zeichenfolge "02\/03\/04" dargestellten Datums es sich um den Monat, den Tag und das Jahr handelt.  In diesem Fall werden die Komponenten entsprechend der Reihenfolge ähnlicher Datumsformate im Formatanbieter interpretiert.  
  
## Parse  
 Der folgende Beispielcode veranschaulicht die Verwendung der **Parse**\-Methode, um eine Zeichenfolge in eine **DateTime** zu konvertieren.  Um die Verarbeitung durchzuführen, wird die Kultur verwendet, die dem aktuellen Thread zugeordnet ist.  Wenn die der aktuellen Kultur zugeordnete <xref:System.Globalization.CultureInfo> die eingegebene Zeichenfolge nicht verarbeiten kann, wird eine <xref:System.FormatException> ausgelöst.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 Sie können auch eine **CultureInfo** angeben, die auf eine der vom Objekt definierten Kulturen festgelegt ist, oder Sie können eines der standardmäßigen <xref:System.Globalization.DateTimeFormatInfo>\-Objekte angeben, die von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben werden.  Im folgenden Beispielcode wird ein Formatanbieter verwendet, um eine deutsche Zeichenfolge in eine **DateTime** umzuwandeln.  Eine **CultureInfo**, die die Kultur de\-DE repräsentiert, wird zusammen mit der verarbeiteten Zeichenfolge definiert und übergeben, um eine erfolgreiche Verarbeitung dieser bestimmten Zeichenfolge zu gewährleisten.  Dadurch wird die unter **CurrentCulture** des **CurrentThread** vorhandene Einstellung irrelevant.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Obwohl Sie Überladungen der <xref:System.DateTime.Parse%2A>\-Methode zum Festlegen von benutzerdefinierten Formatanbietern verwenden können, unterstützt die Methode nur die Verwendung standardmäßiger Formatanbieter und keiner anderen.  Um ein Datum und eine Uhrzeit in einem nicht standardmäßigen Format zu verarbeiten, verwenden Sie stattdessen die <xref:System.DateTime.ParseExact%2A>\-Methode.  
  
 Im folgenden Codebeispiel wird die <xref:System.Globalization.DateTimeStyles>\-Enumeration verwendet, um festzulegen, dass die aktuellen Informationen zu Datum und Uhrzeit nicht in Felder für **DateTime** eingetragen werden, die durch die Zeichenfolge nicht definiert werden.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## ParseExact  
 Die <xref:System.DateTime.ParseExact%2A?displayProperty=fullName>\-Methode konvertiert eine Zeichenfolge, die mit einem bestimmten Zeichenfolgenmuster eines **DateTime**\-Objekts übereinstimmt.  Wenn eine Zeichenfolge, die nicht der angegebenen Form entspricht, an diese Methode übergeben wird, wird eine <xref:System.FormatException> ausgelöst.  Sie können einen der gebräuchlichen Formatbezeichner für Datum und Uhrzeit oder eine begrenzte Kombination benutzerdefinierter Formatbezeichner angeben.  Mithilfe der benutzerdefinierten Formatbezeichner können Sie Zeichenfolgen mit benutzerdefinierter Erkennung konstruieren.  Eine Erläuterung der Bezeichner finden Sie in den Themen zu [Standardformatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) und zu [benutzerdefinierten Zeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Jede Überladung der <xref:System.DateTime.ParseExact%2A>\-Methode verfügt außerdem über einen <xref:System.IFormatProvider>\-Parameter, der normalerweise kulturspezifische Daten zur Formatierung der Zeichenfolge enthält.  In der Regel handelt es sich bei diesem <xref:System.IFormatProvider>\-Objekt um ein <xref:System.Globalization.CultureInfo>\-Objekt, das eine Standardkultur darstellt, oder ein <xref:System.Globalization.DateTimeFormatInfo>\-Objekt, das von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird.  Im Gegensatz zu anderen Verarbeitungsfunktionen für Datum und Uhrzeit unterstützt diese Methode jedoch auch einen <xref:System.IFormatProvider>, der nicht standardmäßige Datums\- und Uhrzeitformate definiert.  
  
 Im folgenden Codebeispiel wird der **ParseExact**\-Methode ein Zeichenfolgenobjekt zur Verarbeitung übergeben, gefolgt von einem Formatbezeichner und einem **CultureInfo**\-Objekt.  Diese **ParseExact**\-Methode kann nur Zeichenfolgen im langen Datumsformat verarbeiten, das in der Kultur en\-US verwendet wird.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## Siehe auch  
 [Analysieren von Zeichenfolgen](../../../docs/standard/base-types/parsing-strings.md)   
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)   
 [Typkonvertierung in .NET Framework](../../../docs/standard/base-types/type-conversion.md)