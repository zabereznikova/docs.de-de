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
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505121"
---
# <a name="using-fonts-and-text"></a>Verwenden von Schriftarten und Text
Es gibt mehrere Klassen, die zum Zeichnen von Text in Windows Forms von GDI + und GDI angeboten. Die GDI + <xref:System.Drawing.Graphics> -Klasse verfügt über mehrere <xref:System.Drawing.Graphics.DrawString%2A> Methoden, die Ihnen ermöglichen, verschiedene Funktionen des Texts an, wie Standort, umschließendes Rechteck, Schriftart und Format anzugeben. Darüber hinaus können Sie zeichnen und messen Sie Text mit GDI, die mit der statischen <xref:System.Windows.Forms.TextRenderer.DrawText%2A> und <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> Methoden bereitgestellt werden, indem die `TextRenderer` Klasse. Die GDI-Methoden ermöglichen auch Sie Format, Schriftart und Speicherort angeben. Sie können zum Rendern von Text GDI oder GDI + auswählen; GDI bietet jedoch im Allgemeinen eine bessere Leistung und genauere Text messen. Andere Klassen, die zum Rendern von Text beitragen sind `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, und `TextFormatFlags`.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten](how-to-construct-font-families-and-fonts.md)  
 Veranschaulicht das Erstellen `Font` und `FontFamily` Objekte.  
  
 [Vorgehensweise: Zeichnen von Text an einer angegebenen Position](how-to-draw-text-at-a-specified-location.md)  
 Beschreibt, wie Text in einem bestimmten Speicherort mit GDI + und GDI gezeichnet werden soll.  
  
 [Vorgehensweise: Zeichnen von umbrochenem Text in einem Rechteck](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Erläutert, wie Text in einem Rechteck mit GDI + und GDI gezeichnet werden soll.  
  
 [Vorgehensweise: Zeichnen von Text mit GDI](how-to-draw-text-with-gdi.md)  
 Veranschaulicht, wie GDI zum Zeichnen von Text.  
  
 [Vorgehensweise: Ausrichten von gezeichnetem Text](how-to-align-drawn-text.md)  
 Veranschaulicht, wie GDI + und GDI-Text zu formatieren.  
  
 [Vorgehensweise: Erstellen von vertikalem Text](how-to-create-vertical-text.md)  
 Beschreibt, wie vertikal ausgerichteten Text mit GDI + gezeichnet werden soll.  
  
 [Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text](how-to-set-tab-stops-in-drawn-text.md)  
 Veranschaulicht das Zeichnen von Text mit Tabstopps mit GDI +.  
  
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
