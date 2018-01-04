---
title: "Gewusst wie: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a533f4cbf5000489e774ba8661c3ab03cea4948a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Gewusst wie: Hinzufügen von QuickInfos zu einzelnen Zellen in einem DataGridView-Steuerelement in Windows Forms
Standardmäßig QuickInfos werden zum Anzeigen der Werte von <xref:System.Windows.Forms.DataGridView> Zellen, die zu klein, um den gesamten Inhalt anzuzeigen. Sie können dieses Verhalten jedoch überschreiben, um QuickInfo-Text-Werte für einzelne Zellen festzulegen. Dies ist hilfreich, die Benutzer zusätzliche Informationen zu einer Zelle angezeigt oder eine alternative Beschreibung des Zelleninhalts Benutzer bereitzustellen. Haben eine Zeile, die Statussymbolen anzeigt, sollten Sie erläuterungen zu den Text mithilfe von QuickInfos bereitstellen.  
  
 Sie können die Anzeige von QuickInfos auf Zellenebene auch deaktivieren, indem die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> Eigenschaft `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>So fügen Sie eine QuickInfo auf eine Zelle hinzu  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>-Eigenschaft fest.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView> Steuerelement namens `dataGridView1` , enthält eine Spalte namens `Rating` für die Anzeige von Zeichenfolgenwerten, die von einem bis vier Sternchen ("*") Symbole. Die <xref:System.Windows.Forms.DataGridView.CellFormatting> -Ereignisses des Steuerelements muss die Ereignishandlermethode, die im Beispiel gezeigte zugeordnet werden.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Beim Binden der <xref:System.Windows.Forms.DataGridView> die Steuerung an eine externe Datenquelle oder eine eigene Datenquelle durch das Implementieren des virtuellen Modus bereitstellen, treten möglicherweise Leistungsprobleme auftreten. Um Leistungseinbußen zu vermeiden, bei der Arbeit mit großen Datenmengen, behandeln die <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> Ereignis statt der Einstellung der <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> Eigenschaft aus mehreren Zellen. Wenn Sie dieses Ereignis behandeln, Abrufen des Werts einer Zelle <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> Eigenschaft löst das-Ereignis aus und gibt den Wert der <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> -Eigenschaft im Ereignishandler angegeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
