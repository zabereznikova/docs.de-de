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
ms.openlocfilehash: 36066d6b2405051a3d35befffe53af8895e26220
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964834"
---
# <a name="datetime-xaml-syntax"></a>DateTime-XAML-Syntax
Einige Steuerelemente, z <xref:System.Windows.Controls.Calendar> . <xref:System.Windows.Controls.DatePicker>b. und, verfügen über <xref:System.DateTime> Eigenschaften, die den-Typ verwenden. Auch wenn Sie in der Regel ein Anfangsdatum oder eine Uhrzeit für diese Steuerelemente im CodeBehind zur Laufzeit angeben, können Sie ein Anfangsdatum oder eine Uhrzeit in XAML angeben. Der WPF-XAML-Parser behandelt die <xref:System.DateTime> Analyse von Werten mithilfe einer integrierten XAML-Text Syntax. In diesem Thema werden die Besonderheiten der <xref:System.DateTime> XAML-Text Syntax beschrieben.  

<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>Verwenden von DateTime-XAML-Syntax  
 Das Festlegen von Datumsangaben in XAML ist nicht immer erforderlich und möglicherweise auch nicht erwünscht. Beispielsweise können Sie die <xref:System.DateTime.Now%2A?displayProperty=nameWithType> -Eigenschaft verwenden, um ein Datum zur Laufzeit zu initialisieren, oder Sie können alle Datums Anpassungen für einen Kalender im Code-Behind basierend auf Benutzereingaben durchführen. Es gibt jedoch Szenarios, in denen Sie möglicherweise Datumsangaben in einem <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker> in einer Steuerelement Vorlage hart codieren möchten. Die <xref:System.DateTime> XAML-Syntax muss für diese Szenarien verwendet werden.  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime-XAML-Syntax als natives Verhalten  
 <xref:System.DateTime>ist eine Klasse, die in den Basisklassen Bibliotheken der CLR definiert ist. Da sich die Basisklassen Bibliotheken auf den Rest der CLR beziehen, ist es nicht möglich, auf die Klasse <xref:System.ComponentModel.TypeConverterAttribute> anzuwenden und einen Typkonverter zu verwenden, um Zeichen folgen aus XAML zu verarbeiten und Sie <xref:System.DateTime> in das Laufzeitobjekt Modell zu konvertieren. Es gibt keine `DateTimeConverter`-Klasse, die das Konvertierungsverhalten ermöglicht. Das in diesem Thema beschriebene Konvertierungsverhalten ist vielmehr ein natives Verhalten im WPF-XAML-Parser.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>Formatzeichenfolgen für DateTime-XAML-Syntax  
 Sie können das Format <xref:System.DateTime> eines mit einer Format Zeichenfolge angeben. Formatzeichenfolgen formalisieren die Textsyntax, die zum Erstellen eines Werts verwendet werden kann. <xref:System.DateTime>Werte für die vorhandenen WPF-Steuerelemente verwenden im Allgemeinen nur die <xref:System.DateTime> Datums Komponenten von und nicht die Zeit Komponenten.  
  
 Wenn Sie in <xref:System.DateTime> XAML angeben, können Sie eine beliebige Format Zeichenfolge verwenden.  
  
 Sie können auch Formate und Formatzeichenfolgen verwenden, die in diesem Thema nicht speziell beschrieben werden. Technisch gesehen verwendet der XAML- <xref:System.DateTime> Code für einen beliebigen Wert, der vom WPF-XAML-Parser analysiert und dann analysiert wird <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, einen internen-Befehl, daher können Sie <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> jede von akzeptierte Zeichenfolge für Ihre XAML-Eingabe verwenden. Weitere Informationen finden Sie unter <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> Die DateTime-XAML-Syntax `en-us` verwendet immer <xref:System.Globalization.CultureInfo> als für die systemeigene Konvertierung. Dies wird nicht durch <xref:System.Windows.FrameworkElement.Language%2A> den Wert oder `xml:lang` Wert in der XAML beeinflusst, da die Typkonvertierung auf Attribut Ebene ohne diesen Kontext erfolgt. Versuchen Sie nicht, die hier angezeigten Formatzeichenfolgen aufgrund von kulturellen Abweichungen, wie z. B. der Reihenfolge von Tag und Monat, zu interpolieren. Die hier angezeigten Formatzeichenfolgen sind die genauen Formatzeichenfolgen für die Analyse von XAML unabhängig von anderen Kultureinstellungen.  
  
 In den folgenden Abschnitten werden einige der allgemeinen <xref:System.DateTime> -Format Zeichenfolgen beschrieben.  
  
### <a name="short-date-pattern-d"></a>Kurzes Datumsmuster („d“)  
 Das folgende Beispiel zeigt das kurze Datumsformat für <xref:System.DateTime> ein in XAML:  
  
 `M/d/YYYY`  
  
 Dies ist die einfachste Möglichkeit, alle erforderlichen Informationen für eine typische Verwendung durch WPF-Steuerelemente anzugeben. Eine Beeinflussung durch versehentliche Zeitzonenverschiebungen gegenüber einer Zeitkomponente ist nicht vorhanden. Daher wird dieses Format anderen Formaten vorgezogen.  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge:  
  
 `3/1/2010`  
  
 Weitere Informationen finden Sie unter <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.  
  
### <a name="sortable-datetime-pattern-s"></a>Sortierbares DateTime-Muster („s“)  
 Der folgende Code zeigt das Sortier <xref:System.DateTime> Bare Muster in XAML:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123-Muster („r“)  
 Das RFC1123-Muster ist hilfreich, da es sich um eine Zeichenfolgeneingabe aus anderen Datumsgeneratoren handeln könnte, die aus kulturinvarianten Gründen auch das RFC1123-Muster verwenden. Der folgende Code zeigt das <xref:System.DateTime> RFC1123-Muster in XAML:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Um z.B. das Datum vom 1. Juni 2010 anzugeben, verwenden Sie die folgende Zeichenfolge (alle Zeitkomponenten werden mit 0 eingegeben):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>Andere Formate und Muster  
 Wie bereits erwähnt, kann <xref:System.DateTime> ein in XAML als eine beliebige Zeichenfolge angegeben werden, die als Eingabe <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>für zulässig ist. Dies schließt andere formalisierte Formate (z <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>. b.) und Formate ein, die nicht als bestimmtes <xref:System.Globalization.DateTimeFormatInfo> Formular formalisiert werden. Beispielsweise ist das Formular `YYYY/mm/dd` als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>zulässig. In diesem Thema werden nicht alle Formate beschrieben, die funktionieren, sondern das kurze Datumsmuster als Standardverfahren empfohlen werden.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
