---
title: Implementieren des virtuellen Modus im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode
- DataGridView control [Windows Forms], large data sets
ms.assetid: 98236267-f08e-4918-bcf9-77acf050a3ca
ms.openlocfilehash: f8612a808ac5c9facee55d820529945f481a2cea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736508"
---
# <a name="how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms
Im folgenden Codebeispiel wird veranschaulicht, wie große Datenmengen mithilfe eines <xref:System.Windows.Forms.DataGridView>-Steuerelements verwaltet werden, dessen <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>-Eigenschaft auf `true` festgelegt ist.  
  
 Eine vollständige Erläuterung dieses Codebeispiels finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#000)]
 [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement in Windows Forms](implementing-virtual-mode-wf-datagridview-control.md)
- [Leistungsoptimierung im DataGridView-Steuerelement in Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Virtueller Modus im DataGridView-Steuerelement in Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
