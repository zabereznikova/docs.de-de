---
title: 'Gewusst wie: Ändern des Abstands und der Ausrichtung von ToolStrip-Elementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182231"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Gewusst wie: Ändern der Abstände und der Ausrichtung der ToolStrip-Elemente in Windows Forms
Das <xref:System.Windows.Forms.ToolStrip> Steuerelement unterstützt Layout-Features wie die <xref:System.Windows.Forms.ToolStripItem> Größenänderung, den Abstand der Steuerelemente <xref:System.Windows.Forms.ToolStrip>relativ zueinander, die <xref:System.Windows.Forms.ToolStrip>Anordnung von Steuerelementen auf dem und den Abstand von Steuerelementen relativ zum .  
  
 Da der Standardwert <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> der `true`Eigenschaft ist , werden <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Steuerelemente `false`automatisch angepasst, es sei denn, Sie legen die Eigenschaft auf fest.  
  
### <a name="to-manually-size-a-toolstripitem"></a>So vergrößern Sie ein ToolStripItem manuell  
  
1. Legen <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> Sie `false` die Eigenschaft für das zugeordnete Steuerelement fest.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Legen <xref:System.Windows.Forms.ToolStripItem.Size%2A> Sie die Eigenschaft so <xref:System.Windows.Forms.ToolStripItem>fest, wie Sie es für die zugeordnete benötigen.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>So legen Sie den Abstand eines ToolStripItem fest  
  
1. Fügen Sie die gewünschten Werte in <xref:System.Windows.Forms.ToolStripItem.Margin%2A> Pixel in die Eigenschaft des zugeordneten Steuerelements ein.  
  
     Die Werte <xref:System.Windows.Forms.ToolStripItem.Margin%2A> der Eigenschaft geben den Abstand zwischen dem Element und benachbarten Elementen in dieser Reihenfolge an: Links, Oben, Rechts und Unten.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>So richten Sie ein ToolStripItem auf der rechten Seite des ToolStrip aus  
  
1. Legen <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Sie <xref:System.Windows.Forms.ToolStripItemAlignment.Right> die Eigenschaft für das zugeordnete Steuerelement fest. Standardmäßig ist <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> auf <xref:System.Windows.Forms.ToolStripItemAlignment.Left>festgelegt, das Steuerelemente auf der <xref:System.Windows.Forms.ToolStrip>linken Seite des ausrichtet.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>So ordnen Sie ToolStrip-Elemente auf dem ToolStrip an  
  
- Legen <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> Sie die Eigenschaft <xref:System.Windows.Forms.ToolStripLayoutStyle> auf den gewünschten Wert fest.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

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
