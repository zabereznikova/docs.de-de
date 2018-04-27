---
title: 'Exemplarische Vorgehensweise: Erstellen einer Master / Detail-Formulars mit zwei DataGridView-Steuerelementen in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5c3dfc547fe775b38ad4c2e658755268f791502
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms
Eines der häufigsten Szenarien für die Verwendung der <xref:System.Windows.Forms.DataGridView> -Steuerelement ist die *Master/Detail-* Form, in dem eine über-/unterordnungsbeziehung zwischen zwei Datenbanktabellen angezeigt wird. Auswählen von Zeilen in der master-Tabelle bewirkt, dass die Detailtabelle, mit den entsprechenden untergeordneten Daten zu aktualisieren.  
  
 Implementieren eine Master-/Detailformulars mit ist einfach die Interaktion zwischen der <xref:System.Windows.Forms.DataGridView> Steuerelement und dem <xref:System.Windows.Forms.BindingSource> Komponente. In dieser exemplarischen Vorgehensweise erstellen Sie das Formular mit zwei <xref:System.Windows.Forms.DataGridView> Steuerelemente und zwei <xref:System.Windows.Forms.BindingSource> Komponenten. Das Formular zeigt zwei verknüpfte Tabellen in der Northwind-SQL Server-Beispieldatenbank: `Customers` und `Orders`. Wenn Sie fertig sind, haben Sie ein Formular, das alle Kunden in der Datenbank in der Masterdatenbank zeigt <xref:System.Windows.Forms.DataGridView> und aller Aufträge für den ausgewählten Kunden in Details <xref:System.Windows.Forms.DataGridView>.  
  
 Um den Code in diesem Thema als einzelne Auflistung kopieren zu können, finden Sie unter [Vorgehensweise: Erstellen einer Master/Detail-Formular mithilfe von zwei Windows Forms DataGridView-Steuerelementen](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:  
  
-   Zugriff auf einen Server, der die Northwind-SQL Server-Beispieldatenbank ist.  
  
## <a name="creating-the-form"></a>Erstellen des Formulars  
  
#### <a name="to-create-a-masterdetail-form"></a>So erstellen eine Master/Detail-Formulars  
  
1.  Erstellen Sie eine Klasse, die abgeleitet <xref:System.Windows.Forms.Form> und enthält zwei <xref:System.Windows.Forms.DataGridView> Steuerelemente und zwei <xref:System.Windows.Forms.BindingSource> Komponenten. Der folgende Code stellt die Initialisierung des Basisformulars bereit und enthält eine `Main` Methode. Wenn Sie Visual Studio-Designer verwenden, um das Formular zu erstellen, verwenden den vom Designer generierten Code anstelle dieses Codes können Achten Sie darauf, dass Sie die Namen in den Variablendeklarationen dargestellt verwenden.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implementieren Sie eine Methode, in dem Formular Klassendefinition für die Behandlung von Details der Herstellen einer Verbindung mit der Datenbank. Dieses Beispiel verwendet eine `GetData` -Methode, die füllt eine <xref:System.Data.DataSet> Objekt, fügt eine <xref:System.Data.DataRelation> -Objekt, das DataSet und bindet die <xref:System.Windows.Forms.BindingSource> Komponenten. Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist.  
  
    > [!IMPORTANT]
    >  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implementieren Sie einen Handler für des Formulars <xref:System.Windows.Forms.Form.Load> Ereignis, das bindet die <xref:System.Windows.Forms.DataGridView> -Steuerelementen an die <xref:System.Windows.Forms.BindingSource> Komponenten und Aufrufe der `GetData` Methode. Das folgende Beispiel enthält Code, der Größe der <xref:System.Windows.Forms.DataGridView> Spalten, die angezeigten Daten anzupassen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Kompilieren Sie die Anwendung, und führen Sie sie aus.  
  
     Sehen Sie zwei <xref:System.Windows.Forms.DataGridView> übereinander steuert. Im Vordergrund werden Kunden aus der Northwind `Customers` Tabelle, und im unteren Bereich werden die `Orders` entspricht, die dem ausgewählten Kunden. Bei Auswahl von unterschiedlichen Zeilen in der oberen <xref:System.Windows.Forms.DataGridView>, den Inhalt des unteren <xref:System.Windows.Forms.DataGridView> entsprechend ändern.  
  
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
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../../../docs/framework/data/adonet/protecting-connection-information.md)
