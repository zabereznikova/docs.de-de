---
title: Binden von Daten an Steuerelemente (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- data binding, WCF Data Services
ms.assetid: b32e1d49-c214-4cb1-867e-88fbb3d08c8d
ms.openlocfilehash: 605ff7a9acaaa217f0e482579968757dd451aed9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974835"
---
# <a name="binding-data-to-controls-wcf-data-services"></a>Binden von Daten an Steuerelemente (WCF Data Services)
Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie Steuerelemente wie `ComboBox` und `ListView` an eine Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse binden. Diese Auflistung, die von der <xref:System.Collections.ObjectModel.ObservableCollection%601>-Klasse erbt, enthält die Daten eines odata-Feeds (Open Data Protocol). Die Klasse stellt eine dynamische Datensammlung dar, die Benachrichtigungen bereitstellt, wenn Elemente hinzugefügt oder entfernt werden. Wenn Sie eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> für die Datenbindung verwenden, behandeln die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Client Bibliotheken diese Ereignisse, um sicherzustellen, dass die vom <xref:System.Data.Services.Client.DataServiceContext> nach verfolgten Objekte mit den Daten im gebundenen Benutzeroberflächen Element synchronisiert bleiben.  
  
 Die <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse implementiert (indirekt) die <xref:System.Collections.Specialized.INotifyCollectionChanged>-Schnittstelle, um den Kontext zu warnen, wenn Objekte der Sammlung hinzugefügt oder daraus entfernt werden. Mit einer <xref:System.Data.Services.Client.DataServiceCollection%601>-Instanz verwendete Datendiensttypobjekte müssen auch die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementieren, um die <xref:System.Data.Services.Client.DataServiceCollection%601>-Instanz zu warnen, wenn sich Eigenschaften von Objekten in der Bindungssammlung geändert haben.  
  
> [!NOTE]
> Wenn Sie das Dialogfeld **Dienstverweis hinzufügen** oder das Tool [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) mit der `/dataservicecollection`-Option zum Generieren der Client Datendienst Klassen verwenden, implementieren die generierten Daten Klassen die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle. Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Generieren von Client Datendienst Klassen](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="creating-the-binding-collection"></a>Erstellen der Bindungsauflistung  
 Erstellen Sie eine neue Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse, indem Sie eine der Klassenkonstruktormethoden mit einer angegebenen <xref:System.Data.Services.Client.DataServiceContext>-Instanz und optional eine <xref:System.Data.Services.Client.DataServiceQuery%601> oder LINQ-Abfrage aufrufen, die bei Ausführung eine <xref:System.Collections.Generic.IEnumerable%601>-Instanz zurückgibt. Diese <xref:System.Collections.Generic.IEnumerable%601> stellt die Quelle von Objekten für die Bindungs Auflistung bereit, die aus einem odata-Feed materialisiert werden. Weitere Informationen finden Sie unter [Objektmaterialisierung](object-materialization-wcf-data-services.md). Standardmäßig werden an in die Auflistung eingefügten gebundenen Objekten und Elementen vorgenommene Änderungen automatisch vom <xref:System.Data.Services.Client.DataServiceContext> nachverfolgt. Wenn Sie diese Änderungen manuell nachverfolgen müssen, müssen Sie eine der Konstruktormethoden aufrufen, die einen `trackingMode`-Parameter annimmt, und den Wert <xref:System.Data.Services.Client.TrackingMode.None>angeben.  
  
 Im folgenden Beispiel wird gezeigt, wie eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601> basierend auf einem angegebenen <xref:System.Data.Services.Client.DataServiceContext> und einer <xref:System.Data.Services.Client.DataServiceQuery%601> erstellt wird, die alle Kunden mit verknüpften Bestellungen zurückgibt:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders2.cs#customersorders2binding)]
 [!code-vb[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders2.vb#customersorders2binding)]  
  
## <a name="binding-data-to-windows-presentation-foundation-elements"></a>Binden von Daten an Windows Presentation Foundation-Elemente  
 Da die <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse von der <xref:System.Collections.ObjectModel.ObservableCollection%601>-Klasse erbt, können Sie Objekte in einer WPF (Windows Presentation Foundation)-Anwendung an ein Element oder Steuerelement binden, ähnlich wie beim Verwenden der <xref:System.Collections.ObjectModel.ObservableCollection%601>-Klasse für die Bindung. Weitere Informationen finden Sie unter [Datenbindung (Windows Presentation Foundation)](../../../desktop-wpf/data/data-binding-overview.md). Eine Möglichkeit zum Binden von Datendienstdaten an WPF-Steuerelemente ist das Festlegen der `DataContext`-Eigenschaft des Elements auf die Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse, die das Abfrageergebnis enthält. In diesem Fall verwenden Sie die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft, um die Objektquelle für das Steuerelement festzulegen. Verwenden Sie die <xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A>-Eigenschaft, um anzugeben, welche Eigenschaft des gebundenen Objekts angezeigt werden soll. Wenn Sie ein Element an ein verknüpftes Objekt binden, das von einer Navigationseigenschaft zurückgegeben wird, schließen Sie den Pfad in die für die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>-Eigenschaft definierte Bindung ein. Der Pfad ist relativ zum Stammobjekt, das von der <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft des übergeordneten Steuerelements festgelegt ist. Im folgenden Beispiel wird die <xref:System.Windows.FrameworkElement.DataContext%2A>-Eigenschaft eines <xref:System.Windows.Controls.StackPanel>-Elements festgelegt, um das übergeordnete Steuerelement an eine <xref:System.Data.Services.Client.DataServiceCollection%601> von Customer-Objekten zu binden:  
  
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#masterdetailbinding)]
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#masterdetailbinding)]  
  
 Das folgende Beispiel veranschaulicht die XAML-Bindungsdefinition des untergeordneten <xref:System.Windows.Controls.DataGrid>-Elements und der <xref:System.Windows.Controls.ComboBox>-Steuerelemente:  
  
 [!code-xaml[Astoria Northwind Client#MasterDetailXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#masterdetailxaml)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten an Windows Presentation Foundation-Elemente](bind-data-to-wpf-elements-wcf-data-services.md).  
  
 Wenn eine Entität an einer 1:n- oder m:n-Beziehung beteiligt ist, gibt die Navigationseigenschaft für die Beziehung eine Auflistung von verknüpften Objekten zurück. Wenn Sie das Dialogfeld **Dienstverweis hinzufügen** oder das Tool DataSvcUtil. exe zum Generieren der Client Datendienst Klassen verwenden, gibt die Navigations Eigenschaft eine Instanz von <xref:System.Data.Services.Client.DataServiceCollection%601>zurück. Dies ermöglicht es Ihnen, verknüpfte Objekte an ein Steuerelement zu binden, und unterstützt allgemeine WPF-Bindungsszenarien, z. B. das Master-Detail-Bindungsmuster für verknüpfte Entitäten. Im vorherigen XAML-Beispiel bindet der XAML-Code die Master-<xref:System.Data.Services.Client.DataServiceCollection%601> an das Stammdatenelement. Die Bestellung <xref:System.Windows.Controls.DataGrid> wird dann an die aus dem ausgewählten Customers-Objekt zurückgegebene Orders-<xref:System.Data.Services.Client.DataServiceCollection%601> gebunden, die wiederum an das Stammdatenelement des <xref:System.Windows.Window> gebunden wird.  
  
## <a name="binding-data-to-windows-forms-controls"></a>Binden von Daten an Windows Forms-Steuerelemente  
 Legen Sie die `DataSource`-Eigenschaft des Steuerelements auf die Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse fest, die das Abfrageergebnis enthält, um Objekte an ein Windows Form-Steuerelement zu binden.  
  
> [!NOTE]
> Die Datenbindung wird nur für Steuerelemente unterstützt, die Änderungsereignisse durch das Implementieren der <xref:System.Collections.Specialized.INotifyCollectionChanged>- und der <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle überwachen. Wenn ein Steuerelement diese Art von Änderungsbenachrichtigung nicht unterstützt, spiegeln sich Änderungen, die an der zugrunde liegenden <xref:System.Data.Services.Client.DataServiceCollection%601> vorgenommen werden, nicht im gebundenen Steuerelement wider.  
  
 Im folgenden Beispiel wird eine <xref:System.Data.Services.Client.DataServiceCollection%601> an ein <xref:System.Windows.Forms.ComboBox>-Steuerelement gebunden:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabindingspecific)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabindingspecific)]  
  
 Wenn Sie das Dialogfeld " **Dienstverweis hinzufügen** " zum Generieren der Client Datendienst Klassen verwenden, wird auch eine Projektdaten Quelle erstellt, die auf dem generierten <xref:System.Data.Services.Client.DataServiceContext>basiert. Mit dieser Datenquelle können Sie Benutzeroberflächen Elemente oder Steuerelemente erstellen, die Daten aus dem Datendienst anzeigen, indem Sie einfach Elemente aus dem **Datenquellen** Fenster auf den Designer ziehen. Diese Elemente werden zu an die Datenquelle gebundenen Elementen auf der Benutzeroberfläche der Anwendung. Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten mit einer Projektdaten Quelle](how-to-bind-data-using-a-project-data-source-wcf-data-services.md).  
  
## <a name="binding-paged-data"></a>Binden von ausgelagerten Daten  
 Ein Datendienst kann so konfiguriert werden, dass die Menge an abgefragten Daten beschränkt wird, die in einer einzelnen Antwortnachricht zurückgegeben werden. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md). Wenn der Datendienst Paging von Antwortdaten durchführt, enthält jede Antwort einen Link, der zum Zurückgeben der nächsten Ergebnisseite verwendet wird. Weitere Informationen finden Sie unter [Laden von verzögertem Inhalt](loading-deferred-content-wcf-data-services.md). In diesem Fall müssen Sie Seiten durch Aufrufen der <xref:System.Data.Services.Client.DataServiceCollection%601.Load%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceCollection%601> explizit laden, indem Sie den aus der <xref:System.Data.Services.Client.DataServiceQueryContinuation.NextLinkUri%2A>-Eigenschaft abgerufenen URI wie im folgenden Beispiel weiterleiten:  
  
 [!code-csharp[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddataspecific)]
 [!code-vb[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddataspecific)]  
  
 Verknüpfte Objekte werden auf ähnliche Weise geladen. Weitere Informationen finden Sie unter Gewusst [wie: Binden von Daten an Windows Presentation Foundation-Elemente](bind-data-to-wpf-elements-wcf-data-services.md).  
  
