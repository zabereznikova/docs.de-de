---
title: 'Vorgehensweise: Behandeln des Opening-Ereignisses von ContextMenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
ms.openlocfilehash: 3001480959ef90cb31048cbcf70aeff1632979fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170715"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a>Vorgehensweise: Behandeln des Opening-Ereignisses von ContextMenuStrip
Sie können das Verhalten anpassen Ihrer <xref:System.Windows.Forms.ContextMenuStrip> -Steuerelements durch Behandeln der <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie behandelt die <xref:System.Windows.Forms.ToolStripDropDown.Opening> Ereignis. Der Ereignishandler fügt Elemente dynamisch zu einem <xref:System.Windows.Forms.ContextMenuStrip> Steuerelement. Das vollständige Codebeispiel finden Sie unter [Vorgehensweise: Dynamisches Hinzufügen von ToolStrip-Elementen](how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> Eigenschaft `true` um zu verhindern, dass Sie im Menü öffnen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
