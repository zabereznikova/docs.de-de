---
title: 'Vorgehensweise: Erstellen von Umschaltflächen in ToolStrip-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 723916eb0c1e242df301c49bf0716e0262a3ba42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614977"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Vorgehensweise: Erstellen von Umschaltflächen in ToolStrip-Steuerelementen
Wenn ein Benutzer eine Umschaltfläche klickt, wird abgesenkt dargestellt und behält die abgesenkt dargestellt, bis der Benutzer erneut auf die Schaltfläche klickt.  
  
### <a name="to-create-a-toggling-toolstripbutton"></a>Erstellen Sie eine ToolStripButton  
  
-   Verwenden Sie Code wie im folgenden Codebeispiel wird ein. Dieser Code setzt voraus, dass das Formular enthält ein <xref:System.Windows.Forms.ToolStrip> -Steuerelement, und dass die <xref:System.Windows.Forms.ToolStrip.Items%2A> Auflistung enthält ein <xref:System.Windows.Forms.ToolStripButton> namens `toolStripButton1`. Außerdem wird angenommen, dass Sie einen Ereignishandler mit dem Namen haben `toolStripButton1_CheckedChanged`.  
  
    ```vb  
    toolStripButton1.CheckOnClick = True  
    toolStripButton1.CheckedChanged AddressOf _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
    ```csharp  
    toolStripButton1.CheckOnClick = true;  
    toolStripButton1.CheckedChanged += new _  
    EventHandler(toolStripButton1_CheckedChanged);  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.ToolStripButton>
- [Übersicht über das ToolStrip-Steuerelement](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
