---
title: Fixieren von Spalten im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
ms.openlocfilehash: 6d1a98e5c4332078c6012cb7c9ed836108abd86c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736742"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Fixieren von Spalten im DataGridView-Steuerelement in Windows Forms
Wenn Benutzer Daten anzeigen, die in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement in Windows Forms angezeigt werden, müssen sie mitunter häufig auf eine bestimmte Spalte oder Gruppe von Spalten zugreifen. Wenn Sie beispielsweise eine Tabelle mit Kundendaten anzeigen, die viele Spalten enthält, ist es hilfreich, wenn die Namen der Kunden immer angezeigt werden, während andere Spalten außerhalb des sichtbaren Bereichs liegen.  
  
 Zu diesem Zweck können Sie Spalten im Steuerelement fixieren. Wenn Sie eine Spalte fixieren, werden automatisch auch alle Spalten links daneben (bzw. rechts daneben in von rechts nach links geschriebenen Sprachen) fixiert. Fixierte Spalten behalten ihre Position bei, während alle anderen Spalten bei einem Bildlauf mitwandern.  
  
> [!NOTE]
> Wenn die Neuanordnung von Spalten aktiviert ist, werden die fixierten Spalten als eine Gruppe im Unterschied zu den nicht fixierten Spalten behandelt. Benutzer können Spalten in beiden Gruppen neu positionieren, jedoch keine Spalte aus einer Gruppe in die andere verschieben.  
  
 Die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A>-Eigenschaft einer Spalte bestimmt, ob die Spalte immer innerhalb des Rasters sichtbar ist.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch Gewusst [wie: Fixieren von Spalten im Windows Forms DataGridView-Steuerelement mithilfe des Designers](freeze-columns-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-freeze-a-column-programmatically"></a>So fixieren Sie eine Spalte programmgesteuert  
  
- Setzen Sie die <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>-Eigenschaft auf `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte namens `AddToCartButton` enthält.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Gewusst wie: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
