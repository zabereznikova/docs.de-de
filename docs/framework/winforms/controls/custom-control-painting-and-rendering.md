---
title: Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: ec9002ffa4a7e2c82f59d52344764a01afe4c568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722138"
---
# <a name="custom-control-painting-and-rendering"></a>Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen
Benutzerdefinierte Zeichnen von Steuerelementen ist einer der zahlreichen komplizierteren Aufgaben, die leicht gemacht, die von .NET Framework. Wenn Sie ein benutzerdefiniertes Steuerelement erstellen zu können, stehen Ihnen viele Optionen in Bezug auf die grafische Darstellung des Steuerelements. Wenn Sie ein Steuerelement erstellen, die von erbt die `Control`, müssen Sie Code, der das Steuerelement zum Rendern der grafischen Darstellung ermöglicht angeben. Wenn Sie ein Benutzersteuerelement erstellen durch Erben von der `UserControl`, oder werden erben von einer Windows Forms-Steuerelemente, können Sie außer Kraft setzen die standardmäßige grafische Darstellung und bieten Sie Ihren eigenen Grafikcode. Wenn Sie benutzerdefiniertes Rendering für die konstituierenden Steuerelemente bereitstellen möchten eine `UserControl` Sie erstellen, die Optionen stärker eingeschränkt werden, aber immer noch eine Vielzahl von grafischen Möglichkeiten für Ihre Steuerelemente und Anwendungen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Wiedergeben eines Windows Forms-Steuerelements](rendering-a-windows-forms-control.md)  
 Zeigt, wie die Logik zu programmieren, die einem Steuerelement angezeigt.  
  
 [Benutzerdefinierte Steuerelemente](user-drawn-controls.md)  
 Bietet eine Übersicht über die Schritte zum Schreiben und das Überschreiben von Code für das Steuerelement rendern.  
  
 [Konstituierende Steuerelemente](constituent-controls.md)  
 Beschreibt, wie benutzerdefinierte Rendering-Code für konstituierende Steuerelemente in Ihre Steuerelemente und Formulare zu implementieren.  
  
 [Vorgehensweise: Ausblenden des Steuerelements zur Laufzeit](how-to-make-your-control-invisible-at-run-time.md)  
 Zeigt, wie die <xref:System.Windows.Forms.Control.Visible%2A> Eigenschaft aus-und Einblenden eines Steuerelements.  
  
 [Vorgehensweise: Fügen Sie dem Steuerelement einen transparenten Hintergrund](how-to-give-your-control-a-transparent-background.md)  
 Zeigt, wie die <xref:System.Windows.Forms.Control.SetStyle%2A> Methode, um eine Hintergrundfarbe zu erstellen, die nicht transparenten, transparente oder teilweise transparent ist.  
  
 [Rendering von Steuerelementen mit visuellen Stilen](rendering-controls-with-visual-styles.md)  
 Zeigt, wie zum Rendern von Steuerelementen mit visuellen Stilen in Betriebssystemen, die sie unterstützen.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.Control>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.UserControl>  
 Beschreibt diese Klasse und enthält Links zu allen Membern.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Wird diese Methode beschrieben.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Vorgehensweise: Erstellen von Grafikobjekten zum Zeichnen](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 Führt [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Grafikfunktionen von Visual Studio Perspektive und bietet Links zu weiteren Informationen.  
  
 [Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)](varieties-of-custom-controls.md)  
 Beschreibt die Arten von benutzerdefinierten Steuerelementen, die Sie erstellen können.
