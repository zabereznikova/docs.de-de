---
title: "Gewusst wie: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern | Microsoft Docs"
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
  - "Formatieren [.NET Framework], Datumsangaben"
  - "Datumsangaben [.NET Framework], Formatieren"
  - "Kalender [.NET Framework], Anzeigen von Datumsangaben"
  - "Anzeigen von Datums- und Uhrzeitdaten"
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Gewusst wie: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern
Der <xref:System.DateTime>\-Typ und der <xref:System.DateTimeOffset>\-Typ verwenden den gregorianischen Kalender als Standardkalender.  Durch Aufrufen der `ToString`\-Methode eines Datums\- oder Uhrzeitwerts werden also die Zeichenfolgendarstellung dieses Datums und dieser Uhrzeit im gregorianischen Kalender angezeigt, auch wenn Datum und Uhrzeit unter Verwendung eines anderen Kalenders erstellt wurden.  Dies wird im folgenden Beispiel veranschaulicht, in dem ein Datums\- und Uhrzeitwert auf der Grundlage des persischen Kalenders auf zwei unterschiedliche Weisen erstellt wird. Beim Aufrufen der <xref:System.DateTime.ToString%2A>\-Methode werden diese Datums\- und Uhrzeitwerte jedoch weiterhin im gregorianischen Kalender angezeigt.  In diesem Beispiel werden zwei gängige, aber falsche Verfahrensweisen zur Anzeige des Datums in einem bestimmten Kalender behandelt.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 Um das Datum in einem bestimmten Kalender anzuzeigen, können zwei unterschiedliche Verfahrensweisen verwendet werden.  Die erste erfordert, dass der Kalender der Standardkalender für eine bestimmte Kultur ist.  Die zweite kann mit einem beliebigen Kalender verwendet werden.  
  
### So zeigen Sie das Datum für den Standardkalender einer Kultur an  
  
1.  Instanziieren Sie ein von der <xref:System.Globalization.Calendar>\-Klasse abgeleitetes Kalenderobjekt, das den zu verwendenden Kalender darstellt.  
  
2.  Instanziieren Sie ein <xref:System.Globalization.CultureInfo>\-Objekt, das die Kultur darstellt, deren Formatierung zur Datumsanzeige verwendet wird.  
  
3.  Rufen Sie die <xref:System.Array.Exists%2A?displayProperty=fullName>\-Methode auf, um festzulegen, ob das Kalenderobjekt ein Member des von der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>\-Eigenschaft zurückgegebenen Arrays ist.  Dadurch wird angegeben, dass der Kalender als Standardkalender für das <xref:System.Globalization.CultureInfo>\-Objekt dienen kann.  Falls es sich um keinen Member des Arrays handelt, befolgen Sie die Anweisungen im Abschnitt "So zeigen Sie das Datum in einem beliebigen Kalender an".  
  
4.  Weisen Sie das Kalenderobjekt der <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A>\-Eigenschaft des von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>\-Eigenschaft zurückgegebenen <xref:System.Globalization.DateTimeFormatInfo>\-Objekts zu.  
  
    > [!NOTE]
    >  Die <xref:System.Globalization.CultureInfo>\-Klasse verfügt auch über eine <xref:System.Globalization.CultureInfo.Calendar%2A>\-Eigenschaft.  Diese ist jedoch schreibgeschützt und konstant. Sie wird nicht in Anpassung an den neuen Standardkalender geändert, der der <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName>\-Eigenschaft zugewiesen wird.  
  
5.  Rufen Sie entweder die <xref:System.DateTime.ToString%2A>\-Methode oder die <xref:System.DateTime.ToString%2A>\-Methode auf, und übergeben Sie ihr das <xref:System.Globalization.CultureInfo>\-Objekt, dessen Standardkalender im vorherigen Schritt geändert wurde.  
  
### So zeigen Sie das Datum in einem beliebigen Kalender an  
  
1.  Instanziieren Sie ein von der <xref:System.Globalization.Calendar>\-Klasse abgeleitetes Kalenderobjekt, das den zu verwendenden Kalender darstellt.  
  
2.  Legen Sie fest, welche Datums\- und Uhrzeitelemente in der Zeichenfolgendarstellung des Datums\- und Uhrzeitwerts angezeigt werden sollen.  
  
3.  Rufen Sie für jedes Datums\- und Uhrzeitelement, das Sie anzeigen möchten, die `Get`\-Methode des Kalenderobjekts auf.  Die folgenden Methoden stehen zur Verfügung:  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A> zur Anzeige des Jahres im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A> zur Anzeige des Monats im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A> zur Anzeige des Tages des Monats im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A> zur Anzeige der Stunde des Tages im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A> zur Anzeige der Minuten in der Stunde im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A> zur Anzeige der Sekunden in der Minute im entsprechenden Kalender.  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A> zur Anzeige der Millisekunden in der Sekunde im entsprechenden Kalender.  
  
