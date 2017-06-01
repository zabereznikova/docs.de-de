---
title: "Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Daten [Windows Forms], Überprüfung"
  - "Datenblätter, Validieren von Daten"
  - "Datenvalidierung, Windows Forms"
  - "DataGridView-Steuerelement [Windows Forms], Datenvalidierung"
  - "Validieren von Daten, Windows Forms"
  - "Exemplarische Vorgehensweisen [Windows Forms], DataGridView-Steuerelement"
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms
Bei der Anzeige von Dateneingabefunktionen für Benutzer müssen die in das Formular eingegebenen Daten häufig validiert werden.  Die <xref:System.Windows.Forms.DataGridView>\-Klasse bietet eine bequeme Möglichkeit zur Datenvalidierung, bevor für die Daten ein Commit ausgeführt und sie im Datenspeicher abgelegt werden.  Sie können Daten validieren, indem Sie das <xref:System.Windows.Forms.DataGridView.CellValidating>\-Ereignis behandeln, das von <xref:System.Windows.Forms.DataGridView> ausgelöst wird, sobald sich die aktuelle Zelle ändert.  
  
 In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der Tabelle `Customers` in der Beispieldatenbank Northwind ab und zeigen diese in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement an.  Wenn ein Benutzer eine Zelle in der Spalte `CompanyName` bearbeitet und die Zelle anschließend verlassen möchte, wird die Zeichenfolge mit dem neuen Firmennamen vom <xref:System.Windows.Forms.DataGridView.CellValidating>\-Ereignishandler überprüft, um sicherzustellen, dass sie nicht leer ist. Wenn es sich bei dem neuen Wert um eine leere Zeichenfolge handelt, wird durch <xref:System.Windows.Forms.DataGridView> verhindert, dass der Mauscursor des Benutzers in eine andere Zelle verschoben werden kann, bevor eine nicht leere Zeichenfolge eingegeben wird.  
  
 Informationen zum Kopieren des in diesem Thema behandelten Codes als einzelne Auflistung finden Sie unter [Gewusst wie: Überprüfen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server mit der SQL Server\-Beispieldatenbank Northwind  
  
## Erstellen des Formulars  
  
#### So validieren Sie die in DataGridView eingegebenen Daten  
  
1.  Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und die ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement sowie eine <xref:System.Windows.Forms.BindingSource>\-Komponente enthält.  
  
     Im folgenden Codebeispiel werden grundlegende Initialisierungsfeatures und eine `Main`\-Methode dargestellt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Implementieren Sie in der Klassendefinition des Formulars eine Methode zum Behandeln der Verbindungsdetails für die Datenbank.  
  
     In diesem Codebeispiel wird eine  `GetData` \-Methode verwendet, die ein gefülltes <xref:System.Data.DataTable>\-Objekt zurückgibt.  Die `connectionString`\-Variable muss auf einen Wert festgelegt werden, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen, beispielsweise Kennwörter, innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Sicherer lässt sich der Zugriff auf eine Datenbank mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars, durch das <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> initialisiert und die Datenbindung eingerichtet werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implementieren Sie Handler für das <xref:System.Windows.Forms.DataGridView.CellValidating>\-Ereignis und das <xref:System.Windows.Forms.DataGridView.CellEndEdit>\-Ereignis des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  
  
     Mithilfe des <xref:System.Windows.Forms.DataGridView.CellValidating>\-Ereignishandlers wird festgestellt, ob der Wert einer Zelle in der Spalte `CompanyName` leer ist.  Wenn die Validierung des Zellenwerts fehlschlägt, legen Sie die <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>\-Eigenschaft der <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=fullName>\-Klasse auf `true` fest.  Auf diese Weise verhindert das <xref:System.Windows.Forms.DataGridView>\-Steuerelement, dass der Cursor die Zelle verlässt.  Legen Sie für die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>\-Eigenschaft in der Zeile eine Zeichenfolge mit einer Erläuterung fest.  Auf diese Weise wird ein Fehlersymbol mit einer QuickInfo angezeigt, die den Fehlertext enthält.  Legen Sie im <xref:System.Windows.Forms.DataGridView.CellEndEdit>\-Ereignishandler die <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A>\-Eigenschaft in der Zeile auf die leere Zeichenfolge fest.  Das <xref:System.Windows.Forms.DataGridView.CellEndEdit>\-Ereignis tritt nur ein, wenn die Zelle den Bearbeitungsmodus verlässt, was nicht möglich ist, wenn die Validierung fehlschlägt.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## Testen der Anwendung  
 Sie können das Formular jetzt testen und prüfen, ob es sich wie wie erwartet verhält.  
  
#### So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sie sehen ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement, das Daten aus der Tabelle `Customers` enthält.  Wenn Sie auf eine Zelle in der Spalte `CompanyName` doppelklicken, können Sie den Wert bearbeiten.  Wenn Sie sämtliche Zeichen löschen und die TAB\-TASTE drücken, um in die nächste Zelle zu wechseln, werden Sie durch <xref:System.Windows.Forms.DataGridView> daran gehindert.  Wenn Sie eine nicht leere Zeichenfolge in die Zelle eingeben, werden Sie vom <xref:System.Windows.Forms.DataGridView>\-Steuerelement nicht daran gehindert, die Zelle zu verlassen.  
  
## Nächste Schritte  
 Anhand dieser Anwendung erhalten Sie einen grundlegenden Einblick in die Fähigkeiten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements auf vielfältige Weisen anpassen:  
  
-   Ändern von Rahmenart und Headerstil.  Weitere Informationen finden Sie unter [Gewusst wie: Ändern des Rahmen\- und Rasterlinienstils im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Beschränken von Benutzereingaben im <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Weitere Informationen finden Sie unter [Gewusst wie: Verhindern, das Zeilen im DataGridView\-Steuerelement in Windows Forms hinzugefügt und gelöscht werden](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) und [Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen der Benutzereingabe auf datenbankbezogene Fehler.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Behandeln sehr umfangreicher Datasets mithilfe des virtuellen Modus.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Gewusst wie: Festlegen von Schriftart\- und Farbstilen im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Dateneingabe im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Überprüfen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)   
 [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)