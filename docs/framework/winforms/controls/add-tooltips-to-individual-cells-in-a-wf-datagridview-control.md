---
title: 'Vorgehensweise: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: 3307c92a13e5730de6dce0fe45b924e44b7af554
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640295"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Vorgehensweise: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms
Standardmäßig QuickInfos werden zum Anzeigen der Werte von <xref:System.Windows.Forms.DataGridView> Zellen, die zu klein, um den gesamten Inhalt anzuzeigen. Sie können dieses Verhalten jedoch überschreiben, um die QuickInfo-Text-Werte für einzelne Zellen festzulegen. Dies ist hilfreich, die Benutzer zusätzliche Informationen zu einer Zelle angezeigt oder eine alternative Beschreibung des Zelleninhalts Benutzern anbieten. Wenn Sie eine Zeile, die Statussymbole anzeigt verfügen, sollten Sie z. B. erklärungstexte, die mithilfe von QuickInfos bereitzustellen.  
  
 Sie können auch die Anzeige von QuickInfos auf Zellenebene deaktivieren, durch Festlegen der <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> Eigenschaft `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Eine QuickInfo auf eine Zelle hinzufügen  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>-Eigenschaft fest.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
- Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView> Steuerelement mit dem Namen `dataGridView1` , enthält eine Spalte namens `Rating` für die Anzeige von Zeichenfolgenwerten, die von einem bis vier Sternchen ("*") Symbole. Die <xref:System.Windows.Forms.DataGridView.CellFormatting> Ereignis des Steuerelements muss die Ereignishandlermethode, die im Beispiel gezeigte zugeordnet werden.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Beim Binden der <xref:System.Windows.Forms.DataGridView> die Steuerung an eine externe Datenquelle oder eine eigene Datenquelle durch Implementieren des virtuellen Modus bereitstellen, treten möglicherweise Leistungsprobleme auftreten. Um eine Leistungseinbuße zu vermeiden, bei der Arbeit mit großen Mengen von Daten, verarbeiten die <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> Ereignis anstelle der Einstellung der <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> -Eigenschaft mehrerer Zellen. Wenn Sie dieses Ereignis behandeln, beim Abrufen des Werts einer Zelle <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> Eigenschaft löst das-Ereignis aus und gibt den Wert des der <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> -Eigenschaft im Ereignishandler angegeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
