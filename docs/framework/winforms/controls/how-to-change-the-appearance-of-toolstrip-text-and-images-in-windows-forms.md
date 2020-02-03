---
title: 'Gewusst wie: Ändern der Darstellung von ToolStrip-Text und-Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: 7816e138e44554683c201895ece1f886ace8bfa6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746594"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a>Gewusst wie: Ändern der Darstellung von ToolStrip-Text und -Bildern in Windows Forms
Sie können steuern, ob Text und Bilder auf einem <xref:System.Windows.Forms.ToolStripItem> angezeigt werden und wie Sie relativ zueinander und <xref:System.Windows.Forms.ToolStrip>ausgerichtet werden.  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a>So definieren Sie, was auf einem ToolStripItem angezeigt wird  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>-Eigenschaft auf den gewünschten Wert fest. Die Möglichkeiten sind `Image`, `ImageAndText`, `None`und `Text`. Der Standardwert lautet `ImageAndText`.  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a>So richten Sie Text auf einem Tool Strip Item aus  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A>-Eigenschaft auf den gewünschten Wert fest. Die Möglichkeiten sind eine beliebige Kombination aus Top, Middle und Bottom mit Links, zentriert und rechts. Der Standardwert lautet `MiddleCenter`.  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a>So richten Sie ein Bild auf einem ToolStripItem-Element aus  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>-Eigenschaft auf den gewünschten Wert fest. Die Möglichkeiten sind eine beliebige Kombination aus Top, Middle und Bottom mit Links, zentriert und rechts. Der Standardwert lautet `MiddleLeft`.  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a>So definieren Sie, wie Text und Bilder von ToolStripItem zueinander zueinander angezeigt werden  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>-Eigenschaft auf den gewünschten Wert fest. Mögliche Werte sind `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage` und `TextBeforeImage`. Der Standardwert lautet `ImageBeforeText`.  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStrip>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
