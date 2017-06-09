---
title: "Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms | Microsoft Docs"
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
  - "Daten [Windows Forms], Anzeigen ohne Bindung an Datenquelle"
  - "Daten [Windows Forms], Nicht gebunden"
  - "DataGridView-Steuerelement [Windows Forms], Anzeigen von Daten ohne Bindung an eine Datenquelle"
  - "DataGridView-Steuerelement [Windows Forms], Nicht gebundene Daten"
  - "Exemplarische Vorgehensweisen [Windows Forms], DataGridView-Steuerelement"
ms.assetid: 5a8d6afa-1b4b-4b24-8db8-501086ffdebe
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms
Möglicherweise möchten Sie häufig Tabellendaten anzeigen, die nicht aus einer Datenbank stammen.  Es kann beispielsweise erforderlich sein, den Inhalt eines zweidimensionalen Zeichenfolgenarrays anzuzeigen.  Die <xref:System.Windows.Forms.DataGridView>\-Klasse bietet ein einfaches, äußerst benutzerfreundliches Verfahren zum Anzeigen von Daten, ohne dass eine Bindung an eine Datenquelle vorgenommen werden muss.  In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement füllen und das Hinzufügen und Löschen von Zeilen im "Ungebunden"\-Modus verwalten.  Der Benutzer kann standardmäßig neue Zeilen hinzufügen.  Um das Hinzufügen von Zeilen zu unterbinden, legen Sie die <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A>\-Eigenschaft auf `false` fest.  
  
 Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter [Gewusst wie: Erstellen eines ungebundenen DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## Erstellen des Formulars  
  
#### So verwenden Sie ein ungebundenes DataGridView\-Steuerelement  
  
1.  Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet wird und die folgenden Variablendeklarationen sowie die `Main`\-Methode enthält.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#02)]  
  
2.  Implementieren Sie eine `SetupLayout`\-Methode in der Klassendefinition des Formulars, um das Formularlayout festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#20)]  
  
3.  Erstellen Sie eine `SetupDataGridView`\-Methode, um die Spalten und Eigenschaften von <xref:System.Windows.Forms.DataGridView> festzulegen.  
  
     Bei dieser Methode wird zunächst das <xref:System.Windows.Forms.DataGridView>\-Steuerelement der <xref:System.Windows.Forms.Control.Controls%2A>\-Auflistung des Formulars hinzugefügt.  Danach wird die Anzahl der anzuzeigenden Spalten mit der <xref:System.Windows.Forms.DataGridView.ColumnCount%2A>\-Eigenschaft festgelegt.  Der Standardstil für Spaltenheader wird durch Festlegen der Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A>, <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> des <xref:System.Windows.Forms.DataGridViewCellStyle> festgelegt, der von der <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>\-Eigenschaft zurückgegeben wird.  
  
     Eigenschaften für Layout und Darstellung werden festgelegt und anschließend Spaltennamen zugewiesen.  Nach Beendigung dieser Methode kann das <xref:System.Windows.Forms.DataGridView>\-Steuerelement gefüllt werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#30)]  
  
4.  Erstellen Sie eine `PopulateDataGridView`\-Methode, um dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement Zeilen hinzuzufügen.  
  
     Jede Zeile stellt ein Lied und zugeordnete Informationen dar.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#40)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#40)]  
  
5.  Mit den geeigneten Dienstprogrammmethoden können Sie Ereignishandler anfügen.  
  
     Sie behandeln die zu den Schaltflächen **Hinzufügen** und **Löschen** gehörigen <xref:System.Windows.Forms.Control.Click>\-Ereignisse, das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars sowie das zum <xref:System.Windows.Forms.DataGridView>\-Steuerelement gehörige <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis.  
  
     Wenn das <xref:System.Windows.Forms.Control.Click>\-Ereignis der Schaltfläche **Hinzufügen** ausgelöst wird, wird <xref:System.Windows.Forms.DataGridView> eine neue, leere Zeile hinzugefügt.  
  
     Wenn das <xref:System.Windows.Forms.Control.Click>\-Ereignis der Schaltfläche **Löschen** ausgelöst wird, wird die ausgewählte Zeile gelöscht, sofern es sich nicht um die Zeile für neue Datensätze handelt, durch die Benutzer neue Zeilen hinzufügen können.  Diese Zeile ist immer die letzte Zeile im <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  
  
     Wenn das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars ausgelöst wird, werden die Dienstprogrammmethoden `SetupLayout`, `SetupDataGridView` und `PopulateDataGridView` aufgerufen.  
  
     Wenn das <xref:System.Windows.Forms.DataGridView.CellFormatting>\-Ereignis ausgelöst wird, werden alle Zellen in der Spalte `Date` als langes Datum formatiert, es sei denn, der Zellwert kann nicht analysiert werden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#10)]  
  
## Testen der Anwendung  
 Sie können das Formular jetzt testen und prüfen, ob es sich wie wie erwartet verhält.  
  
#### So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sie sehen ein <xref:System.Windows.Forms.DataGridView>\-Steuerelement, in dem die in `PopulateDataGridView` aufgelisteten Lieder angezeigt werden.  Sie können neue Zeilen mit der Schaltfläche **Add Row** hinzufügen und ausgewählte Zeilen mit der Schaltfläche **Delete Row** löschen.  Das ungebundene <xref:System.Windows.Forms.DataGridView>\-Steuerelement stellt den Datenspeicher dar. Die darin enthaltenen Daten sind von keiner externen Quelle abhängig, beispielsweise von <xref:System.Data.DataSet> oder von einem Array.  
  
## Nächste Schritte  
 Anhand dieser Anwendung erhalten Sie einen grundlegenden Einblick in die Fähigkeiten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements.  Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView>\-Steuerelements auf vielfältige Weisen anpassen:  
  
-   Ändern von Rahmenart und Headerstil.  Weitere Informationen finden Sie unter [Gewusst wie: Ändern des Rahmen\- und Rasterlinienstils im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Beschränken von Benutzereingaben im <xref:System.Windows.Forms.DataGridView>\-Steuerelement.  Weitere Informationen finden Sie unter [Gewusst wie: Verhindern, das Zeilen im DataGridView\-Steuerelement in Windows Forms hinzugefügt und gelöscht werden](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md) und [Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen der Benutzereingabe auf datenbankbezogene Fehler.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView\-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Behandeln sehr umfangreicher Datasets mithilfe des virtuellen Modus.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen.  Weitere Informationen finden Sie unter [Gewusst wie: Anpassen der Darstellung von Zellen im DataGridView\-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Gewusst wie: Festlegen von Standardzellenformaten für das DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## Siehe auch  
 <xref:System.Windows.Forms.DataGridView>   
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Erstellen eines ungebundenen DataGridView\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)   
 [Datenanzeigemodi im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)