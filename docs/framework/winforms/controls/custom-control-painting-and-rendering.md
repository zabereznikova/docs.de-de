---
title: Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 355a5842348aa4395d1841d0343080ddef634456
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="custom-control-painting-and-rendering"></a>Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
Benutzerdefiniertes Zeichnen von Steuerelementen ist einer der zahlreichen komplizierten Aufgaben, die leicht, von .NET Framework. Wenn Sie ein benutzerdefiniertes Steuerelement zu erstellen, stehen Ihnen viele Optionen zur grafischen Darstellung des Steuerelements. Wenn Sie ein Steuerelement erstellen, die von erben die `Control`, müssen Sie Code, der das Steuerelement zum Rendern der grafischen Darstellung ermöglicht bereitstellen. Wenn Sie ein Benutzersteuerelement erstellen durch Erben von der `UserControl`, oder erben werden aus einer Windows Forms-Steuerelemente, können Sie außer Kraft setzen die standardmäßige grafische Darstellung und fügen Sie eigenen Code Grafiken. Wenn Sie benutzerdefiniertes Rendering für die konstituierenden Steuerelemente bereitstellen möchten eine `UserControl` Sie erstellen, die Optionen eingeschränkt werden, aber weiterhin eine Breite Palette von grafischen Möglichkeiten für Steuerelemente und Anwendungen zu ermöglichen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Wiedergeben eines Windows Forms-Steuerelements](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 Veranschaulicht das Programmieren der Logik, die ein Steuerelement angezeigt.  
  
 [Benutzerdefinierte Steuerelemente](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 Bietet einen Überblick über die Schritte zum Schreiben und überschreiben Code zum Rendern des Steuerelements.  
  
 [Konstituierende Steuerelemente](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 Beschreibt, wie benutzerdefinierte Renderingcodes für konstituierende Steuerelemente in Ihrer Benutzersteuerelementen und-Formularen implementieren.  
  
 [Gewusst wie: Ausblenden des Steuerelements zur Laufzeit](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 Zeigt, wie die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft aus-und Einblenden eines Steuerelements.  
  
 [Gewusst wie: Verwenden eines transparenten Hintergrunds für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 Zeigt, wie die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode, um eine Hintergrundfarbe zu erstellen, die nicht transparenten, transparent oder teilweise transparent ist.  
  
 [Rendering von Steuerelementen mit visuellen Stilen](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 Zeigt, wie zum Rendern von Steuerelementen mit visuellen Stilen in Betriebssystemen, die sie unterstützen.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Windows.Forms.Control>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.UserControl>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Wird diese Methode beschrieben.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Gewusst wie: Erstellen von Grafikobjekten zum Zeichnen](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Führt [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Grafikfunktionen aus einer Visual Studio-Perspektive und enthält Links zu weiteren Informationen.  
  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 Beschreibt die Arten von benutzerdefinierten Steuerelementen, die Sie erstellen können.
