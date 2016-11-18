---
title: "Standardformatzeichenfolgen für Datum und Uhrzeit"
description: "Standardformatzeichenfolgen für Datum und Uhrzeit"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: be239871-10cc-4949-b548-200bb260630a
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 56da9671a0849b0f0a94d8881cdc28e70bcf8549

---

# <a name="standard-date-and-time-format-strings"></a>Standardformatzeichenfolgen für Datum und Uhrzeit

Eine standardmäßige Formatzeichenfolge für Datum und Uhrzeit verwendet einen einzelnen Formatbezeichner, um die Textdarstellung eines Datums- und Uhrzeitwerts zu definieren. Jede Formatzeichenfolge für Datum und Uhrzeit, die mehr als ein Zeichen (einschließlich Leerzeichen) enthält, wird als benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit interpretiert. Weitere Informationen finden Sie unter [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md). Eine standardmäßige oder benutzerdefinierte Formatzeichenfolge kann auf zwei Arten verwendet werden:

* Zum Definieren der Zeichenfolge, die das Ergebnis eines Formatierungsvorgangs ist.

* Zum Definieren der Textdarstellung eines Datums- und Uhrzeitwerts, der bei einem Analysevorgang in einen [DateTime](xref:System.DateTime)- oder einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert konvertiert werden kann.

Standardformatzeichenfolgen für Datum und Uhrzeit können sowohl mit dem [DateTime](xref:System.DateTime)-Wert als auch mit dem [DateTimeOffset](xref:System.DateTimeOffset)-Wert verwendet werden. 

In der folgenden Tabelle werden die Standardformatbezeichner für Datum und Uhrzeit beschrieben. Sofern nicht anders angegeben, erzeugt ein bestimmter Standardformatbezeichner für Datum und Uhrzeit eine identische Zeichenfolgendarstellung, unabhängig davon, ob er mit einem [DateTime](xref:System.DateTime)-Wert oder einem [DateTimeOffset](xref:System.DateTimeOffset)-Wert verwendet wird. Weitere Informationen zum Verwenden von standardmäßigen Formatzeichenfolgen für Datum und Uhrzeit finden Sie im Abschnitt [Hinweise](#notes).

Formatbezeichner | Beschreibung | Beispiele
---------------- | ----------- | --------
"d" | Kurzes Datumsmuster. | `2009-06-15T13:45:30 -> 6/15/2009 (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)`; `2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)`
"D" | Langes Datumsmuster. | `2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)`; `2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)`; `2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)`
"f" | Vollständiges Datums-/Zeitmuster (kurze Zeit). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)`
"F" | Vollständiges Datums-/Zeitmuster (lange Zeit). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)`
"g" | Allgemeines Datums-/Zeitmuster (kurze Zeit). | `2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)`; `2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)`
"G" | Allgemeines Datums-/Zeitmuster (lange Zeit). | `2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)`; `2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)`
„M“, „m“ | Monatstagmuster. | `2009-06-15T13:45:30 -> June 15 (en-US)`; `2009-06-15T13:45:30 -> 15. juni (da-DK)`; `2009-06-15T13:45:30 -> 15 Juni (id-ID)`
"O", "o" | Zurückkonvertieren von Datums-/Zeitmuster. | [DateTime](xref:System.DateTime)-Werte: `2009-06-15T13:45:30 (DateTimeKind.Local) --> 2009-06-15T13:45:30.0000000-07:00`; `2009-06-15T13:45:30 (DateTimeKind.Utc) --> 2009-06-15T13:45:30.0000000Z`; `2009-06-15T13:45:30 (DateTimeKind.Unspecified) --> 2009-06-15T13:45:30.0000000`. [DateTimeOffset](xref:System.DateTimeOffset)-Werte: `2009-06-15T13:45:30-07:00 --> 2009-06-15T13:45:30.0000000-07:00`
"R", "r" | RFC1123-Muster. | `2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT`
"s" | Sortierbares Datums-/Zeitmuster. | `2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30`; `2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30`
"t" | Kurzes Zeitmuster. | `2009-06-15T13:45:30 -> 1:45 PM (en-US)`; `2009-06-15T13:45:30 -> 13:45 (hr-HR)`; `2009-06-15T13:45:30 -> 01:45 م (ar-EG)` 
"T" | Langes Zeitmuster. | `2009-06-15T13:45:30 -> 1:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> 13:45:30 (hr-HR)`; `2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)`
"u" | Universelles, sortierbares Datums-/Zeitmuster. | Mit einem [DateTime](xref:System.DateTime)-Wert: `2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z`. Mit einem [DateTimeOffset](xref:System.DateTimeOffset)-Wert: `2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z`
"U" | Universelles Datums-/Zeitmuster (Koordinierte Weltzeit). | `2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)`; `2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)`; `2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)`
"Y", "y" | Jahr-Monat-Muster. | `2009-06-15T13:45:30 -> June, 2009 (en-US)`; `2009-06-15T13:45:30 -> juni 2009 (da-DK)`; `2009-06-15T13:45:30 -> Juni 2009 (id-ID)`
Jedes andere einzelne Zeichen | Unbekannter Bezeichner. | Löst zur Laufzeit eine [FormatException](xref:System.FormatException) aus.

