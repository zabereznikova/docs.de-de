---
title: Übersicht über ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
ms.openlocfilehash: 405d06a8da8ec5c428c1565bcd08236de0f1fa88
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68672056"
---
# <a name="cleartype-overview"></a>Übersicht über ClearType
Dieses Thema enthält eine Übersicht über die Microsoft ClearType-Technologie, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]in der enthalten ist.  

<a name="overview"></a>   
## <a name="technology-overview"></a>Übersicht über die Technologie  
 ClearType ist eine von entwickelte Softwaretechnologie [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] , mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), wie z. b. Laptop Bildschirmen, Pocket PC-Bildschirme und Flatpanel-Monitoren, verbessert wird.  ClearType funktioniert, indem auf die einzelnen vertikalen Farbstreifen Elemente in jedem Pixel eines LCD-Bildschirms zugegriffen wird. Vor ClearType war der kleinste Detailgrad, der von einem Computer angezeigt werden konnte, ein einzelnes Pixel, aber mit ClearType, der auf einem LCD-Monitor ausgeführt wird, können wir jetzt Funktionen von Text anzeigen, die kleiner als ein Bruchteil eines Pixels in der Breite sind. Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details in der Textanzeige, was das Lesen über lange Zeiträume hinweg erleichtert.  
  
 Der in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verfügbare ClearType ist die neueste Generation von ClearType, die über mehrere Verbesserungen gegenüber der Version in Microsoft Windows Graphics Device Interface (GDI) verfügt.  
  
<a name="sub-pixel_positioning"></a>   
## <a name="sub-pixel-positioning"></a>Subpixel-Positionierung  
 Eine bedeutende Verbesserung gegenüber der früheren Version von ClearType ist die Verwendung der unter Pixel Positionierung. Anders als bei der ClearType-Implementierung in GDI ermöglicht der ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in, dass Glyphen innerhalb des Pixels gestartet werden und nicht nur die Anfangs Grenze des Pixels. Aufgrund dieser zusätzlichen Auflösung bei der Positionierung von Glyphen sind deren Abstände und Proportionen präziser und einheitlicher.  
  
 In den folgenden zwei Beispielen wird gezeigt, dass Glyphen auf jeder Subpixelgrenze beginnen können, wenn die Subpixel-Positionierung verwendet wird. Das Beispiel auf der linken Seite wird mit der früheren Version des ClearType-Renderers gerendert, der keine unter Pixel Positionierung verwendet hat. Das Beispiel auf der rechten Seite wird mithilfe der neuen Version des ClearType-Renderers gerendert, wobei die unter Pixel Positionierung verwendet wird. Beachten Sie, dass die Buchstaben **e** und **l** im Bild rechts minimal anders gerendert werden, da jedes auf einem anderen Subpixel beginnt. Wenn den Text in Normalgröße auf dem Bildschirm angezeigt wird, ist dieser Unterschied aufgrund des hohen Kontrasts des Glyphenbilds nicht wahrnehmbar. Dies ist nur möglich, da die in ClearType enthaltene hoch entwickelte Farb Filterung ist.  
  
 ![Mit zwei Versionen von ClearType angezeigter Text](./media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
Mit zwei Versionen von ClearType angezeigter Text  
  
 In den folgenden beiden Beispielen wird die Ausgabe des vorherigen ClearType-Renderers mit der neuen Version des ClearType-Renderers verglichen. Die rechts dargestellte Subpixel-Positionierung verbessert den Abstand zwischen Buchstaben auf dem Bildschirm erheblich, insbesondere bei kleinen Schriftgrößen, bei denen der Unterschied zwischen einem Subpixel und einem Pixel einen bedeutenden Anteil an der Glyphenbreite ausmacht. Es ist deutlich zu sehen, dass der Abstand zwischen den Buchstaben im zweiten Bild gleichmäßiger ist. Der kumulative Vorteil der untergeordneten Pixel Positionierung auf die allgemeine Darstellung eines Bildschirms wird erheblich erhöht und stellt eine bedeutende Weiterentwicklung in ClearType-Technologie dar.  
  
 ![Mit einer früheren Version von ClearType angezeigter Text](./media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
Mit einer früheren Version von ClearType angezeigter Text  
  
<a name="y-direction_antialiasing"></a>   
## <a name="y-direction-antialiasing"></a>Antialiasing auf der y-Achse  
 Eine weitere Verbesserung von ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in ist das Antialiasing in y-Richtung. Der ClearType in GDI ohne y-Direction-Antialiasing bietet eine bessere Auflösung auf der x-Achse, aber nicht auf der y-Achse. Die Lesbarkeit wird über und unter flachen Kurven durch gezackte Kanten beeinträchtigt.  
  
 Im folgenden Beispiel werden die Auswirkungen von fehlendem Antialiasing auf der y-Achse dargestellt. Die gezackten Kanten oben und unten am Buchstaben treten deutlich hervor.  
  
 ![Text mit verzweigten Kanten an flachen Kurven](./media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
Text mit Flatterrändern an flachen Kurven  
  
 ClearType in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Antialiasing auf der Ebene der y-Richtung, um alle verzweigten Kanten zu glätten. Dies ist besonders für die Verbesserung der Lesbarkeit ostasiatischer Sprachen wichtig, in denen Ideogramme über nahezu gleiche Anteile von horizontalen und vertikalen flachen Kurven verfügen.  
  
 Im folgenden Beispiel wird die Auswirkung von Antialiasing auf der y-Achse gezeigt. In diesem Fall weisen der obere und untere Rand des Buchstabens eine glatte Kurve auf.  
  
 ![Text mit ClearType-&#45;Antialiasing&#45;in y-Richtung](./media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
Text mit ClearType-Antialiasing auf der y-Achse  
  
<a name="hardware_acceleration"></a>   
## <a name="hardware-acceleration"></a>Hardwarebeschleunigung  
 ClearType in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] kann die Hardwarebeschleunigung nutzen, um die Leistung zu verbessern und die CPU-Auslastung und die Systemspeicher Anforderungen zu reduzieren. Mithilfe der Pixel-Shader und des Video Speichers einer Grafikkarte bietet ClearType ein schnelleres Rendering von Text, insbesondere dann, wenn Animation verwendet wird.  
  
 ClearType in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ändert nicht die systemweiten ClearType-Einstellungen. Deaktivieren von ClearType in [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] legt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] das Antialiasing auf den Graustufen Modus fest. Außerdem ändert ClearType in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nicht die Einstellungen des [ClearType-tunerpowertoy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx).  
  
 Eine der Designentscheidungen hinsichtlich der Architektur von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bestand darin, dass das von Auflösung unabhängige Layout höher auflösende DPI-Monitore besser unterstützen soll, da diese immer mehr Verbreitung finden. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] unterstützt daher weder Textrendering mit Aliasing noch die Bitmaps in bestimmten ostasiatischen Schriftarten, da beides von der Auflösung abhängt.  
  
<a name="further_information"></a>   
## <a name="further-information"></a>Weitere Informationen  
 [ClearType Information (ClearType-Informationen)](https://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType Tuner PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>Siehe auch

- [ClearType Registry Settings (ClearType-Registrierungseinstellungen)](cleartype-registry-settings.md)
