---
title: "XamlName-Grammatik | Microsoft Docs"
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
  - "DottedXamlName-Grammatik [XAML-Dienste]"
  - "Grammatik [XAML-Dienste], DottedXamlName"
  - "Grammatik [XAML-Dienste], XamlName"
  - "Namen in XAML [XAML-Dienste]"
  - "XamlName-Grammatik [XAML-Dienste]"
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# XamlName-Grammatik
XamlName Grammar ist eine bestimmte Grammatik, die in der XAML\-Sprachspezifikation \[MS\-XAML\] definiert wurde, die zur leichteren Handhabbarkeit hier reproduziert wird.  
  
## Über die XAML\-Spezifikation  
 Die \[MS\-XAML\]\-Spezifikation definiert die XamlName\-Grammatik zur Kennzeichnung der Gruppe der zulässigen symbolischen Bezeichner für Typen und Eigenschaften.  
  
 Zeichenfolgenwerte des Typs XamlName müssen der folgenden Grammatik entsprechen:  
  
```  
XamlName ::= NameStartChar ( NameChar )*   
NameStartChar ::= LetterCharacter | '_'   
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter   
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl   
DecimalDigit ::= UnicodeNd   
CombiningCharacter ::= UnicodeMn | UnicodeMc  
  
```  
  
 Es können folgende allgemeine Kategoriewerte gemäß der Definition in der Unicode\-Zeichendatenbank angenommen werden:  
  
```  
  
Lu  
Letter, Uppercase  
Ll  
Letter, Lowercase  
Lt  
Letter, Titlecase  
Lm  
Letter, Modifier  
Lo  
Letter, Other  
Mn  
Mark, Non-Spacing  
Mc  
Mark, Spacing Combining  
Nd  
Number, Decimal  
Nl  
Number, Letter  
```  
  
 XAML definiert eine zweite Grammatik, DottedXamlName, die für qualifizierte Eigenschaften\- und Ereignisverweise sowie für angefügte Member verwendet wird.  Weitere Informationen finden Sie unter <xref:System.Windows.DependencyProperty> und [Übersicht über XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
 Zeichenfolgenwerte des Typs DottedXamlName müssen der folgenden Grammatik entsprechen:  
  
```  
DottedXamlName ::= XamlName '.' XamlName  
```  
  
## Hinweise  
 Die vollständige Spezifikation finden Sie unter [\[MS\-XAML\] Abschnitt 5.2.6](http://go.microsoft.com/fwlink/?LinkId=114525).