---
title: "Gewusst wie: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms"
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
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aada475af0ccac03dfa6ef9248b0fb07fd86b3ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Abrufen der ausgewählten Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms
Sie erhalten die ausgewählten Zellen, Zeilen oder Spalten aus einer <xref:System.Windows.Forms.DataGridView> Steuerelement mithilfe der entsprechenden Eigenschaften: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, und <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. In den folgenden Verfahren wird die ausgewählten Zellen abzurufen und zeigen die Zeilen- und Spaltenindizes in einem <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Zum Abrufen der ausgewählten Zellen in einem DataGridView-Steuerelement  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>-Eigenschaft.  
  
    > [!NOTE]
    >  Verwenden der <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> Methode zur Vermeidung eine möglicherweise große Anzahl von Zellen angezeigt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Zum Abrufen der ausgewählten Zeilen in einem DataGridView-Steuerelement  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>-Eigenschaft. Um Benutzern die Auswahl von Zeilen zu aktivieren, müssen Sie festlegen der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Zum Abrufen der ausgewählten Spalten in einem DataGridView-Steuerelement  
  
-   Verwenden Sie die <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>-Eigenschaft. Um Benutzern die Auswahl von Spalten zu aktivieren, müssen Sie festlegen der <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> Eigenschaft <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> oder <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   <xref:System.Windows.Forms.Button>-Steuerelemente namens `selectedCellsButton`, `selectedRowsButton`, und `selectedColumnsButton`, jeweils mit Handler für das <xref:System.Windows.Forms.Control.Click> Ereignis angefügt.  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Sammlungen, die in diesem Thema beschriebenen führen nicht effizient aus, wenn große Anzahl von Zellen, Zeilen oder Spalten ausgewählt werden. Weitere Informationen zur Verwendung dieser Sammlungen mit großen Mengen von Daten finden Sie unter [Best Practices zum Skalieren des DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>  
 [Verwendung von Auswahl und Zwischenablage mit dem DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
