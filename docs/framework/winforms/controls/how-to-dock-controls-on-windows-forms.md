---
title: 'Vorgehensweise: Andocken von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: d015dce7307bec092f6da1dc5ee31691a6baf1f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941496"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Vorgehensweise: Andocken von Steuerelementen in Windows Forms
Sie können Andocken von Steuerelementen an den Rändern des Formulars oder Sie geben Sie im Container des Steuerelements (ein Formular oder ein Container-Steuerelement). Beispielsweise Windows-Explorer angedockt seine <xref:System.Windows.Forms.TreeView> Steuerelement auf der linken Seite des Fensters und die zugehörige <xref:System.Windows.Forms.ListView> Steuerelement auf die rechte Seite des Fensters. Verwenden der <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft für alle sichtbaren Windows Forms-Steuerelemente, um den Andockmodus zu definieren.  
  
> [!NOTE]
>  Steuerelemente werden in umgekehrter Z-Reihenfolge angedockt.  
  
 Die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>So docken Sie ein Steuerelement an  
  
1. Wählen Sie das Steuerelement, das Sie andocken möchten.  
  
2. Klicken Sie im Eigenschaftenfenster auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft.  
  
     Ein Editor wird mit einer Reihe von Feldern, die darstellt, die Kanten und der Mitte des Formulars angezeigt.  
  
3. Klicken Sie auf die Schaltfläche ", die den Rand des Formulars darstellt, in dem das Steuerelement angedockt werden soll. Klicken Sie auf das mittlere Feld, um den Inhalt des Steuerelements Formular oder Containersteuerelement zu füllen. Klicken Sie auf **(keine)** zum Andocken zu deaktivieren.  
  
     Das Steuerelement wird automatische größenanpassung die Grenzen der verankerten Kante.  
  
    > [!NOTE]
    >  Geerbte Steuerelemente muss `Protected` angedockt werden kann. Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen **Modifizierer** Eigenschaft im Eigenschaftenfenster angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Windows Forms-Steuerelemente](index.md)
- [Anordnen von Steuerelementen in Windows Forms](arranging-controls-on-windows-forms.md)
- [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
- [Windows Forms-Steuerelemente nach Funktion](windows-forms-controls-by-function.md)
- [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)
- [Vorgehensweise: Verankern von Steuerelementen in Windows Forms](how-to-anchor-controls-on-windows-forms.md)
