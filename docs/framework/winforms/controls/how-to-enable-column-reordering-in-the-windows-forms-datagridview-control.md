---
title: Neuanordnung von Spalten im DataGridView-Steuerelement aktivieren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], reordering columns
- columns [Windows Forms], reordering
ms.assetid: cc20eae3-e4db-493f-95ce-a4215e29472a
ms.openlocfilehash: 681489cdb874677079e2577140040921e587d21e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745495"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms
Wenn Sie die Neuanordnung von Spalten im <xref:System.Windows.Forms.DataGridView>-Steuerelement aktivieren, können die Benutzer eine Spalte an eine neuen Position ziehen, indem sie den Spaltenkopf mit der Maus ziehen. Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der Wert der Eigenschaftswert <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>, ob Benutzer Spalten an andere Positionen ziehen können.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch Gewusst [wie: Aktivieren der Neuanordnung von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](enable-column-reordering-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-enable-column-reordering-programmatically"></a>So aktivieren Sie die Neuanordnung von Spalten programmgesteuert  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> -Eigenschaft auf `true`fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#060)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#060](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#060)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)
