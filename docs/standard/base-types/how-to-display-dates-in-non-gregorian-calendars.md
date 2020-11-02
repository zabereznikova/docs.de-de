---
title: 'Vorgehensweise: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET], dates
- dates [.NET], formatting
- calendars [.NET], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
ms.openlocfilehash: 6c1ab51114a1b39234adbc89526d111b3b9ba44c
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888442"
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Vorgehensweise: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern
Die Typen <xref:System.DateTime> und <xref:System.DateTimeOffset> verwenden den gregorianischen Kalender als Standardkalender. Das bedeutet, dass ein Aufruf der `ToString`-Methode eines Datums- und Uhrzeitwerts die Zeichenfolgendarstellung dieses Datums und dieser Uhrzeit im gregorianischen Kalender anzeigt, selbst wenn dieses Datum und diese Uhrzeit in einem anderen Kalender erstellt wurden. Dies wird im folgenden Beispiel veranschaulicht. Hierbei werden zwei verschiedene Möglichkeiten verwendet, um einen Datums- und Uhrzeitwert mit dem persischen Kalender zu erstellen. Beim Aufruf der <xref:System.DateTime.ToString%2A>-Methode werden diese Datums- und Uhrzeitwerte aber weiterhin im gregorianischen Kalender angezeigt. Dieses Beispiel zeigt zwei häufig verwendete, aber falsche Verfahren zum Anzeigen des Datums in einem bestimmten Kalender.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Zum Anzeigen des Datums in einem bestimmten Kalender können zwei verschiedene Verfahren verwendet werden. Für das erste Verfahren muss der Kalender der Standardkalender für eine bestimmte Kultur sein. Das zweite kann mit jedem beliebigen Kalender verwendet werden.  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Anzeigen des Datums für den Standardkalender einer Kultur  
  
1. Instanziieren Sie ein aus der <xref:System.Globalization.Calendar>-Klasse abgeleitetes Kalenderobjekt, das den zu verwendenden Kalender darstellt.  
  
2. Instanziieren Sie ein <xref:System.Globalization.CultureInfo>-Objekt, das die Kultur darstellt, deren Formatierung für die Datumsanzeige verwendet wird.  
  
3. Rufen Sie die <xref:System.Array.Exists%2A?displayProperty=nameWithType>-Methode auf, um zu ermitteln, ob das Kalenderobjekt ein Member des von der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen Arrays ist. Wenn dies der Fall ist, kann der Kalender als Standardkalender für das <xref:System.Globalization.CultureInfo>-Objekt dienen. Wenn das Objekt kein Member des Arrays ist, befolgen Sie die Anweisungen im Abschnitt „Anzeigen des Datums in einem beliebigen Kalender“.  
  
4. Weisen Sie das Kalenderobjekt zu, um die von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebene <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A>-Eigenschaft des <xref:System.Globalization.DateTimeFormatInfo>-Objekts festzulegen.  
  
    > [!NOTE]
    > Die <xref:System.Globalization.CultureInfo>-Klasse verfügt auch über eine <xref:System.Globalization.CultureInfo.Calendar%2A>-Eigenschaft. Diese ist jedoch schreibgeschützt und konstant. Sie ändert sich nicht, um den neuen, der <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft zugewiesenen Standardkalender widerzuspiegeln.  
  
5. Rufen Sie entweder die <xref:System.DateTime.ToString%2A>- oder <xref:System.DateTime.ToString%2A>-Methode auf, und übergeben Sie ihr das <xref:System.Globalization.CultureInfo>-Objekt, dessen Standardkalender im vorherigen Schritt geändert wurde.  
  
### <a name="to-display-the-date-in-any-calendar"></a>Anzeigen des Datums in einem beliebigen Kalender  
  
1. Instanziieren Sie ein aus der <xref:System.Globalization.Calendar>-Klasse abgeleitetes Kalenderobjekt, das den zu verwendenden Kalender darstellt.  
  
2. Bestimmen Sie, welche Datums- und Uhrzeitelemente in der Zeichenfolgendarstellung des Datums- und Uhrzeitwerts angezeigt werden sollen.  
  
3. Rufen Sie für jedes Datums- und Uhrzeitelement, das Sie anzeigen möchten, die `Get`... -Methode. Die folgenden Methoden sind verfügbar:  
  
    - <xref:System.Globalization.Calendar.GetYear%2A> zum Anzeigen des Jahrs im entsprechenden Kalender  
  
    - <xref:System.Globalization.Calendar.GetMonth%2A> zum Anzeigen des Monats im entsprechenden Kalender  
  
    - <xref:System.Globalization.Calendar.GetDayOfMonth%2A> zum Anzeigen der Zahl, die dem Tag des Monats im entsprechenden Kalender entspricht  
  
    - <xref:System.Globalization.Calendar.GetHour%2A> zum Anzeigen der Stunde des Tages im entsprechenden Kalender  
  
    - <xref:System.Globalization.Calendar.GetMinute%2A> zum Anzeigen der Minuten in der Stunde im entsprechenden Kalender  
  
    - <xref:System.Globalization.Calendar.GetSecond%2A> zum Anzeigen der Sekunden in der Minute im entsprechenden Kalender  
  
    - <xref:System.Globalization.Calendar.GetMilliseconds%2A> zum Anzeigen der Millisekunden in der Sekunde im entsprechenden Kalender  
  
