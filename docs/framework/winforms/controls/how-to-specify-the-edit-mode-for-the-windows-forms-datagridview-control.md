---
title: 'Vorgehensweise: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: 7cb9278cd311d211ef95df238b930970ae472d05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012944"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Vorgehensweise: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms
Standardmäßig können Benutzer bearbeiten Sie den Inhalt des aktuellen <xref:System.Windows.Forms.DataGridView> Textfeldzelle, indem Sie darin eingeben oder F2 drücken. Dadurch wird die Zelle im Bearbeitungsmodus befindet, wenn alle der folgenden Bedingungen erfüllt sind:  
  
- Die zugrunde liegenden Datenquelle unterstützt die Bearbeitung.  
  
- Die <xref:System.Windows.Forms.DataGridView> -Steuerelements aktiviert ist.  
  
- Die <xref:System.Windows.Forms.DataGridView.EditMode%2A> Eigenschaftswert ist keine <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
- Die `ReadOnly` Eigenschaften der Zelle, Zeile, Spalte und Steuerelement sind mit `false`.  
  
 Im Bearbeitungsmodus befindet kann der Benutzer ändern Sie den Zellenwert, und drücken Sie EINGABETASTE zum committen der Änderung oder die ESC-Taste, um die Zelle auf den ursprünglichen Wert zurückgesetzt.  
  
 Sie können konfigurieren, eine <xref:System.Windows.Forms.DataGridView> Steuerelement, sodass eine Zelle den Bearbeitungsmodus versetzt wird, sobald sie die aktuelle Zelle wird. Das Verhalten der Schlüssel eingeben und die ESC-Taste wird in diesem Fall nicht geändert, aber die Zelle im Bearbeitungsmodus bleibt, nachdem der Wert ein Commit oder zurückgesetzt wird. Sie können auch das Steuerelement konfigurieren, sodass Zellen Bearbeitungsmodus eingeben, nur wenn der Benutzer in der Zelle oder nur, wenn Benutzer F2 drücken. Schließlich können Sie verhindern Zellen in den Bearbeitungsmodus wechselt, außer beim Aufrufen der <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> Methode.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>So ändern Sie den Bearbeitungsmodus des DataGridView-Steuerelements  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.DataGridViewEditMode> Enumeration.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System> und <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
