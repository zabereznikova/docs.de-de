---
title: Festlegen der Sortierungs Modi für Spalten im DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742997"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms
Im <xref:System.Windows.Forms.DataGridView> Steuerelement wird bei Text Feld Spalten standardmäßig die automatische Sortierung verwendet, während andere Spaltentypen nicht automatisch sortiert werden. Manchmal sollten Sie diese Standardeinstellungen überschreiben. Beispielsweise können Sie Bilder anstelle von Text-, Zahlen-oder enumerationszellwerten anzeigen. Obwohl die Bilder nicht sortiert werden können, können die zugrunde liegenden Werte sortiert werden.  
  
 Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>-Eigenschafts Wert einer Spalte das Sortier Verhalten.  
  
 Das folgende Verfahren zeigt die `Priority` Spalte unter Gewusst [wie: Anpassen der Datenformatierung im Windows Forms DataGridView-Steuer](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)Element. Diese Spalte ist eine Image-Spalte und ist nicht standardmäßig sortierbar. Sie enthält jedoch tatsächliche Zellwerte, bei denen es sich um Zeichen folgen handelt, sodass Sie automatisch sortiert werden kann.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>So legen Sie den Sortiermodus für eine Spalte fest  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>-Eigenschaft fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1`, das eine Spalte namens `Priority` enthält.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [Sortieren von Daten im DataGridView-Steuerelement in Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Spaltensortiermodi im DataGridView-Steuerelement von Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
