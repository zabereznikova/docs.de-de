---
title: 'Gewusst wie: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern'
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
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79860091e549dcf4eaa7090947f9506eceb6119
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Gewusst wie: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern
Die <xref:System.DateTime> und <xref:System.DateTimeOffset> Typen verwenden den gregorianischen Kalender als Standardkalender. Das bedeutet, dass ein Aufruf der `ToString`-Methode eines Datums- und Uhrzeitwerts die Zeichenfolgendarstellung dieses Datums und dieser Uhrzeit im gregorianischen Kalender anzeigt, selbst wenn dieses Datum und diese Uhrzeit in einem anderen Kalender erstellt wurden. Dies wird im folgenden Beispiel werden zwei verschiedene Möglichkeiten So erstellen Sie einen Wert für Datum und Uhrzeit mit den persischen Kalender dar, aber diese Datum und Uhrzeit-Werte immer noch im gregorianischen Kalender angezeigt wird, beim Aufrufen von veranschaulicht die <xref:System.DateTime.ToString%2A> Methode. Dieses Beispiel zeigt zwei häufig verwendete, aber falsche Verfahren zum Anzeigen des Datums in einem bestimmten Kalender.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Zum Anzeigen des Datums in einem bestimmten Kalender können zwei verschiedene Verfahren verwendet werden. Für das erste Verfahren muss der Kalender der Standardkalender für eine bestimmte Kultur sein. Das zweite kann mit jedem beliebigen Kalender verwendet werden.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Anzeigen des Datums für den Standardkalender einer Kultur  
  
1.  Instanziieren Sie ein Kalenderobjekt abgeleitet wurde. die <xref:System.Globalization.Calendar> Klasse, die den zu verwendenden Kalender darstellt.  
  
2.  Instanziieren einer <xref:System.Globalization.CultureInfo> Objekt, das die Kultur, deren Formatierung verwendet wird, um die Anzeige des Datums, darstellt.  
  
3.  Rufen Sie die <xref:System.Array.Exists%2A?displayProperty=nameWithType> Methode, um zu bestimmen, ob das Kalenderobjekt ein Mitglied über das zurückgegebene Array ist die <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> Eigenschaft. Dies bedeutet, dass der Kalender als Standardkalender für dienen kann die <xref:System.Globalization.CultureInfo> Objekt. Wenn das Objekt kein Member des Arrays ist, befolgen Sie die Anweisungen im Abschnitt „Anzeigen des Datums in einem beliebigen Kalender“.  
  
4.  Weisen Sie das Kalenderobjekt, das die <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> Eigenschaft von der <xref:System.Globalization.DateTimeFormatInfo> zurückgegebenes Objekt die <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> Eigenschaft.  
  
    > [!NOTE]
    >  Die <xref:System.Globalization.CultureInfo> -Klasse verfügt auch über eine <xref:System.Globalization.CultureInfo.Calendar%2A> Eigenschaft. Es ist jedoch nur-Lese und Konstante; ändert sich nicht um die neuen Standardkalender zugewiesen der <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> Eigenschaft.  
  
5.  Rufen Sie entweder die <xref:System.DateTime.ToString%2A> oder <xref:System.DateTime.ToString%2A> -Methode, und übergeben sie die <xref:System.Globalization.CultureInfo> -Objekt, dessen Standardkalender im vorherigen Schritt geändert wurde.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Anzeigen des Datums in einem beliebigen Kalender  
  
1.  Instanziieren Sie ein Kalenderobjekt abgeleitet wurde. die <xref:System.Globalization.Calendar> Klasse, die den zu verwendenden Kalender darstellt.  
  
2.  Bestimmen Sie, welche Datums- und Uhrzeitelemente in der Zeichenfolgendarstellung des Datums- und Uhrzeitwerts angezeigt werden sollen.  
  
3.  Für jedes Datum und Uhrzeit-Element, das Sie anzeigen möchten, rufen Sie die Kalenderobjekts `Get`... -Methode. Die folgenden Methoden sind verfügbar:  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A>, um das Jahr im entsprechenden Kalender anzuzeigen.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A>, auf die Anzeige des Monats im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A>, um die Anzahl der Tag des Monats im entsprechenden Kalender anzuzeigen.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A>, um die Stunde des Tages im entsprechenden Kalender anzuzeigen.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A>, um die Minuten in der Stunde im entsprechenden Kalender anzuzeigen.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A>, um die Sekunden in der Minute im entsprechenden Kalender anzuzeigen.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A>, um die Millisekunden in die zweite im entsprechenden Kalender anzuzeigen.  
  
