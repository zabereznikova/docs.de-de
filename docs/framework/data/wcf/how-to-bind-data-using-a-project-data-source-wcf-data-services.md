---
title: "Vorgehensweise: Binden von Daten mit einer Projektdatenquelle (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Datenbindung, WCF Data Services"
  - "WCF Data Services, Datenbindung"
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Vorgehensweise: Binden von Daten mit einer Projektdatenquelle (WCF Data Services)
Sie können Datenquellen erstellen, die auf den generierten Datenobjekten in einer [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientanwendung basieren.  Wenn Sie einem Datendienst einen Verweis mit dem Dialogfeld **Dienstverweis hinzufügen** hinzufügen, wird mit den generierten Clientdatenklassen eine Projektdatenquelle erstellt. Eine Datenquelle wird für jede Entitätenmenge erstellt, die der Datendienst verfügbar macht.  Sie können Formulare zum Anzeigen von Daten aus dem Dienst erstellen, indem Sie diese Datenquellenelemente aus dem Fenster **Datenquellen** auf den Designer ziehen.  Diese Elemente werden zu Steuerelementen, die an die Datenquelle gebunden sind.  Während der Ausführung wird diese Datenquelle an eine Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601>\-Klasse gebunden, die mit von einer Abfrage an den Datendienst zurückgegebenen Objekten gefüllt ist.  Weitere Informationen finden Sie unter [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 In den Beispielen in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Clientdatendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
### So verwenden Sie eine Projektdatenquelle in einem WPF\-Fenster  
  
1.  Fügen Sie in einem WPF\-Projekt dem Northwind\-Datendienst einen Verweis hinzu.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
2.  Erweitern Sie im Fenster **Datenquellen** den Knoten `Customers` in der Projektdatenquelle **NorthwindEntities**.  
  
3.  Klicken Sie auf das **CustomerID**\-Element, wählen Sie **ComboBox** aus der Liste aus, und ziehen Sie das **CustomerID**\-Element aus dem Knoten **Customers** auf den Designer.  
  
     Die folgenden Objektelemente in der XAML\-Datei für das Fenster werden erstellt:  
  
    -   Ein <xref:System.Windows.Data.CollectionViewSource>\-Element mit dem Namen `customersViewSource`.  Die <xref:System.Windows.FrameworkElement.DataContext%2A>\-Eigenschaft des <xref:System.Windows.Controls.Grid>\-Objektelements der obersten Ebene wird auf diese neue <xref:System.Windows.Data.CollectionViewSource> festgelegt.  
  
    -   Ein datengebundenes <xref:System.Windows.Controls.ComboBox>\-Element mit dem Namen `CustomerID`.  
  
    -   Ein <xref:System.Windows.Controls.Label>  
  
4.  Ziehen Sie die **Orders**\-Navigationseigenschaft auf den Designer.  
  
     Die folgenden zusätzlichen Objektelemente in der XAML\-Datei für das Fenster werden erstellt:  
  
    -   Ein zweites <xref:System.Windows.Data.CollectionViewSource>\-Element mit dem Namen `customersOrdersViewSource` und der `customerViewSource`.  
  
    -   Ein datengebundenes <xref:System.Windows.Controls.DataGrid>\-Steuerelement mit dem Namen `ordersDataGrid`.  
  
5.  \(Optional\) Ziehen Sie zusätzliche Elemente aus dem Knoten **Customers** auf den Designer.  
  
6.  Öffnen Sie die Codepage für das Formular, und fügen Sie die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]  
  
7.  Fügen Sie in der partiellen Klasse, die das Formular definiert, den folgenden Code hinzu, mit dem eine <xref:System.Data.Objects.ObjectContext>\-Instanz erstellt wird und die `customerID`\-Konstante definiert wird.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]  
  
8.  Wählen Sie im Designer das Fenster aus.  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass Sie das Fenster selbst und nicht Inhalt auszuwählen, der sich innerhalb des Fensters befindet.  Wenn das Fenster ausgewählt wird, sollte das Textfeld **Name** im oberen Bereich des Fensters **Eigenschaften** den Namen des Fensters enthalten.  
  
