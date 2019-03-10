---
title: 'Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: add865eedc54253ad257e0e142e555da52f341dd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703347"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms
Sie können die Darstellung jeder Zelle anpassen, indem die Behandlung der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis. Extrahieren der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Drawing.Graphics> aus der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Mit diesem <xref:System.Drawing.Graphics>, Sie können die Darstellung des gesamten beeinflussen <xref:System.Windows.Forms.DataGridView> -Steuerelement, aber Sie sollten in der Regel nur auf die Darstellung der Zelle zu beeinflussen, das gerade gezeichnet wird. Die <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> ermöglicht es Ihnen, Ihre Zeichenvorgänge auf die Zelle zu beschränken, die gerade gezeichnet wird.  
  
 Das folgende Codebeispiel zeigt, zeichnen Sie alle Zellen in einer `ContactName` Spalte unter Verwendung der <xref:System.Windows.Forms.DataGridView> Farbschema des Steuerelements. Jede Zelle des Text-Inhalt gezeichnet wird <xref:System.Drawing.Color.Crimson%2A>, und eine abgesenktes Rechteck gezeichnet wird, in die gleiche Farbe wie die <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.GridColor%2A> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1` mit einem `ContactName` Spalte wie in der Customers-Tabelle in der Northwind-Beispieldatenbank.  
  
-   Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
