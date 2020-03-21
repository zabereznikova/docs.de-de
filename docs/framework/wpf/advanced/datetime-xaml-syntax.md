---
title: DateTime-XAML-Syntax
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186333"
---
# <a name="datetime-xaml-syntax"></a>DateTime-XAML-Syntax
Einige Steuerelemente, <xref:System.Windows.Controls.Calendar> <xref:System.Windows.Controls.DatePicker>z. B. <xref:System.DateTime> und , verfügen über Eigenschaften, die den Typ verwenden. Auch wenn Sie in der Regel ein Anfangsdatum oder eine Uhrzeit für diese Steuerelemente im CodeBehind zur Laufzeit angeben, können Sie ein Anfangsdatum oder eine Uhrzeit in XAML angeben. Der WPF XAML-Parser verarbeitet <xref:System.DateTime> die Analyse von Werten mithilfe einer integrierten XAML-Textsyntax. In diesem Thema werden <xref:System.DateTime> die Besonderheiten der XAML-Textsyntax beschrieben.  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a>Verwenden von DateTime-XAML-Syntax  
 Das Festlegen von Datumsangaben in XAML ist nicht immer erforderlich und möglicherweise auch nicht erwünscht. Sie können die <xref:System.DateTime.Now%2A?displayProperty=nameWithType> Eigenschaft beispielsweise verwenden, um ein Datum zur Laufzeit zu initialisieren, oder Sie können alle Datumsanpassungen für einen Kalender im CodeBehind basierend auf Benutzereingaben vornehmen. Es gibt jedoch Szenarien, in denen Sie Daten <xref:System.Windows.Controls.Calendar> <xref:System.Windows.Controls.DatePicker> in einer und in einer Steuerelementvorlage hartcodieren möchten. Die <xref:System.DateTime> XAML-Syntax muss für diese Szenarien verwendet werden.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime-XAML-Syntax als natives Verhalten  
 <xref:System.DateTime>ist eine Klasse, die in den Basisklassenbibliotheken der CLR definiert ist. Aufgrund der Beziehung der Basisklassenbibliotheken zum Rest der CLR ist <xref:System.ComponentModel.TypeConverterAttribute> es nicht möglich, die Klasse anzuwenden und einen Typkonverter zu verwenden, um Zeichenfolgen aus XAML zu verarbeiten und in das Laufzeitobjektmodell zu <xref:System.DateTime> konvertieren. Es gibt keine `DateTimeConverter`-Klasse, die das Konvertierungsverhalten ermöglicht. Das in diesem Thema beschriebene Konvertierungsverhalten ist vielmehr ein natives Verhalten im WPF-XAML-Parser.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a>Formatzeichenfolgen für DateTime-XAML-Syntax  
 Sie können das Format <xref:System.DateTime> von a mit einer Formatzeichenfolge angeben. Formatzeichenfolgen formalisieren die Textsyntax, die zum Erstellen eines Werts verwendet werden kann. <xref:System.DateTime>Werte für die vorhandenen WPF-Steuerelemente <xref:System.DateTime> verwenden in der Regel nur die Datumskomponenten und nicht die Zeitkomponenten.  
  
 Wenn Sie <xref:System.DateTime> eine in XAML angeben, können Sie eine der Formatzeichenfolgen austauschbar verwenden.  
  
 Sie können auch Formate und Formatzeichenfolgen verwenden, die in diesem Thema nicht speziell beschrieben werden. Technisch gesehen verwendet das XAML für jeden <xref:System.DateTime> Wert, der vom WPF XAML-Parser angegeben und dann analysiert wird, einen internen Aufruf von <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, daher können Sie eine beliebige Zeichenfolge verwenden, die von <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> für Ihre XAML-Eingabe akzeptiert wird. Weitere Informationen finden Sie unter <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> Die DateTime XAML-Syntax `en-us` <xref:System.Globalization.CultureInfo> verwendet immer als die für die systemeigene Konvertierung. Dies wird nicht <xref:System.Windows.FrameworkElement.Language%2A> durch `xml:lang` den Wert oder Wert in XAML beeinflusst, da die XAML-Attributtypkonvertierung ohne diesen Kontext wirkt. Versuchen Sie nicht, die hier angezeigten Formatzeichenfolgen aufgrund von kulturellen Abweichungen, wie z. B. der Reihenfolge von Tag und Monat, zu interpolieren. Die hier angezeigten Formatzeichenfolgen sind die genauen Formatzeichenfolgen für die Analyse von XAML unabhängig von anderen Kultureinstellungen.  
  
 In den folgenden Abschnitten <xref:System.DateTime> werden einige der allgemeinen Formatzeichenfolgen beschrieben.  
  
### <a name="short-date-pattern-d"></a>Kurzes Datumsmuster („d“)  
 Im Folgenden wird das kurze <xref:System.DateTime> Datumsformat für ein in XAML angezeigt:  
  
 `M/d/YYYY`  
  
 Dies ist die einfachste Möglichkeit, alle erforderlichen Informationen für eine typische Verwendung durch WPF-Steuerelemente anzugeben. Eine Beeinflussung durch versehentliche Zeitzonenverschiebungen gegenüber einer Zeitkomponente ist nicht vorhanden. Daher wird dieses Format anderen Formaten vorgezogen.  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge:  
  
 `3/1/2010`  
  
 Weitere Informationen finden Sie unter <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Sortierbares DateTime-Muster („s“)  
 Im Folgenden wird <xref:System.DateTime> das sortierbare Muster in XAML angezeigt:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123-Muster („r“)  
 Das RFC1123-Muster ist hilfreich, da es sich um eine Zeichenfolgeneingabe aus anderen Datumsgeneratoren handeln könnte, die aus kulturinvarianten Gründen auch das RFC1123-Muster verwenden. Im Folgenden wird das RFC1123-Muster <xref:System.DateTime> in XAML gezeigt:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Andere Formate und Muster  
 Wie bereits erwähnt, kann ein <xref:System.DateTime> in XAML als beliebige <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>Zeichenfolge angegeben werden, die als Eingabe für zulässig ist. Dazu gehören andere formalisierte <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>Formate (z. B. ) <xref:System.Globalization.DateTimeFormatInfo> und Formate, die nicht als bestimmte Form formalisiert sind. Das Formular `YYYY/mm/dd` ist z. B. als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>akzeptabel. In diesem Thema werden nicht alle Formate beschrieben, die funktionieren, sondern das kurze Datumsmuster als Standardverfahren empfohlen werden.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
