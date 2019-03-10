---
title: 'Vorgehensweise: Ausführen einer benutzerdefinierten Aktion basierend auf Änderungen in einer Zelle des DataGridView-Steuerelement für eine Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: ad1c60c34fc5461de21e2ad5d4d02f5b2abd6dfd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705583"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Vorgehensweise: Ausführen einer benutzerdefinierten Aktion basierend auf Änderungen in einer Zelle des DataGridView-Steuerelement für eine Windows Forms
Die <xref:System.Windows.Forms.DataGridView> Steuerelement hat eine Anzahl von Ereignissen Sie zum Erkennen von Änderungen in den Zustand des können <xref:System.Windows.Forms.DataGridView> Zellen. Die beiden am häufigsten verwendeten sind die <xref:System.Windows.Forms.DataGridView.CellValueChanged> und <xref:System.Windows.Forms.DataGridView.CellStateChanged> Ereignisse.  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>Zum Erkennen von Änderungen in die Werte von DataGridView-Zellen  
  
-   Schreiben Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellValueChanged> Ereignis.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>Änderungen am Zustand der DataGridView-Zellen erkannt  
  
-   Schreiben Sie einen Handler für die <xref:System.Windows.Forms.DataGridView.CellStateChanged> Ereignis.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`. Für C#, die Ereignishandler müssen eine Verbindung mit den entsprechenden Ereignissen.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [Exemplarische Vorgehensweise: Überprüfen von Daten in das DataGridView-Steuerelement in Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
