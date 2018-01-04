---
title: "Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 016a30e4b578ead199124d70cc12f240c74bf370
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Exemplarische Vorgehensweise: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten
Behandeln von Fehlern aus dem zugrunde liegenden Datenspeicher ist ein erforderliches Feature für die eine Dateneingabe Anwendung. Windows Forms <xref:System.Windows.Forms.DataGridView> Steuerelement macht dies einfach, verfügbar machen, die <xref:System.Windows.Forms.DataGridView.DataError> Ereignis, das ausgelöst wird, wenn der Datenspeicher Verletzung einer Einschränkung oder Geschäftsregel ermittelt werden.  
  
 In dieser exemplarischen Vorgehensweise rufen Sie Zeilen aus der `Customers` -Tabelle in der Northwind-Beispieldatenbank und angezeigt werden können, die in einem <xref:System.Windows.Forms.DataGridView> Steuerelement. Wenn ein Duplikat `CustomerID` Wert wird erkannt, in eine neue Zeile oder eine bearbeitete vorhandene Zeile der <xref:System.Windows.Forms.DataGridView.DataError> Ereignis erfolgt, wird durch das Anzeigen von behandelt werden eine <xref:System.Windows.Forms.MessageBox> , die die Ausnahme beschreibt.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [wie: Behandeln Fehler, dass auftreten, während der Dateneingabe im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server, der die Northwind-SQL Server-Beispieldatenbank ist.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Zum Behandeln von Fehlern der Dateneingabe im DataGridView-Steuerelement  
  
1.  Erstellen Sie eine Klasse, die abgeleitet <xref:System.Windows.Forms.Form> und enthält eine <xref:System.Windows.Forms.DataGridView> Steuerelement und ein <xref:System.Windows.Forms.BindingSource> Komponente.  
  
     Das folgende Codebeispiel stellt die grundlegende Initialisierung bereit und enthält eine `Main` Methode.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implementieren Sie eine Methode, in dem Formular Klassendefinition für die Behandlung der Details zum Herstellen einer Verbindung mit der Datenbank.  
  
     Dieses Codebeispiel verwendet eine `GetData` Methode, die ein aufgefülltes zurückgibt <xref:System.Data.DataTable> Objekt. Achten Sie darauf, dass Sie legen die `connectionString` -Variable auf einen Wert, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implementieren Sie einen Handler für Ihr Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das initialisiert die <xref:System.Windows.Forms.DataGridView> und <xref:System.Windows.Forms.BindingSource> und dem Datenbindung eingerichtet.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Behandeln der <xref:System.Windows.Forms.DataGridView.DataError> Ereignis auf der <xref:System.Windows.Forms.DataGridView>.  
  
     Wenn der Kontext für den Fehler einem Commitvorgang ist, zeigen Sie den Fehler in einem <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sehen Sie eine <xref:System.Windows.Forms.DataGridView> Steuerelement mit Daten aus der Customers-Tabelle gefüllt. Wenn Sie einen doppelten Wert für eingeben `CustomerID` und commit bearbeiten, der Wert der Zelle wird automatisch zurückgesetzt, und sehen Sie eine <xref:System.Windows.Forms.MessageBox> , die die Dateneingabefehler anzeigt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung erhalten Sie einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelements auf unterschiedliche Weise:  
  
-   Ändern von Formaten für Rahmen und Header. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern der Rahmen- und Rasterlinienstils im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Einschränken von Benutzereingaben an das <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [wie: verhindern Hinzufügens und Löschens im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Stellen Spalten schreibgeschützter im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen Sie alle Benutzereingaben, die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Behandeln von sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [wie: Anpassen der Darstellung von Zellen im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von standardmäßigen Zellenstilen für DataGridView-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Dateneingabe im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Behandeln von Fehlern, die während der Dateneingabe im DataGridView-Steuerelement in Windows Forms auftreten](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Exemplarische Vorgehensweise: Validieren von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
