---
title: Verwenden von Schriftarten und Text
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-fonts-and-text"></a>Verwenden von Schriftarten und Text
Es gibt mehrere Klassen von Angeboten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text in Windows Forms. Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> -Klasse verfügt über mehrere <xref:System.Drawing.Graphics.DrawString%2A> Methoden, die Ihnen ermöglichen, verschiedene Funktionen des Texts, z. B. der Speicherort, umgebende Rechteck, Schriftart und Format anzugeben. Darüber hinaus können Sie zeichnen und Messen von Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mithilfe der statischen <xref:System.Windows.Forms.TextRenderer.DrawText%2A> und <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> Methoden bereitgestellt werden, indem die `TextRenderer` Klasse. Die [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Methoden ermöglichen auch die Position, Schriftart und Format angeben. Stehen Ihnen beide [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oder [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Textrendering; allerdings [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bietet im Allgemeinen besser, Leistung und genauere Text messen. Schließen Sie andere Klassen, die zum Rendern von Text beitragen `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, und `TextFormatFlags`.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst wie: Erstellen von Schriftartfamilien und Schriftarten](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Zeigt, wie `Font` und `FontFamily` Objekte.  
  
 [Gewusst wie: Zeichnen von Text an einer angegebenen Position](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Beschreibt, wie Zeichnen von Text in einem bestimmten Speicherort mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Gewusst wie: Zeichnen von umbrochenem Text in einem Rechteck](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Erläutert das Zeichnen von Text in einem Rechteck von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Gewusst wie: Zeichnen von Text mit GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Veranschaulicht, wie [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text.  
  
 [Gewusst wie: Ausrichten von gezeichnetem Text](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Veranschaulicht das Formatieren von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Text.  
  
 [Gewusst wie: Erstellen von vertikalem Text](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Beschreibt das Zeichnen von Texts mit vertikal ausgerichteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Veranschaulicht das Zeichnen von Text mit Tabstopps mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Gewusst wie: Auflisten installierter Schriftarten](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Erläutert, wie die Namen der installierten Schriftarten aufgelistet.  
  
 [Gewusst wie: Erstellen einer privaten Schriftartenauflistung](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Enthält Informationen zum Erstellen einer <xref:System.Drawing.Text.PrivateFontCollection> Objekt.  
  
 [Gewusst wie: Abrufen von Schriftarteigenschaften](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Veranschaulicht das Abrufen von Schriftarteigenschaften wie Versalhöhe und Unterlänge.  
  
 [Gewusst wie: Verwenden der Bildkantenglättung mit Text](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 Erklärt, wie Antialiasing beim Zeichnen von Text.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Drawing.Font>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Drawing.FontFamily>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.
