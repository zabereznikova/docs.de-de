---
title: "DateTime-XAML-Syntax | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DateTime-XAML-Syntax [WPF]"
  - "DateTime-XAML-Syntax [WPF], Formatzeichenfolgen für"
  - "DateTime-XAML-Syntax [WPF], Zeichenfolgen für"
  - "DateTime-XAML-Syntax [WPF], Verwendung"
  - "DateTime-XAML-Text [WPF]"
  - "Kurzes Datumsformat [WPF], DateTime"
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# DateTime-XAML-Syntax
Einige Steuerelemente, z. B. <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker>, verfügen über Eigenschaften, die den <xref:System.DateTime>\-Typ verwenden.  Obwohl Sie in der Regel ein Anfangsdatum oder eine Uhrzeit für diese Steuerelemente zur Laufzeit in Code\-Behind angeben, können Sie ein Anfangsdatum oder eine Uhrzeit in XAML angeben.  Der WPF\-XAML\-Parser behandelt die Analyse von <xref:System.DateTime>\-Werten mithilfe einer integrierten XAML\-Textsyntax.  In diesem Thema werden die Einzelheiten der <xref:System.DateTime> XAML\-Textsyntax beschrieben.  
  
   
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## Verwendungszeitpunkt der DateTime\-XAML\-Syntax  
 Datumsangaben in XAML festzulegen ist nicht immer notwendig und möglicherweise nicht einmal erwünscht.  Beispielsweise können Sie die <xref:System.DateTime.Now%2A?displayProperty=fullName>\-Eigenschaft verwenden, um ein Datum zur Laufzeit zu initialisieren, oder alle Datumsanpassungen für einen Kalender in Code\-Behind auf Grundlage von Benutzereingaben durchführen.  Es gibt jedoch Szenarios, in denen Sie Datumsangaben in <xref:System.Windows.Controls.Calendar> und <xref:System.Windows.Controls.DatePicker> in einer Steuerelementvorlage hartcodieren sollten.  Die <xref:System.DateTime>\-XAML\-Syntax muss für diese Szenarien verwendet werden.  
  
### DateTime XAML\-Syntax ist ein systemeigenes Verhalten  
 <xref:System.DateTime> ist eine Klasse, die in den Basisklassenbibliotheken der CLR definiert ist.  Aufgrund der Art, auf die sich die Basisklassenbibliotheken auf den Rest der CLR beziehen, ist es nicht möglich, <xref:System.ComponentModel.TypeConverterAttribute> für die Klasse zu übernehmen und einen Typkonverter zu verwenden, um Zeichenfolgen in XAML zu verarbeiten und sie in <xref:System.DateTime> im Laufzeitobjektmodell zu konvertieren.  Es gibt keine `DateTimeConverter`\-Klasse, die das Verhalten der Konvertierung bereitstellt. Das in diesem Thema beschriebene Verhalten bei der Konvertierung ist ein systemeigenes Verhalten im WPF\-XAML\-Parser.  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## Formatzeichenfolgen für DateTime\-XAML\-Syntax  
 Sie können das Format von <xref:System.DateTime> mit einer Formatzeichenfolge angeben.  Formatzeichenfolgen formalisieren die Textsyntax, die verwendet werden kann, um einen Wert zu erstellen.  <xref:System.DateTime>\-Werte für die vorhandenen WPF\-Steuerelemente verwenden im Allgemeinen nur die Datumskomponenten von <xref:System.DateTime> und nicht den Zeitkomponenten.  
  
 Wenn Sie in XAML ein <xref:System.DateTime>\-Objekt angeben, können Sie eine beliebige Formatzeichenfolge austauschbar verwenden.  
  
 Sie können auch Formate und Formatzeichenfolgen verwenden, die nicht speziell in diesem Thema angezeigt werden.  Technisch verwendet XAML für jeden <xref:System.DateTime>\-Wert, der angegeben und dann vom WPF XAML\-Parser analysiert wird, einen internen Aufruf von <xref:System.DateTime.Parse%2A?displayProperty=fullName>. Daher können Sie jede von <xref:System.DateTime.Parse%2A?displayProperty=fullName> akzeptierte Zeichenfolge für Ihre XAML\-Eingabe verwenden.  Weitere Informationen finden Sie unter <xref:System.DateTime.Parse%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Die DateTime\-XAML\-Syntax verwendet immer `en-us` als <xref:System.Globalization.CultureInfo> für seine systemeigene Konvertierung.  Dies wird nicht vom <xref:System.Windows.FrameworkElement.Language%2A>\-Wert oder `xml:lang`\-Wert im XAML beeinflusst, da Typkonvertierung auf XAML\-Attributebene ohne diesen Kontext ausgeführt wird.  Versuchen Sie nicht, die aufgrund kultureller Variationen hier angezeigten Formatzeichenfolgen zu interpolieren, z. B. die Reihenfolge, in der Tag und Monat angezeigt werden.  Die hier angezeigten Formatzeichenfolgen entsprechen den beim Analysieren des XAML verwendeten Formatzeichenfolgen, ungeachtet der Kultureinstellungen.  
  
 In den folgenden Abschnitten werden einige der allgemeinen <xref:System.DateTime>\-Formatzeichenfolgen beschrieben.  
  
