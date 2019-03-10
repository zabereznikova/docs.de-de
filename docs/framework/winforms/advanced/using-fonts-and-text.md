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
ms.openlocfilehash: c9fe16752223203806c7d3828f632aad0cab0c28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703366"
---
# <a name="using-fonts-and-text"></a>Verwenden von Schriftarten und Text
Es gibt mehrere Klassen von angebotenen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text in Windows Forms. Die [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> -Klasse verfügt über mehrere <xref:System.Drawing.Graphics.DrawString%2A> Methoden, die Ihnen ermöglichen, verschiedene Funktionen des Texts an, wie Standort, umschließendes Rechteck, Schriftart und Format anzugeben. Darüber hinaus können Sie zeichnen und messen Sie Text mit [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] mit der statischen <xref:System.Windows.Forms.TextRenderer.DrawText%2A> und <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> Methoden bereitgestellt werden, indem die `TextRenderer` Klasse. Die [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Methoden auch ermöglichen es Ihnen an der Position, Schriftart und Format. Wählen Sie entweder [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] oder [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] zum Rendern von Text; allerdings [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] bietet im Allgemeinen besser, Leistung und genauere Text messen. Andere Klassen, die zum Rendern von Text beitragen sind `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, und `TextFormatFlags`.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](how-to-construct-font-families-and-fonts.md)  
 Veranschaulicht das Erstellen `Font` und `FontFamily` Objekte.  
  
 [Vorgehensweise: Zeichnen von Text an einer angegebenen Position](how-to-draw-text-at-a-specified-location.md)  
 Beschreibt die zum Zeichnen von Text in einem bestimmten Speicherort mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Erläutert das Zeichnen von Text in einem Rechteck mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)  
 Veranschaulicht, wie [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] zum Zeichnen von Text.  
  
 [Vorgehensweise: Ausrichten von gezeichnetem Text](how-to-align-drawn-text.md)  
 Veranschaulicht das Formatieren von [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Text.  
  
 [Vorgehensweise: Erstellen von vertikalem Text](how-to-create-vertical-text.md)  
 Beschreibt, wie Sie vertikal ausgerichteten Text mit zeichnen [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text](how-to-set-tab-stops-in-drawn-text.md)  
 Veranschaulicht das Zeichnen von Text mit Tabstopps mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Vorgehensweise: Auflisten installierter Schriftarten](how-to-enumerate-installed-fonts.md)  
 Es wird erläutert, wie die Namen der installierten Schriftarten aufzulisten.  
  
 [Vorgehensweise: Erstellen einer privaten Schriftartenauflistung](how-to-create-a-private-font-collection.md)  
 Beschreibt das Erstellen einer <xref:System.Drawing.Text.PrivateFontCollection> Objekt.  
  
 [Vorgehensweise: Abrufen von Schriftarteigenschaften](how-to-obtain-font-metrics.md)  
 Zeigt, wie zum Abrufen von Schriftarteigenschaften wie z. B. Zellaufstieg (Versalhöhe) und die Unterlänge.  
  
 [Vorgehensweise: Verwenden der Bildkantenglättung mit Text](how-to-use-antialiasing-with-text.md)  
 Erläutert, wie Antialiasing beim Zeichnen von Text.  
  
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