## <a name="customizing-data-binding-behaviors"></a>Anpassen von Datenbindungsverhalten  
 Die <xref:System.Data.Services.Client.DataServiceCollection%601>-Klasse ermöglicht Ihnen das Abfangen der Ereignisse, die ausgelöst werden, wenn Änderungen an der Auflistung wie das Hinzufügen oder Entfernen eines Objekts und wenn Änderungen an den Eigenschaften des Objekts in einer Auflistung vorgenommen werden. Sie können die Datenbindungsereignisse ändern, um das Standardverhalten zu überschreiben, was die folgenden Einschränkungen einschließt:  
  
- Innerhalb der Delegaten wird keine Validierung ausgeführt.  
  
- Beim Hinzufügen einer Entität werden automatisch verknüpfte Entitäten hinzugefügt.  
  
- Beim Löschen einer Entität werden die verknüpften Entitäten nicht gelöscht.  
  
 Wenn Sie eine neue Instanz der <xref:System.Data.Services.Client.DataServiceCollection%601> erstellen, haben Sie die Option, die folgenden Parameter anzugeben, die Delegaten für Methoden definieren, die die beim Ändern gebundener Objekte ausgelösten Ereignisse behandeln:  
  
- `entityChanged` - ein Methode, die aufgerufen wird, wenn die Eigenschaft eines gebundenen Objekts geändert wird. Dieser <xref:System.Func%602>-Delegat akzeptiert ein <xref:System.Data.Services.Client.EntityChangedParams>-Objekt und gibt einen booleschen Wert zurück, der angibt, ob das Standardverhalten, <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> für den <xref:System.Data.Services.Client.DataServiceContext> aufzurufen, noch auftreten soll.  
  
