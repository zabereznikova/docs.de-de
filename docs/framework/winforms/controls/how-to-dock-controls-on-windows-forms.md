---
title: "Gewusst wie: Andocken von Steuerelementen in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Steuerelemente [Windows Forms], Andocken"
  - "Dock-Eigenschaft"
  - "Explorer-ähnliche Anwendungen, Erstellen"
  - "Windows Forms-Steuerelemente, Füllen des Clientbereichs"
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Andocken von Steuerelementen in Windows&#160;Forms
Steuerelemente können an den Formularrändern angedockt werden, oder sie können den Steuerelementcontainer \(entweder ein Formular oder ein Containersteuerelement\) ausfüllen.  In Windows Explorer ist das <xref:System.Windows.Forms.TreeView>\-Steuerelement beispielsweise am linken und das <xref:System.Windows.Forms.ListView>\-Steuerelement am rechten Fensterrand angedockt.  Verwenden Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft, um den Andockmodus für alle sichtbaren Steuerelemente für Windows Forms zu definieren.  
  
> [!NOTE]
>  Steuerelemente werden in umgekehrter z\-Reihenfolge angedockt.  
  
 Die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft interagiert mit der <xref:System.Windows.Forms.Control.AutoSize%2A>\-Eigenschaft.  Weitere Informationen finden Sie unter [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### So docken Sie ein Steuerelement an  
  
1.  Markieren Sie das anzudockende Steuerelement.  
  
2.  Klicken Sie im Eigenschaftenfenster auf den Pfeil rechts neben der <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft.  
  
     Es wird ein Editor mit einer Reihe von Feldern geöffnet, die den Rändern sowie der Mitte des Formulars entsprechen.  
  
3.  Klicken Sie auf die Schaltfläche für den Formularrand, an dem das Steuerelement angedockt werden soll.  Um das Formular bzw. das Containersteuerelement auszufüllen, klicken Sie auf das mittlere Feld.  Klicken Sie auf **None**, um das Andocken zu deaktivieren.  
  
     Die Größe des Steuerelements wird automatisch in Anpassung an die Begrenzungen des angedockten Randes geändert.  
  
    > [!NOTE]
    >  Für geerbte Steuerelemente muss `Protected` angegeben sein, damit sie angedockt werden können.  Um die Zugriffsebene eines Steuerelements zu ändern, legen Sie seine **Modifier**\-Eigenschaft im Eigenschaftenfenster fest.  
  
## Siehe auch  
 [Windows Forms\-Steuerelemente](../../../../docs/framework/winforms/controls/index.md)   
 [Anordnen von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Windows Forms\-Steuerelemente nach Funktion](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [Gewusst wie: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Übersicht über die AutoSize\-Eigenschaft](../../../../docs/framework/winforms/controls/autosize-property-overview.md)   
 [Gewusst wie: Verankern von Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)