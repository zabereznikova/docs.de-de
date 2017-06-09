---
title: "Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
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
  - "DataGridView-Steuerelement [Windows Forms], Master/Detail-Formular"
  - "Master/Detail-Listen, Anzeigen in Windows Forms"
  - "Übergeordnete/untergeordnete Tabellen, Anzeigen in Windows Forms"
  - "Exemplarische Vorgehensweisen [Windows Forms], DataGridView-Steuerelement"
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms
Eines der häufigsten Szenarien für die Verwendung des <xref:System.Windows.Forms.DataGridView>\-Steuerelements stellt das *Master\-\/Detailformular* dar, in dem Beziehungen zwischen übergeordneten und untergeordneten Datenbanktabellen angezeigt werden.  Durch die Auswahl von Zeilen in der Mastertabelle wird die Detailtabelle mit den entsprechenden untergeordneten Daten aktualisiert.  
  
 Die Implementierung eines Master\-\/Detailformulars verläuft einfach, wenn Sie sich die Interaktion zwischen dem <xref:System.Windows.Forms.DataGridView>\-Steuerelement und der <xref:System.Windows.Forms.BindingSource>\-Komponente zunutze machen.  In dieser exemplarischen Vorgehensweise erstellen Sie das Formular mit zwei <xref:System.Windows.Forms.DataGridView>\-Steuerelementen und zwei <xref:System.Windows.Forms.BindingSource>\-Komponenten.  Im Formular werden zwei verknüpfte Tabellen aus der SQL Server\-Beispieldatenbank Northwind angezeigt: `Customers` und `Orders`.  Zum Schluss verfügen Sie über ein Formular, in dem sämtliche Kunden aus der Datenbank in der <xref:System.Windows.Forms.DataGridView>\-Mastertabelle und sämtliche Bestellungen für den ausgewählten Kunden in der <xref:System.Windows.Forms.DataGridView>\-Detailtabelle angezeigt werden.  
  
 Informationen zum Kopieren des in diesem Thema behandelten Codes als einzelne Auflistung finden Sie unter [Gewusst wie: Erstellen eines Master\-\/Detailformulars mit zwei DataGridView\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md).  
  
## Vorbereitungsmaßnahmen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server mit der SQL Server\-Beispieldatenbank Northwind  
  
## Erstellen des Formulars  
  
#### So erstellen Sie ein Master\-\/Detailformular  
  
1.  Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet wird und die zwei <xref:System.Windows.Forms.DataGridView>\-Steuerelemente sowie zwei <xref:System.Windows.Forms.BindingSource>\-Komponenten enthält.  Im folgenden Code werden grundlegende Initialisierungsfeatures und eine `Main`\-Methode dargestellt.  Wenn Sie das Formular mithilfe des [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]\-Designers erstellen, können Sie anstelle dieses Codes den vom Designer generierten Code verwenden. Stellen Sie jedoch sicher, dass Sie die Namen aus den Variablendeklarationen in diesem Beispiel verwenden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implementieren Sie in der Klassendefinition des Formulars eine Methode zum Behandeln der Verbindungsdetails für die Datenbank.  In diesem Beispiel wird eine `GetData`\-Methode für folgende Aufgaben verwendet: Auffüllen eines <xref:System.Data.DataSet>\-Objekts, Hinzufügen eines <xref:System.Data.DataRelation>\-Objekts zum Dataset und Binden der <xref:System.Windows.Forms.BindingSource>\-Komponenten.  Die `connectionString`\-Variable muss auf einen Wert festgelegt werden, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen, beispielsweise Kennwörter, innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen.  Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows\-Authentifizierung \(wird auch als integrierte Sicherheit bezeichnet\) sicherer steuern.  Weitere Informationen finden Sie unter [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load>\-Ereignis des Formulars, durch den die <xref:System.Windows.Forms.DataGridView>\-Steuerelemente an die <xref:System.Windows.Forms.BindingSource>\-Komponenten gebunden werden und die `GetData`\-Methode aufgerufen wird.  Das folgende Beispiel umfasst Code, durch den die Größe von <xref:System.Windows.Forms.DataGridView>\-Spalten in Anpassung an die angezeigten Daten geändert wird.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## Testen der Anwendung  
 Sie können das Formular jetzt testen und prüfen, ob es sich wie wie erwartet verhält.  
  
#### So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sie sehen zwei übereinander angeordnete <xref:System.Windows.Forms.DataGridView>\-Steuerelemente.  Im oberen Steuerelement sind die Kunden aus der Northwind\-Tabelle `Customers` und im unteren Steuerelement die Bestellungen aus der Tabelle `Orders` aufgeführt, die den ausgewählten Kunden betreffen.  Wenn Sie im oberen <xref:System.Windows.Forms.DataGridView> andere Zeile auswählen, ändert sich der Inhalt des unteren <xref:System.Windows.Forms.DataGridView> entsprechend.  
  
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
 [Anzeigen von Daten im DataGridView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Gewusst wie: Erstellen eines Master\-\/Detailformulars mit zwei DataGridView\-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagrids.md)   
 [Schützen von Verbindungsinformationen](../../../../docs/framework/data/adonet/protecting-connection-information.md)