## Beispiel  
 Im Beispiel wird ein Datum unter Verwendung zwei verschiedener Kalender angezeigt.  Sie sehen das Datum, nachdem der Hijri\-Kalender als Standardkalender für die Kultur ar\-JO festgelegt wurde, sowie das Datum auf Grundlage des persischen Kalenders, der von der Kultur fa\-IR nicht als optionaler Kalender unterstützt wird.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 Jedes <xref:System.Globalization.CultureInfo>\-Objekt kann einen oder mehrere Kalender unterstützen, die von der <xref:System.Globalization.CultureInfo.OptionalCalendars%2A>\-Eigenschaft angegeben werden.  Einer dieser Kalender wird als Standardkalender der Kultur festgelegt und von der schreibgeschützten <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben.  Ein anderer optionaler Kalender kann als Standardkalender festgelegt werden, indem ein <xref:System.Globalization.Calendar>\-Objekt zugewiesen wird, das diesen Kalender für die <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName>\-Eigenschaft darstellt, die von der <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName>\-Eigenschaft zurückgegeben wird.  Einige Kalender, wie der durch die <xref:System.Globalization.PersianCalendar>\-Klasse dargestellte persische Kalender, können jedoch nicht als optionale Kalender für beliebige Kulturen verwendet werden.  
  
 Im Beispiel wird die wiederverwendbare Kalender\-Dienstprogrammklasse `CalendarUtility` definiert, die viele der Details behandelt, die beim Erstellen der Zeichenfolgendarstellung eines Datums nach einem bestimmten Kalender eine Rolle spielen.  Die `CalendarUtility`\-Klasse verfügt über die folgenden Member:  
  
-   Ein parametrisierter Konstruktor, dessen einzelner Parameter einem <xref:System.Globalization.Calendar>\-Objekt entspricht, in dem ein Datum dargestellt werden soll.  Dieser wird einem privaten Feld der Klasse zugewiesen.  
  
-   `CalendarExists`, eine private Methode, die einen booleschen Wert zurückgibt, der angibt, ob der vom `CalendarUtility`\-Objekt dargestellte Kalender vom <xref:System.Globalization.CultureInfo>\-Objekt unterstützt wird, das als Parameter an die Methode übergeben wird.  Die Methode umschließt einen Aufruf der <xref:System.Array.Exists%2A?displayProperty=fullName>\-Methode, an die sie das <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName>\-Array übergibt.  
  
-   `HasSameName`, eine private Methode, die dem <xref:System.Predicate%601>\-Delegaten zugewiesen wird, der als Parameter an die <xref:System.Array.Exists%2A?displayProperty=fullName>\-Methode übergeben wird.  Jeder Member des Arrays wird so lange an die Methode übergeben, bis die Methode `true` zurückgibt.  Durch die Methode wird ermittelt, ob der Name eines optionalen Kalenders dem Kalendernamen entspricht, der vom `CalendarUtility`\-Objekt dargestellt wird.  
  
-   `DisplayDate`, eine überladene öffentliche Methode, an die zwei Parameter übergeben werden: entweder ein <xref:System.DateTime>\-Wert oder ein <xref:System.DateTimeOffset>\-Wert, der in dem vom `CalendarUtility`\-Objekt dargestellten Kalender ausgedrückt werden soll, sowie die Kultur, deren Formatierungsregeln verwendet werden sollen.  Das Verhalten bei der Rückgabe der Zeichenfolgendarstellung eines Datums hängt davon ab, ob der Zielkalender von der Kultur unterstützt wird, deren Formatierungsregeln verwendet werden sollen.  
  
 Unabhängig von dem Kalender, der zum Erstellen eines <xref:System.DateTime>\-Werts oder eines <xref:System.DateTimeOffset>\-Werts verwendet wird, wird der Wert in diesem Beispiel normalerweise als gregorianisches Datum ausgedrückt.  Dies liegt daran, dass der <xref:System.DateTime>\-Typ und der <xref:System.DateTimeOffset>\-Typ keine Kalenderinformationen beibehalten.  Intern entsprechen sie der Anzahl der Teilstriche, die seit dem 01. Januar 0001, Mitternacht, verstrichen sind.  Die Darstellung dieser Zahl hängt vom Kalender ab.  In den meisten Kulturen ist der Standardkalender der gregorianische Kalender.  
  
## Kompilieren des Codes  
 Für dieses Beispiel ist ein Verweis auf System.Core.dll erforderlich.  
  
 Kompilieren Sie den Code über csc.exe oder vb.exe in der Befehlszeile.  Um den Code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)