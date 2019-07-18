---
title: Grafik und Zeichnen in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505539"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Grafik und Zeichnen in Windows Forms
Die common Language Runtime verwendet eine erweiterte Implementierung von der Windows Graphics Device Interface (GDI) wird aufgerufen, GDI +. Mit GDI + können Sie Grafiken erstellen, Zeichnen von Text und Bearbeiten von Bildern als Objekte. GDI + soll Leistung und benutzerfreundlichkeit bieten. GDI + können zum Rendern von Grafiken in Windows Forms und Steuerelementen. Obwohl Sie GDI + in Web Forms nicht direkt verwendet, können Sie grafische Bilder mit der Image-Webserversteuerelement anzeigen.  
  
 In diesem Abschnitt finden Sie Themen, in denen die Grundlagen der Programmierung von GDI + eingeführt. Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern. Weitere Informationen finden Sie unter [GDI + Verweis](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](getting-started-with-graphics-programming.md). Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Grafiken](graphics-overview-windows-forms.md)  
 Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.  
  
 [Verwalteter Code in GDI+](about-gdi-managed-code.md)  
 Enthält Informationen zu den verwalteten GDI +-Klassen.  
  
 [Verwenden von verwalteten Grafikklassen](using-managed-graphics-classes.md)  
 Veranschaulicht, wie zum Abschluss eine Vielzahl von Aufgaben, die mithilfe von GDI + Klassen verwaltet.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Drawing>  
 Bietet Zugriff auf die grundlegende GDI +-Grafikfunktionen.  
  
 <xref:System.Drawing.Drawing2D>  
 Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.  
  
 <xref:System.Drawing.Imaging>  
 Stellt erweiterte GDI +-Grafikfunktionen.  
  
 <xref:System.Drawing.Text>  
 Stellt erweiterte GDI +-Typografiefunktionen bereit. Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.  
  
 <xref:System.Drawing.Printing>  
 Stellt Druckfunktionen bereit.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Zeichnen und Rendern von benutzerdefinierten Steuerelementen](../controls/custom-control-painting-and-rendering.md)  
 Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.
