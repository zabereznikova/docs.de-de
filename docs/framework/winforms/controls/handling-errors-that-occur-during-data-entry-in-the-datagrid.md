---
title: "Exemplarische Vorgehensweise: Behandeln von Fehlern, die w&#228;hrend der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten | Microsoft Docs"
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
  - "Dateneingabe, Fehlerbehandlung"
  - "Datenblätter, Fehlerbehandlung"
  - "DataGridView-Steuerelement [Windows Forms], Fehlerbehandlung"
  - "Fehlerbehandlung, Dateneingabe"
  - "Fehlerbehandlung, DataGridView-Steuerelement"
  - "Exemplarische Vorgehensweisen [Windows Forms], DataGridView-Steuerelement"
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Exemplarische Vorgehensweise: Behandeln von Fehlern, die w&#228;hrend der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten
Das Behandeln von Fehlern, die vom zugrunde liegenden Datenspeicher gemeldet werden, ist für ein Datenerfassungsprogramm unverzichtbar.  Das <xref:System.Windows.Forms.DataGridView>\-Steuerelement in Windows Forms unterstützt diesen Aspekt mithilfe des <xref:System.Windows.Forms.DataGridView.DataError>\-Ereignisses, das ausgelöst wird, wenn vom Datenspeicher die Verletzung einer Einschränkung oder Geschäftsregel festgestellt wird.  
  
 In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der Tabelle `Customers` in der Beispieldatenbank Northwind ab und zeigen diese in einem <xref:System.Windows.Forms.DataGridView>\-Steuerelement an.  Wenn in einer neuen oder bearbeiteten vorhandenen Zeile ein doppelter Wert `CustomerID` gefunden wird, tritt das <xref:System.Windows.Forms.DataGridView.DataError>\-Ereignis auf. Das Ereignis wird durch die Anzeige von <xref:System.Windows.Forms.MessageBox> behandelt, in dem die Ausnahme beschrieben wird.  
  
 Informationen zum Kopieren des in diesem Thema enthaltenen Codes als einzelne Auflistung finden Sie unter [Gewusst wie: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server mit der SQL Server\-Beispieldatenbank Northwind  
  
## Erstellen des Formulars  
  
#### So behandeln Sie Dateneingabefehler im DataGridView\-Steuerelement  
  
1.  Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und die ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement sowie eine <xref:System.Windows.Forms.BindingSource>\-Komponente enthält.  
  
     Im folgenden Codebeispiel werden grundlegende Initialisierungsfeatures und eine `Main`\-Methode dargestellt.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implementieren Sie in der Klassendefinition des Formulars eine Methode zum Behandeln der Verbindungsdetails für die Datenbank.  
  
     In diesem Codebeispiel wird eine  `GetData` \-Methode verwendet, die ein gefülltes <xref:System.Data.DataTable>\-Objekt zurückgibt.  Die `connectionString`\-Variable muss auf einen Wert festgelegt werden, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen, beispielsweise Kennwörter, innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) sicherer steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars, durch das <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> initialisiert und die Datenbindung eingerichtet werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Behandeln Sie das <xref:System.Windows.Forms.DataGridView.DataError>\-Ereignis in <xref:System.Windows.Forms.DataGridView>.  
  
     Wenn der Kontext für den Fehler einem Commitvorgang entspricht, zeigen Sie den Fehler in <xref:System.Windows.Forms.MessageBox> an.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## Testen der Anwendung  
 Sie können das Formular jetzt testen und prüfen, ob es sich wie wie erwartet verhält.  
  
#### So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Es wird ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement angezeigt, das mit Daten aus der Tabelle Customers gefüllt ist.  Wenn Sie für `CustomerID` einen doppelten Wert eingeben und ein Commit für den Bearbeitungsvorgang ausführen, wird der Zellwert automatisch wieder zurückversetzt und <xref:System.Windows.Forms.MessageBox> mit dem Dateneingabefehler angezeigt.  
  
## Nächste Schritte  
 Anhand dieser Anwendung erhalten Sie einen grundlegenden Einblick in die Fähigkeiten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements auf vielfältige Weisen anpassen:  
  
-   Ändern von Rahmenart und Headerstil.  Weitere Informationen finden Sie unter [Gewusst wie: Ändern des Rahmen\- und Rasterlinienstils im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Beschränken von Benutzereingaben im <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Weitere Informationen finden Sie unter [Gewusst wie: Verhindern, das Zeilen im DataGridView\-Steuerelement in Windows Forms hinzugefügt und gelöscht werden](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) und [Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Validieren von Benutzereingaben in das <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Behandeln sehr umfangreicher Datasets mithilfe des virtuellen Modus.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Dateneingabe im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)