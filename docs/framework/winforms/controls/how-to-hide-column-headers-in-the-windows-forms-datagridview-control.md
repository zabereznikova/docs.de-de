---
title: 'Vorgehensweise: Ausblenden von Spaltenüberschriften in der DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: 80377aa598938031f9708c4b7657594985ec0746
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717063"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Ausblenden von Spaltenüberschriften in der DataGridView-Steuerelement in Windows Forms
Manchmal sollten Sie zum Anzeigen einer <xref:System.Windows.Forms.DataGridView> ohne Spaltenheader. In der <xref:System.Windows.Forms.DataGridView> -Steuerelement, das <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> Eigenschaftswert bestimmt, ob die Spaltenköpfe angezeigt werden.  
  
### <a name="to-hide-the-column-headers"></a>So blenden Sie die Spaltenüberschriften aus  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> -Eigenschaft auf `false`fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