## <a name="how-standard-format-strings-work"></a>Funktionsweise der Standardformatzeichenfolgen

Bei einem Formatierungsvorgang ist eine Standardformatzeichenfolge lediglich ein Alias für eine benutzerdefinierte Formatzeichenfolge. Die Verwendung eines Alias, der auf eine benutzerdefinierte Formatzeichenfolge verweist, hat den Vorteil, dass der Alias unveränderlich bleibt, während die benutzerdefinierte Formatzeichenfolge selbst variieren kann. Dies ist wichtig, da sich die Zeichenfolgenentsprechungen von Datums- und Uhrzeitwerten i. d. R. abhängig von der Kultur unterscheiden. So gibt beispielsweise die Standardformatzeichenfolge "d" an, dass der Datums- und Uhrzeitwert in einem kurzen Datumsmuster angezeigt wird. Für die invariante Kultur lautet dieses Muster "MM/dd/yyyy". Für die Kultur fr-FR lautet es "dd/MM/yyyy". Für die Kultur ja-JP lautet es "yyyy/MM/dd".

Wenn eine Standardformatzeichenfolge in einem Formatierungsvorgang der benutzerdefinierte Formatzeichenfolge einer bestimmten Kultur zugeordnet wird, kann die Anwendung eine bestimmte Kultur definieren, deren benutzerdefinierte Formatzeichenfolgen auf eine der folgenden Weisen verwendet werden:

* Sie können die Standardkultur (die aktuelle Kultur) verwenden. Das folgende Beispiel zeigt ein Datum unter Verwendung des kurzen Datumsformat der aktuellen Kultur an. In diesem Fall ist die aktuelle Kultur en-US. 

  ```csharp
  // Display using current (en-us) culture's short date format
  DateTime thisDate = new DateTime(2008, 3, 15);
  Console.WriteLine(thisDate.ToString("d"));           // Displays 3/15/2008
  ```

  ```vb
  ' Display using current (en-us) culture's short date format
  Dim thisDate As Date = #03/15/2008#
  Console.WriteLine(thisDate.ToString("d"))     ' Displays 3/15/2008
  ```
  
* Sie können ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt, das die Kultur darstellt, deren Formatierung verwendet werden soll, an eine Methode mit einem [IFormatProvider](xref:System.IFormatProvider)-Parameter übergeben. Das folgenden Beispiel zeigt ein Datum unter Verwendung des kurzen Datumsformat der Kultur pt-BR an.
  
  ```csharp
  // Display using pt-BR culture's short date format
  DateTime thisDate = new DateTime(2008, 3, 15);
  CultureInfo culture = new CultureInfo("pt-BR");      
  Console.WriteLine(thisDate.ToString("d", culture));  // Displays 15/3/2008
  ```

  ```vb
  ' Display using pt-BR culture's short date format
  Dim thisDate As Date = #03/15/2008#
  Dim culture As New CultureInfo("pt-BR")      
  Console.WriteLine(thisDate.ToString("d", culture))   ' Displays 15/3/2008
  ```
  
* Sie können ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, das Formatierungsinformationen liefert, an eine Methode mit einem [IFormatProvider](xref:System.IFormatProvider)-Parameter übergeben. Das folgenden Beispiel zeigt ein Datum unter Verwendung des kurzen Datumsformats aus einem DateTimeFormatInfo-Objekt für die hr-HR-Kultur an.  

  ```csharp
  // Display using date format information from hr-HR culture
  DateTime thisDate = new DateTime(2008, 3, 15);
  DateTimeFormatInfo fmt = (new CultureInfo("hr-HR")).DateTimeFormat;
  Console.WriteLine(thisDate.ToString("d", fmt));      // Displays 15.3.2008
  ```

  ```vb
  ' Display using date format information from hr-HR culture
  Dim thisDate As Date = #03/15/2008#
  Dim fmt As DateTimeFormatInfo = (New CultureInfo("hr-HR")).DateTimeFormat
  Console.WriteLine(thisDate.ToString("d", fmt))   ' Displays 15.3.2008
  ```
  
In einigen Fällen dient die Standardformatzeichenfolge als praktische Abkürzung für eine längere benutzerdefinierte Formatzeichenfolge, die unveränderlich ist. Vier Standardformatzeichenfolgen fallen in diese Kategorie: "O" (oder "o"), "R" (oder "r"), "s" und "u". Diese Zeichenfolgen entsprechen benutzerdefinierten Formatzeichenfolgen, die durch die invariante Kultur definiert werden. Sie erzeugen Zeichenfolgenentsprechungen von Datums- und Uhrzeitwerten, die über Kulturen hinweg identisch sein sollen. In der folgenden Tabelle werden Informationen über dieses vier Standardformatzeichenfolgen für Datum und Uhrzeit bereitgestellt.

Standardformatzeichenfolge | Definiert durch die DateTimeFormatInfo.InvariantInfo-Eigenschaft | Benutzerdefinierte Formatzeichenfolge
---------------------- | ---------------------------------------------------- | --------------------
"O" oder "o" | Keine | yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzz
"R" oder "r" | [RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern) | ddd, dd MMM yyyy HH':'mm':'ss 'GMT'
"s" | [SortableDateTime](xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern) | yyyy'-'MM'-'dd'T'HH':'mm':'ss
"u" | [UniversalSortableDateTime](xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern) | yyyy'-'MM'-'dd HH':'mm':'ss'Z'

