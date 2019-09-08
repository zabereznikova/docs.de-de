---
title: 'Vorgehensweise: Binden von Daten mit einer Projektdaten Quelle (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
ms.openlocfilehash: 85d5974f43349d91d56a1ab41b314521a6ee7348
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780163"
---
# <a name="how-to-bind-data-using-a-project-data-source-wcf-data-services"></a>Vorgehensweise: Binden von Daten mit einer Projektdaten Quelle (WCF Data Services)

Sie können Datenquellen erstellen, die auf den generierten Datenobjekten in einer WCF Data Services Client Anwendung basieren. Wenn Sie mithilfe des Dialog Felds **Dienstverweis hinzufügen** einen Verweis auf einen Datendienst hinzufügen, wird eine Projektdaten Quelle zusammen mit den generierten Client Daten Klassen erstellt. Eine Datenquelle wird für jede Entitätenmenge erstellt, die der Datendienst verfügbar macht. Sie können Formulare erstellen, die Daten aus dem Dienst anzeigen, indem Sie diese Datenquellen Elemente aus dem **Datenquellen** Fenster auf den Designer ziehen. Diese Elemente werden zu Steuerelementen, die an die Datenquelle gebunden sind. Während der Ausführung wird diese Datenquelle an eine Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601> -Klasse gebunden, die mit Objekten gefüllt wird, die von einer Abfrage an den Datendienst zurückgegeben werden. Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](binding-data-to-controls-wcf-data-services.md).

 In den Beispielen in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.

## <a name="use-a-project-data-source-in-a-wpf-window"></a>Verwenden einer Projektdaten Quelle in einem WPF-Fenster

1. Fügen Sie in Visual Studio in einem WPF-Projekt einen Verweis auf den Northwind-Datendienst hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Fügen Sie einen Datendienst](how-to-add-a-data-service-reference-wcf-data-services.md)Verweis hinzu.

2. Erweitern Sie im Fenster **Datenquellen** den `Customers` Knoten in der Projektdaten Quelle **NorthwindEntities** .

3. Klicken Sie auf das Element **CustomerID** , wählen Sie **ComboBox** aus der Liste aus, und ziehen Sie das Element **CustomerID** aus dem Knoten **Customers** auf den Designer.

     Die folgenden Objektelemente in der XAML-Datei für das Fenster werden erstellt:

    - Ein <xref:System.Windows.Data.CollectionViewSource>-Element mit dem Namen `customersViewSource`. Die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des <xref:System.Windows.Controls.Grid>-Objektelements der obersten Ebene wird auf diese neue <xref:System.Windows.Data.CollectionViewSource> festgelegt.

    - Ein datengebundenes <xref:System.Windows.Controls.ComboBox>-Element mit dem Namen `CustomerID`.

    - Ein <xref:System.Windows.Controls.Label>.

4. Ziehen Sie die **Orders** -Navigations Eigenschaft in den Designer.

     Die folgenden zusätzlichen Objektelemente in der XAML-Datei für das Fenster werden erstellt:

    - Ein zweites <xref:System.Windows.Data.CollectionViewSource>-Element mit dem Namen `customersOrdersViewSource` und der `customerViewSource`.

    - Ein datengebundenes <xref:System.Windows.Controls.DataGrid>-Steuerelement mit dem Namen `ordersDataGrid`.

5. Optionale Ziehen Sie zusätzliche Elemente aus dem Knoten **Customers** auf den Designer.

6. Öffnen Sie die Codepage für das Formular, und fügen Sie die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]

7. Fügen Sie in der partiellen Klasse, die das Formular definiert, den folgenden Code hinzu, mit dem eine <xref:System.Data.Objects.ObjectContext>-Instanz erstellt wird und die `customerID`-Konstante definiert wird.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]

8. Wählen Sie im Designer das Fenster aus.

    > [!NOTE]
    > Stellen Sie sicher, dass Sie das Fenster selbst und nicht Inhalt auszuwählen, der sich innerhalb des Fensters befindet. Wenn das Fenster ausgewählt ist, sollte das Textfeld **Name** im oberen Bereich des Fensters **Eigenschaften** den Namen des Fensters enthalten.

