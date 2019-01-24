---
title: 'Exemplarische Vorgehensweise: Erstellen eines Master / Detail-Formulars mit zwei DataGridView-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: e06e2e71e28c62f06189374e84d1469ec521c5d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585306"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Exemplarische Vorgehensweise: Erstellen eine Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms
Einer der häufigsten Szenarios für die Verwendung der <xref:System.Windows.Forms.DataGridView> Steuerelement ist die *Master/Detail-* Form, in dem eine über-/unterordnungsbeziehung zwischen zwei Datenbanktabellen angezeigt wird. Auswählen von Zeilen in der master-Tabelle bewirkt, dass die Detailtabelle um mit den entsprechenden untergeordneten Daten zu aktualisieren.  
  
 Implementieren eine Master-/Detailformulars kann leicht mit der die Interaktion zwischen der <xref:System.Windows.Forms.DataGridView> Steuerelement und die <xref:System.Windows.Forms.BindingSource> Komponente. In dieser exemplarischen Vorgehensweise erstellen Sie das Formular mit zwei <xref:System.Windows.Forms.DataGridView> -Steuerelemente und zwei <xref:System.Windows.Forms.BindingSource> Komponenten. Das Formular zeigt zwei verknüpfte Tabellen in der Beispieldatenbank Northwind-SQL Server: `Customers` und `Orders`. Wenn Sie fertig sind, haben Sie ein Formular, das zeigt, alle Kunden in der Datenbank in der Masterdatenbank <xref:System.Windows.Forms.DataGridView> und alle Aufträge für den ausgewählten Kunden in die Details <xref:System.Windows.Forms.DataGridView>.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren möchten, finden Sie unter [Vorgehensweise: Erstellen Sie eine Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server, der die Beispieldatenbank Northwind-SQL-Server verfügt.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-create-a-masterdetail-form"></a>Erstellen eines Master/Detail-Formulars  
  
1.  Erstellen Sie eine abgeleitete Klasse <xref:System.Windows.Forms.Form> und enthält zwei <xref:System.Windows.Forms.DataGridView> -Steuerelemente und zwei <xref:System.Windows.Forms.BindingSource> Komponenten. Der folgende Code stellt die grundlegende Form Initialisierung bereit und enthält eine `Main` Methode. Wenn Sie Visual Studio-Designer verwenden, um das Formular zu erstellen, können Sie verwenden Sie den vom Designer generierten Code anstelle dieser Code, aber Achten Sie darauf, dass Sie die in den Variablen Deklarationen in den hier angezeigten Namen zu verwenden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implementieren Sie eine Methode in Ihres Formulars Klassendefinition für die Verarbeitung von Details der Verbindung zur Datenbank. Dieses Beispiel verwendet eine `GetData` -Methode, die füllt eine <xref:System.Data.DataSet> Objekt, fügt ein <xref:System.Data.DataRelation> Objekt, das Dataset, und bindet die <xref:System.Windows.Forms.BindingSource> Komponenten. Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implementieren einen Handler für Ihres Formulars <xref:System.Windows.Forms.Form.Load> -Ereignis, das gebunden wird die <xref:System.Windows.Forms.DataGridView> -Steuerelementen an die <xref:System.Windows.Forms.BindingSource> Komponenten und ruft die `GetData` Methode. Das folgende Beispiel enthält Code, der Größe der <xref:System.Windows.Forms.DataGridView> Spalten sind die angezeigten Daten anpassen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sie sehen zwei <xref:System.Windows.Forms.DataGridView> übereinander steuert. Sind Sie oben auf die Kunden aus dem Northwind `Customers` Tabelle, und werden am unteren Rand der `Orders` für den ausgewählten Kunden. Bei Auswahl von unterschiedlichen Zeilen in der oberen <xref:System.Windows.Forms.DataGridView>, den Inhalt der unteren <xref:System.Windows.Forms.DataGridView> entsprechend ändern.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung verfügt über einen grundlegenden Überblick der <xref:System.Windows.Forms.DataGridView> Funktionen des Steuerelements. Sie können das Aussehen und Verhalten der Anpassen der <xref:System.Windows.Forms.DataGridView> Steuerelement auf verschiedene Weise:  
  
-   Ändern von Rahmen und Header-Formaten. Weitere Informationen finden Sie unter [Vorgehensweise: Ändern des Rahmen- und Rasterlinienstils in der Windows Forms DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Aktivieren oder Einschränken von Benutzereingaben in die <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Verhindern des Hinzufügens der Zeile, und Löschen in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), und [Vorgehensweise: Festlegen von Spalten schreibgeschützt in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Überprüfen Sie Benutzereingaben an das <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Überprüfen von Daten in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Behandeln Sie sehr großen Datasets, die Verwendung des virtuellen Modus. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Implementieren des virtuellen Modus in der Windows Forms-DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Anpassen der Darstellung von Zellen an. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) und [Vorgehensweise: Festlegen von Standardzellenformaten für das Windows-DataGridView-Steuerelement Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Vorgehensweise: Erstellen Sie eine Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
