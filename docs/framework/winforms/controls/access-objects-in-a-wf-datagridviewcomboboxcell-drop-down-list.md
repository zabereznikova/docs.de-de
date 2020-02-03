---
title: Zugreifen auf Objekte in der DataGridViewComboBoxCell-Dropdown Liste
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], accessing objects in combo box cells
- combo boxes [Windows Forms], in DataGridView control
- combo boxes [Windows Forms], accessing objects in DataGridViewComboBoxCell drop-down lists
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
ms.openlocfilehash: 7e76ab1ac9089778e4371f4ee65b06d5ebc570bf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746307"
---
# <a name="how-to-access-objects-in-a-windows-forms-datagridviewcomboboxcell-drop-down-list"></a>Gewusst wie: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste
Wie das <xref:System.Windows.Forms.ComboBox>-Steuerelement können Sie mit den Typen <xref:System.Windows.Forms.DataGridViewComboBoxColumn> und <xref:System.Windows.Forms.DataGridViewComboBoxCell> beliebige Objekte zu ihren Dropdown Listen hinzufügen. Mit dieser Funktion können Sie komplexe Zustände in einer Dropdown Liste darstellen, ohne die entsprechenden Objekte in einer separaten Auflistung speichern zu müssen.  
  
 Im Gegensatz zum <xref:System.Windows.Forms.ComboBox>-Steuerelement verfügen die <xref:System.Windows.Forms.DataGridView> Typen nicht über eine <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>-Eigenschaft zum Abrufen des aktuell ausgewählten Objekts. Stattdessen müssen Sie die Eigenschaft <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=nameWithType> auf den Namen einer Eigenschaft für das Geschäftsobjekt festlegen. Wenn der Benutzer eine Auswahl trifft, legt die Eigenschaft des Geschäftsobjekts die Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A> Eigenschaft fest.  
  
 Um das Geschäftsobjekt über den Zellwert abzurufen, muss die `ValueMember`-Eigenschaft eine Eigenschaft angeben, die einen Verweis auf das Geschäftsobjekt selbst zurückgibt. Wenn sich der Typ des Geschäftsobjekts nicht unter ihrer Kontrolle befindet, müssen Sie daher eine solche Eigenschaft hinzufügen, indem Sie den Typ durch Vererbung erweitern.  
  
 Die folgenden Prozeduren veranschaulichen, wie Sie eine Dropdown Liste mit Geschäftsobjekten auffüllen und die Objekte über die Cell <xref:System.Windows.Forms.DataGridViewCell.Value%2A>-Eigenschaft abrufen.  
  
### <a name="to-add-business-objects-to-the-drop-down-list"></a>So fügen Sie der Dropdown Liste Geschäftsobjekte hinzu  
  
1. Erstellen Sie einen neuen <xref:System.Windows.Forms.DataGridViewComboBoxColumn>, und füllen Sie seine <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A> Sammlung auf. Alternativ können Sie die Spalte <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>-Eigenschaft auf die Auflistung der Geschäftsobjekte festlegen. In diesem Fall ist es jedoch nicht möglich, "nicht zugewiesen" der Dropdown Liste hinzuzufügen, ohne ein entsprechendes Geschäftsobjekt in ihrer Auflistung zu erstellen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2. Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> fest. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> gibt die Eigenschaft des Geschäftsobjekts an, das in der Dropdown Liste angezeigt werden soll. <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> gibt die Eigenschaft an, die einen Verweis auf das Geschäftsobjekt zurückgibt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3. Stellen Sie sicher, dass Ihr Geschäfts Objekttyp eine Eigenschaft enthält, die einen Verweis auf die aktuelle Instanz zurückgibt. Diese Eigenschaft muss mit dem Wert benannt werden, der <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> im vorherigen Schritt zugewiesen wurde.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### <a name="to-retrieve-the-currently-selected-business-object"></a>So rufen Sie das aktuell ausgewählte Geschäftsobjekt ab  
  
- Die Zelle <xref:System.Windows.Forms.DataGridViewCell.Value%2A>-Eigenschaft erhalten und in den Geschäfts Objekttyp umwandeln.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## <a name="example"></a>Beispiel  
 Das komplette Beispiel veranschaulicht die Verwendung von Geschäftsobjekten in einer Dropdown Liste. Im Beispiel ist ein <xref:System.Windows.Forms.DataGridView>-Steuerelement an eine Auflistung von `Task`-Objekten gebunden. Jedes `Task`-Objekt verfügt über eine `AssignedTo`-Eigenschaft, die das `Employee` Objekt angibt, das zurzeit der Aufgabe zugewiesen ist. In der Spalte `Assigned To` wird der Wert der `Name`-Eigenschaft für jeden zugewiesenen Mitarbeiter oder "nicht zugewiesen" angezeigt, wenn der `Task.AssignedTo`-Eigenschafts Wert `null`ist.  
  
 Führen Sie die folgenden Schritte aus, um das Verhalten dieses Beispiels anzuzeigen:  
  
1. Ändern Sie die Zuweisungen in der `Assigned To` Spalte, indem Sie unterschiedliche Werte aus den Dropdown Listen auswählen oder in einer Kombinations Feld Zelle STRG + 0 drücken.  
  
2. Klicken Sie auf `Generate Report`, um die aktuellen Zuweisungen anzuzeigen. Dadurch wird veranschaulicht, dass die `tasks` Auflistung durch eine Änderung in der Spalte `Assigned To` automatisch aktualisiert wird.  
  
3. Klicken Sie auf eine `Request Status` Schaltfläche, um die `RequestStatus`-Methode des aktuellen `Employee`-Objekts für diese Zeile aufzurufen. Dies zeigt, dass das ausgewählte Objekt erfolgreich abgerufen wurde.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Weitere Informationen

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