- `entityCollectionChanged` - eine Methode, die aufgerufen wird, wenn ein Objekt der Bindungsauflistung hinzugefügt oder daraus entfernt wird. Dieser <xref:System.Func%602>-Delegat akzeptiert ein <xref:System.Data.Services.Client.EntityCollectionChangedParams>-Objekt und gibt einen booleschen Wert zurück, der angibt, ob das Standardverhalten, <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> für eine <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Add>-Aktion oder <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> für eine <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove>-Aktion für den <xref:System.Data.Services.Client.DataServiceContext> aufzurufen, beibehalten werden soll.  
  
> [!NOTE]
> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] überprüft die benutzerdefinierten Verhalten nicht, die Sie in diesen Delegaten implementieren.  
  
 Im folgenden Beispiel wird die <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove>-Aktion angepasst, um die <xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A>-Methode und <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>-Methode zum Entfernen von `Orders_Details`-Entitäten aufzurufen, die zu einer gelöschten `Orders`-Entität gehören. Diese benutzerdefinierte Aktion wird ausgeführt, da abhängige Entitäten beim Löschen der übergeordneten Entität nicht automatisch gelöscht werden.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#customersordersdeleterelated)]  
  
 Weitere Informationen finden Sie unter Gewusst [wie: Anpassen des Daten Bindungs Verhaltens](how-to-customize-data-binding-behaviors-wcf-data-services.md).  
  
 Das Standardverhalten beim Entfernen eines Objekts aus einer <xref:System.Data.Services.Client.DataServiceCollection%601> mit der <xref:System.Collections.ObjectModel.Collection%601.Remove%2A>-Methode ist, dass das Objekt auch im <xref:System.Data.Services.Client.DataServiceContext> als gelöscht markiert wird. Sie können einen Delegaten für eine Methode im `entityCollectionChanged`-Parameter angeben, der beim Auftreten des <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>-Ereignisses aufgerufen wird, um dieses Verhalten zu ändern.  
  
