---
title: "Gewusst wie: Andocken von Steuerelementen in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4897a195dcafb8264bbab619f1a46118a829f44e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Gewusst wie: Andocken von Steuerelementen in Windows Forms
Sie können Steuerelemente an den Rändern des Formulars angedockt oder Steuerelementcontainers (ein Formular oder Containersteuerelement) ausfüllen. Z. B. Windows-Explorer dockt an seine <xref:System.Windows.Forms.TreeView> Steuerelement auf der linken Seite des Fensters und die zugehörige <xref:System.Windows.Forms.ListView> Steuerelement auf die rechte Seite des Fensters. Verwenden der <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft für alle sichtbaren Windows Forms-Steuerelemente den Andockmodus definieren.  
  
> [!NOTE]
>  Steuerelemente werden in umgekehrter Z-Reihenfolge angedockt.  
  
 Die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft interagiert mit den <xref:System.Windows.Forms.Control.AutoSize%2A> Eigenschaft. Weitere Informationen finden Sie unter [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>So docken Sie ein Steuerelement an  
  
1.  Wählen Sie das Steuerelement, das Sie andocken möchten.  
  
2.  Klicken Sie im Fenster Eigenschaften auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft.  
  
     Ein Editor wird angezeigt, die eine Reihe von Feldern, die die Kanten und der Mitte des Formulars darstellt.  
  
3.  Klicken Sie auf die Schaltfläche ", die den Rand des Formulars darstellt, in dem das Steuerelement angedockt werden soll. Klicken Sie auf das mittlere Feld, um den Inhalt des Steuerelements Formular oder Containersteuerelement zu füllen. Klicken Sie auf **(keine)** zum Andocken zu deaktivieren.  
  
     Das Steuerelement wird automatisch die Grenzen des angedockten Rands entsprechend angepasst.  
  
    > [!NOTE]
    >  Geerbte Steuerelemente muss `Protected` angedockt werden können. Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie dessen **Modifizierer** Eigenschaft im Eigenschaftenfenster angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)  
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Windows Forms-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Übersicht über die AutoSize-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Gewusst wie: Verankern von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
