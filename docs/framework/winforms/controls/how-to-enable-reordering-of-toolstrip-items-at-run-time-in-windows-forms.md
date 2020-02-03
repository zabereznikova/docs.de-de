---
title: 'Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit'
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
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745475"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms
Sie können es dem Benutzer ermöglichen, <xref:System.Windows.Forms.ToolStripItem> Steuerelemente auf dem <xref:System.Windows.Forms.ToolStrip>neu anzuordnen.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>So aktivieren Sie die Neuanordnung von ToolStripItem zur Laufzeit  
  
- Setzen Sie die <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>-Eigenschaft auf `true`. Standardmäßig ist <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> `false`.  
  
     Zur Laufzeit hält der Benutzer die Alt-Taste gedrückt und die linke Maustaste, um ein <xref:System.Windows.Forms.ToolStripItem> an einen anderen Speicherort auf dem <xref:System.Windows.Forms.ToolStrip>zu ziehen.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Übersicht über das ToolStrip-Steuerelement](toolstrip-control-overview-windows-forms.md)
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Zusammenfassung der ToolStrip-Technologie](toolstrip-technology-summary.md)
