---
title: "Gewusst wie: Umgang mit dem ToolStrip-Überlauf in Windows Forms"
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
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1ae4172dbdf82b4bd5bdd9a7f8afc1901fcfa3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Gewusst wie: Umgang mit dem ToolStrip-Überlauf in Windows Forms
Wenn alle Elemente in einer <xref:System.Windows.Forms.ToolStrip> Steuerelement in den zugewiesenen Speicherplatz nicht passen, können Sie Überlauffunktion aktivieren, auf die <xref:System.Windows.Forms.ToolStrip> und bestimmen das Überlaufverhalten bei bestimmten <xref:System.Windows.Forms.ToolStripItem>s.  
  
 Beim Hinzufügen von <xref:System.Windows.Forms.ToolStripItem>s, die mehr Platz benötigen, als zu erfordern die <xref:System.Windows.Forms.ToolStrip> aktuelle Größe des Formulars, ein <xref:System.Windows.Forms.ToolStripOverflowButton> automatisch angezeigt, auf die <xref:System.Windows.Forms.ToolStrip>. Die <xref:System.Windows.Forms.ToolStripOverflowButton> angezeigt wird, und die Overflow-fähige Elemente in der Dropdown-Überlaufmenü verschoben werden. Dadurch können Sie anpassen und priorisieren wie Ihre <xref:System.Windows.Forms.ToolStrip> Elemente ordnungsgemäß angepasst werden, um unterschiedliche Formulargrößen. Sie können auch die Darstellung der Elemente ändern, wenn sie in der Überlaufspalte mithilfe fallen die <xref:System.Windows.Forms.ToolStripItem.Placement%2A> und <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> Eigenschaften und die <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> Ereignis. Wenn Sie das Formular zur Entwurfszeit oder zur Laufzeit mehr vergrößern, <xref:System.Windows.Forms.ToolStripItem>s angezeigt werden kann, klicken Sie im hauptblatt <xref:System.Windows.Forms.ToolStrip> und die <xref:System.Windows.Forms.ToolStripOverflowButton> möglicherweise ausgeblendet, bis Sie die Größe des Formulars zu verringern.  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a>So aktivieren Sie einen Überlauf in einem ToolStrip-Steuerelement  
  
-   Sicherstellen, dass die <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> Eigenschaft nicht festgelegt ist, um `false` für die <xref:System.Windows.Forms.ToolStrip>. Die Standardeinstellung ist `True`.  
  
     Beim <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> ist `True` (Standard), eine <xref:System.Windows.Forms.ToolStripItem> wird gesendet, um die Dropdownliste Überlaufmenü bei den Inhalt des der <xref:System.Windows.Forms.ToolStripItem> überschreitet die Breite einer horizontalen <xref:System.Windows.Forms.ToolStrip> oder die Höhe eines vertikalen <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Überlaufverhalten eines bestimmten ToolStripItem angeben  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> Eigenschaft von der <xref:System.Windows.Forms.ToolStripItem> auf den gewünschten Wert. Mögliche Werte sind `Always`, `Never`, und `AsNeeded`. Die Defaultis `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Architektur des ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Zusammenfassung der ToolStrip-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
