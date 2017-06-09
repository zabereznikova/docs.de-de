---
title: "ColorConvertedBitmap-Markuperweiterung | Microsoft Docs"
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
  - "ColorConvertedBitmap-Markuperweiterung"
  - "XAML, ColorConvertedBitmap-Markuperweiterung"
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# ColorConvertedBitmap-Markuperweiterung
Bietet eine Möglichkeit zur Angabe einer Bitmapquelle, die über kein eingebettetes Profil verfügt.  Farbkontexte\/\-profile werden durch [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] angegeben, wie auch der Bildquellen\-[!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`imageSource`|Der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der profillosen Bitmap.|  
|`sourceIIC`|Der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der Quellprofilkonfiguration.|  
|`destinationIIC`|Der [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der Zielprofilkonfiguration.|  
  
## Hinweise  
 Diese Markuperweiterung ist dazu vorgesehen, eine zugehörige Gruppe von Eigenschaftswerten der Bildquelle wie <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A> auszufüllen.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  `ColorConvertedBitmap` \(oder `ColorConvertedBitmapExtension`\) kann in der Eigenschaftenelementsyntax nicht verwendet werden, da die Werte nur als Werte für den ursprünglichen Konstruktor festgelegt werden können, wobei es sich um die auf den Erweiterungsbezeichner folgende Zeichenfolge handelt.  
  
 `ColorConvertedBitmap` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden die Zeichen { und } in der Attributsyntax. Dies ist die Konvention, anhand der ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)