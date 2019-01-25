---
title: 'Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms'
ms.date: 03/30/2017
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
ms.openlocfilehash: 1ed062b3991d7738269d30a6ff13cda3c80927c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630319"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Vorgehensweise: Ändern der Darstellung der TabControl-Steuerelement in Windows Forms
Sie können die Darstellung der Registerkarten in Windows Forms ändern, indem Sie mit den Eigenschaften des der <xref:System.Windows.Forms.TabControl> und <xref:System.Windows.Forms.TabPage> Objekte, die die einzelnen Registerkarten des Steuerelements bilden. Durch Festlegen dieser Eigenschaften an, können Sie Bilder auf Registerkarten anzeigen, Anzeigen von Registerkarten vertikal statt horizontal, Anzeigen mehrerer Zeilen mit Registerkarten, und aktivieren oder deaktivieren Registerkarten programmgesteuert.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>Ein Symbol auf dem Label-Teil einer Registerkarte angezeigt.  
  
1.  Hinzufügen einer <xref:System.Windows.Forms.ImageList> -Steuerelement auf das Formular.  
  
2.  Hinzufügen von Bildern der Bildliste.  
  
     Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3.  Legen Sie die <xref:System.Windows.Forms.TabControl.ImageList%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> auf der <xref:System.Windows.Forms.ImageList> Steuerelement.  
  
4.  Legen Sie die <xref:System.Windows.Forms.TabPage.ImageIndex%2A> Eigenschaft der <xref:System.Windows.Forms.TabPage> auf den Index der geeigneten Bildes in der Liste.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>Um mehrere Zeilen mit Registerkarten zu erstellen.  
  
1.  Fügen Sie die Anzahl der gewünschten Registerkartenseiten hinzu.  
  
2.  Legen Sie die <xref:System.Windows.Forms.TabControl.Multiline%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> zu `true`.  
  
3.  Wenn die Registerkarten nicht bereits in mehreren Zeilen angezeigt werden, legen Sie die <xref:System.Windows.Forms.Control.Width%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> schmaler als alle Registerkarten sein.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>So ordnen Sie die Registerkarten im Zweifelsfall das Steuerelement an  
  
-   Legen Sie die <xref:System.Windows.Forms.TabControl.Alignment%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> zu <xref:System.Windows.Forms.TabAlignment.Left> oder <xref:System.Windows.Forms.TabAlignment.Right>.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>Programmgesteuertes aktivieren oder deaktivieren alle Steuerelemente auf einer Registerkarte  
  
1.  Legen Sie die <xref:System.Windows.Forms.TabPage.Enabled%2A> Eigenschaft der <xref:System.Windows.Forms.TabPage> zu `true` oder `false`.  
  
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
  
-   Legen Sie die <xref:System.Windows.Forms.TabControl.Appearance%2A> Eigenschaft der <xref:System.Windows.Forms.TabControl> zu <xref:System.Windows.Forms.TabAppearance.Buttons> oder <xref:System.Windows.Forms.TabAppearance.FlatButtons>.  
  
## <a name="see-also"></a>Siehe auch
- [TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)
- [Übersicht über das TabControl-Steuerelement](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen eines Steuerelements zu einer Registerkarte](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)
- [Vorgehensweise: Deaktivieren von Registerkarten](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Registerkarten zu TabControls in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
