---
title: Ausführen benutzerdefinierter Aktionen auf der Grundlage von Änderungen in einer Zelle des DataGridView-Steuer Elements
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: a809134b0a79bc9685c5b84acce58b4c61b5c526
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744281"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Gewusst wie: Ausführen einer benutzerdefinierten Aktion aufgrund von Änderungen in einer Zelle des DataGridView-Steuerelements in Windows Forms
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement verfügt über eine Reihe von Ereignissen, die Sie verwenden können, um Änderungen im Status von <xref:System.Windows.Forms.DataGridView> Zellen zu erkennen. Zwei der am häufigsten verwendeten Ereignisse sind die <xref:System.Windows.Forms.DataGridView.CellValueChanged>-und <xref:System.Windows.Forms.DataGridView.CellStateChanged>-Ereignisse.  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>So erkennen Sie Änderungen an den Werten von DataGridView-Zellen  
  
- Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellValueChanged>-Ereignis.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>So erkennen Sie Änderungen in den Zuständen von DataGridView-Zellen  
  
- Schreiben Sie einen Handler für das <xref:System.Windows.Forms.DataGridView.CellStateChanged>-Ereignis.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`. Für C#müssen die Ereignishandler mit den entsprechenden Ereignissen verbunden werden.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
