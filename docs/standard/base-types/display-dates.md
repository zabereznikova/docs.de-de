---
title: 'Gewusst wie: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern'
description: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 93f06e1d-544b-4ccc-a0b2-95cd674852cb
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 69a33b3e162c07a1d8a065a150c6db96f04334f6
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>Gewusst wie: Anzeigen von Datumsangaben in nicht gregorianischen Kalendern

Die Typen [DateTime](xref:System.DateTime) und [DateTimeOffset](xref:System.DateTimeOffset) verwenden den gregorianischen Kalender als Standardkalender. Das bedeutet, dass ein Aufruf der `ToString`-Methode eines Datums- und Uhrzeitwerts die Zeichenfolgendarstellung dieses Datums und dieser Uhrzeit im gregorianischen Kalender anzeigt, selbst wenn dieses Datum und diese Uhrzeit in einem anderen Kalender erstellt wurden. Dies wird im folgenden Beispiel veranschaulicht. Hierbei werden zwei verschiedene Möglichkeiten verwendet, um einen Datums- und Uhrzeitwert mit dem persischen Kalender zu erstellen. Beim Aufruf der [ToString](xref:System.DateTime.ToString)-Methode werden diese Datums- und Uhrzeitwerte aber weiterhin im gregorianischen Kalender angezeigt. Dieses Beispiel zeigt zwei häufig verwendete, aber falsche Verfahren zum Anzeigen des Datums in einem bestimmten Kalender.

```csharp
PersianCalendar persianCal = new PersianCalendar();

DateTime persianDate = persianCal.ToDateTime(1387, 3, 18, 12, 0, 0, 0);
Console.WriteLine(persianDate.ToString());

persianDate = new DateTime(1387, 3, 18, persianCal);
Console.WriteLine(persianDate.ToString());
// The example displays the following output to the console:
//       6/7/2008 12:00:00 PM
//       6/7/2008 12:00:00 AM
```

```vb
Dim persianCal As New PersianCalendar()

Dim persianDate As Date = persianCal.ToDateTime(1387, 3, 18, _
                                                12, 0, 0, 0)
Console.WriteLine(persianDate.ToString())

persianDate = New DateTime(1387, 3, 18, persianCal)
Console.WriteLine(persianDate.ToString())
' The example displays the following output to the console:
'       6/7/2008 12:00:00 PM
'       6/7/2008 12:00:00 AM
```

Zum Anzeigen des Datums in einem bestimmten Kalender können zwei verschiedene Verfahren verwendet werden. Für das erste Verfahren muss der Kalender der Standardkalender für eine bestimmte Kultur sein. Das zweite kann mit jedem beliebigen Kalender verwendet werden.

## <a name="to-display-the-date-for-a-cultures-default-calendar"></a>Anzeigen des Datums für den Standardkalender einer Kultur

1. Instanziieren Sie ein aus der [Calendar](xref:System.Globalization.Calendar)-Klasse abgeleitetes Kalenderobjekt, das den zu verwendenden Kalender darstellt.

2. Instanziieren Sie ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die Kultur darstellt, deren Formatierung für die Datumsanzeige verwendet wird.