9. Klicken Sie im Fenster **Eigenschaften** auf die Schaltfläche **Ereignisse**.  
  
10. Suchen Sie das **Loaded**\-Ereignis, und doppelklicken Sie auf die Dropdownliste neben diesem Ereignis.  
  
     Visual Studio öffnet die Code\-Behind\-Datei für das Fenster und generiert einen <xref:System.Windows.FrameworkElement.Loaded>\-Ereignishandler.  
  
11. Kopieren Sie den folgenden Code und fügen Sie ihn in den neu erstellten <xref:System.Windows.FrameworkElement.Loaded>\-Ereignishandler ein.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]  
  
12. Dieser Code erstellt eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> für den `Customers`\-Typ basierend auf der Ausführung einer LINQ\-Abfrage, die zusammen mit verknüpften `Orders`\-Objekten aus dem Northwind\-Datendienst eine <xref:System.Collections.Generic.IEnumerable%601> von `Customers` zurückgibt und an die `customersViewSource` bindet.  
  
### So verwenden Sie eine Projektdatenquelle in einem Windows Form  
  
1.  Erweitern Sie im Fenster **Datenquellen** den Knoten **Customers** in der Projektdatenquelle **NorthwindEntities**.  
  
2.  Klicken Sie auf das **CustomerID**\-Element, wählen Sie **ComboBox** aus der Liste aus, und ziehen Sie das **CustomerID**\-Element aus dem Knoten **Customers** auf den Designer.  
  
     Dadurch werden die folgenden Steuerelemente im Formular erstellt:  
  
    -   Eine Instanz von <xref:System.Windows.Forms.BindingSource> mit dem Namen `customersBindingSource`.  
  
    -   Eine Instanz von <xref:System.Windows.Forms.BindingNavigator> mit dem Namen `customersBindingNavigator`.  Sie können dieses Steuerelement löschen, da es nicht benötigt wird.  
  
    -   Ein datengebundenes <xref:System.Windows.Forms.ComboBox>\-Element mit dem Namen `CustomerID`.  
  
    -   Ein <xref:System.Windows.Forms.Label>  
  
3.  Ziehen Sie die **Orders**\-Navigationseigenschaft auf das Formular.  
  
4.  Hirdurch wird das `ordersBindingSource`\-Steuerelement mit der <xref:System.Windows.Forms.BindingSource.DataSource%2A>\-Eigenschaft `customersBindingSource` und der <xref:System.Windows.Forms.BindingSource.DataMember%2A>\-Eigenschaft `Customers` erstellt.  Es wird auch das datengebundene `ordersDataGridView`\-Steuerelement mit einem entsprechend bezeichneten Label\-Steuerelement auf dem Formular erstellt.  
  
5.  \(Optional\) Ziehen Sie zusätzliche Elemente aus dem Knoten **Customers** auf den Designer.  
  
6.  Öffnen Sie die Codepage für das Formular, und fügen Sie die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersusing)]  
  
7.  Fügen Sie in der partiellen Klasse, die das Formular definiert, den folgenden Code hinzu, mit dem eine <xref:System.Data.Objects.ObjectContext>\-Instanz erstellt wird und die `customerID`\-Konstante definiert wird.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdefinition)]  
  
8.  Doppelklicken Sie im Formular\-Designer auf das Formular.  
  
     Dadurch wird die Codeseite für das Formular geöffnet und die Methode erstellt, die das `Load`\-Ereignis für das Formular behandelt.  
  
9. Kopieren Sie den folgenden Code und fügen Sie ihn in den `Load`\-Ereignishandler ein.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdatabinding)]  
  
10. Dieser Code erstellt eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> für den `Customers`\-Typ basierend auf der Ausführung einer <xref:System.Data.Services.Client.DataServiceQuery%601>, die aus dem Northwind\-Datendienst eine <xref:System.Collections.Generic.IEnumerable%601> von `Customers` zurückgibt und an die `customersBindingSource` bindet.  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Gewusst wie: Binden von Daten an Windows Presentation Foundation\-Elemente](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)