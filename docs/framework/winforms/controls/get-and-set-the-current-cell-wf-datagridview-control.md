---
title: Anzeigen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 0fb01d5392e02b53e0e5bf905c872dbeeb22fad9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745660"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms
Die Interaktion mit dem <xref:System.Windows.Forms.DataGridView> erfordert häufig, dass Sie Programm gesteuert ermitteln, welche Zelle derzeit aktiv ist. Möglicherweise müssen Sie auch die aktuelle Zelle ändern. Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>-Eigenschaft ausführen.  
  
> [!NOTE]
> Die aktuelle Zelle kann nicht in einer Zeile oder Spalte festgelegt werden, deren <xref:System.Windows.Forms.DataGridViewBand.Visible%2A>-Eigenschaft auf `false`festgelegt ist.  
  
 Abhängig vom Auswahlmodus des <xref:System.Windows.Forms.DataGridView> Steuer Elements kann das Ändern der aktuellen Zelle die Auswahl ändern. Weitere Informationen finden Sie unter [Auswahl Modi im Windows Forms DataGridView-Steuer](selection-modes-in-the-windows-forms-datagridview-control.md)Element.  
  
### <a name="to-get-the-current-cell-programmatically"></a>So erhalten Sie die aktuelle Zelle Programm gesteuert  
  
- Verwenden Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridView> Steuer Elements.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>So legen Sie die aktuelle Zelle Programm gesteuert fest  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.CurrentCell%2A>-Eigenschaft des <xref:System.Windows.Forms.DataGridView> Steuer Elements fest. Im folgenden Codebeispiel wird die aktuelle Zelle auf Zeile 0, Spalte 1, festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- <xref:System.Windows.Forms.Button> Steuerelemente mit dem Namen `getCurrentCellButton` und `setCurrentCellButton`. In Visual C#müssen Sie die <xref:System.Windows.Forms.Control.Click>-Ereignisse für jede Schaltfläche an den zugeordneten Ereignishandler im Beispielcode anfügen.  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
