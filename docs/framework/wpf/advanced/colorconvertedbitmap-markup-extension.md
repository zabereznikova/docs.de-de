---
title: ColorConvertedBitmap-Markuperweiterung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f1946ec2a5b607d9fce350da0676092d6e0407a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="colorconvertedbitmap-markup-extension"></a>ColorConvertedBitmap-Markuperweiterung
Bietet eine Möglichkeit, eine Bitmapquelle angeben, die nicht über ein eingebettetes Profil verfügt. Farbe von Kontexten / Profile werden angegeben, indem [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)], wie die Bildquelle [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)].  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`imageSource`|Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der profillosen Bitmap.|  
|`sourceIIC`|Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] der Profil-Quellkonfiguration.|  
|`destinationIIC`|Die [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] des Ziel-Profilkonfiguration|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Markuperweiterung soll z. B. eine zusammengehörige Gruppe von Image-Source-Eigenschaftswerte füllen <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. `ColorConvertedBitmap`(oder `ColorConvertedBitmapExtension`) kann nicht in eine Eigenschaftenelementsyntax, verwendet werden, da die Werte nur als Werte für den ursprünglichen Konstruktor festgelegt werden können, die Zeichenfolge ist der Erweiterungsbezeichner befolgen.  
  
 `ColorConvertedBitmap` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Übersicht über die Bildverarbeitung](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
