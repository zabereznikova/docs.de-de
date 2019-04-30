---
title: 'Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: fb71a6e3259d3007e11f528377c95a9c4cbeb023
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971326"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms
Interaktion mit der <xref:System.Windows.Forms.DataGridView> häufig erforderlich, dass Sie programmgesteuert ermitteln, welche Zelle derzeit aktiv ist. Sie müssen möglicherweise auch die aktuelle Zelle zu ändern. Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.  
  
> [!NOTE]
>  Können Sie die aktuelle Zelle in einer Zeile oder Spalte, die Festlegen seiner <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> -Eigenschaftensatz auf `false`.  
  
 Je nachdem auf die <xref:System.Windows.Forms.DataGridView> Auswahlmodus des Steuerelements ändern der aktuellen Zelle kann die Auswahl ändern. Weitere Informationen finden Sie unter [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Um die aktuelle Zelle programmtechnisch zu erhalten.  
  
- Verwenden der <xref:System.Windows.Forms.DataGridView> des Steuerelements <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>So legen Sie die aktuelle Zelle programmgesteuert fest  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft der <xref:System.Windows.Forms.DataGridView> Steuerelement. Im folgenden Codebeispiel wird die aktuelle Zelle 0, Spalte 1 Zeile festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- <xref:System.Windows.Forms.Button> Steuerelemente, die mit dem Namen `getCurrentCellButton` und `setCurrentCellButton`. In visuellen C#, Anfügen muss der <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugeordneten Ereignishandler im Beispielcode.  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
