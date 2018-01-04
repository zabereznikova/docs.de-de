---
title: Grafik und Zeichnen in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8ae9810b10a7357f7f8d00783335335a391a5211
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Grafik und Zeichnen in Windows Forms
Die Common Language Runtime verwendet eine erweiterte Implementierung der Windows-Grafikdesignoberfläche ([!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]), die so genannte [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] können Sie Grafiken erstellen, Text zeichnen und grafische Bilder als Objekte bearbeiten. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] vereint Leistung und Komfort. Mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] lassen sich grafische Bilder in Windows Forms und Steuerelementen rendern. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann zwar in Web Forms nicht direkt verwendet werden, jedoch können Sie grafische Bilder mit dem Image-Webserversteuerelement anzeigen.  
  
 Dieser Abschnitt enthält Themen, die Sie in die Grundlagen der Programmierung mit [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] einführen. Er ist nicht als umfassende Referenz gedacht, sondern enthält Informationen zu den Objekten <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> und <xref:System.Drawing.Color> und erläutert die Ausführung von Aufgaben wie Zeichnen von Formen, Zeichnen von Text oder Anzeigen von Bildern. Weitere Informationen finden Sie unter [GDI + Verweis](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).  
  
 Wenn Sie gleich einsteigen möchten, lesen Sie [Erste Schritte mit der Grafikprogrammierung](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md). Hier finden Sie Themen zur Verwendung von Code zum Zeichnen von u. a. Linien, Formen und Text in Windows Forms.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über Grafiken](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 Enthält eine Einführung in die Arbeit mit Grafiken und verwalteten Klassen.  
  
 [Verwalteter Code in GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 Enthält Informationen zu den verwalteten Klassen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Verwenden von verwalteten Grafikklassen](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 Veranschaulicht die Ausführung verschiedener Aufgaben mithilfe der verwalteten Klassen in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
## <a name="reference"></a>Verweis  
 <xref:System.Drawing>  
 Ermöglicht den Zugriff auf die grundlegenden [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Grafikfunktionen.  
  
 <xref:System.Drawing.Drawing2D>  
 Stellt erweiterte Funktionen für zweidimensionale Grafiken und Vektorgrafiken bereit.  
  
 <xref:System.Drawing.Imaging>  
 Stellt erweiterte [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Bildfunktionen bereit.  
  
 <xref:System.Drawing.Text>  
 Stellt erweiterte [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]-Typografiefunktionen bereit. Die Klassen in diesem Namespace können zum Erstellen und Verwenden von Schriftartauflistungen verwendet werden.  
  
 <xref:System.Drawing.Printing>  
 Stellt Druckfunktionen bereit.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Zeichnen und Rendern von benutzerdefinierten Steuerelementen](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 Erläutert die Bereitstellung von Code zum Zeichnen von Steuerelementen.
