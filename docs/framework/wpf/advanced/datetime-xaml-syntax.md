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
ms.openlocfilehash: 8180064d1a500ea17568f6790e13398524eb5f36
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365684"
---
# <a name="datetime-xaml-syntax"></a>DateTime-XAML-Syntax
Einige Steuerelemente, z. B. <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker>, verfügen über Eigenschaften, mit denen die <xref:System.DateTime> Typ. Auch wenn Sie in der Regel ein Anfangsdatum oder eine Uhrzeit für diese Steuerelemente im CodeBehind zur Laufzeit angeben, können Sie ein Anfangsdatum oder eine Uhrzeit in XAML angeben. Der WPF XAML-Parser behandelt die Analyse von <xref:System.DateTime> Werte mithilfe einer integrierten XAML-Textsyntax. In diesem Thema wird beschrieben, die Einzelheiten der <xref:System.DateTime> XAML-Textsyntax.  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Verwenden von DateTime-XAML-Syntax  
 Das Festlegen von Datumsangaben in XAML ist nicht immer erforderlich und möglicherweise auch nicht erwünscht. Beispielsweise können Sie die <xref:System.DateTime.Now%2A?displayProperty=nameWithType> -Eigenschaft zum Initialisieren einer Datumsangabe zur Laufzeit ausgeführt wird oder Sie möglich aller Ihrer Datum Korrekturen für den Kalender im Code-Behind auf Grundlage der Benutzereingabe. Es gibt jedoch Szenarien unter Umständen Sie zum Programmieren von Datumsangaben in möchten einem <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker> in einer Steuerelementvorlage. Die <xref:System.DateTime> XAML-Syntax für diese Szenarien verwendet werden dürfen.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime-XAML-Syntax als natives Verhalten  
 <xref:System.DateTime> ist eine Klasse, die in der CLR den Basisklassenbibliotheken definiert ist. Aufgrund der Art, die Basisklassenbibliotheken zum Rest der CLR beziehen, ist es nicht möglich, gelten <xref:System.ComponentModel.TypeConverterAttribute> auf die Klasse und verwendet einen Typkonverter zum Verarbeiten von Zeichenfolgen aus XAML und konvertieren sie <xref:System.DateTime> im Objektmodell zur Laufzeit. Es gibt keine `DateTimeConverter`-Klasse, die das Konvertierungsverhalten ermöglicht. Das in diesem Thema beschriebene Konvertierungsverhalten ist vielmehr ein natives Verhalten im WPF-XAML-Parser.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Formatzeichenfolgen für DateTime-XAML-Syntax  
 Sie können angeben, das Format einer <xref:System.DateTime> mit einer Formatzeichenfolge. Formatzeichenfolgen formalisieren die Textsyntax, die zum Erstellen eines Werts verwendet werden kann. <xref:System.DateTime> Werte für die vorhandenen WPF-in der Regel nur verwenden, die Datumskomponenten von Steuerelemente <xref:System.DateTime> und nicht die Zeitkomponenten.  
  
 Beim Angeben einer <xref:System.DateTime> in XAML, können Sie mithilfe eines Formatzeichenfolgen sind austauschbar.  
  
 Sie können auch Formate und Formatzeichenfolgen verwenden, die in diesem Thema nicht speziell beschrieben werden. Technisch gesehen das XAML für eine beliebige <xref:System.DateTime> -Wert, der angegeben ist, und klicken Sie dann vom WPF XAML-Parser analysiert verwendet einen internen Aufruf für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, daher können Sie eine beliebige Zeichenfolge, die vom akzeptiert <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> als Eingabe für Ihre XAML. Weitere Informationen finden Sie unter <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Die DateTime XAML-Syntax verwendet immer `en-us` als die <xref:System.Globalization.CultureInfo> für die native Konvertierung. Dies wird nicht beeinflusst, indem <xref:System.Windows.FrameworkElement.Language%2A> Wert oder `xml:lang` Wert in das XAML, da die typkonvertierung für XAML-Attributebene ohne diesen Kontext funktioniert. Versuchen Sie nicht, die hier angezeigten Formatzeichenfolgen aufgrund von kulturellen Abweichungen, wie z. B. der Reihenfolge von Tag und Monat, zu interpolieren. Die hier angezeigten Formatzeichenfolgen sind die genauen Formatzeichenfolgen für die Analyse von XAML unabhängig von anderen Kultureinstellungen.  
  
 Den folgenden Abschnitten werden einige der gängigsten <xref:System.DateTime> Formatzeichenfolgen.  
  
### <a name="short-date-pattern-d"></a>Kurzes Datumsmuster („d“)  
 Das folgende Beispiel zeigt das kurze Datumsformat für eine <xref:System.DateTime> in XAML:  
  
 `M/d/YYYY`  
  
 Dies ist die einfachste Möglichkeit, alle erforderlichen Informationen für eine typische Verwendung durch WPF-Steuerelemente anzugeben. Eine Beeinflussung durch versehentliche Zeitzonenverschiebungen gegenüber einer Zeitkomponente ist nicht vorhanden. Daher wird dieses Format anderen Formaten vorgezogen.  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge:  
  
 `3/1/2010`  
  
 Weitere Informationen finden Sie unter <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Sortierbares DateTime-Muster („s“)  
 Das folgende Beispiel zeigt das sortierbare <xref:System.DateTime> Muster in XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123-Muster („r“)  
 Das RFC1123-Muster ist hilfreich, da es sich um eine Zeichenfolgeneingabe aus anderen Datumsgeneratoren handeln könnte, die aus kulturinvarianten Gründen auch das RFC1123-Muster verwenden. Das folgende Beispiel zeigt das RFC1123 <xref:System.DateTime> Muster in XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Andere Formate und Muster  
 Wie zuvor erwähnt ein <xref:System.DateTime> in XAML als eine beliebige Zeichenfolge, die akzeptable angegeben werden als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. Dies schließt andere formalisierte Formate (z. B. <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), und Formate, die nicht als ein bestimmtes formalisiert werden <xref:System.Globalization.DateTimeFormatInfo> Formular. Z. B. das Formular `YYYY/mm/dd` ist akzeptabel, als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>. In diesem Thema werden nicht alle Formate beschrieben, die funktionieren, sondern das kurze Datumsmuster als Standardverfahren empfohlen werden.  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
