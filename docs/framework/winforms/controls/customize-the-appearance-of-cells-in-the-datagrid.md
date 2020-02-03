---
title: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744054"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms
Sie können die Darstellung jeder Zelle anpassen, indem Sie das <xref:System.Windows.Forms.DataGridView.CellPainting> Ereignis des <xref:System.Windows.Forms.DataGridView>-Steuer Elements verarbeiten. Sie können die <xref:System.Drawing.Graphics> des <xref:System.Windows.Forms.DataGridView>-Steuer Elements aus der Eigenschaft <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>extrahieren. Mit diesem <xref:System.Drawing.Graphics>können Sie die Darstellung des gesamten <xref:System.Windows.Forms.DataGridView> Steuer Elements beeinflussen, Sie sollten sich jedoch in der Regel nur auf die Darstellung der Zelle auswirken, die gerade gezeichnet wird. Mit der <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> können Sie die Zeichnungsvorgänge auf die Zelle beschränken, die gerade gezeichnet wird.  
  
 Im folgenden Codebeispiel zeichnen Sie alle Zellen in einer `ContactName` Spalte mit dem Farbschema des <xref:System.Windows.Forms.DataGridView> Steuer Elements. Der Text Inhalt jeder Zelle wird in <xref:System.Drawing.Color.Crimson%2A>gezeichnet, und ein einfügen-Rechteck wird in derselben Farbe wie die <xref:System.Windows.Forms.DataGridView.GridColor%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridView> Steuer Elements gezeichnet.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1` mit einer `ContactName` Spalte, z. b. in der Customers-Tabelle der Beispieldatenbank Northwind.  
  
- Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Anpassen des DataGridView-Steuerelements von Windows Forms](customizing-the-windows-forms-datagridview-control.md)
