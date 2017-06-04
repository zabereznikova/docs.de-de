---
title: "Gewusst wie: &#196;ndern der Darstellung der TabControl-Komponente in Windows&#160;Forms | Microsoft Docs"
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
  - "Schaltflächen, Anzeigen von Registerkarten als"
  - "Symbole, Anzeigen auf Registerkarten"
  - "TabControl-Steuerelement [Windows Forms], Ändern der Seitendarstellung"
  - "Registerkarten, Steuern der Darstellung"
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Gewusst wie: &#196;ndern der Darstellung der TabControl-Komponente in Windows&#160;Forms
Sie können die Darstellung von Registerkarten in Windows Forms mithilfe der Eigenschaften des <xref:System.Windows.Forms.TabControl>\-Objekts und des <xref:System.Windows.Forms.TabPage>\-Objekts ändern, aus denen sich die einzelnen Registerkarten im Steuerelement zusammensetzen.  Durch das Festlegen dieser Eigenschaften können Sie Folgendes anzeigen: Bilder auf Registerkarten, vertikale statt horizontale Registerkarten und mehrere Zeilen von Registerkarten. Darüber hinaus können Sie Registerkarten programmgesteuert aktivieren oder deaktivieren.  
  
### So zeigen Sie ein Symbol auf dem Bezeichnungsteil einer Registerkarte an  
  
1.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.ImageList>\-Steuerelement hinzu.  
  
2.  Fügen Sie der Bildliste Bilder hinzu.  
  
     Weitere Informationen über Bildlisten finden Sie unter [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Legen Sie die <xref:System.Windows.Forms.TabControl.ImageList%2A>\-Eigenschaft von <xref:System.Windows.Forms.TabControl> auf das <xref:System.Windows.Forms.ImageList>\-Steuerelement fest.  
  
4.  Legen Sie die <xref:System.Windows.Forms.TabPage.ImageIndex%2A>\-Eigenschaft von <xref:System.Windows.Forms.TabPage> auf den Index eines geeigneten Bildes in der Liste fest.  
  
### So erstellen Sie mehrere Reihen von Registerkarten  
  
1.  Fügen Sie die Anzahl der gewünschten Registerkarten hinzu.  
  
2.  Legen Sie die <xref:System.Windows.Forms.TabControl.Multiline%2A>\-Eigenschaft von <xref:System.Windows.Forms.TabControl> auf `true` fest.  
  
3.  Wenn die Registerkarten noch nicht in mehreren Zeilen angezeigt werden, legen Sie die <xref:System.Windows.Forms.Control.Width%2A>\-Eigenschaft von <xref:System.Windows.Forms.TabControl> auf einen Wert fest, der kleiner als die gesamte Breite aller Registerkarten ist.  
  
### So ordnen Sie Registerkarten an der Seite des Steuerelements an  
  
-   Legen Sie die <xref:System.Windows.Forms.TabControl.Alignment%2A>\-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAlignment> oder <xref:System.Windows.Forms.TabAlignment> fest.  
  
### So aktivieren oder deaktivieren Sie alle Steuerelemente auf einer Registerkarte programmgesteuert  
  
1.  Legen Sie die <xref:System.Windows.Forms.TabPage.Enabled%2A>\-Eigenschaft der <xref:System.Windows.Forms.TabPage> auf `true` oder `false` fest.  
  
    ```vb  
    TabPage1.Enabled = False  
  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### So zeigen Sie Registerkarten als Schaltflächen an  
  
-   Legen Sie die <xref:System.Windows.Forms.TabControl.Appearance%2A>\-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAppearance> oder <xref:System.Windows.Forms.TabAppearance> fest.  
  
## Siehe auch  
 [TabControl\-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Übersicht über das TabControl\-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)   
 [Gewusst wie: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)