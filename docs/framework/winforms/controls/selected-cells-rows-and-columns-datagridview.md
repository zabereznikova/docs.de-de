---
title: 'Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 25b3ed50081add77b9f522ca8e597f2b3306cb2e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960517"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms
Die ausgewählten Zellen, Zeilen oder Spalten können Sie mithilfe der entsprechenden Eigenschaften <xref:System.Windows.Forms.DataGridView> aus einem-Steuerelement erhalten: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. In den folgenden Prozeduren werden die ausgewählten Zellen angezeigt, und die Zeilen-und Spalten Indizes werden <xref:System.Windows.Forms.MessageBox>in einem angezeigt.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>So erhalten Sie die ausgewählten Zellen in einem DataGridView-Steuerelement  
  
- Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>-Eigenschaft.  
  
    > [!NOTE]
    > Verwenden Sie <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> die-Methode, um die Anzeige einer potenziell großen Anzahl von Zellen zu vermeiden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>So erhalten Sie die ausgewählten Zeilen in einem DataGridView-Steuerelement  
  
- Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>-Eigenschaft. Um Benutzern das Auswählen von Zeilen zu ermöglichen, müssen Sie <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> die- <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>auf oder festlegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>So erhalten Sie die ausgewählten Spalten in einem DataGridView-Steuerelement  
  
- Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>-Eigenschaft. Um Benutzern die Auswahl von Spalten zu ermöglichen, müssen Sie <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> die- <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>auf oder festlegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- <xref:System.Windows.Forms.Button>Steuerelemente `selectedCellsButton`mit `selectedRowsButton`den Namen `selectedColumnsButton`, und, jeweils mit Handlern <xref:System.Windows.Forms.Control.Click> für das angefügte Ereignis.  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die in diesem Thema beschriebenen Sammlungen werden nicht effizient durchgeführt, wenn eine große Anzahl von Zellen, Zeilen oder Spalten ausgewählt ist. Weitere Informationen zur Verwendung dieser Sammlungen mit großen Datenmengen finden Sie unter [bewährte Methoden zum Skalieren des Windows Forms DataGridView-Steuer](best-practices-for-scaling-the-windows-forms-datagridview-control.md)Elements.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