In den folgenden Abschnitten werden die Standardformatbezeichner für den [DateTime](xref:System.DateTime)-Wert und den [DateTimeOffset](xref:System.DateTimeOffset)-Wert beschrieben.

## <a name="the-short-date-d-format-specifier"></a>Der Formatbezeichner „d“ für kurzes Datum

Der Standardformatbezeichner „d“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern)-Eigenschaft einer bestimmten Kultur definiert wird. Die benutzerdefinierte Formatzeichenfolge, die von der [ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern)-Eigenschaft der invarianten Kultur zurückgegeben wird, lautet beispielsweise „MM/dd/yyyy“. 

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.
Im folgenden Beispiel wird der d-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008,4, 10);
Console.WriteLine(date1.ToString("d", DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays 4/10/2008                       
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("en-NZ")));
// Displays 10/04/2008                       
Console.WriteLine(date1.ToString("d", 
                  CultureInfo.CreateSpecificCulture("de-DE")));
// Displays 10.04.2008 
```

```vb
Dim date1 As Date = #4/10/2008#
Console.WriteLine(date1.ToString("d", DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays 4/10/2008                       
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("en-NZ")))
' Displays 10/04/2008                       
Console.WriteLine(date1.ToString("d", _
                  CultureInfo.CreateSpecificCulture("de-DE")))
' Displays 10.04.2008 
```

## <a name="the-long-date-d-format-specifier"></a>Der Formatbezeichner „D“ für langes Datum

Der Standardformatbezeichner „D“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die aktuelle [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern)-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "dddd, dd MMMM yyyy".

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

Eigenschaft | Beschreibung
-------- | -----------
[LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) | Definiert das Gesamtformat der Ergebniszeichenfolge.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.

Im folgenden Beispiel wird der D-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10);
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008                        
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("pt-BR")));
// Displays quinta-feira, 10 de abril de 2008                        
Console.WriteLine(date1.ToString("D", 
                  CultureInfo.CreateSpecificCulture("es-MX")));
// Displays jueves, 10 de abril de 2008
```

```vb
Dim date1 As Date = #4/10/2008#
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008                        
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("pt-BR")))
' Displays quinta-feira, 10 de abril de 2008                        
Console.WriteLine(date1.ToString("D", _
                  CultureInfo.CreateSpecificCulture("es-MX")))
' Displays jueves, 10 de abril de 2008
```

## <a name="the-full-date-short-time-f-format-specifier"></a>Der Formatbezeichner „f“ für vollständiges Datum und kurze Zeit