## <a name="data-binding-with-custom-client-data-classes"></a>Datenbindung mit benutzerdefinierten Clientdatenklassen  
 Um Objekte in eine <xref:System.Data.Services.Client.DataServiceCollection%601> laden zu können, müssen die Objekte selbst die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementieren. Datendienst-Client Klassen, die generiert werden, wenn Sie das Dialogfeld **Dienstverweis hinzufügen** oder das Tool [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) verwenden, implementieren diese Schnittstelle. Wenn Sie eigene Clientdatenklassen bereitstellen, müssen Sie einen anderen Auflistungstyp für die Datenbindung verwenden. Wenn sich Objekte ändern, müssen Sie Ereignisse in den datengebundenen Steuerelementen behandeln, um die folgenden Methoden der <xref:System.Data.Services.Client.DataServiceContext>-Klasse aufzurufen:  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> - wenn der Auflistung ein neues Objekt hinzugefügt wird.  
  
- <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> - wenn ein Objekt aus der Auflistung entfernt wird.  
  
- <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> - wenn die Eigenschaft eines Objekts in der Auflistung geändert wird.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> - wenn einer Auflistung des verknüpften Objekts ein Objekt hinzugefügt wird.  
  
- <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> - wenn einer Auflistung verknüpfter Objekte ein Objekt hinzugefügt wird.  
  
 Weitere Informationen finden Sie unter [Aktualisieren des Daten Dienstanbieter](updating-the-data-service-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [: Manuelles Generieren von Client-Datendienstklassen](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienstverweises](how-to-add-a-data-service-reference-wcf-data-services.md)
