---
title: 'Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms'
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
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73ea6d3615780c8def31b7dbdcf870020a106e80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Gewusst wie: Aktivieren der Neuanordnung von ToolStrip-Elementen zur Laufzeit in Windows Forms
Sie können die Benutzer zum Ändern der Anordnung ermöglichen <xref:System.Windows.Forms.ToolStripItem> auf steuert die <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>So aktivieren Sie ToolStripItem neuanordnung zur Laufzeit  
  
-   Legen Sie die <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>-Eigenschaft auf `true` fest. Standardmäßig <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> ist `false`.  
  
     Zur Laufzeit, hält der Benutzer die ALT-Taste und die linke Maustaste gedrückt, ziehen eine <xref:System.Windows.Forms.ToolStripItem> an einen anderen Speicherort auf dem <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>  
 [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Architektur des ToolStrip-Steuerelements](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Zusammenfassung der ToolStrip-Technologie](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
