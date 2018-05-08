---
title: 'Gewusst wie: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: 5117dfe2e017cf4af1d352fdbf23c6599c0e56a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Gewusst wie: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms
Standardmäßig können Benutzer den Inhalt des aktuellen bearbeiten <xref:System.Windows.Forms.DataGridView> Text im Feld Zelle durch darin eingeben oder durch Drücken von F2. Dies versetzt die Zelle im Bearbeitungsmodus befindet, wenn alle der folgenden Bedingungen erfüllt sind:  
  
-   Die zugrunde liegenden Datenquelle unterstützt bearbeiten.  
  
-   Die <xref:System.Windows.Forms.DataGridView> Steuerelement aktiviert ist.  
  
-   Die <xref:System.Windows.Forms.DataGridView.EditMode%2A> -Eigenschaftswert ist <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
-   Die `ReadOnly` Eigenschaften der Zelle, Zeile, Spalte und Steuerelement sind auf `false`.  
  
 Der Benutzer kann in den Bearbeitungsmodus wechseln ändern Sie den Zellenwert und drücken Sie EINGABETASTE, um einen commit der Änderung oder die ESC-Taste, um die Zelle auf den ursprünglichen Wert zurückzusetzen.  
  
 Sie können konfigurieren, eine <xref:System.Windows.Forms.DataGridView> steuern, sodass eine Zelle den Bearbeitungsmodus wechselt, sobald er zur aktiven Zelle wird. Das Verhalten der EINGABETASTE und ESC-Taste wird in diesem Fall nicht geändert, aber die Zelle im Bearbeitungsmodus bleibt, nachdem der Wert übernommen oder zurückgesetzt wird. Sie können auch das Steuerelement konfigurieren, sodass Zellen Bearbeitungsmodus nur, wenn Benutzer geben Sie in die Zelle oder nur, wenn Benutzer F2 drücken. Schließlich können Sie verhindern Zellen in den Bearbeitungsmodus wechselt, außer beim Aufrufen der <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> Methode.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>So ändern Sie den Bearbeitungsmodus eines DataGridView-Steuerelements  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.DataGridViewEditMode> Enumeration.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System> und <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [Dateneingabe im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
