---
title: Ändern der Darstellung von TabControl
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
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746611"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>Gewusst wie: Ändern der Darstellung der TabControl-Komponente in Windows Forms
Sie können die Darstellung von Registerkarten in Windows Forms ändern, indem Sie die Eigenschaften des <xref:System.Windows.Forms.TabControl> und die <xref:System.Windows.Forms.TabPage> Objekte verwenden, die die einzelnen Registerkarten des Steuer Elements bilden. Durch Festlegen dieser Eigenschaften können Sie Bilder auf Registerkarten anzeigen, Registerkarten vertikal anstatt horizontal anzeigen, mehrere Zeilen von Registerkarten anzeigen und Registerkarten Programm gesteuert aktivieren oder deaktivieren.  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>So zeigen Sie ein Symbol auf dem Bezeichnungs Teil einer Registerkarte an  
  
1. Fügen Sie dem Formular ein <xref:System.Windows.Forms.ImageList>-Steuerelement hinzu.  
  
2. Fügen Sie der Bildliste Bilder hinzu.  
  
     Weitere Informationen zu Bildlisten finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und Gewusst [wie: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
3. Legen Sie die <xref:System.Windows.Forms.TabControl.ImageList%2A>-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf das <xref:System.Windows.Forms.ImageList>-Steuerelement fest.  
  
4. Legen Sie die <xref:System.Windows.Forms.TabPage.ImageIndex%2A>-Eigenschaft des <xref:System.Windows.Forms.TabPage> auf den Index eines entsprechenden Bilds in der Liste fest.  
  
### <a name="to-create-multiple-rows-of-tabs"></a>So erstellen Sie mehrere Zeilen von Registerkarten  
  
1. Fügen Sie die gewünschte Anzahl von Registerkarten hinzu.  
  
2. Legen Sie die <xref:System.Windows.Forms.TabControl.Multiline%2A>-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf `true`fest.  
  
3. Wenn die Registerkarten nicht bereits in mehreren Zeilen angezeigt werden, legen Sie die <xref:System.Windows.Forms.Control.Width%2A>-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf einen engeren Wert als alle Registerkarten fest.  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>So ordnen Sie Registerkarten auf der Seite des Steuer Elements an  
  
- Legen Sie die <xref:System.Windows.Forms.TabControl.Alignment%2A>-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAlignment.Left> oder <xref:System.Windows.Forms.TabAlignment.Right>fest.  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>So aktivieren oder deaktivieren Sie alle Steuerelemente auf einer Registerkarte Programm gesteuert  
  
1. Legen Sie die <xref:System.Windows.Forms.TabPage.Enabled%2A>-Eigenschaft des <xref:System.Windows.Forms.TabPage> auf `true` oder `false`fest.  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>Anzeigen von Registerkarten als Schaltflächen  
  
- Legen Sie die <xref:System.Windows.Forms.TabControl.Appearance%2A>-Eigenschaft des <xref:System.Windows.Forms.TabControl> auf <xref:System.Windows.Forms.TabAppearance.Buttons> oder <xref:System.Windows.Forms.TabAppearance.FlatButtons>fest.  
  
## <a name="see-also"></a>Siehe auch

- [TabControl-Steuerelement](tabcontrol-control-windows-forms.md)
- [Übersicht über das TabControl-Steuerelement](tabcontrol-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen eines Steuerelements zu einer Registerkarte](how-to-add-a-control-to-a-tab-page.md)
- [Gewusst wie: Deaktivieren von Registerkarten](how-to-disable-tab-pages.md)
- [Gewusst wie: Hinzufügen und Entfernen von Registerkarten mit dem TabControl-Steuerelement in Windows Forms](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
