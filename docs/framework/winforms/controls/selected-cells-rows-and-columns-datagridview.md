---
title: 'Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 95229f1915b25962a700a7d6aced0a012bbe6657
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626913"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms
Erhalten Sie die ausgewählten Zellen, Zeilen oder Spalten aus einer <xref:System.Windows.Forms.DataGridView> Kontrolle über die entsprechenden Eigenschaften: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. In den folgenden Verfahren Sie die ausgewählten Zellen abzurufen und zeigen die Zeilen- und Spaltenindizes in einem <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Um die ausgewählten Zellen in einem DataGridView-Steuerelement zu erhalten.  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>-Eigenschaft.  
  
    > [!NOTE]
    >  Verwenden der <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode, um zu verhindern, dass eine potenziell große Anzahl von Zellen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Um die ausgewählten Zeilen in einem DataGridView-Steuerelement zu erhalten.  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>-Eigenschaft. Um Benutzer zum Auswählen von Zeilen zu aktivieren, müssen Sie legen die <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Um die ausgewählten Spalten in einem DataGridView-Steuerelement zu erhalten.  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>-Eigenschaft. Um Benutzern das Auswählen von Spalten zu aktivieren, müssen Sie festlegen der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   <xref:System.Windows.Forms.Button> Steuerelemente, die mit dem Namen `selectedCellsButton`, `selectedRowsButton`, und `selectedColumnsButton`, jeweils mit Handlern für die <xref:System.Windows.Forms.Control.Click> Ereignis angefügt.  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Sammlungen, die in diesem Thema beschriebenen ist nicht effizient, wenn große Anzahl von Zellen, Zeilen oder Spalten ausgewählt sind. Weitere Informationen zur Verwendung dieser Sammlungen mit großen Mengen von Daten finden Sie unter [Best Practices für das Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