3. Rufen Sie die [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0}))-Methode auf, um zu ermitteln, ob das Kalenderobjekt ein Member des von der [CultureInfo.OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars)-Eigenschaft zurückgegebenen Arrays ist. Wenn dies der Fall ist, kann der Kalender als Standardkalender für das [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt dienen. Wenn das Objekt kein Member des Arrays ist, befolgen Sie die Anweisungen im Abschnitt „Anzeigen des Datums in einem beliebigen Kalender“.

4. Weisen Sie das Kalenderobjekt der [Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar)-Eigenschaft des [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts zu, das von der [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat)-Eigenschaft zurückgegeben wird.

  > [!NOTE]
  > Die [CultureInfo](xref:System.Globalization.CultureInfo)-Klasse besitzt auch eine [Calendar](xref:System.Globalization.CultureInfo.Calendar)-Eigenschaft. Diese ist jedoch schreibgeschützt und konstant. Sie ändert sich nicht, um den neuen, der [DateTimeFormatInfo.Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar)-Eigenschaft zugewiesenen Standardkalender widerzuspiegeln.
  
5. Rufen Sie entweder die [DateTime.ToString(IFormatProvider)](xref:System.DateTime.ToString(System.IFormatProvider))-Methode oder die [DateTime.ToString(String,IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider))-Methode auf, und übergeben Sie das [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, dessen Standardkalender im vorherigen Schritt geändert wurde.

## <a name="to-display-the-date-in-any-calendar"></a>Anzeigen des Datums in einem beliebigen Kalender

1. Instanziieren Sie ein aus der [Calendar](xref:System.Globalization.Calendar)-Klasse abgeleitetes Kalenderobjekt, das den zu verwendenden Kalender darstellt.

2. Bestimmen Sie, welche Datums- und Uhrzeitelemente in der Zeichenfolgendarstellung des Datums- und Uhrzeitwerts angezeigt werden sollen.

3. Rufen Sie für jedes Datums- und Uhrzeitelement, das Sie anzeigen möchten, die `Get…`-Methode des Kalenderobjekts auf. Die folgenden Methoden sind verfügbar:

    * [GetYear](xref:System.Globalization.Calendar.GetYear(System.DateTime)) zum Anzeigen des Jahrs im entsprechenden Kalender.
    
    * [GetMonth](xref:System.Globalization.Calendar.GetMonth(System.DateTime)) zum Anzeigen des Monats im entsprechenden Kalender. 
    
    * [GetDayOfMonth](xref:System.Globalization.Calendar.GetDayOfMonth(System.DateTime)) zum Anzeigen der Zahl, die dem Tag des Monats im entsprechenden Kalender entspricht.
    
    * [GetHour](xref:System.Globalization.Calendar.GetHour(System.DateTime)) zum Anzeigen der Stunde des Tages im entsprechenden Kalender.
    
    * [GetMinute](xref:System.Globalization.Calendar.GetMinute(System.DateTime)) zum Anzeigen der Minuten in der Stunde im entsprechenden Kalender.
    
    * [GetSecond](xref:System.Globalization.Calendar.GetSecond(System.DateTime)) zum Anzeigen der Sekunden in der Minute im entsprechenden Kalender. 
    
    * [GetMilliseconds](xref:System.Globalization.Calendar.GetMilliseconds(System.DateTime)) zum Anzeigen der Millisekunden in der Sekunde im entsprechenden Kalender.
    
## <a name="example"></a>Beispiel
    
Das Beispiel zeigt ein Datum mithilfe von zwei verschiedenen Kalendern an. Es zeigt das Datum an, nachdem der Hijri-Kalender als Standardkalender für die Kultur „ar-JO“ definiert wurde, und es zeigt das Datum unter Verwendung des persischen Kalenders an, der nicht als optionaler Kalender von der fa-IR-Kultur unterstützt wird.

```csharp
using System;
using System.Globalization;

public class CalendarDates
{
   public static void Main()
   {
      HijriCalendar hijriCal = new HijriCalendar();
      CalendarUtility hijriUtil = new CalendarUtility(hijriCal);
      DateTime dateValue1 = new DateTime(1429, 6, 29, hijriCal);
      DateTimeOffset dateValue2 = new DateTimeOffset(dateValue1, 
                                  TimeZoneInfo.Local.GetUtcOffset(dateValue1));
      CultureInfo jc = CultureInfo.CreateSpecificCulture("ar-JO");

      // Display the date using the Gregorian calendar.
      Console.WriteLine("Using the system default culture: {0}", 
                        dateValue1.ToString("d"));
      // Display the date using the ar-JO culture's original default calendar.
      Console.WriteLine("Using the ar-JO culture's original default calendar: {0}", 
                        dateValue1.ToString("d", jc));
      // Display the date using the Hijri calendar.
      Console.WriteLine("Using the ar-JO culture with Hijri as the default calendar:");
      // Display a Date value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue1, jc));
      // Display a DateTimeOffset value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue2, jc));

      Console.WriteLine();

      PersianCalendar persianCal = new PersianCalendar();
      CalendarUtility persianUtil = new CalendarUtility(persianCal);
      CultureInfo ic = CultureInfo.CreateSpecificCulture("fa-IR");

      // Display the date using the ir-FA culture's default calendar.
      Console.WriteLine("Using the ir-FA culture's default calendar: {0}",       
                        dateValue1.ToString("d", ic));
      // Display a Date value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue1, ic));
      // Display a DateTimeOffset value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue2, ic));
   }
}

public class CalendarUtility
{
   private Calendar thisCalendar;
   private CultureInfo targetCulture;

   public CalendarUtility(Calendar cal)
   {
      this.thisCalendar = cal;
   }

   private bool CalendarExists(CultureInfo culture)
   {
      this.targetCulture = culture;
      return Array.Exists(this.targetCulture.OptionalCalendars, 
                          this.HasSameName);
   }

   private bool HasSameName(Calendar cal)
   {
      if (cal.ToString() == thisCalendar.ToString())
         return true;
      else
         return false;
   }

   public string DisplayDate(DateTime dateToDisplay, CultureInfo culture)
   {
      DateTimeOffset displayOffsetDate = dateToDisplay;
      return DisplayDate(displayOffsetDate, culture);
   }

   public string DisplayDate(DateTimeOffset dateToDisplay, 
                             CultureInfo culture)
   {
      string specifier = "yyyy/MM/dd";

      if (this.CalendarExists(culture))
      {
         Console.WriteLine("Displaying date in supported {0} calendar...", 
                           this.thisCalendar.GetType().Name);
         culture.DateTimeFormat.Calendar = this.thisCalendar;
         return dateToDisplay.ToString(specifier, culture);
      }
      else
      {
         Console.WriteLine("Displaying date in unsupported {0} calendar...", 
                           thisCalendar.GetType().Name);

         string separator = targetCulture.DateTimeFormat.DateSeparator;

         return thisCalendar.GetYear(dateToDisplay.DateTime).ToString("0000") +
                separator +
                thisCalendar.GetMonth(dateToDisplay.DateTime).ToString("00") + 
                separator +
                thisCalendar.GetDayOfMonth(dateToDisplay.DateTime).ToString("00"); 
      }
   } 
}
// The example displays the following output to the console:
//       Using the system default culture: 7/3/2008
//       Using the ar-JO culture's original default calendar: 03/07/2008
//       Using the ar-JO culture with Hijri as the default calendar:
//       Displaying date in supported HijriCalendar calendar...
//       1429/06/29
//       Displaying date in supported HijriCalendar calendar...
//       1429/06/29
//       
//       Using the ir-FA culture's default calendar: 7/3/2008
//       Displaying date in unsupported PersianCalendar calendar...
//       1387/04/13
//       Displaying date in unsupported PersianCalendar calendar...
//       1387/04/13
```

```vb
Imports System.Globalization

Public Class CalendarDates
   Public Shared Sub Main()
      Dim hijriCal As New HijriCalendar()
      Dim hijriUtil As New CalendarUtility(hijriCal)
      Dim dateValue1 As Date = New Date(1429, 6, 29, hijriCal)
      Dim dateValue2 As DateTimeOffset = New DateTimeOffset(dateValue1, _
                                         TimeZoneInfo.Local.GetUtcOffset(dateValue1))
      Dim jc As CultureInfo = CultureInfo.CreateSpecificCulture("ar-JO")

      ' Display the date using the Gregorian calendar.
      Console.WriteLine("Using the system default culture: {0}", _
                        dateValue1.ToString("d"))
      ' Display the date using the ar-JO culture's original default calendar.
      Console.WriteLine("Using the ar-JO culture's original default calendar: {0}", _
                        dateValue1.ToString("d", jc))
      ' Display the date using the Hijri calendar.
      Console.WriteLine("Using the ar-JO culture with Hijri as the default calendar:")
      ' Display a Date value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue1, jc))
      ' Display a DateTimeOffset value.
      Console.WriteLine(hijriUtil.DisplayDate(dateValue2, jc))

      Console.WriteLine()

      Dim persianCal As New PersianCalendar()
      Dim persianUtil As New CalendarUtility(persianCal)
      Dim ic As CultureInfo = CultureInfo.CreateSpecificCulture("fa-IR")

      ' Display the date using the ir-FA culture's default calendar.
      Console.WriteLine("Using the ir-FA culture's default calendar: {0}", _      
                        dateValue1.ToString("d", ic))
      ' Display a Date value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue1, ic))
      ' Display a DateTimeOffset value.
      Console.WriteLine(persianUtil.DisplayDate(dateValue2, ic))
   End Sub
End Class

Public Class CalendarUtility
   Private thisCalendar As Calendar
   Private targetCulture As CultureInfo

   Public Sub New(cal As Calendar)
      Me.thisCalendar = cal
   End Sub

   Private Function CalendarExists(culture As CultureInfo) As Boolean
      Me.targetCulture = culture
      Return Array.Exists(Me.targetCulture.OptionalCalendars, _
                          AddressOf Me.HasSameName)
   End Function 

   Private Function HasSameName(cal As Calendar) As Boolean
      If cal.ToString() = thisCalendar.ToString() Then
         Return True
      Else
         Return False
      End If
   End Function

   Public Function DisplayDate(dateToDisplay As Date, _
                               culture As CultureInfo) As String
      Dim displayOffsetDate As DateTimeOffset = dateToDisplay
      Return DisplayDate(displayOffsetDate, culture)
   End Function

   Public Function DisplayDate(dateToDisplay As DateTimeOffset, _
                               culture As CultureInfo) As String
      Dim specifier As String = "yyyy/MM/dd"

      If Me.CalendarExists(culture) Then
         Console.WriteLine("Displaying date in supported {0} calendar...", _
                           thisCalendar.GetType().Name)
         culture.DateTimeFormat.Calendar = Me.thisCalendar
         Return dateToDisplay.ToString(specifier, culture)
      Else
         Console.WriteLine("Displaying date in unsupported {0} calendar...", _
                           thisCalendar.GetType().Name)

         Dim separator As String = targetCulture.DateTimeFormat.DateSeparator

         Return thisCalendar.GetYear(dateToDisplay.DateTime).ToString("0000") & separator & _
                thisCalendar.GetMonth(dateToDisplay.DateTime).ToString("00") & separator & _
                thisCalendar.GetDayOfMonth(dateToDisplay.DateTime).ToString("00") 
      End If             
   End Function
End Class
' The example displays the following output to the console:
'       Using the system default culture: 7/3/2008
'       Using the ar-JO culture's original default calendar: 03/07/2008
'       Using the ar-JO culture with Hijri as the default calendar:
'       Displaying date in supported HijriCalendar calendar...
'       1429/06/29
'       Displaying date in supported HijriCalendar calendar...
'       1429/06/29
'       
'       Using the ir-FA culture's default calendar: 7/3/2008
'       Displaying date in unsupported PersianCalendar calendar...
'       1387/04/13
'       Displaying date in unsupported PersianCalendar calendar...
'       1387/04/13
```

Jedes [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt kann mindestens einen Kalender unterstützen, die von der [OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars)-Eigenschaft angegeben werden. Einer dieser Kalender ist als Standardkalender der Kultur festgelegt und wird von der schreibgeschützten [CultureInfo.Calendar](xref:System.Globalization.CultureInfo.Calendar)-Eigenschaft zurückgegeben. Ein anderer der optionalen Kalender kann als Standard festgelegt werden, indem ein [Calendar](xref:System.Globalization.Calendar)-Objekt zugewiesen wird, das diesen Kalender für die [DateTimeFormatInfo.Calendar](xref:System.Globalization.DateTimeFormatInfo.Calendar)-Eigenschaft darstellt, die von der [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat)-Eigenschaft zurückgegeben wird. Einige Kalender jedoch, wie z.B. der von der [PersianCalendar](xref:System.Globalization.PersianCalendar)-Klasse dargestellte persische Kalender, dienen nicht als optionale Kalender für irgendeine Kultur.   

Das Beispiel definiert eine wiederverwendbare Kalenderhilfsprogrammklasse, `CalendarUtility`, um viele der Details beim Generieren der Zeichenfolgendarstellung eines Datums mithilfe eines bestimmten Kalenders zu verarbeiten. Die `CalendarUtility`-Klasse verfügt über die folgenden Member: 

* Einen parametrisierten Konstruktor, dessen einziger Parameter ein [Calendar](xref:System.Globalization.Calendar)-Objekt ist, in dem ein Datum dargestellt werden soll. Dieser wird einem privaten Klassenfeld zugewiesen.

* `CalendarExists`, eine private Methode, die einen booleschen Wert zurückgibt, um anzugeben, ob der durch das `CalendarUtility`-Objekt dargestellte Kalender von dem [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt unterstützt wird, das als Parameter an die Methode übergeben wird. Die Methode umschließt einen Aufruf der [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0}))-Methode und übergibt dieser das [CultureInfo.OptionalCalendars](xref:System.Globalization.CultureInfo.OptionalCalendars)-Array.

* `HasSameName`, eine dem [Predicate&lt;T&gt;](xref:System.Predicate%601)-Delegaten zugeordnete private Methode, die als Parameter an die [Array.Exists&lt;T&gt;](xref:System.Array.Exists``1(``0[],System.Predicate{``0}))-Methode übergeben wird. Jeder Member des Arrays wird an die Methode übergeben, bis die Methode `true` zurückgibt. Die Methode bestimmt, ob der Name eines optionalen Kalenders dem Kalender entspricht, der durch das `CalendarUtility`-Objekt dargestellt wird.

* `DisplayDate`, eine überladene öffentliche Methode, an die zwei Parameter übergeben werden: erstens entweder ein [DateTime](xref:System.DateTime)- oder ein [DateTimeOffset-Wert](xref:System.DateTimeOffset), der in dem durch das `CalendarUtility`-Objekt dargestellten Kalender ausgedrückt werden soll. Zweitens wird die Kultur übergeben, deren Formatierungsregeln verwendet werden sollen. Das Verhalten bei der Rückgabe der Zeichenfolgendarstellung eines Datums richtet sich danach, ob der Zielkalender von der Kultur unterstützt wird, deren Formatierungsregeln verwendet werden sollen.

Unabhängig von dem Kalender, der in diesem Beispiel zum Erstellen eines [DateTime](xref:System.DateTime)- oder [DateTimeOffset](xref:System.DateTimeOffset)-Werts verwendet wird, wird dieser Wert üblicherweise als Gregorianisches Datum ausgedrückt. Dies liegt daran, dass die Typen [DateTime](xref:System.DateTime) und [DateTimeOffset](xref:System.DateTimeOffset) keine Kalenderinformationen beibehalten. Intern werden sie als Anzahl von Zeiteinheiten (Ticks) dargestellt, die seit Mitternacht des 1. Januar 0001 verstrichen sind. Die Interpretation dieser Zahl hängt vom Kalender ab. In den meisten Kulturen ist der Gregorianische Kalender der Standardkalender. 

## <a name="see-also"></a>Siehe auch

[Durchführen von Formatierungsvorgängen](performing-formatting-operations.md)

