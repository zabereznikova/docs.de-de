---
title: Ändern der Rahmen-und Rasterlinien Stile im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
ms.openlocfilehash: 918102a87ee29a3d3b78d6e6eedce57237135a51
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744701"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Ändern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms
Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie die Darstellung der Rahmen-und Gitternetz Linien des Steuer Elements anpassen, um die Benutzer Leistung zu verbessern. Sie können die Gitternetz Linien Farbe und die Rahmenart des Steuer Elements zusätzlich zu den Rahmen Stilen für die Zellen im Steuerelement ändern. Sie können auch unterschiedliche Zell Rahmen Stile für normale Zellen, Zeilen Header Zellen und Spaltenheader Zellen anwenden.  
  
> [!NOTE]
> Die Gitternetz Linien Farbe wird nur mit den Werten <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>und <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> der <xref:System.Windows.Forms.DataGridViewCellBorderStyle> Enumeration und des <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> Werts der <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>-Enumeration verwendet. Bei den anderen Werten dieser Enumerationen werden vom Betriebssystem angegebene Farben verwendet. Wenn visuelle Stile unter Windows XP und der Windows Server 2003-Familie durch die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>-Methode aktiviert sind, wird der Wert der Eigenschaft <xref:System.Windows.Forms.DataGridView.GridColor%2A> nicht verwendet.  
  
### <a name="to-change-the-gridline-color-programmatically"></a>So ändern Sie die Gitternetz Linien Farbe Programm gesteuert  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a>So ändern Sie die Rahmenart des gesamten DataGridView-Steuer Elements Programm gesteuert  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.BorderStyle%2A>-Eigenschaft auf einen der <xref:System.Windows.Forms.BorderStyle>-Enumerationswerte fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a>So ändern Sie die Rahmen Stile für DataGridView-Zellen Programm gesteuert  
  
- Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>und <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.BorderStyle>
- <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellBorderStyle>
- <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