9. Wählen Sie im Fenster **Eigenschaften** die Schaltfläche **Ereignisse** aus.

10. Suchen Sie nach dem **geladenen** Ereignis, und doppelklicken Sie dann auf die Dropdown Liste neben diesem Ereignis.

     Visual Studio öffnet die Code-Behind-Datei für das Fenster und generiert einen <xref:System.Windows.FrameworkElement.Loaded>-Ereignishandler.

11. Kopieren Sie den folgenden Code und fügen Sie ihn in den neu erstellten <xref:System.Windows.FrameworkElement.Loaded>-Ereignishandler ein.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]

12. Dieser Code erstellt eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> für den `Customers`-Typ basierend auf der Ausführung einer LINQ-Abfrage, die zusammen mit verknüpften <xref:System.Collections.Generic.IEnumerable%601>-Objekten aus dem Northwind-Datendienst eine `Customers` von `Orders` zurückgibt und an die `customersViewSource` bindet.

## <a name="use-a-project-data-source-in-a-windows-form"></a>Verwenden einer Projektdaten Quelle in einem Windows Form

1. Erweitern Sie im Fenster **Datenquellen** den Knoten **Customers** in der Projektdaten Quelle **NorthwindEntities** .

2. Klicken Sie auf das Element **CustomerID** , wählen Sie **ComboBox** aus der Liste aus, und ziehen Sie das Element **CustomerID** aus dem Knoten **Customers** auf den Designer.

     Dadurch werden die folgenden Steuerelemente im Formular erstellt:

    - Eine Instanz von <xref:System.Windows.Forms.BindingSource> mit dem Namen `customersBindingSource`.

    - Eine Instanz von <xref:System.Windows.Forms.BindingNavigator> mit dem Namen `customersBindingNavigator`. Sie können dieses Steuerelement löschen, da es nicht benötigt wird.

    - Ein datengebundenes <xref:System.Windows.Forms.ComboBox>-Element mit dem Namen `CustomerID`.

    - Ein <xref:System.Windows.Forms.Label>.

3. Ziehen Sie die **Orders** -Navigations Eigenschaft auf das Formular.

4. Hirdurch wird das `ordersBindingSource`-Steuerelement mit der <xref:System.Windows.Forms.BindingSource.DataSource%2A>-Eigenschaft `customersBindingSource` und der <xref:System.Windows.Forms.BindingSource.DataMember%2A>-Eigenschaft `Customers` erstellt. Es wird auch das datengebundene `ordersDataGridView`-Steuerelement mit einem entsprechend bezeichneten Label-Steuerelement auf dem Formular erstellt.

5. Optionale Ziehen Sie zusätzliche Elemente aus dem Knoten **Customers** auf den Designer.

6. Öffnen Sie die Codepage für das Formular, und fügen Sie die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersusing)]

7. Fügen Sie in der partiellen Klasse, die das Formular definiert, den folgenden Code hinzu, mit dem eine <xref:System.Data.Objects.ObjectContext>-Instanz erstellt wird und die `customerID`-Konstante definiert wird.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdefinition)]

8. Doppelklicken Sie im Formular-Designer auf das Formular.

     Dadurch wird die Codeseite für das Formular geöffnet und die Methode erstellt, die das `Load`-Ereignis für das Formular behandelt.

9. Kopieren Sie den folgenden Code und fügen Sie ihn in den `Load`-Ereignishandler ein.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabinding)]

10. Dieser Code erstellt eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> für den `Customers`-Typ basierend auf der Ausführung einer <xref:System.Data.Services.Client.DataServiceQuery%601>, die aus dem Northwind-Datendienst eine <xref:System.Collections.Generic.IEnumerable%601> von `Customers` zurückgibt und an die `customersBindingSource` bindet.

## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Vorgehensweise: Binden von Daten an Windows Presentation Foundation Elemente](bind-data-to-wpf-elements-wcf-data-services.md)
