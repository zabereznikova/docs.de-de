---
title: "Gewusst wie: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Kombinationsfelder, Zugreifen auf Objekte in DataGridViewComboBoxCell-Dropdownlisten"
  - "Kombinationsfelder, Im DataGridView-Steuerelement"
  - "DataGridView-Steuerelement [Windows Forms], Zugreifen auf Objekte in Kombinationsfeldzellen"
ms.assetid: bcbe794a-d1fa-47f8-b5a3-5f085b32097d
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Gewusst wie: Zugreifen auf Objekte in einer Windows Forms-DataGridViewComboBoxCell-Dropdownliste
Ähnlich wie das <xref:System.Windows.Forms.ComboBox>\-Steuerelement ermöglichen der <xref:System.Windows.Forms.DataGridViewComboBoxColumn>\-Typ und der <xref:System.Windows.Forms.DataGridViewComboBoxCell>\-Typ das Hinzufügen beliebiger Objekte zu den entsprechenden Dropdownlisten.  Mit diesem Feature können Sie komplizierte Funktionen in einer Dropdownliste darstellen, ohne entsprechende Objekte in einer getrennten Auflistung speichern zu müssen.  
  
 Im Gegensatz zum <xref:System.Windows.Forms.ComboBox>\-Steuerelement verfügen die <xref:System.Windows.Forms.DataGridView>\-Typen nicht über eine <xref:System.Windows.Forms.ComboBox.SelectedItem%2A>\-Eigenschaft zum Abrufen des aktuell ausgewählten Objekts.  Stattdessen müssen Sie die <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName>\-Eigenschaft oder die <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName>\-Eigenschaft auf den Namen einer Eigenschaft des Geschäftsobjekts festlegen.  Wenn der Benutzer eine Auswahl vornimmt, wird die <xref:System.Windows.Forms.DataGridViewCell.Value%2A>\-Eigenschaft der Zelle durch die angegebene Eigenschaft des Geschäftsobjekts festgelegt.  
  
 Um das Geschäftsobjekt mithilfe des Zellwerts abzurufen, muss die `ValueMember`\-Eigenschaft eine Eigenschaft angeben, die einen Verweis auf das Geschäftsobjekt selbst zurückgibt.  Sie müssen daher, wenn der Typ des Geschäftsobjekts nicht von Ihnen gesteuert werden kann, eine solche Eigenschaft hinzufügen, indem Sie den Typ durch Vererbung erweitern.  
  
 In den folgenden Verfahren wird das Auffüllen einer Dropdownliste mit Geschäftsobjekten und das Abrufen dieser Objekte mit der <xref:System.Windows.Forms.DataGridViewCell.Value%2A>\-Eigenschaft veranschaulicht.  
  
### So fügen Sie der Dropdownliste Geschäftsobjekte hinzu  
  
1.  Erstellen Sie eine neue <xref:System.Windows.Forms.DataGridViewComboBoxColumn>. und füllen Sie die <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A>\-Auflistung auf.  Sie können wahlweise auch die <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A>\-Eigenschaft der Spalte auf die Auflistung der Geschäftsobjekte festlegen.  Der Dropdownliste kann in diesem Fall jedoch nicht "Nicht zugewiesen" hinzugefügt werden, ohne ein entsprechendes Geschäftsobjekt in der Auflistung zu erstellen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#110)]  
  
2.  Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> und <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> fest.  <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DisplayMember%2A> gibt die in der Dropdownliste anzuzeigende Eigenschaft des Geschäftsobjekts an.  Eine <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> gibt die Eigenschaft an, die einen Verweis auf das Geschäftsobjekt zurückgibt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#115)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#115](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#115)]  
  
3.  Stellen Sie sicher, dass der Geschäftsobjekttyp eine Eigenschaft enthält, die einen Verweis auf die aktuelle Instanz zurückgibt.  Diese Eigenschaft muss mit dem Wert benannt werden, der im vorherigen Schritt <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A> zugewiesen wurde.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#310)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#310](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#310)]  
  
### So rufen Sie das derzeit ausgewählte Geschäftsobjekt ab  
  
-   Rufen Sie die <xref:System.Windows.Forms.DataGridViewCell.Value%2A>\-Eigenschaft der Zelle ab. Wandeln Sie die Eigenschaft in den Geschäftsobjekttyp um.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#120)]  
  
## Beispiel  
 Im vollständigen Beispiel wird das Verwenden von Geschäftsobjekten in einer Dropdownliste veranschaulicht.  Im Beispiel wird ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement an eine Auflistung von `Task`\-Objekten gebunden.  Jedes `Task`\-Objekt verfügt über eine `AssignedTo`\-Eigenschaft, die das `Employee`\-Objekt angibt, das der Aufgabe derzeit zugewiesen ist.  In der Spalte `Assigned To` wird der `Name`\-Eigenschaftswert für jeden zugewiesenen Mitarbeiter bzw. "Nicht zugewiesen" angezeigt, wenn die `Task.AssignedTo`\-Eigenschaft den Wert `null` hat.  
  
 Gehen Sie zum Darstellen des Verhaltens dieses Beispiels folgendermaßen vor:  
  
1.  Ändern Sie Zuweisungen in der Spalte `Assigned To`, indem Sie in den Dropdownlisten verschiedene Werte auswählen oder in einer Kombinationsfeldzelle die Tastenkombination STRG\+0 drücken.  
  
2.  Klicken Sie auf `Generate Report`, um die aktuellen Zuweisungen anzuzeigen.  Hierdurch wird veranschaulicht, dass die `tasks`\-Auflistung bei Änderungen in der Spalte `Assigned To` automatisch aktualisiert wird.  
  
3.  Klicken Sie auf eine `Request Status`\-Schaltfläche, um die `RequestStatus`\-Methode des aktuellen `Employee`\-Objekts für diese Zeile abzurufen.  Hierdurch wird veranschaulicht, dass das ausgewählte Objekt erfolgreich abgerufen wurde.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/CS/form1.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewComboBoxObjectBinding#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewComboBoxObjectBinding/vb/form1.vb#000)]  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf die Assemblys System und System.Windows.Forms.  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxColumn.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.DataSource%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewComboBoxCell.ValueMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell.Value%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ComboBox>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)