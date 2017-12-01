---
title: "Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET Framework"
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
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1beceb2b2d32c500e73cd7786c480fcd84c3001c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Analysieren von Uhrzeitzeichenfolgen für Datum und in .NET
Analysemethoden konvertiert die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe in eine gleichbedeutende <xref:System.DateTime> Objekt. Die <xref:System.DateTime.Parse%2A> und <xref:System.DateTime.TryParse%2A> Methoden Konvertieren eines mehrere gemeinsame Darstellungen von einer Datums- und Uhrzeitangabe. Die <xref:System.DateTime.ParseExact%2A> und <xref:System.DateTime.TryParseExact%2A> Methoden konvertieren eine Zeichenfolgendarstellung, die entspricht der von einer Formatzeichenfolge für Datum und Uhrzeit angegebenen Muster. (Informationen hierzu finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).)  
  
 Die Analyse wird durch die Eigenschaften eines Formatanbieters beeinflusst. Dieser stellt Informationen wie die Zeichenfolgen, die als Datums- und Zeittrennzeichen verwendet werden, und die Namen von Monaten, Tagen und Zeiträumen bereit. Der Formatanbieter ist das aktuelle <xref:System.Globalization.DateTimeFormatInfo> -Objekt, das implizit, durch die aktuelle Threadkultur oder explizit durch bereitgestellt wird die <xref:System.IFormatProvider> Parameter einer Analysemethode. Für die <xref:System.IFormatProvider> Parameter, geben Sie einen <xref:System.Globalization.CultureInfo> -Objekt, das eine Kultur darstellt, oder ein <xref:System.Globalization.DateTimeFormatInfo> Objekt.  
  
 Die Zeichenfolgendarstellung eines zu analysierenden Datums muss den Monat und mindestens einen Tag oder das Jahr enthalten. Die Zeichenfolgendarstellung einer Uhrzeit muss die Stundenangabe und mindestens die Minuten oder den AM/PM-Kennzeichner enthalten. Bei der Analyse werden jedoch nach Möglichkeit Standardwerte für ausgelassene Komponenten ergänzt. Für ein fehlendes Datum wird standardmäßig das aktuelle Datum eingesetzt, für eine fehlende Jahresangabe das aktuelle Jahr, für einen fehlenden Monatstag der erste Tag im Monat, und für eine fehlende Uhrzeit wird standardmäßig Mitternacht angenommen.  
  
 Wenn Zeichenfolgendarstellung nur eine Uhrzeit angibt, Analyse gibt eine <xref:System.DateTime> -Objekt mit dessen <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, und <xref:System.DateTime.Day%2A> legen Sie auf die entsprechenden Werte der Eigenschaften der <xref:System.DateTime.Today%2A> Eigenschaft. Jedoch, wenn die <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> Konstante wird angegeben, in die Analysemethode, die sich ergebende Jahr, Monat und Tag Eigenschaften werden festgelegt, auf den Wert `1`.  
  
 Zusätzlich zu einer Datums- und Zeitkomponente kann die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe einen Zeitraum enthalten, der angibt, um wie viel die Zeit von der koordinierten Weltzeit (UTC) abweicht. Beispielsweise definiert die Zeichenfolge „2/14/2007 5:32:00 -7:00“ eine Uhrzeit, die sieben Stunden vor UTC liegt. Analysieren Sie ein Offset von der Zeichenfolgendarstellung einer fehlt, gibt eine <xref:System.DateTime> -Objekt mit dessen <xref:System.DateTime.Kind%2A> -Eigenschaftensatz auf <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>. Analysieren Sie, wenn ein Offset angegeben wird, gibt eine <xref:System.DateTime> -Objekt mit dessen <xref:System.DateTime.Kind%2A> -Eigenschaftensatz auf <xref:System.DateTimeKind.Local> und seinen Wert auf der lokalen Zeitzone des Computers angepasst. Sie können dieses Verhalten ändern, indem Sie mit einem <xref:System.Globalization.DateTimeStyles> -Konstante mit dem Analysemethode.  
  
 Der Formatanbieter wird auch zum Interpretieren mehrdeutiger numerischer Datumsangaben verwendet. Beispielsweise ist nicht eindeutig zu erkennen, welche Komponenten des in der Zeichenfolge „02/03/04“ dargestellten Datums für den Monat, den Tag und das Jahr stehen. In diesem Fall werden die Komponenten entsprechend der Reihenfolge ähnlicher Datumsformate im Formatanbieter interpretiert.  
  
