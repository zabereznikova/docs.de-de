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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6e3ef01abdb615b2850b5a9d07e1208ee22eda95
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET
Durch die Analyse wird die Zeichenfolgendarstellung eines Datums und einer Uhrzeit in ein entsprechendes <xref:System.DateTime>-Objekt konvertiert. Die Methoden <xref:System.DateTime.Parse%2A> und <xref:System.DateTime.TryParse%2A> konvertieren aus beliebigen mehreren gängigen Darstellungen von Datum und Uhrzeit. Die Methoden <xref:System.DateTime.ParseExact%2A> und <xref:System.DateTime.TryParseExact%2A> konvertieren eine Zeichenfolgendarstellung entsprechend dem Muster, das durch eine Formatzeichenfolge für Datum und Uhrzeit angegeben wird. (Informationen hierzu finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).)  
  
 Die Analyse wird durch die Eigenschaften eines Formatanbieters beeinflusst. Dieser stellt Informationen wie die Zeichenfolgen, die als Datums- und Zeittrennzeichen verwendet werden, und die Namen von Monaten, Tagen und Zeiträumen bereit. Der Formatanbieter ist das aktuelle <xref:System.Globalization.DateTimeFormatInfo>-Objekt, das implizit durch die aktuelle Threadkultur oder explizit durch den <xref:System.IFormatProvider>-Parameter einer Analysemethode bereitgestellt wird. Geben Sie für den <xref:System.IFormatProvider>-Parameter ein <xref:System.Globalization.CultureInfo>-Objekt an, das eine Kultur darstellt, oder ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt.  
  
 Die Zeichenfolgendarstellung eines zu analysierenden Datums muss den Monat und mindestens einen Tag oder das Jahr enthalten. Die Zeichenfolgendarstellung einer Uhrzeit muss die Stundenangabe und mindestens die Minuten oder den AM/PM-Kennzeichner enthalten. Bei der Analyse werden jedoch nach Möglichkeit Standardwerte für ausgelassene Komponenten ergänzt. Für ein fehlendes Datum wird standardmäßig das aktuelle Datum eingesetzt, für eine fehlende Jahresangabe das aktuelle Jahr, für einen fehlenden Monatstag der erste Tag im Monat, und für eine fehlende Uhrzeit wird standardmäßig Mitternacht angenommen.  
  
 Wenn die Zeichenfolgendarstellung nur eine Uhrzeit angibt, wird durch die Analyse ein <xref:System.DateTime>-Objekt zurückgegeben, dessen <xref:System.DateTime.Year%2A>-, <xref:System.DateTime.Month%2A>- und <xref:System.DateTime.Day%2A>-Eigenschaften auf die entsprechenden Werte der Eigenschaft <xref:System.DateTime.Today%2A> festgelegt sind. Wenn jedoch die <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault>-Konstante in der Analysemethode angegeben wird, werden die year-, month- und day-Eigenschaften auf den Wert `1` festgelegt.  
  
 Zusätzlich zu einer Datums- und Zeitkomponente kann die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe einen Zeitraum enthalten, der angibt, um wie viel die Zeit von der koordinierten Weltzeit (UTC) abweicht. Beispielsweise definiert die Zeichenfolge „2/14/2007 5:32:00 -7:00“ eine Uhrzeit, die sieben Stunden vor UTC liegt. Wenn die Abweichung in der Zeichenfolgendarstellung einer Uhrzeit fehlt, gibt die Analyse ein <xref:System.DateTime>-Objekt zurück, dessen <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> festgelegt ist. Wird eine Abweichung angegeben, gibt die Analyse ein <xref:System.DateTime>-Objekt zurück, dessen <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Local> festgelegt ist und dessen Wert an die lokale Zeitzone des Computers angepasst wird. Sie können dieses Verhalten ändern, indem Sie eine <xref:System.Globalization.DateTimeStyles>-Konstante mit der Analysemethode verwenden.  
  
 Der Formatanbieter wird auch zum Interpretieren mehrdeutiger numerischer Datumsangaben verwendet. Beispielsweise ist nicht eindeutig zu erkennen, welche Komponenten des in der Zeichenfolge „02/03/04“ dargestellten Datums für den Monat, den Tag und das Jahr stehen. In diesem Fall werden die Komponenten entsprechend der Reihenfolge ähnlicher Datumsformate im Formatanbieter interpretiert.  
  