## <a name="example"></a>Beispiel  
 Das Beispiel zeigt ein Datum mithilfe von zwei verschiedenen Kalendern an. Es zeigt das Datum an, nachdem der Hijri-Kalender als Standardkalender für die Kultur „ar-JO“ definiert wurde, und es zeigt das Datum unter Verwendung des persischen Kalenders an, der nicht als optionaler Kalender von der fa-IR-Kultur unterstützt wird.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Jede <xref:System.Globalization.CultureInfo> Objekt kann eine oder mehrere Kalender ersichtlich sind unterstützen die <xref:System.Globalization.CultureInfo.OptionalCalendars%2A> Eigenschaft. Eines der folgenden als Standardkalender der Kultur festgelegt wurde und der schreibgeschützten zurückgegebenes <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> Eigenschaft. Ein anderer optionaler Kalender kann durch zuweisen als Standard festgelegt werden eine <xref:System.Globalization.Calendar> -Objekt, das diesen Kalender zu darstellt, die <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> von zurückgegebene Eigenschaft der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> Eigenschaft. Allerdings einige Kalender, z. B. den persischen Kalender dar, dargestellt durch die <xref:System.Globalization.PersianCalendar> Klasse, die als optionale Kalender für jede Kultur nicht erfüllen.  
  
 Das Beispiel definiert eine wiederverwendbare Kalenderhilfsprogrammklasse, `CalendarUtility`, um viele der Details beim Generieren der Zeichenfolgendarstellung eines Datums mithilfe eines bestimmten Kalenders zu verarbeiten. Die `CalendarUtility`-Klasse verfügt über die folgenden Member:  
  
-   Einen parametrisierten Konstruktor, dessen einzelner Parameter ist, ein <xref:System.Globalization.Calendar> Objekt, in dem ein Datum dargestellt werden. Dieser wird einem privaten Klassenfeld zugewiesen.  
  
-   `CalendarExists`, eine private Methode, die einen booleschen Wert, der angibt, ob der Kalender szenariobeschreibungen zurückgibt der `CalendarUtility` Objekt wird von unterstützt die <xref:System.Globalization.CultureInfo> -Objekt, das an die Methode als Parameter übergeben wird. Die Methode bindet einen Aufruf der <xref:System.Array.Exists%2A?displayProperty=nameWithType> -Methode, an denen übergibt die <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> Array.  
  
-   `HasSameName`, eine private Methode zugewiesen der <xref:System.Predicate%601> Delegat, der als Parameter übergeben wird, die <xref:System.Array.Exists%2A?displayProperty=nameWithType> Methode. Jeder Member des Arrays wird an die Methode übergeben, bis die Methode `true` zurückgibt. Die Methode bestimmt, ob der Name eines optionalen Kalenders dem Kalender entspricht, der durch das `CalendarUtility`-Objekt dargestellt wird.  
  
-   `DisplayDate`, eine überladene öffentliche Methode, die zwei Parameter übergeben wird: entweder ein <xref:System.DateTime> oder <xref:System.DateTimeOffset> Wert, der im Kalender dargestellte express die `CalendarUtility` Objekt und die Kultur, deren Formatierungsregeln verwendet werden sollen. Das Verhalten bei der Rückgabe der Zeichenfolgendarstellung eines Datums richtet sich danach, ob der Zielkalender von der Kultur unterstützt wird, deren Formatierungsregeln verwendet werden sollen.  
  
 Unabhängig von den Kalender, die zum Erstellen einer <xref:System.DateTime> oder <xref:System.DateTimeOffset> Wert in diesem Beispiel ist der Wert in der Regel als gregorianisches Datum ausgedrückt wird. Grund hierfür ist die <xref:System.DateTime> und <xref:System.DateTimeOffset> Typen Kalenderinformationen nicht beibehalten. Intern werden sie als Anzahl von Zeiteinheiten (Ticks) dargestellt, die seit Mitternacht des 1. Januar 0001 verstrichen sind. Die Interpretation dieser Zahl hängt vom Kalender ab. In den meisten Kulturen ist der Gregorianische Kalender der Standardkalender.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert einen Verweis auf "System.Core.dll".  
  
 Kompilieren Sie den Code über csc.exe oder vb.exe in der Befehlszeile. Um den Code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## <a name="see-also"></a>Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)