## <a name="parse"></a>Parse  
 Das folgende Codebeispiel veranschaulicht die Verwendung von der **analysieren** Methode zum Konvertieren einer Zeichenfolge in eine **"DateTime"**. In diesem Beispiel wird die dem aktuellen Thread zugeordnete Kultur zum Durchführen der Analyse verwendet. Wenn die <xref:System.Globalization.CultureInfo> verknüpft sind, mit der aktuellen Kultur die Eingabezeichenfolge kann nicht analysiert werden eine <xref:System.FormatException> ausgelöst wird.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 Sie können auch angeben, ein **CultureInfo** auf eine der vom Objekt definierten Kulturen festgelegt, oder Sie können angeben, zu den standardmäßigen <xref:System.Globalization.DateTimeFormatInfo> zurückgegebenen Objekte die <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> Eigenschaft. Im folgenden Codebeispiel verwendet einen Formatanbieter analysiert eine deutsche Zeichenfolge in eine **"DateTime"**. Ein **CultureInfo** definiert und mit der Zeichenfolge analysiert wird, um sicherzustellen, dass erfolgreiche Verarbeitung dieser bestimmten Zeichenfolge übergeben wird, das der Kultur de-DE darstellt. Dadurch wird die Einstellung in der **CurrentCulture** von der **CurrentThread**.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Jedoch, obwohl Sie Überladungen von verwenden, können die <xref:System.DateTime.Parse%2A> Methode, um benutzerdefinierte Formatanbietern, geben die Methode unterstützt nicht die Verwendung von nicht standardmäßigen Formatanbietern. Verwenden, um eine Datums- und Uhrzeitangabe, ausgedrückt in einem nicht standardmäßigen Format zu analysieren, die <xref:System.DateTime.ParseExact%2A> Methode stattdessen.  
  
 Im folgenden Codebeispiel wird mit der <xref:System.Globalization.DateTimeStyles> Enumeration, um anzugeben, dass die aktuelle Informationen für Datum und Uhrzeit nicht hinzugefügt werden sollen die **"DateTime"** für Felder, die die Zeichenfolge nicht definiert ist.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 Die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> -Methode konvertiert eine Zeichenfolge, die entspricht an ein Muster für die angegebene Zeichenfolge an eine **"DateTime"** Objekt. Wenn eine Zeichenfolge, die nicht der angegebenen Form ist für diese Methode übergeben, wird eine <xref:System.FormatException> ausgelöst wird. Sie können einen der Standardformatbezeichner für Datum und Uhrzeit oder eine begrenzte Kombination der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit angeben. Mithilfe der benutzerdefinierten Formatbezeichner können Sie eine benutzerdefinierte Erkennungszeichenfolge erstellen. Erläuterungen zu den Bezeichnern finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Jeder Überladung der <xref:System.DateTime.ParseExact%2A> Methode enthält auch eine <xref:System.IFormatProvider> Parameter, der in der Regel kulturspezifische Informationen über die Formatierung der Zeichenfolge enthält. In der Regel wird dies <xref:System.IFormatProvider> Objekt ist ein <xref:System.Globalization.CultureInfo> -Objekt, das eine Standardkultur darstellt oder eine <xref:System.Globalization.DateTimeFormatInfo> von zurückgegebene Objekt der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> Eigenschaft. Im Gegensatz zu anderen Datums- und Uhrzeitangabe Funktionen analysieren, diese Methode unterstützt jedoch auch eine <xref:System.IFormatProvider> , eine nicht standardmäßige Datums- und Zeitformat definiert.  
  
 Im folgenden Codebeispiel die **ParseExact** -Methode übergeben ein String-Objekt, zu analysieren, gefolgt von einem Formatbezeichner, gefolgt von einem **CultureInfo** Objekt. Dies **ParseExact** Methode kann nur Analysieren von Zeichenfolgen, die das langen Datumsmuster in der Kultur En-US aufweisen.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von Zeichenfolgen](../../../docs/standard/base-types/parsing-strings.md)  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)  
 [Typkonvertierung in .NET](../../../docs/standard/base-types/type-conversion.md)
