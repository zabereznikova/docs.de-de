---
title: Benutzerdefinierter Demux
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: "41"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 540469571f06f9c2ab38f9754a40aae5a3c3b267
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="custom-demux"></a>Benutzerdefinierter Demux
In diesem Beispiel wird veranschaulicht, wie MSMQ-Nachrichtenheader unterschiedlichen Dienstvorgängen zugeordnet werden können, damit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Dienste, bei denen <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> besteht keine Einschränkung auf die Verwendung eines einzigen Dienstvorgangs aus, wie in der [Message Queuing Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) und [Windows Communication Foundation zu Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) Beispiele.  
  
 Der Dienst ist in diesem Beispiel eine selbst gehostete Konsolenanwendung, sodass Sie den Dienst beobachten können, der Nachrichten in Warteschlangen empfängt.  
  
 Der Dienstvertrag ist `IOrderProcessor` und definiert einen unidirektionalen Dienst, der für die Verwendung mit Warteschlangen geeignet ist.  
  
```  
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```  
  
 Eine MSMQ-Nachricht besitzt keinen Aktionsheader. Es ist nicht möglich, Vorgangsverträgen unterschiedliche MSMQ-Nachrichten automatisch zuzuordnen. Deshalb kann es nur einen Vorgangsvertrag geben. Um diese Einschränkung zu umgehen, implementiert der Dienst die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>-Methode der <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Schnittstelle. Die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>-Methode ermöglicht dem Dienst, einem bestimmten Dienstvorgang einen bestimmten Nachrichtenheader zuzuordnen. In diesem Beispiel wird den Dienstvorgängen der Bezeichnungsheader der Nachricht zugeordnet. Der `Name`-Parameter des Vorgangsvertrags legt fest, welcher Dienstvorgang für eine bestimmte Nachrichtenbezeichnung weitergeleitet werden muss. Wenn der Bezeichnungsheader der Nachricht z. B. "SubmitPurchaseOrder" enthält, wird der "SubmitPurchaseOrder"-Dienstvorgang aufgerufen.  
  
```  
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```  
  
 Der Dienst muss die <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29>-Methode der <xref:System.ServiceModel.Description.IContractBehavior>-Schnittstelle implementieren, wie im folgenden Beispielcode dargestellt. Diese wendet den benutzerdefinierten `OperationSelector` auf die Dienstframework-Dispatchlaufzeit an.  
  
```  
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```  
  
 Eine Nachricht muss den <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> des Verteilers durchlaufen, bevor die Vorgangsauswahl erreicht wird. Standardmäßig wird eine Nachricht zurückgewiesen, wenn ihre Aktion auf keinem der vom Dienst implementierten Verträge gefunden werden kann. Um diese Prüfung zu vermeiden, implementieren wir ein <xref:System.ServiceModel.Description.IEndpointBehavior> namens `MatchAllFilterBehavior`, das es allen Nachrichten ermöglicht, den `ContractFilter` zu passieren, indem der <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> folgendermaßen angewendet wird.  
  
```  
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```  
  
 Wenn der Dienst eine Nachricht empfängt, wird der entsprechende Dienstvorgang mithilfe der Informationen im Bezeichnungsheader verteilt. Der Nachrichtentext wird in ein `PurchaseOrder`-Objekt deserialisiert, wie im folgenden Beispielcode dargestellt.  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```  
  
 Der Dienst ist selbst gehostet. Bei der Verwendung von MSMQ muss die Warteschlange im Voraus erstellt werden. Dies kann manuell erfolgen oder mithilfe eines Codes. In diesem Beispiel enthält der Dienst einen Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist und um die Warteschlange gegebenenfalls zu erstellen. Der Warteschlangenname wird aus der Konfigurationsdatei gelesen.  
  
```  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```  
  
 Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben.  
  
> [!NOTE]
>  Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet. Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunktadresse gibt ein msmq.formatname-Schema an, und für den lokalen Computer wird localhost verwendet. Dem Schema folgt eine ordnungsgemäß entsprechend den Namens- und Adressierungsrichtlinien des MSMQ-Formats formatierte Warteschlangenadresse.  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  Dieses Beispiel erfordert die Installation von [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).  
  
 Starten Sie den Dienst, und führen Sie den Client aus.  
  
 Auf dem Client wird die folgende Ausgabe angezeigt.  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 Auf dem Dienst muss die folgende Ausgabe angezeigt werden.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist. Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt. Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen. Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:  
  
    1.  Öffnen Sie Server-Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Erweitern Sie die **Funktionen** Registerkarte.  
  
    3.  Mit der rechten Maustaste **Private Meldungswarteschlangen**, und wählen Sie **neu**, **Private Warteschlange**.  
  
    4.  Überprüfen Sie die **transaktional** Feld.  
  
    5.  Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange.  
  
3.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
4.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1.  Kopieren Sie die Dienstprogrammdateien aus dem Ordner \service\bin\ (unterhalb des sprachspezifischen Ordners) auf den Dienstcomputer.  
  
2.  Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
3.  Ändern Sie in der Datei Client.exe.config den Wert von orderQueueName, und geben Sie anstelle von "." den Namen des Dienstcomputers an.  
  
4.  Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.  
  
5.  Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a>Siehe auch  
 [Queuing in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143)
