---
title: Übersicht über ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
ms.openlocfilehash: 0127ee4112c4b42a7a55b9233217ea1e02604042
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085193"
---
# <a name="cleartype-overview"></a>Übersicht über ClearType
Dieses Thema bietet eine Übersicht über die [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]-Technologie in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  

<a name="overview"></a>   
## <a name="technology-overview"></a>Übersicht über die Technologie  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] ist eine von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] entwickelte Softwaretechnologie, mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), z.B. auf Laptopbildschirmen, Pocket PC-Bildschirmen und Flachbildschirmen, optimiert wird.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] greift dabei auf die einzelnen vertikalen Farbstreifenelemente in jedem Pixel auf einem LCD-Bildschirm zu. Vor [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] war ein einzelnes Pixel das kleinste Detail, das auf einem Computer angezeigt werden konnte. Mithilfe von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] können Texteigenschaften, die nur einen Bruchteil eines Pixels groß sind, auf einem LCD-Bildschirm dargestellt werden. Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details in der Textanzeige, was das Lesen über lange Zeiträume hinweg erleichtert.  
  
 Die in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verfügbare [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Technologie gehört der aktuellsten Generation von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] an, die gegenüber der Version in [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] zahlreiche Verbesserungen enthält.  
  
<a name="sub-pixel_positioning"></a>   
## <a name="sub-pixel-positioning"></a>Subpixel-Positionierung  
 Eine erhebliche Verbesserung gegenüber der vorherigen Version von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] ist die Subpixel-Positionierung. Im Gegensatz zur [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Implementierung in [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] können Glyphen in [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] innerhalb des Pixels beginnen und nicht erst an der Pixelgrenze. Aufgrund dieser zusätzlichen Auflösung bei der Positionierung von Glyphen sind deren Abstände und Proportionen präziser und einheitlicher.  
  
 In den folgenden zwei Beispielen wird gezeigt, dass Glyphen auf jeder Subpixelgrenze beginnen können, wenn die Subpixel-Positionierung verwendet wird. Das Beispiel links wird mithilfe der früheren Version des [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Renderers gerendert, der keine Subpixel-Positionierung verwendete. Das Beispiel rechts wird mithilfe der neuen Version des [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Renderers mit der Subpixel-Positionierung gerendert. Beachten Sie, dass die Buchstaben **e** und **l** im Bild rechts minimal anders gerendert werden, da jedes auf einem anderen Subpixel beginnt. Wenn den Text in Normalgröße auf dem Bildschirm angezeigt wird, ist dieser Unterschied aufgrund des hohen Kontrasts des Glyphenbilds nicht wahrnehmbar. Dies ist nur wegen der komplexen, in [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] integrierten Farbfilterung möglich.  
  
 ![Mit zwei Versionen von ClearType angezeigter Text](./media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
Mit zwei Versionen von ClearType angezeigter Text  
  
 In den folgenden beiden Beispielen wird die Ausgabe des älteren [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Renderers mit der neuen Version des [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Renderers verglichen. Die rechts dargestellte Subpixel-Positionierung verbessert den Abstand zwischen Buchstaben auf dem Bildschirm erheblich, insbesondere bei kleinen Schriftgrößen, bei denen der Unterschied zwischen einem Subpixel und einem Pixel einen bedeutenden Anteil an der Glyphenbreite ausmacht. Es ist deutlich zu sehen, dass der Abstand zwischen den Buchstaben im zweiten Bild gleichmäßiger ist. Der kumulierte Vorteil der Subpixel-Positionierung für die Gesamtdarstellung eines Texts auf einem Bildschirm erhöht sich damit beträchtlich und stellt eine wesentliche Weiterentwicklung der [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Technologie dar.  
  
 ![Mit einer früheren Version von ClearType angezeigter Text](./media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
Mit einer früheren Version von ClearType angezeigter Text  
  
<a name="y-direction_antialiasing"></a>   
## <a name="y-direction-antialiasing"></a>Antialiasing auf der y-Achse  
 Eine weitere Verbesserung von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist das Antialiasing in y-Richtung. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] ohne Antialiasing in y-Richtung liefert zwar eine bessere Auflösung auf der x-Achse, nicht jedoch auf der y-Achse. Die Lesbarkeit wird über und unter flachen Kurven durch gezackte Kanten beeinträchtigt.  
  
 Im folgenden Beispiel werden die Auswirkungen von fehlendem Antialiasing auf der y-Achse dargestellt. Die gezackten Kanten oben und unten am Buchstaben treten deutlich hervor.  
  
 ![Text mit gezackten Kanten an flachen Kurven](./media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
Text mit Flatterrändern an flachen Kurven  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt Antialiasing auf der y-Achse zum Glätten der gezackten Kanten bereit. Dies ist besonders für die Verbesserung der Lesbarkeit ostasiatischer Sprachen wichtig, in denen Ideogramme über nahezu gleiche Anteile von horizontalen und vertikalen flachen Kurven verfügen.  
  
 Im folgenden Beispiel wird die Auswirkung von Antialiasing auf der y-Achse gezeigt. In diesem Fall weisen der obere und untere Rand des Buchstabens eine glatte Kurve auf.  
  
 ![Text mit ClearType-y&#45;Richtung&#45;Aliasing](./media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
Text mit ClearType-Antialiasing auf der y-Achse  
  
<a name="hardware_acceleration"></a>   
## <a name="hardware-acceleration"></a>Hardwarebeschleunigung  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] kann die Hardwarebeschleunigung nutzen, um eine bessere Leistung zu erzielen und die CPU-Auslastung und die Systemspeicheranforderungen zu verringern. Mithilfe der Pixelshader und Videospeicher einer Grafikkarte stellt [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] schnelleres Rendering von Text bereit, besonders bei Animationen.  
  
 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ändert die systemweiten [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Einstellungen nicht. Durch das Deaktivieren von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] wird das [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Antialiasing auf den Graustufenmodus festgelegt. Darüber hinaus ändert [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nicht die Einstellungen von [ClearType Tuner PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx).  
  
 Eine der Designentscheidungen hinsichtlich der Architektur von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bestand darin, dass das von Auflösung unabhängige Layout höher auflösende DPI-Monitore besser unterstützen soll, da diese immer mehr Verbreitung finden. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt daher weder Textrendering mit Aliasing noch die Bitmaps in bestimmten ostasiatischen Schriftarten, da beides von der Auflösung abhängt.  
  
<a name="further_information"></a>   
## <a name="further-information"></a>Weitere Informationen  
 [ClearType Information (ClearType-Informationen)](https://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType Tuner PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>Siehe auch

- [ClearType Registry Settings (ClearType-Registrierungseinstellungen)](cleartype-registry-settings.md)
