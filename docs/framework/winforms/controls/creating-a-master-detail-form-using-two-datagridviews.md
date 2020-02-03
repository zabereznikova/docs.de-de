---
title: 'Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen'
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
ms.openlocfilehash: bb3da36430c7493b941f3711cb584b4517d5bd54
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740584"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Exemplarische Vorgehensweise: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms

Eines der gängigsten Szenarien für die Verwendung des <xref:System.Windows.Forms.DataGridView>-Steuer Elements ist das *Master-/Detailformular* , in dem eine über-/Unterordnungsbeziehung zwischen zwei Datenbanktabellen angezeigt wird. Das Auswählen von Zeilen in der Master Tabelle bewirkt, dass die Detail Tabelle mit den entsprechenden untergeordneten Daten aktualisiert wird.

Das Implementieren eines Master-/Detailformulars ist einfach, indem die Interaktion zwischen dem <xref:System.Windows.Forms.DataGridView>-Steuerelement und der <xref:System.Windows.Forms.BindingSource> Komponente verwendet wird. In dieser exemplarischen Vorgehensweise erstellen Sie das Formular mit zwei <xref:System.Windows.Forms.DataGridView>-Steuerelementen und zwei <xref:System.Windows.Forms.BindingSource>-Komponenten. Im Formular werden zwei verknüpfte Tabellen in der Beispieldatenbank Northwind SQL Server angezeigt: `Customers` und `Orders`. Wenn Sie fertig sind, verfügen Sie über ein Formular, in dem alle Kunden in der Datenbank in der Master <xref:System.Windows.Forms.DataGridView> und alle Bestellungen für den ausgewählten Kunden im Detail <xref:System.Windows.Forms.DataGridView>angezeigt werden.

Informationen zum Kopieren des Codes in diesem Thema als einzelne Auflistung finden Sie unter Gewusst [wie: Erstellen eines Master-/Detailformulars mit zwei Windows Forms DataGridView-Steuerelementen](create-a-master-detail-form-using-two-datagridviews.md).

## <a name="prerequisites"></a>Voraussetzungen

Wenn Sie diese exemplarische Vorgehensweise abschließen möchten, müssen folgende Voraussetzungen erfüllt sein:

- Zugriff auf einen Server mit der Beispieldatenbank Northwind SQL Server.

## <a name="creating-the-form"></a>Erstellen des Formulars

#### <a name="to-create-a-masterdetail-form"></a>So erstellen Sie ein Master-/Detailformular

1. Erstellen Sie eine Klasse, die von <xref:System.Windows.Forms.Form> abgeleitet ist und zwei <xref:System.Windows.Forms.DataGridView>-Steuerelemente und zwei <xref:System.Windows.Forms.BindingSource>-Komponenten enthält. Der folgende Code stellt die grundlegende Formular Initialisierung bereit und enthält eine `Main`-Methode. Wenn Sie den Visual Studio-Designer verwenden, um das Formular zu erstellen, können Sie den vom Designer generierten Code anstelle dieses Codes verwenden, aber achten Sie darauf, die in den Variablen Deklarationen gezeigten Namen zu verwenden.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Implementieren Sie eine Methode in der Klassendefinition Ihres Formulars, um die Details der Verbindungs Herstellung mit der Datenbank zu verarbeiten. In diesem Beispiel wird eine `GetData`-Methode verwendet, die ein <xref:System.Data.DataSet> Objekt auffüllt, dem Dataset ein <xref:System.Data.DataRelation>-Objekt hinzufügt und die <xref:System.Windows.Forms.BindingSource> Komponenten bindet. Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist.

    > [!IMPORTANT]
    > Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Implementieren Sie einen Handler für das <xref:System.Windows.Forms.Form.Load> Ereignis des Formulars, das die <xref:System.Windows.Forms.DataGridView> Steuerelemente an die <xref:System.Windows.Forms.BindingSource> Komponenten bindet und die `GetData`-Methode aufruft. Das folgende Beispiel enthält Code, der die Größe <xref:System.Windows.Forms.DataGridView> Spalten anpasst, damit Sie den angezeigten Daten entspricht.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Testen der Anwendung

Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.

#### <a name="to-test-the-form"></a>So testen Sie das Formular

- Kompilieren Sie die Anwendung, und führen Sie sie aus.

  Zwei <xref:System.Windows.Forms.DataGridView> Steuerelemente werden angezeigt. Im oberen Bereich sind die Kunden aus der Northwind-`Customers` Tabelle und im unteren Bereich die `Orders`, die dem ausgewählten Kunden entsprechen. Wenn Sie in der oberen <xref:System.Windows.Forms.DataGridView>unterschiedliche Zeilen auswählen, wird der Inhalt des unteren <xref:System.Windows.Forms.DataGridView> entsprechend geändert.

## <a name="next-steps"></a>Nächste Schritte

Diese Anwendung bietet grundlegende Kenntnisse über die Funktionen des <xref:System.Windows.Forms.DataGridView>-Steuer Elements. Sie können die Darstellung und das Verhalten des <xref:System.Windows.Forms.DataGridView> Steuer Elements auf verschiedene Weise anpassen:

- Ändern von Rahmen-und Header Stilen. Weitere Informationen finden Sie unter Gewusst [wie: Ändern der Rahmen-und Rasterlinien Stile im Windows Forms DataGridView-Steuer](change-the-border-and-gridline-styles-in-the-datagrid.md)Element.

- Aktiviert oder schränkt die Benutzereingabe auf das <xref:System.Windows.Forms.DataGridView> Steuerelement ein. Weitere Informationen finden Sie unter Gewusst [wie: verhindern des Hinzufügens und Löschens von Zeilen im Windows Forms DataGridView-Steuer](prevent-row-addition-and-deletion-datagridview.md)Element und Gewusst wie: Festlegen von schreibgeschützten [Spalten im Windows Forms DataGridView-Steuer](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)Element.

- Überprüfen Sie die Benutzereingaben für das <xref:System.Windows.Forms.DataGridView> Steuerelement. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Validieren von Daten im Windows Forms DataGridView-Steuer](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)Element.

- Verarbeiten Sie sehr große Datasets im virtuellen Modus. Weitere Informationen finden Sie unter Exemplarische [Vorgehensweise: Implementieren des virtuellen Modus im Windows Forms DataGridView-Steuer](implementing-virtual-mode-wf-datagridview-control.md)Element.

- Passen Sie die Darstellung von Zellen an. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen der Darstellung von Zellen im Windows Forms DataGridView-Steuer](customize-the-appearance-of-cells-in-the-datagrid.md) Element und Gewusst [wie: Festlegen von Standardzellen Formaten für das Windows Forms DataGridView-Steuer](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)Element.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