## <a name="parse"></a>Parse  
 Das folgende Codebeispiel veranschaulicht die Verwendung der **Parse**-Methode zum Konvertieren einer Zeichenfolge in einen **DateTime**-Wert. In diesem Beispiel wird die dem aktuellen Thread zugeordnete Kultur zum Durchführen der Analyse verwendet. Wenn die der aktuellen Kultur zugeordnete <xref:System.Globalization.CultureInfo>-Klasse nicht die Eingabezeichenfolge analysieren kann, wird eine <xref:System.FormatException> ausgelöst.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 Sie können auch eine **CultureInfo**-Klasse angeben, die auf eine der durch dieses Objekt definierten Kulturen festgelegt ist, oder Sie können eines der <xref:System.Globalization.DateTimeFormatInfo>-Standardobjekte angeben, das von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird. Im folgenden Codebeispiel wird ein Formatanbieter verwendet, um eine deutsche Zeichenfolge in einen **DateTime**-Wert zu analysieren. Eine **CultureInfo**-Klasse, die für die Kultur „de-DE“ steht, wird definiert und mit der zu analysierenden Zeichenfolge übergeben, um eine erfolgreiche Analyse dieser Zeichenfolge sicherzustellen. Dadurch werden die Einstellungen in **CurrentCulture** von **CurrentThread** ausgeschlossen.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 Auch wenn Sie Überladungen der <xref:System.DateTime.Parse%2A>-Methode zur Angabe benutzerdefinierter Formatanbieter verwenden können, werden nicht dem Standard entsprechende Formatanbieter nicht von der Methode unterstützt. Um ein Datum und eine Uhrzeit in einem nicht dem Standard entsprechenden Format zu analysieren, verwenden Sie stattdessen die <xref:System.DateTime.ParseExact%2A>-Methode.  
  
 Im folgenden Codebeispiel wird anhand der <xref:System.Globalization.DateTimeStyles>-Enumeration angegeben, dass die aktuellen Datums- und Uhrzeitinformationen nicht dem **DateTime**-Wert hinzugefügt werden sollen für Felder, die nicht durch die Zeichenfolge definiert werden.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 Die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>-Methode konvertiert eine Zeichenfolge, die einem angegebenen Zeichenfolgenmuster entspricht, in ein **DateTime**-Objekt. Wenn eine Zeichenfolge, die nicht dem angegebenen Format entspricht, an diese Methode übergeben wird, wird eine <xref:System.FormatException> ausgelöst. Sie können einen der Standardformatbezeichner für Datum und Uhrzeit oder eine begrenzte Kombination der benutzerdefinierten Formatbezeichner für Datum und Uhrzeit angeben. Mithilfe der benutzerdefinierten Formatbezeichner können Sie eine benutzerdefinierte Erkennungszeichenfolge erstellen. Erläuterungen zu den Bezeichnern finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md).  
  
 Jede Überladung der <xref:System.DateTime.ParseExact%2A>-Methode enthält auch einen <xref:System.IFormatProvider>-Parameter, der normalerweise kulturspezifische Informationen zur Formatierung der Zeichenfolge enthält. In der Regel handelt es sich bei diesem <xref:System.IFormatProvider>-Objekt um ein <xref:System.Globalization.CultureInfo>-Objekt, das eine Standardkultur darstellt, oder um ein von der Eigenschaft <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> zurückgegebenes <xref:System.Globalization.DateTimeFormatInfo>-Objekt. Im Gegensatz zu anderen Funktionen zur Datums- und Uhrzeitanalyse unterstützt diese Methode jedoch auch einen <xref:System.IFormatProvider>, der ein nicht dem Standard entsprechendes Datums- und Zeitformat definiert.  
  
 Im folgenden Codebeispiel wird die **ParseExact**-Methode an ein zu analysierendes Zeichenfolgenobjekt übergeben, gefolgt von einem Formatbezeichner und einem **CultureInfo**-Objekt. Diese **ParseExact**-Methode kann nur Zeichenfolgen analysieren, die in der Kultur „en-US“ das lange Datumsmuster aufweisen.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)  
 [Typkonvertierung in .NET](../../../docs/standard/base-types/type-conversion.md)
