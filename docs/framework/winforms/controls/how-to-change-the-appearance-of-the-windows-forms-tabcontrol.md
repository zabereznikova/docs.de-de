---
title: "Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b244930f0837d3b1d548e0f7a8c77dd80e1ce039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms
Sie können die Darstellung der Registerkarten in Windows Forms mithilfe von Eigenschaften ändern die <xref:System.Windows.Forms.TabControl> und <xref:System.Windows.Forms.TabPage> Objekte, die die einzelnen Registerkarten des Steuerelements bilden. Durch Festlegen dieser Eigenschaften, können Sie Bilder auf Registerkarten anzeigen, Registerkarten vertikal anstatt horizontal anzuzeigen, mehrere Zeilen mit Registerkarten anzeigen und aktivieren oder deaktivieren Registerkarten programmgesteuert.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Ein Symbol auf dem Etikett Teil einer Registerkarte angezeigt.  
  
1.  Hinzufügen einer <xref:System.Windows.Forms.ImageList> Steuerelement dem Formular.  
  
2.  Hinzufügen von Bildern auf die Bildliste.  
  
     Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [wie: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Festlegen der <xref:System.Windows.Forms.TabControl.ImageList%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf die <xref:System.Windows.Forms.ImageList> Steuerelement.  
  
4.  Legen Sie die <xref:System.Windows.Forms.TabPage.ImageIndex%2A> Eigenschaft von der <xref:System.Windows.Forms.TabPage> auf den Index des geeigneten Bildes in der Liste.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>So erstellen mehrere Zeilen mit Registerkarten  
  
1.  Fügen Sie die Anzahl der gewünschten Registerkarten hinzu.  
  
2.  Festlegen der <xref:System.Windows.Forms.TabControl.Multiline%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf `true`.  
  
3.  Wenn die Registerkarten nicht bereits in mehreren Zeilen angezeigt werden, legen Sie die <xref:System.Windows.Forms.Control.Width%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> enger gefasst als aller Registerkarten werden.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>So ordnen Sie die Registerkarten auf das Steuerelement an  
  
-   Festlegen der <xref:System.Windows.Forms.TabControl.Alignment%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAlignment.Left> oder <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Programmgesteuertes aktivieren oder deaktivieren alle Steuerelemente auf einer Registerkarte  
  
1.  Festlegen der <xref:System.Windows.Forms.TabPage.Enabled%2A> Eigenschaft von der <xref:System.Windows.Forms.TabPage> auf `true` oder `false`.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Zum Anzeigen von Registerkarten als Schaltflächen  
  
-   Festlegen der <xref:System.Windows.Forms.TabControl.Appearance%2A> Eigenschaft von der <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAppearance.Buttons> oder <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>Siehe auch  
 [TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [Übersicht über das TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [Gewusst wie: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
