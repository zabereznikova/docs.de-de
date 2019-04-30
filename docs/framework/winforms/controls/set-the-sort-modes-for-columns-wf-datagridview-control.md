---
title: 'Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 4894de00a323f70ca244ea877101a5af1cbb37e0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012190"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Festlegen der Sortierungsmodi für Spalten im DataGridView-Steuerelement in Windows Forms
In der <xref:System.Windows.Forms.DataGridView> Steuerung, verwenden die in den Spalten der Box automatische Sortierung in der Standardeinstellung, während andere Spaltentypen nicht automatisch sortiert werden. Manchmal möchten Sie diese Standardeinstellungen überschreiben. Beispielsweise können Sie Bilder anstelle von Text, Zahlen oder Enumerationswerte für die Zelle anzeigen. Während die Bilder nicht sortiert werden, können die zugrunde liegenden Werte, die sie darstellen, sortiert werden.  
  
 In der <xref:System.Windows.Forms.DataGridView> -Steuerelement, das <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> ihr Sortierverhalten bestimmt der Wert einer Spalte.  
  
 Die folgende Prozedur zeigt die `Priority` Spalte [Vorgehensweise: Anpassen der Datenformatierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Diese Spalte ist eine Image-Spalte und ist nicht standardmäßig sortierbar. Sie enthält tatsächlichen Zellwerte, die Zeichenfolgen, jedoch sind, damit es automatisch sortiert werden kann.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Um den Sortiermodus für eine Spalte festzulegen.  
  
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
- [Vorgehensweise: Anpassen der Sortierung im DataGridView-Steuerelement in Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