Der Standardformatbezeichner "f" stellt eine Kombination aus dem Muster für langes Datum ("D") und dem Muster für kurze Zeit ("t") getrennt durch ein Leerzeichen dar.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der benutzerdefinierte Formatbezeichner, der von der [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern)-Eigenschaft und der [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern)-Eigenschaft einiger Kulturen zurückgegeben wird, nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) | Definiert das Format der Datumskomponente der Ergebniszeichenfolge.
[ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Im folgenden Beispiel wird der f-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("f", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 6:30 AM                        
Console.WriteLine(date1.ToString("f", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays jeudi 10 avril 2008 06:30 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("f", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 6:30 AM                        
Console.WriteLine(date1.ToString("f", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays jeudi 10 avril 2008 06:30 
```

## <a name="the-full-date-long-time-f-format-specifier"></a>Der Formatbezeichner „F“ für vollständiges Datum und lange Zeit

Der Standardformatbezeichner „F“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die aktuelle [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern)-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "dddd, dd MMMM yyyy HH:mm:ss".

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der [FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern)-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) | Definiert das Gesamtformat der Ergebniszeichenfolge.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Im folgenden Beispiel wird der F-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("F", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("F", 
                  CultureInfo.CreateSpecificCulture("fr-FR")));
// Displays jeudi 10 avril 2008 06:30:00 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("F", _
                  CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("F", _
                  CultureInfo.CreateSpecificCulture("fr-FR")))
' Displays jeudi 10 avril 2008 06:30:00 
```

## <a name="the-general-date-short-time-g-format-specifier"></a>Der Formatbezeichner „g“ für allgemeines Datum und kurze Zeit

Der Standardformatbezeichner "g" stellt eine Kombination aus dem Muster für kurzes Datum ("d") und dem Muster für kurze Zeit ("t") getrennt durch ein Leerzeichen dar.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der benutzerdefinierte Formatbezeichner, der von der [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern)-Eigenschaft und der [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern)-Eigenschaft einiger Kulturen zurückgegeben wird, nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) | Definiert das Format der Datumskomponente der Ergebniszeichenfolge.
[ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Im folgenden Beispiel wird der g-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen. 

``` csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("g", 
                  DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008 06:30                      
Console.WriteLine(date1.ToString("g", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 4/10/2008 6:30 AM                       
Console.WriteLine(date1.ToString("g", 
                  CultureInfo.CreateSpecificCulture("fr-BE")));
// Displays 10/04/2008 6:30 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("g", _
                  DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008 06:30                      
Console.WriteLine(date1.ToString("g", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 4/10/2008 6:30 AM                       
Console.WriteLine(date1.ToString("g", _
                  CultureInfo.CreateSpecificCulture("fr-BE")))
' Displays 10/04/2008 6:30  
```

## <a name="the-general-date-long-time-g-format-specifier"></a>Der Formatbezeichner „G“ für allgemeines Datum und lange Zeit

Der Standardformatbezeichner "G" stellt eine Kombination aus dem Muster für kurzes Datum ("d") und dem Muster für lange Zeit ("T") getrennt durch ein Leerzeichen dar.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der benutzerdefinierte Formatbezeichner, der von der [DateTimeFormatInfo.ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern)-Eigenschaft und der [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern)-Eigenschaft einiger Kulturen zurückgegeben wird, nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[ShortDatePattern](xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern) | Definiert das Format der Datumskomponente der Ergebniszeichenfolge.
[LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) | Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Im folgenden Beispiel wird der G-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("G", 
                  DateTimeFormatInfo.InvariantInfo));
// Displays 04/10/2008 06:30:00
Console.WriteLine(date1.ToString("G", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 4/10/2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("G", 
                  CultureInfo.CreateSpecificCulture("nl-BE")));
// Displays 10/04/2008 6:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("G", _
                  DateTimeFormatInfo.InvariantInfo))
' Displays 04/10/2008 06:30:00
Console.WriteLine(date1.ToString("G", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 4/10/2008 6:30:00 AM                        
Console.WriteLine(date1.ToString("G", _
                  CultureInfo.CreateSpecificCulture("nl-BE")))
' Displays 10/04/2008 6:30:00                       
```

## <a name="the-month-m-m-format-specifier"></a>Die Formatbezeichner „M“, „m“ für Monat

Der Standardformatbezeichner „M“ oder „m“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die aktuelle [DateTimeFormatInfo.MonthDayPattern](xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern)-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "MMMM dd".

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

Eigenschaft | Beschreibung
-------- | -----------
[MonthDayPattern](xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern) | Definiert das Gesamtformat der Ergebniszeichenfolge.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.

Im folgenden Beispiel wird der m-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("m", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays April 10                        
Console.WriteLine(date1.ToString("m", 
                  CultureInfo.CreateSpecificCulture("ms-MY")));
// Displays 10 April  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("m", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays April 10                        
Console.WriteLine(date1.ToString("m", _
                  CultureInfo.CreateSpecificCulture("ms-MY")))
' Displays 10 April
```

## <a name="the-roundtrip-o-o-format-specifier"></a>Die Formatbezeichner „O“, „o“ für Roundtrips

Der Standardformatbezeichner "O" oder "o" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit unter Verwendung eines Musters dar, bei dem die Zeitzoneninformationen beibehalten werden, und gibt eine Ergebniszeichenfolge aus, die die Anforderungen von ISO 8601 erfüllt. Für [DateTime](xref:System.DateTime)-Werte wurde diese Formatzeichenfolge entwickelt, um Datums- und Uhrzeitwerte zusammen mit der [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft in Text beizubehalten. Die formatierte Zeichenfolge kann mithilfe der Methoden [DateTime.Parse(String, IFormatProvider, DateTimeStyles)](xref:System.DateTime.Parse(System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) oder [DateTime.ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles)) analysiert werden, wenn der styles-Parameter auf [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) festgelegt ist. 

Der Standardformatbezeichner „O“ oder „o“ entspricht der benutzerdefinierten Formatzeichenfolge „yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK“ für DateTime-Werte und der benutzerdefinierten Formatzeichenfolge „yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzzz“ für [DateTimeOffset](xref:System.DateTimeOffset)-Werte. In dieser Zeichenfolge signalisieren die einfachen Anführungszeichen, die einzelne Zeichen wie Bindestriche, Doppelpunkte oder den Buchstaben "T" begrenzen, dass das einzelne Zeichen ein Literal ist, das nicht geändert werden kann. Die Anführungszeichen werden nicht in der Ausgabezeichenfolge angezeigt. 

Der Standardformatbezeichner „O“ oder „o“ (und die benutzerdefinierte Formatzeichenfolge „yyyy'-'MM'-'dd'T'HH':'mm':'ss'.fffffffK“) nutzt die drei Methoden, mit denen ISO 8601 Zeitzoneninformationen darstellt, um die [Kind](xref:System.DateTime.Kind)-Eigenschaft von [DateTime](xref:System.DateTime)-Werten beizubehalten: 

* Die Zeitzonenkomponente der [DateTimeKind.Local](xref:System.DateTimeKind.Local)-Datums- und Uhrzeitwerte ist eine Abweichung von der UTC (z.B. +01:00, -07:00). Alle DateTimeOffset-Werte werden auch in diesem Format dargestellt. 

* Die Zeitzonenkomponente der [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)-Datums- und Uhrzeitwerte verwendet „Z“ (keine Abweichung), um die UTC darzustellen. 

* [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)-Datums- und Uhrzeitwerte enthalten keine Zeitzoneninformationen. 

Da der Standardformatbezeichner "O" oder "o" einem internationalen Standard entspricht, nutzt der Formatierungs- oder Analysevorgang, der den Bezeichner verwendet, stets die invariante Kultur und den gregorianischen Kalender. 

Zeichenfolgen, die an die `Parse`-, `TryParse`-, `ParseExact`- und `TryParseExact`-Methoden von [DateTime](xref:System.DateTime) und [DateTimeOffset](xref:System.DateTimeOffset) übergeben werden, können mit dem Formatbezeichner „O“ oder „o“ analysiert werden, wenn sie in einem dieser Formate vorliegen. Bei [DateTime](xref:System.DateTime)-Objekten sollte die Analyseüberladung, die Sie aufrufen, auch einen styles-Parameter mit einem Wert von [DateTimeStyles.RoundtripKind](xref:System.Globalization.DateTimeStyles.RoundtripKind) enthalten. Beachten Sie, dass Sie durch Aufrufen einer Analysemethode mit der benutzerdefinierten Formatzeichenfolge, die dem Formatbezeichner "O" oder "o" entspricht, nicht die gleichen Ergebnisse wie "O" oder "o" erhalten. Der Grund dafür ist, dass Analysemethoden, die benutzerdefinierte Formatzeichenfolgen verwenden, die Zeichenfolgendarstellung von Datums- und Zeitwerten nicht analysieren können, wenn diese keine Zeitzonenkomponente enthalten oder "Z" zur Angabe von UTC verwenden. 

Im folgenden Beispiel wird der Formatbezeichner „o“ verwendet, um eine Reihe von [DateTime](xref:System.DateTime)-Werten und einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert in einem System in der Zeitzone Pacific anzuzeigen. 

```csharp
using System;

public class Example
{
   public static void Main()
   {
       DateTime dat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                   DateTimeKind.Unspecified);
       Console.WriteLine("{0} ({1}) --> {0:O}", dat, dat.Kind); 

       DateTime uDat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                    DateTimeKind.Utc);
       Console.WriteLine("{0} ({1}) --> {0:O}", uDat, uDat.Kind);

       DateTime lDat = new DateTime(2009, 6, 15, 13, 45, 30, 
                                    DateTimeKind.Local);
       Console.WriteLine("{0} ({1}) --> {0:O}\n", lDat, lDat.Kind);

       DateTimeOffset dto = new DateTimeOffset(lDat);
       Console.WriteLine("{0} --> {0:O}", dto);
   }
}
// The example displays the following output:
//    6/15/2009 1:45:30 PM (Unspecified) --> 2009-06-15T13:45:30.0000000
//    6/15/2009 1:45:30 PM (Utc) --> 2009-06-15T13:45:30.0000000Z
//    6/15/2009 1:45:30 PM (Local) --> 2009-06-15T13:45:30.0000000-07:00
//    
//    6/15/2009 1:45:30 PM -07:00 --> 2009-06-15T13:45:30.0000000-07:00
```

```vb
Module Example
   Public Sub Main()
       Dim dat As New Date(2009, 6, 15, 13, 45, 30, 
                           DateTimeKind.Unspecified)
       Console.WriteLine("{0} ({1}) --> {0:O}", dat, dat.Kind) 

       Dim uDat As New Date(2009, 6, 15, 13, 45, 30, DateTimeKind.Utc)
       Console.WriteLine("{0} ({1}) --> {0:O}", uDat, uDat.Kind)

       Dim lDat As New Date(2009, 6, 15, 13, 45, 30, DateTimeKind.Local)
       Console.WriteLine("{0} ({1}) --> {0:O}", lDat, lDat.Kind)
       Console.WriteLine()

       Dim dto As New DateTimeOffset(lDat)
       Console.WriteLine("{0} --> {0:O}", dto)
   End Sub
End Module
' The example displays the following output:
'    6/15/2009 1:45:30 PM (Unspecified) --> 2009-06-15T13:45:30.0000000
'    6/15/2009 1:45:30 PM (Utc) --> 2009-06-15T13:45:30.0000000Z
'    6/15/2009 1:45:30 PM (Local) --> 2009-06-15T13:45:30.0000000-07:00
'    
'    6/15/2009 1:45:30 PM -07:00 --> 2009-06-15T13:45:30.0000000-07:00
```

Im folgenden Beispiel wird der o-Formatbezeichner verwendet, um eine formatierte Zeichenfolge zu erstellen, und anschließend wird der ursprüngliche Datums- und Uhrzeitwert wiederhergestellt, indem eine `Parse`-Methode für Datum und Uhrzeit aufgerufen wird.

```csharp
// Round-trip DateTime values.
DateTime originalDate, newDate;
string dateString;
// Round-trip a local time.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 10, 6, 30, 0), DateTimeKind.Local);
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);
// Round-trip a UTC time.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 12, 9, 30, 0), DateTimeKind.Utc);                  
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);
// Round-trip time in an unspecified time zone.
originalDate = DateTime.SpecifyKind(new DateTime(2008, 4, 13, 12, 30, 0), DateTimeKind.Unspecified);                  
dateString = originalDate.ToString("o");
newDate = DateTime.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, 
                  newDate, newDate.Kind);

// Round-trip a DateTimeOffset value.
DateTimeOffset originalDTO = new DateTimeOffset(2008, 4, 12, 9, 30, 0, new TimeSpan(-8, 0, 0));
dateString = originalDTO.ToString("o");
DateTimeOffset newDTO = DateTimeOffset.Parse(dateString, null, DateTimeStyles.RoundtripKind);
Console.WriteLine("Round-tripped {0} to {1}.", originalDTO, newDTO);
// The example displays the following output:
//    Round-tripped 4/10/2008 6:30:00 AM Local to 4/10/2008 6:30:00 AM Local.
//    Round-tripped 4/12/2008 9:30:00 AM Utc to 4/12/2008 9:30:00 AM Utc.
//    Round-tripped 4/13/2008 12:30:00 PM Unspecified to 4/13/2008 12:30:00 PM Unspecified.
//    Round-tripped 4/12/2008 9:30:00 AM -08:00 to 4/12/2008 9:30:00 AM -08:00.
```

```vb
' Round-trip DateTime values.
Dim originalDate, newDate As Date
Dim dateString As String
' Round-trip a local time.
originalDate = Date.SpecifyKind(#4/10/2008 6:30AM#, DateTimeKind.Local)
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)
' Round-trip a UTC time.
originalDate = Date.SpecifyKind(#4/12/2008 9:30AM#, DateTimeKind.Utc)                  
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)
' Round-trip time in an unspecified time zone.
originalDate = Date.SpecifyKind(#4/13/2008 12:30PM#, DateTimeKind.Unspecified)                  
dateString = originalDate.ToString("o")
newDate = Date.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} {1} to {2} {3}.", originalDate, originalDate.Kind, _
                  newDate, newDate.Kind)

' Round-trip a DateTimeOffset value.
Dim originalDTO As New DateTimeOffset(#4/12/2008 9:30AM#, New TimeSpan(-8, 0, 0))
dateString = originalDTO.ToString("o")
Dim newDTO As DateTimeOffset = DateTimeOffset.Parse(dateString, Nothing, DateTimeStyles.RoundtripKind)
Console.WriteLine("Round-tripped {0} to {1}.", originalDTO, newDTO)
' The example displays the following output:
'    Round-tripped 4/10/2008 6:30:00 AM Local to 4/10/2008 6:30:00 AM Local.
'    Round-tripped 4/12/2008 9:30:00 AM Utc to 4/12/2008 9:30:00 AM Utc.
'    Round-tripped 4/13/2008 12:30:00 PM Unspecified to 4/13/2008 12:30:00 PM Unspecified.
'    Round-tripped 4/12/2008 9:30:00 AM -08:00 to 4/12/2008 9:30:00 AM -08:00.
```

## <a name="the-rfc1123-r-r-format-specifier"></a>Die RFC1123-Formatbezeichner „R“, „r“

Der Standardformatbezeichner „R“ oder „r“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die [DateTimeFormatInfo.RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern)-Eigenschaft definiert wird. Bei dem Muster handelt es sich um einen definierten Standard. Die Eigenschaft ist schreibgeschützt. Es ist daher unabhängig von der verwendeten Kultur oder dem bereitgestellten Formatanbieter immer identisch. Die benutzerdefinierte Formatzeichenfolge lautet "ddd, dd MMM yyyy HH':'mm':'ss 'GMT'". Wenn dieser Standardformatbezeichner verwendet wird, wird bei der Formatierungs- oder Analysemethode immer die invariante Kultur verwendet.

Die Ergebniszeichenfolge wird von den folgenden Eigenschaften des [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst, die von der [DateTimeFormatInfo.InvariantInfo](xref:System.Globalization.DateTimeFormatInfo.InvariantInfo)-Eigenschaft zurückgegeben werden, die die invariante Kultur darstellt.

Eigenschaft | Beschreibung
-------- | -----------
[RFC1123Pattern](xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern) | Definiert das Format der Ergebniszeichenfolge.
[AbbreviatedDayNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames) | Definiert die abgekürzten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.
[AbbreviatedMonthNames](xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames) | Definiert die abgekürzten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.

Auch wenn eine Zeitangabe gemäß der RFC-Spezifikation 1123 als koordinierte Weltzeit (UTC) ausgedrückt wird, wird der Wert des [DateTime](xref:System.DateTime)-Objekts, das formatiert wird, durch den Formatierungsvorgang nicht geändert. Daher müssen Sie den [DateTime](xref:System.DateTime)-Wert in die UTC konvertieren. Rufen Sie hierzu die [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime)-Methode auf, bevor Sie den Formatierungsvorgang ausführen. Im Gegensatz dazu wird diese Konvertierung durch [DateTimeOffset](xref:System.DateTimeOffset)-Werte automatisch ausgeführt, und es besteht keine Notwendigkeit, die [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Methode vor Ausführung des Formatierungsvorgangs aufzurufen. 

Im folgenden Beispiel wird der Formatbezeichner „r“ verwendet, um einen [DateTime](xref:System.DateTime)-Wert und einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert in einem System in der Zeitzone Pacific anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
DateTimeOffset dateOffset = new DateTimeOffset(date1, 
                            TimeZoneInfo.Local.GetUtcOffset(date1));
Console.WriteLine(date1.ToUniversalTime().ToString("r"));
// Displays Thu, 10 Apr 2008 13:30:00 GMT                       
Console.WriteLine(dateOffset.ToUniversalTime().ToString("r"));
// Displays Thu, 10 Apr 2008 13:30:00 GMT  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Dim dateOffset As New DateTimeOffset(date1, TimeZoneInfo.Local.GetUtcOFfset(date1))
Console.WriteLine(date1.ToUniversalTime.ToString("r"))
' Displays Thu, 10 Apr 2008 13:30:00 GMT                       
Console.WriteLine(dateOffset.ToUniversalTime.ToString("r"))
' Displays Thu, 10 Apr 2008 13:30:00 GMT
```

## <a name="the-sortable-s-format-specifier"></a>Der Bezeichner „s“ für sortierbares Format

Der Standardformatbezeichner „s“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die [DateTimeFormatInfo.SortableDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern)-Eigenschaft definiert wird. Bei dem Muster handelt es sich um einen definierten Standard (ISO 8601). Die Eigenschaft ist schreibgeschützt. Es ist daher unabhängig von der verwendeten Kultur oder dem bereitgestellten Formatanbieter immer identisch. Die benutzerdefinierte Formatzeichenfolge lautet "yyyy'-'MM'-'dd'T'HH':'mm':'ss".

Der Formatbezeichner "s" dient dazu, Ergebniszeichenfolgen zu generieren, die konsistent in aufsteigender oder absteigender Reihenfolge auf der Grundlage von Datums-und Uhrzeitwerten sortieren. Obwohl der Standardformatbezeichner „s“ einen Datums- und Uhrzeitwert in einem konsistenten Format darstellt, ändert der Formatierungsvorgang daher nicht den Wert des Datums- und Uhrzeitobjekts, das formatiert wird, entsprechend seiner [DateTime.Kind](xref:System.DateTime.Kind)-Eigenschaft oder seines [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset)-Werts. Die Ergebniszeichenfolgen, die durch Formatieren der Datums- und Uhrzeitwerte 2014-11-15T18:32:17+00:00 und 2014-11-15T18:32:17+08:00 generiert werden, sind z. B. identisch. 

Wenn dieser Standardformatbezeichner verwendet wird, wird bei der Formatierungs- oder Analysemethode immer die invariante Kultur verwendet. 

Im folgenden Beispiel wird der Formatbezeichner „s“ verwendet, um einen [DateTime](xref:System.DateTime)-Wert und einen [DateTimeOffset](xref:System.DateTimeOffset)-Wert in einem System in der Zeitzone Pacific anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("s"));
// Displays 2008-04-10T06:30:00
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("s"))
' Displays 2008-04-10T06:30:00 
```

## <a name="the-short-time-t-format-specifier"></a>Der Formatbezeichner „t“ für kurze Zeit

Der Standardformatbezeichner „t“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die aktuelle [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern)-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "HH:mm".

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst. In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der [DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern)-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[DateTimeFormatInfo.ShortTimePattern](xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern) | Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Im folgenden Beispiel wird der t-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("t", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 6:30 AM                        
Console.WriteLine(date1.ToString("t", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays 6:30  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("t", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 6:30 AM                        
Console.WriteLine(date1.ToString("t", _
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays 6:30
```

## <a name="the-long-time-t-format-specifier"></a>Der Formatbezeichner „T“ für lange Zeit

Der Standardformatbezeichner „T“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern)-Eigenschaft einer bestimmten Kultur definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "HH:mm:ss".

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der [DateTimeFormatInfo.LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern)-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[LongTimePattern](xref:System.Globalization.DateTimeFormatInfo.LongTimePattern) | Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Im folgenden Beispiel wird der T-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("T", 
                  CultureInfo.CreateSpecificCulture("en-us")));
// Displays 6:30:00 AM                       
Console.WriteLine(date1.ToString("T", 
                  CultureInfo.CreateSpecificCulture("es-ES")));
// Displays 6:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("T", _
                  CultureInfo.CreateSpecificCulture("en-us")))
' Displays 6:30:00 AM                       
Console.WriteLine(date1.ToString("T", _
                  CultureInfo.CreateSpecificCulture("es-ES")))
' Displays 6:30:00 
```

## <a name="the-universal-sortable-u-format-specifier"></a>Der Bezeichner „u“ für universelles sortierbares Format

Der Standardformatbezeichner „u“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die [DateTimeFormatInfo.UniversalSortableDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern)-Eigenschaft definiert wird. Bei dem Muster handelt es sich um einen definierten Standard. Die Eigenschaft ist schreibgeschützt. Es ist daher unabhängig von der verwendeten Kultur oder dem bereitgestellten Formatanbieter immer identisch. Die benutzerdefinierte Formatzeichenfolge lautet "yyyy'-'MM'-'dd HH':'mm':'ss'Z'". Wenn dieser Standardformatbezeichner verwendet wird, wird bei der Formatierungs- oder Analysemethode immer die invariante Kultur verwendet. 

Obwohl die Ergebniszeichenfolge eine Zeitangabe als koordinierte Weltzeit (UTC) ausdrücken soll, wird der ursprüngliche [DateTime](xref:System.DateTime)-Wert während des Formatierungsvorgangs nicht konvertiert. Daher müssen Sie einen [DateTime](xref:System.DateTime)-Wert in die UTC konvertieren. Rufen Sie hierzu die [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime)-Methode auf, bevor Sie die Formatierung durchführen. Im Gegensatz dazu wird diese Konvertierung durch [DateTimeOffset](xref:System.DateTimeOffset)-Werte automatisch ausgeführt, und es besteht keine Notwendigkeit, die [DateTimeOffset.ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime)-Methode vor Ausführung des Formatierungsvorgangs aufzurufen.   

Im folgenden Beispiel wird der u-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToUniversalTime().ToString("u"));
// Displays 2008-04-10 13:30:00Z
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToUniversalTime.ToString("u"))
' Displays 2008-04-10 13:30:00Z                       
```

## <a name="the-universal-full-u-format-specifier"></a>Der Bezeichner „U“ für universelles vollständiges Format

Der Standardformatbezeichner „U“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die durch die [DateTimeFormatInfo.FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern)-Eigenschaft einer angegebenen Kultur definiert wird. Das Muster ist gleich dem F-Muster. Der [DateTime](xref:System.DateTime)-Wert wird jedoch vor der Formatierung automatisch in die UTC konvertiert.

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der [FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern)-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

Eigenschaft | Beschreibung
-------- | -----------
[FullDateTimePattern](xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern) | Definiert das Gesamtformat der Ergebniszeichenfolge.
[DayNames](xref:System.Globalization.DateTimeFormatInfo.DayNames) | Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.
[AMDesignator](xref:System.Globalization.DateTimeFormatInfo.AMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.
[PMDesignator](xref:System.Globalization.DateTimeFormatInfo.PMDesignator) | Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.

Der Formatbezeichner „U“ wird vom [DateTimeOffset](xref:System.DateTimeOffset)-Typ nicht unterstützt und löst eine [FormatException](xref:System.FormatException) aus, wenn er zur Formatierung eines [DateTimeOffset](xref:System.DateTimeOffset)-Werts verwendet wird.

Im folgenden Beispiel wird der U-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

``` csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("U", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays Thursday, April 10, 2008 1:30:00 PM                       
Console.WriteLine(date1.ToString("U", 
                  CultureInfo.CreateSpecificCulture("sv-FI")));
// Displays den 10 april 2008 13:30:00  
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("U", CultureInfo.CreateSpecificCulture("en-US")))
' Displays Thursday, April 10, 2008 1:30:00 PM                       
Console.WriteLine(date1.ToString("U", CultureInfo.CreateSpecificCulture("sv-FI")))
' Displays den 10 april 2008 13:30:00                       
```

## <a name="the-year-month-y-y-format-specifier"></a>Die Formatbezeichner „Y“, „y“ für Jahr-Monat

Der Standardformatbezeichner „Y“ oder „y“ stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, durch die [DateTimeFormatInfo.YearMonthPattern](xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern)-Eigenschaft einer angegebenen Kultur definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "yyyy MMMM".

In der folgenden Tabelle sind die [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

Eigenschaft | Beschreibung
-------- | -----------
[YearMonthPattern](xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern) | Definiert das Gesamtformat der Ergebniszeichenfolge.
[MonthNames](xref:System.Globalization.DateTimeFormatInfo.MonthNames) | Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.

Im folgenden Beispiel wird der y-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

```csharp
DateTime date1 = new DateTime(2008, 4, 10, 6, 30, 0);
Console.WriteLine(date1.ToString("Y", 
                  CultureInfo.CreateSpecificCulture("en-US")));
// Displays April, 2008                       
Console.WriteLine(date1.ToString("y", 
                  CultureInfo.CreateSpecificCulture("af-ZA")));
// Displays April 2008 
```

```vb
Dim date1 As Date = #4/10/2008 6:30AM#
Console.WriteLine(date1.ToString("Y", CultureInfo.CreateSpecificCulture("en-US")))
' Displays April, 2008                       
Console.WriteLine(date1.ToString("y", CultureInfo.CreateSpecificCulture("af-ZA")))
' Displays April 2008
```                       

## <a name="notes"></a>Notizen

### <a name="datetimeformatinfo-properties"></a>DateTimeFormatInfo-Eigenschaften

Die Formatierung wird durch die Eigenschaften des aktuellen [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts beeinflusst, das implizit durch die aktuelle Threadkultur oder explizit durch den [IFormatProvider](xref:System.IFormatProvider)-Parameter der Methode bereitgestellt wird, die die Formatierung aufruft. Für den [IFormatProvider](xref:System.IFormatProvider)-Parameter sollte Ihre Anwendung ein [CultureInfo](xref:System.Globalization.CultureInfo)-Objekt angeben, das eine Kultur darstellt, oder ein [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekt, das die Formatierungskonventionen einer bestimmten Kultur für Datum und Uhrzeit darstellt. Bei vielen der Standardformatbezeichner für Datum und Uhrzeit handelt es sich um Aliase für Formatierungsmuster, die durch Eigenschaften des aktuellen [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Objekts definiert werden. Die Anwendung kann das von einigen Standardformatbezeichnern für Datum und Uhrzeit erzeugte Ergebnis ändern, indem sie die entsprechenden Datums- und Uhrzeitformatmuster der entsprechenden [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo)-Eigenschaft ändert.

## <a name="see-also"></a>Siehe auch

[Formatierung von Typen](formatting-types.md)

[Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-datetime.md)




<!--HONumber=Nov16_HO3-->


