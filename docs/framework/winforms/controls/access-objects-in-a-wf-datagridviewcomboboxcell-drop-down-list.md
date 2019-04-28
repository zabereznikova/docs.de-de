---
title: 'Vorgehensweise: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 17b7c93effe9338a9e2d6cb207a948a956d9b666
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640428"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Vorgehensweise: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste
Wie die <xref:System.Windows.Forms.ComboBox> -Steuerelement, das <xref:System.Windows.Forms.DataGridViewComboBoxColumn> und <xref:System.Windows.Forms.DataGridViewComboBoxCell> Typen ermöglichen es Ihnen, beliebige Objekte in die Dropdown-Liste hinzufügen. Mit diesem Feature können Sie komplexer Zustände in einer Dropdown-Liste darstellen, ohne entsprechenden Objekte in einer separaten Sammlung speichern zu müssen.  
  
 Im Gegensatz zu den <xref:System.Windows.Forms.ComboBox> -Steuerelement, das <xref:System.Windows.Forms.DataGridView> Typen verfügen nicht über eine <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> -Eigenschaft für das aktuell ausgewählte Objekt abrufen. Stattdessen müssen Sie festlegen der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> -Eigenschaft auf den Namen einer Eigenschaft für das Business-Objekt. Wenn der Benutzer eine Auswahl trifft, legt die angegebene Eigenschaft des das Geschäftsobjekt, das die Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft.  
  
 Das Geschäftsobjekt, das durch den Wert der Zelle Abrufen der `ValueMember` Eigenschaft muss angeben, dass eine Eigenschaft, die einen Verweis auf das Geschäftsobjekt, das sich selbst zurückgibt. Wenn der Typ des Geschäftsobjekts nicht unter Ihrer Kontrolle ist, müssen Sie aus diesem Grund eine solche Eigenschaft hinzufügen, durch den Typ durch Vererbung erweitern.  
  
 Die folgenden Verfahren wird veranschaulicht, wie zum Auffüllen einer Dropdownliste mit Geschäftsobjekten und zum Abrufen der Objekte über die Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Hinzufügen von Geschäftsobjekten auf die Dropdown-Liste  
  
1. Erstellen Sie ein neues <xref:System.Windows.Forms.DataGridViewComboBoxColumn> , und füllen Sie die <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> Auflistung. Alternativ können Sie festlegen, die Spalte <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> Eigenschaft, um die Auflistung von Geschäftsobjekten. In diesem Fall können nicht, Sie jedoch hinzufügen "nicht zugeordnete" auf die Dropdown-Liste ohne eine entsprechende Geschäftsobjekt, das in Ihrer Sammlung erstellen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. Legen Sie für die Eigenschaften <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> fest. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> Gibt die Eigenschaft an das Geschäftsobjekt, das in der Dropdown Liste angezeigt. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> Gibt die Eigenschaft, die einen Verweis auf das Geschäftsobjekt zurückgibt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. Stellen Sie sicher, dass für der Geschäftstyp für das Objekt eine Eigenschaft enthält, die einen Verweis auf die aktuelle Instanz zurückgibt. Diese Eigenschaft muss den Namen mit den zugewiesenen Wert <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> im vorherigen Schritt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Das aktuell ausgewählte Geschäftsobjekt abrufen  
  
- Abrufen der Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft und wandeln sie in der Business-Objekttyp.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Beispiel  
 Das vollständige Beispiel veranschaulicht die Verwendung von Geschäftsobjekten in einem Dropdown-Liste. Im Beispiel eine <xref:System.Windows.Forms.DataGridView> -Steuerelement gebunden ist, eine Auflistung von `Task` Objekte. Jede `Task` Objekt verfügt über eine `AssignedTo` Eigenschaft, die angibt der `Employee` -Objekt, für die jeweilige Aufgabe gerade zugewiesen. Die `Assigned To` angezeigt, die `Name` zugewiesenen Wert für die einzelnen, Mitarbeiter oder "nicht zugewiesen", wenn die `Task.AssignedTo` Eigenschaftswert ist `null`.  
  
 Um das Verhalten der in diesem Beispiel anzuzeigen, führen Sie die folgenden Schritte aus:  
  
1. Ändern von Zuweisungen in der `Assigned To` Spalte nach dem auswählen abweichender Parameterwerte aus den Dropdown-Listen, oder drücken STRG + 0, die in einer Zelle im Kombinationsfeld.  
  
2. Klicken Sie auf `Generate Report` um die aktuellen Zuweisungen anzuzeigen. Dies zeigt, dass eine Änderung in der `Assigned To` Spalte automatisch aktualisiert, die `tasks` Auflistung.  
  
3. Klicken Sie auf eine `Request Status` Schaltfläche zum Aufrufen der `RequestStatus` Methode des aktuellen `Employee` Objekt für diese Zeile. Dies zeigt, dass das ausgewählte Objekt erfolgreich abgerufen wurde.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ComboBox>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