## <a name="example"></a>Beispiel  
 Das Beispiel zeigt ein Datum mithilfe von zwei verschiedenen Kalendern an. Es zeigt das Datum an, nachdem der Hijri-Kalender als Standardkalender für die Kultur „ar-JO“ definiert wurde, und es zeigt das Datum unter Verwendung des persischen Kalenders an, der nicht als optionaler Kalender von der fa-IR-Kultur unterstützt wird.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Jedes <xref:System.Globalization.CultureInfo>-Objekt kann mindestens einen Kalender unterstützen, der von der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>-Eigenschaft angegeben wird. Einer dieser Kalender ist als Standardkalender der Kultur festgelegt und wird von der schreibgeschützten <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben. Ein anderer der optionalen Kalender kann als Standard festgelegt werden, indem ein <xref:System.Globalization.Calendar>-Objekt, das diesen Kalender darstellt, der von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>-Eigenschaft zurückgegebenen <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>-Eigenschaft zugewiesen wird. Einige Kalender jedoch, wie der von der <xref:System.Globalization.PersianCalendar>-Klasse dargestellte persische Kalender, dienen nicht als optionale Kalender für irgendeine Kultur.  
  
 Das Beispiel definiert eine wiederverwendbare Kalenderhilfsprogrammklasse, `CalendarUtility`, um viele der Details beim Generieren der Zeichenfolgendarstellung eines Datums mithilfe eines bestimmten Kalenders zu verarbeiten. Die `CalendarUtility`-Klasse verfügt über die folgenden Member:  
  
- Einen parametrisierten Konstruktor, dessen einziger Parameter ein <xref:System.Globalization.Calendar>-Objekt ist, in dem ein Datum dargestellt werden soll. Dieser wird einem privaten Klassenfeld zugewiesen.  
  
- `CalendarExists`, eine private Methode, die einen booleschen Wert zurückgibt, um anzugeben, ob der durch das `CalendarUtility`-Objekt dargestellte Kalender von dem <xref:System.Globalization.CultureInfo>-Objekt unterstützt wird, das als Parameter an die Methode übergeben wird. Die Methode umschließt einen Aufruf der <xref:System.Array.Exists%2A?displayProperty=nameWithType>-Methode, an die das <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>-Array übergeben wird.  
  
- `HasSameName`, eine dem <xref:System.Predicate%601>-Delegaten zugewiesene private Methode, die als Parameter an die <xref:System.Array.Exists%2A?displayProperty=nameWithType>-Methode übergeben wird. Jeder Member des Arrays wird an die Methode übergeben, bis die Methode `true` zurückgibt. Die Methode bestimmt, ob der Name eines optionalen Kalenders dem Kalender entspricht, der durch das `CalendarUtility`-Objekt dargestellt wird.  
  
- `DisplayDate`, eine überladene öffentliche Methode, an die zwei Parameter übergeben werden: erstens entweder ein <xref:System.DateTime>- oder ein <xref:System.DateTimeOffset>-Wert, der in dem durch das `CalendarUtility`-Objekt dargestellten Kalender ausgedrückt werden soll. Zweitens wird die Kultur übergeben, deren Formatierungsregeln verwendet werden sollen. Das Verhalten bei der Rückgabe der Zeichenfolgendarstellung eines Datums richtet sich danach, ob der Zielkalender von der Kultur unterstützt wird, deren Formatierungsregeln verwendet werden sollen.  
  
 Unabhängig von dem Kalender, der in diesem Beispiel zum Erstellen eines <xref:System.DateTime>- oder <xref:System.DateTimeOffset>-Werts verwendet wird, wird dieser Wert üblicherweise als gregorianisches Datum ausgedrückt. Dies liegt daran, dass die Typen <xref:System.DateTime> und <xref:System.DateTimeOffset> keine Kalenderinformationen beibehalten. Intern werden sie als Anzahl von Zeiteinheiten (Ticks) dargestellt, die seit Mitternacht des 1. Januar 0001 verstrichen sind. Die Interpretation dieser Zahl hängt vom Kalender ab. In den meisten Kulturen ist der Gregorianische Kalender der Standardkalender.
