---
title: 'Vorgehensweise: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: c7a874659be8dbaec66b78e1e065bcbec21da3b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650878"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Vorgehensweise: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms
Die <xref:System.Windows.Forms.ToolStrip> Steuerelement vollständig unterstützt Funktionen wie z. B. das Ändern der Größe, des Abstands des <xref:System.Windows.Forms.ToolStripItem> Steuerelemente relativ zueinander und die Anordnung von Steuerelementen auf der <xref:System.Windows.Forms.ToolStrip>, und der Abstand der Steuerelemente relativ zu den <xref:System.Windows.Forms.ToolStrip>.  
  
 Da der Standardwert der <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> -Eigenschaft ist `true`, Steuerelemente werden automatisch angepasst, es sei denn, Sie legen die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft, um `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Manuell auf einem ToolStripItem Größe  
  
1. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Eigenschaft `false` für das zugeordnete Steuerelement.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Size%2A> Eigenschaft wie gewünscht, für das zugeordnete <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Um den Abstand eines ToolStripItem festzulegen  
  
1. Legen Sie die gewünschten Werte in Pixel in der <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Eigenschaft des zugeordneten Steuerelements.  
  
     Die Werte der <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Eigenschaft geben den Abstand zwischen dem Element und angrenzenden Elementen in der folgenden Reihenfolge: Links, oben, rechts und unten.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Ausrichten ein ToolStripItem auf die rechte Seite des ToolStrip  
  
1. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Eigenschaft <xref:System.Windows.Forms.ToolStripItemAlignment.Right> für das zugeordnete Steuerelement. Standardmäßig <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> nastaven NA hodnotu <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, die Steuerelemente auf der linken Seite des richtet die <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>ToolStrip-Elementen auf der Toolleiste anordnen  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> Eigenschaft, um den Wert der <xref:System.Windows.Forms.ToolStripLayoutStyle> , die Sie möchten.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
