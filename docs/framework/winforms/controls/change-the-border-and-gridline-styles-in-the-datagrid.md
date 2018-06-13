---
title: 'Gewusst wie: Ändern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 94e5ae11d7fb2b67e028f368183246f8d8543a08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528748"
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Ändern des Rahmen- und Rasterlinienstils im DataGridView-Steuerelement in Windows Forms
Mit der <xref:System.Windows.Forms.DataGridView> -Steuerelement, Sie können die Darstellung von Rahmen und Gitternetzlinien zur Verbesserung der benutzerfreundlichkeit des Steuerelements anpassen. Sie können die Farbe der Gitternetzlinien und den Rahmenstil zusätzlich die Rahmenarten für die Zellen im Steuerelement zu ändern. Sie können auch andere Zelle Rahmenarten für normale Zellen, Zeilenheaderzellen und Spaltenheaderzellen anwenden.  
  
> [!NOTE]
>  Die Farbe der Gitternetzlinien dient nur mit der <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, und <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> Werte von der <xref:System.Windows.Forms.DataGridViewCellBorderStyle> Enumeration und die <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> Wert der <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> Enumeration. Die anderen Werte dieser Enumerationen verwenden, Farben, die vom Betriebssystem angegeben wird. Darüber hinaus, wenn visuelle Stile unter Windows XP und Windows Server 2003-Produktfamilie über aktiviert sind die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> -Methode, die <xref:System.Windows.Forms.DataGridView.GridColor%2A> Eigenschaftswert wird nicht verwendet.  
  
### <a name="to-change-the-gridline-color-programmatically"></a>So ändern Sie die Farbe der Gitternetzlinien programmgesteuert  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a>So ändern Sie die Rahmenart des gesamten DataGridView-Steuerelement programmgesteuert  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.BorderStyle%2A>-Eigenschaft auf einen der <xref:System.Windows.Forms.BorderStyle>-Enumerationswerte fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a>So ändern Sie die Rahmenarten für DataGridView-Zellen programmgesteuert  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, und <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> Eigenschaften.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> und <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.BorderStyle>  
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>  
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>  
 [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
