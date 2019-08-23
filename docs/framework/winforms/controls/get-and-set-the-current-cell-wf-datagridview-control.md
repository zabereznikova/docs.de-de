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
ms.openlocfilehash: 670708f342e1cd1ac495c215b7508093349ac2e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933702"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms
Die Interaktion mit <xref:System.Windows.Forms.DataGridView> dem erfordert häufig, dass Sie Programm gesteuert ermitteln, welche Zelle derzeit aktiv ist. Möglicherweise müssen Sie auch die aktuelle Zelle ändern. Sie können diese Aufgaben mit der <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> -Eigenschaft ausführen.  
  
> [!NOTE]
> Die aktuelle Zelle kann nicht in einer Zeile oder Spalte festgelegt werden, <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> deren-Eigenschaft `false`auf festgelegt ist.  
  
 Abhängig vom Auswahl <xref:System.Windows.Forms.DataGridView> Modus des-Steuer Elements kann das Ändern der aktuellen Zelle die Auswahl ändern. Weitere Informationen finden Sie unter [Auswahl Modi im Windows Forms DataGridView-Steuer](selection-modes-in-the-windows-forms-datagridview-control.md)Element.  
  
### <a name="to-get-the-current-cell-programmatically"></a>So erhalten Sie die aktuelle Zelle Programm gesteuert  
  
- Verwenden Sie <xref:System.Windows.Forms.DataGridView> die- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> Eigenschaft des-Steuer Elements.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>So legen Sie die aktuelle Zelle Programm gesteuert fest  
  
- Legen Sie <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> die-Eigenschaft <xref:System.Windows.Forms.DataGridView> des-Steuer Elements fest. Im folgenden Codebeispiel wird die aktuelle Zelle auf Zeile 0, Spalte 1, festgelegt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- <xref:System.Windows.Forms.Button>Steuerelemente `getCurrentCellButton` mit `setCurrentCellButton`dem Namen und. In Visual C#müssen Sie die <xref:System.Windows.Forms.Control.Click> Ereignisse für jede Schaltfläche an den zugeordneten Ereignishandler im Beispielcode anfügen.  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Auswahlmodi im DataGridView-Steuerelement von Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
