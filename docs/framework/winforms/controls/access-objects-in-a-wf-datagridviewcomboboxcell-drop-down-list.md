---
title: 'Gewusst wie: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 2758841031be9ca9f0a5eb5e57165191d6870e87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529401"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Gewusst wie: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste
Wie die <xref:System.Windows.Forms.ComboBox> -Steuerelement, das <xref:System.Windows.Forms.DataGridViewComboBoxColumn> und <xref:System.Windows.Forms.DataGridViewComboBoxCell> Typen ermöglichen es Ihnen, beliebige Objekte in die Dropdown-Liste hinzufügen. Mit dieser Funktion können Sie komplexe Zuständen in einer Dropdownliste darstellen, ohne entsprechende Objekte in eine eigene Auflistung zu speichern.  
  
 Im Gegensatz zu den <xref:System.Windows.Forms.ComboBox> -Steuerelement, das <xref:System.Windows.Forms.DataGridView> Typen verfügen nicht über eine <xref:System.Windows.Forms.ComboBox.SelectedItem%2A> -Eigenschaft für das aktuell ausgewählte Objekt abrufen. Sie müssen stattdessen Festlegen der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> -Eigenschaft auf den Namen einer Eigenschaft das Geschäftsobjekt. Wenn der Benutzer eine Auswahl trifft, legt die angegebene Eigenschaft des Geschäftsobjekts Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft.  
  
 Beim Abrufen des Objekts Business, durch den Wert der Zelle die `ValueMember` Eigenschaft muss angeben, dass eine Eigenschaft, die einen Verweis auf das Geschäftsobjekt selbst zurückgibt. Ist der Typ des Geschäftsobjekts nicht steuern können, müssen Sie daher eine solche Eigenschaft hinzufügen, durch die Erweiterung des Typs durch Vererbung.  
  
 Die folgenden Verfahren veranschaulichen, wie Sie Auffüllen einer Dropdownliste mit Geschäftsobjekten und das Abrufen der Objekte über die Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>Die Dropdown-Liste Geschäftsobjekte hinzu  
  
1.  Erstellen Sie ein neues <xref:System.Windows.Forms.DataGridViewComboBoxColumn> , und füllen Sie seine <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> Auflistung. Alternativ können Sie festlegen, die Spalte <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A> Eigenschaft auf die Auflistung von Geschäftsobjekten. In diesem Fall können nicht, Sie jedoch hinzufügen "nicht zugewiesene" auf die Dropdown-Liste ohne Erstellen eines entsprechenden Business-Objekts in der Auflistung.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  Legen Sie für die Eigenschaften <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> fest. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> Gibt die Eigenschaft an das Geschäftsobjekt, das in der Dropdown Liste angezeigt. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> Gibt an, die Eigenschaft, die einen Verweis auf das Geschäftsobjekt zurückgibt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  Stellen Sie sicher, dass für der Geschäftstyp für das Objekt eine Eigenschaft enthält, die einen Verweis auf die aktuelle Instanz zurückgibt. Diese Eigenschaft muss den Namen mit den zugewiesenen Wert <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> im vorherigen Schritt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>Das aktuell ausgewählte Geschäftsobjekt abrufen  
  
-   Abrufen der Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft in Business Object-Typ umgewandelt werden muss.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Beispiel  
 Das vollständige Beispiel veranschaulicht die Verwendung von Geschäftsobjekten in einer Dropdownliste. Im Beispiel eine <xref:System.Windows.Forms.DataGridView> gebunden ist, eine Auflistung von `Task` Objekte. Jede `Task` Objekt verfügt über eine `AssignedTo` Eigenschaft, die anzeigt die `Employee` Objekts, das diese Aufgabe derzeit zugewiesen. Die `Assigned To` Spalte zeigt die `Name` Wert für jede Eigenschaft zugewiesen, Mitarbeiter oder "nicht zugewiesene", wenn die `Task.AssignedTo` Eigenschaftswert ist `null`.  
  
 Um das Verhalten dieses Beispiels anzuzeigen, führen Sie die folgenden Schritte aus:  
  
1.  Ändern Sie die Zuweisungen in der `Assigned To` Spalte nach dem auswählen abweichender Parameterwerte aus den Dropdown-Listen, oder drücken STRG + 0 in einer Zelle im Kombinationsfeld.  
  
2.  Klicken Sie auf `Generate Report` um den aktuellen Zuweisungen anzuzeigen. Dies zeigt, dass eine Änderung in der `Assigned To` Spalte automatisch aktualisiert, die `tasks` Auflistung.  
  
3.  Klicken Sie auf eine `Request Status` Schaltfläche zum Aufrufen der `RequestStatus` Methode des aktuellen `Employee` Objekt für diese Zeile. Dadurch wird bewiesen, dass das ausgewählte Objekt erfolgreich abgerufen wurde.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ComboBox>  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
