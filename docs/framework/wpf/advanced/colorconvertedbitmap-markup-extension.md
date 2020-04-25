---
title: ColorConvertedBitmap-Markuperweiterung
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], ColorConvertedBitmap markup extension
- ColorConvertedBitmap markup extension [WPF]
ms.assetid: 18321c18-c898-4470-93fa-a702b47770c1
ms.openlocfilehash: a5b491723a036c1b1fd0bb61736e6f2ee53fbcd3
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141230"
---
# <a name="colorconvertedbitmap-markup-extension"></a>ColorConvertedBitmap-Markuperweiterung
Bietet eine Möglichkeit, eine Bitmapquelle anzugeben, die kein eingebettetes Profil besitzt. Farb Kontexte/-Profile werden durch den URI angegeben, ebenso wie der Bildquellen-URI.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{ColorConvertedBitmap imageSource sourceIIC destinationIIC}" ... />
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`imageSource`|Der URI der Bitmap ohne Profilerstellung.|  
|`sourceIIC`|Der URI der Quell Profil Konfiguration.|  
|`destinationIIC`|Der URI der Ziel Profil Konfiguration.|  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Markup Erweiterung dient zum Auffüllen eines verknüpften Satzes von Bildquellen-Eigenschafts Werten, <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>wie z. b..  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. `ColorConvertedBitmap`(oder `ColorConvertedBitmapExtension`) kann nicht in der Eigenschafts Element Syntax verwendet werden, da die Werte nur als Werte für den ursprünglichen Konstruktor festgelegt werden können. Dies ist die Zeichenfolge, die auf den Erweiterungs Bezeichner folgt.  
  
 `ColorConvertedBitmap` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Imaging.BitmapImage.UriSource%2A>
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [Übersicht über die Bildverarbeitung](../graphics-multimedia/imaging-overview.md)
