---
title: Bidirektionale Kommunikation
ms.date: 03/30/2017
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
ms.openlocfilehash: 9cf8d3746cea5746bee186a8a68a515c8503cb85
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715896"
---
# <a name="two-way-communication"></a>Bidirektionale Kommunikation
Dieses Beispiel veranschaulicht das Ausführen der transaktiven bidirektionalen Warteschlangenkommunikation über MSMQ. In diesem Beispiel wird die `netMsmqBinding`-Bindung verwendet. Der Dienst ist in diesem Fall eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel basiert auf der [transaktiven MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).  
  
 In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Der Client sendet Nachrichten an eine Warteschlange, und der Dienst empfängt Nachrichten von der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.  
  
 In diesem Beispiel wird die bidirektionale Kommunikation mit Warteschlangen veranschaulicht. Der Client sendet Bestellungen aus dem Bereich einer Transaktion an die Warteschlange. Der Dienst empfängt die Bestellungen, verarbeitet die Bestellungen und meldet an den Client den Status der Bestellung aus der Warteschlange innerhalb des Bereichs der Transaktion. Zur Vereinfachung der bidirektionalen Kommunikation verwenden sowohl der Client als auch der Dienst Warteschlangen für Bestellungen und den Auftragsstatus.  
  
 Der `IOrderProcessor`-Dienstvertrag definiert einen unidirektionalen Dienstvorgang, der für die Verwendung mit Warteschlangen geeignet ist. Der Dienstvorgang beinhaltet den Antwortendpunkt, an den der Auftragsstatus gesendet wird. Der Antwortendpunkt ist der URI der Warteschlange für die Rücksendung des Auftragsstatus an den Client. Die Anwendung für die Auftragsverarbeitung implementiert diesen Vertrag.  

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string   
                                  reportOrderStatusTo);  
}
```
  
 Der Antwortvertrag für die Sendung des Auftragsstatus wird vom Client angegeben. Der Client implementiert den Auftragsstatusvertrag. Der Dienst verwendet den generierten Proxy dieses Vertrags, um den Auftragsstatus an den Client zurückzusenden.  

```csharp
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```

 Der Dienstvorgang verarbeitet die übermittelte Bestellung. Das <xref:System.ServiceModel.OperationBehaviorAttribute> wird auf den Dienstvorgang angewendet, um die automatische Eintragung für eine Transaktion festzulegen, die für den Empfang der Nachricht aus der Warteschlange verwendet wird, und für die automatische Fertigstellung von Transaktionen, wenn der Dienstvorgang fertig gestellt wird. Die `Orders`-Klasse kapselt die Auftragsverarbeitungsfunktion. In diesem Fall fügt sie die Bestellung einem Wörterbuch hinzu. Die Transaktion, in der der Dienstvorgang eingetragen wurde, steht den Vorgängen in der `Orders`-Klasse zur Verfügung.  
  
 Der Dienstvorgang verarbeitet die übermittelte Bestellung und meldet dem Client den Status des Auftrags.  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```

 Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben. Der Endpunkt für den Dienst wird im Abschnitt System.ServiceModel der Konfigurationsdatei definiert.  
  
> [!NOTE]
> Der Name der MSMQ-Warteschlange und die Endpunktadresse verwenden geringfügig abweichende Adressierungskonventionen. Im MSMQ-Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet. Die Windows Communication Foundation (WCF)-Endpunkt Adresse gibt ein net. MSMQ:-Schema an, verwendet "localhost" für den lokalen Computer und verwendet Schrägstriche im Pfad. Um in einer Warteschlange zu lesen, die auf einem Remotecomputer gehostet wird, ersetzen Sie "." und "localhost" durch den Namen des Remotecomputers.  
  
 Der Dienst ist selbst gehostet. Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden. Dies kann manuell erfolgen oder mithilfe eines Codes. In diesem Beispiel prüft der Dienst, ob die Warteschlange vorhanden ist, und erstellt sie gegebenenfalls. Der Warteschlangenname wird aus der Konfigurationsdatei gelesen. Die Basisadresse wird vom [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, um den Proxy für den Dienst zu generieren.  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderProcessorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```

 Der Client erstellt eine Transaktion. Die Kommunikation mit der Warteschlange findet innerhalb des Geltungsbereichs der Transaktion statt, sodass diese in der Folge als unteilbare Einheit behandelt wird, in der alle Nachrichten entweder erfolgreich sind oder fehlschlagen.  

```csharp
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```

 Der Clientcode implementiert den `IOrderStatus`-Vertrag, um den Auftragsstatus vom Dienst zu empfangen. In diesem Fall druckt er den Auftragsstatus aus.  

```csharp
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,   
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,   
                                                           status);  
    }  
}  
```

 Die Auftragsstatuswarteschlange wird in der `Main`-Methode erstellt. Die Clientkonfiguration beinhaltet die Dienstkonfiguration für den Auftragsstatus, um den Auftragsstatusdienst zu hosten, wie in der folgenden Beispielkonfiguration dargestellt.  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service   
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
              binding="netMsmqBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt. Sie können sehen, wie der Dienst Nachrichten vom Client empfängt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
 Der Dienst zeigt die Bestellungsinformationen an und sendet sie für die Rücksendung an den Auftragsstatus an die Auftragsstatuswarteschlage.  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 Der Client zeigt die vom Dienst gesendeten Auftragsstatusinformationen an.  
  
```console  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei "Svcutil.exe" verwenden, müssen Sie die Endpunktnamen in der Clientkonfiguration ändern, sodass sie mit dem Clientcode übereinstimmen.  
  
 Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert. Es gibt zwei relevante Eigenschaften für die MSMQ-Transportsicherheit, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> und <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` standardmäßig ist der Authentifizierungsmodus auf `Windows` festgelegt, und die Schutz Ebene ist auf `Sign`festgelegt. Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein. Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt  
  
1. Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie in der folgenden Beispielkonfiguration gezeigt.  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"   
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2. Wenn die Sicherheit für eine Clientkonfiguration deaktiviert wird, wird Folgendes generiert:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service   
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
                    binding="netMsmqBinding"   
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3. Der Dienst für dieses Beispiel erstellt eine Bindung im `OrderProcessorService`. Fügen Sie eine Codezeile hinzu, nachdem die Bindung instanziiert wurde, um den Sicherheitsmodus auf `None` festzulegen.  
  
    ```csharp
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4. Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.  
  
    > [!NOTE]
    > Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> oder der `Message`-Sicherheit auf `None`.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
