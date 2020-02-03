---
title: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743762"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Gewusst wie: Festlegen des Bearbeitungsmodus für das DataGridView-Steuerelement in Windows Forms
Standardmäßig können Benutzer den Inhalt der aktuellen <xref:System.Windows.Forms.DataGridView> Textfeld-Zelle bearbeiten, indem Sie Sie eingeben oder F2 drücken. Dadurch wird die Zelle in den Bearbeitungsmodus versetzt, wenn alle der folgenden Bedingungen erfüllt sind:  
  
- Die zugrunde liegende Datenquelle unterstützt die Bearbeitung.  
  
- Das <xref:System.Windows.Forms.DataGridView> Steuerelement ist aktiviert.  
  
- Der <xref:System.Windows.Forms.DataGridView.EditMode%2A>-Eigenschaftswert lautet nicht <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
- Die `ReadOnly` Eigenschaften von Zelle, Zeile, Spalte und Steuerelement sind auf `false`festgelegt.  
  
 Im Bearbeitungsmodus kann der Benutzer den Zellwert ändern und die EINGABETASTE drücken, um die Änderung zu übernehmen, oder ESC, um die Zelle auf den ursprünglichen Wert zurückzusetzen.  
  
 Sie können ein <xref:System.Windows.Forms.DataGridView> Steuerelement so konfigurieren, dass eine Zelle in den Bearbeitungsmodus wechselt, sobald Sie zur aktuellen Zelle wird. Das Verhalten der Enter-Taste und der ESC-Taste ist in diesem Fall unverändert, aber die Zelle bleibt im Bearbeitungsmodus, nachdem ein Commit oder ein Commit für den Wert ausgeführt wurde. Sie können das Steuerelement auch so konfigurieren, dass die Zellen in den Bearbeitungsmodus wechseln, wenn Benutzer in der Zelle eingeben oder nur dann, wenn Benutzer die Taste F2 drücken. Schließlich können Sie verhindern, dass Zellen in den Bearbeitungsmodus wechseln, außer wenn Sie die <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>-Methode aufrufen.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>So ändern Sie den Bearbeitungsmodus eines DataGridView-Steuer Elements  
  
- Legen Sie die <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>-Eigenschaft auf die entsprechende <xref:System.Windows.Forms.DataGridViewEditMode> Enumeration fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System> und <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Dateneingabe im DataGridView-Steuerelement in Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
