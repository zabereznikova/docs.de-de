---
title: Festlegen von abwechselnden Zeilen Stilen für das DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: b87ad50ef7e5118a95998949bc62299955856b27
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747134"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a>Gewusst wie: Festlegen von abwechselnden Zeilenstilen für das DataGridView-Steuerelement in Windows Forms
Tabellendaten werden oft in einem Ledger-ähnlichen Format präsentiert, bei dem die einzelnen Zeilen abwechselnde Hintergrundfarben haben. Dieses Format erleichtert es dem Benutzer, zu erkennen, welche Zellen sich in jeder Zeile befinden, insbesondere bei breiten Tabellen mit vielen Spalten.  
  
 Mit dem <xref:System.Windows.Forms.DataGridView>-Steuerelement können Sie vollständige Stilinformationen für abwechselnde Zeilen angeben. Auf diese Weise können Sie Stileigenschaften wie Vordergrundfarbe und Schriftart zusätzlich zur Hintergrundfarbe verwenden, um abwechselnde Zeilen zu unterscheiden.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch Gewusst [wie: Festlegen von abwechselnden Zeilen Stilen für das Windows Forms DataGridView-Steuerelement mithilfe des Designers](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
### <a name="to-set-alternating-row-styles-programmatically"></a>So legen Sie abwechselnde Zeilenstile programmgesteuert fest  
  
- Legen Sie die Eigenschaften der <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte fest, die von der <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>- und der <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>-Eigenschaft der <xref:System.Windows.Forms.DataGridView> zurückgegeben werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    > Die Stile, die über die <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>- und die <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>-Eigenschaft angegeben sind, überschreiben die Stile, die auf Spalten- und <xref:System.Windows.Forms.DataGridView>-Ebene festgelegt sind, werden jedoch durch die Stile überschrieben, die auf der einzelnen Zeilen- und Zellenebene festgelegt sind. Weitere Informationen finden Sie unter [Zellen Stile im Windows Forms DataGridView-Steuer](cell-styles-in-the-windows-forms-datagridview-control.md)Element.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Robuste Programmierung  
 Um maximale Skalierbarkeit zu erreichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für mehrere Zeilen, Spalten oder Zellen, in denen dieselben Stile verwendet werden, gemeinsam verwenden, anstatt die Stileigenschaften für jedes einzelne Element festzulegen. Weitere Informationen finden Sie unter [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Empfohlene Vorgehensweisen für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
