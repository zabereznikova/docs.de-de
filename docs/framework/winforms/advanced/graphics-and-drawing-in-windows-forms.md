---
title: Grafiken und zeichnen
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746406"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Grafik und Zeichnen in Windows Forms
Die Common Language Runtime verwendet eine erweiterte Implementierung der Windows Graphics Device Interface (GDI) mit dem Namen GDI+. Mit GDI+ können Sie Grafiken erstellen, Text zeichnen und grafische Bilder als Objekte bearbeiten. GDI+ wurde entwickelt, um Leistung und Benutzerfreundlichkeit zu bieten. Mit GDI+ können Sie grafische Bilder auf Windows Forms-und-Steuerelementen darstellen. Obwohl Sie GDI+ nicht direkt auf Web Forms verwenden können, können Sie grafische Bilder mit dem Image-Webserver Steuerelement anzeigen.  
  
 In diesem Abschnitt finden Sie Themen, in denen die Grundlagen der GDI+-Programmierung vorgestellt werden. Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern. Weitere Informationen finden Sie unter [GDI+-Referenz](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md). Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Grafiken](graphics-overview-windows-forms.md)  
 Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.  
  
 [Verwalteter Code in GDI+](about-gdi-managed-code.md)  
 Stellt Informationen zu den verwalteten GDI+-Klassen bereit.  
  
 [Verwenden von verwalteten Grafikklassen](using-managed-graphics-classes.md)  
 Veranschaulicht, wie eine Vielzahl von Tasks mithilfe der verwalteten GDI+-Klassen ausgeführt wird.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Drawing>  
 Bietet Zugriff auf die grundlegenden GDI+-Grafikfunktionen.  
  
 <xref:System.Drawing.Drawing2D>  
 Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.  
  
 <xref:System.Drawing.Imaging>  
 Stellt erweiterte GDI+-Bildverarbeitungsfunktionen bereit.  
  
 <xref:System.Drawing.Text>  
 Stellt erweiterte GDI+-Typografiefunktionen bereit. Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.  
  
 <xref:System.Drawing.Printing>  
 Stellt Druckfunktionen bereit.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Zeichnen und Rendern von benutzerdefinierten Steuerelementen](../controls/custom-control-painting-and-rendering.md)  
 Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.