### Kurzes Datumsmuster \("d"\)  
 Das Folgende ist das kurze Datumsformat für ein <xref:System.DateTime>\-Objekt in XAML:  
  
 `M/d/YYYY`  
  
 Dies ist das einfachste Format, das alle notwendigen Informationen für typische Verwendungen durch WPF\-Steuerelemente angibt. Es kann nicht von zufälligen Zeitzonenoffsets gegenüber einer Zeitkomponente beeinflusst werden und wird daher anstelle der anderen Formate empfohlen.  
  
 Um das Datum vom 1. Juni 2010 anzugeben, verwenden Sie z. B. die folgende Zeichenfolge:  
  
 `3/1/2010`  
  
 Weitere Informationen finden Sie unter <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=fullName>.  
  
### Sortierbares DateTime\-Muster \("s"\)  
 Im Folgenden wird das sortierbare <xref:System.DateTime>\-Muster in XAML dargestellt:  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 Um das Datum vom 1. Juni 2010 anzugeben, verwenden Sie z. B. die folgende Zeichenfolge \(Zeitkomponenten werden alle als 0 eingegeben\):  
  
 `2010-06-01T000:00:00`  
  
### RFC1123\-Muster \("r"\)  
 Das RFC1123\-Muster ist nützlich, da es sich um eine Zeichenfolgeneingabe aus anderen Datumsgeneratoren handeln kann, die auch das RFC1123\-Muster aus kulturinvarianten Gründen verwenden.  Im Folgenden wird das <xref:System.DateTime>\-RFC1123\-Muster in XAML dargestellt:  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 Um das Datum vom 1. Juni 2010 anzugeben, verwenden Sie z. B. die folgende Zeichenfolge \(Zeitkomponenten werden alle als 0 eingegeben\):  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### Andere Formate und Muster  
 Wie zuvor angegeben, kann ein <xref:System.DateTime> in XAML als jede Zeichenfolge angegeben werden, die als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=fullName> akzeptabel ist.  Dies schließt andere formalisierte Formate \(zum Beispiel <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>\) und Formate ein, die nicht als ein bestimmtes <xref:System.Globalization.DateTimeFormatInfo>\-Formular formalisiert werden.  Beispiel: Die Form `YYYY/mm/dd` ist als Eingabe für <xref:System.DateTime.Parse%2A?displayProperty=fullName> akzeptabel.  In diesem Thema werden nicht alle möglichen Formate beschrieben, die funktionieren, vielmehr wird als Standard das kurze Datumsmuster empfohlen.  
  
## Siehe auch  
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)