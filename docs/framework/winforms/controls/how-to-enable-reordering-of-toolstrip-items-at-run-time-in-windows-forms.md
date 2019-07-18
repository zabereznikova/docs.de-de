---
title: 'Vorgehensweise: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 46a5a70206e7620341a484912c7fada82d64747a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609850"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Vorgehensweise: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms
Sie können die Benutzer zum Ändern der Anordnung ermöglichen <xref:System.Windows.Forms.ToolStripItem> steuert, auf die <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>ToolStripItem-neuanordnung zur Laufzeit zu aktivieren  
  
- Legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> -Eigenschaft auf `true`fest. In der Standardeinstellung <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> ist `false`.  
  
     Zur Laufzeit wird der Benutzer hält die ALT-Taste und die linke Maustaste gedrückt, ziehen eine <xref:System.Windows.Forms.ToolStripItem> an einen anderen Speicherort auf dem <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
