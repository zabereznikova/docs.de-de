---
title: Sitzungen und Warteschlangen
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 489a8f5e782faca679991809e575e98153de95e0
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140606"
---
# <a name="sessions-and-queues"></a>Sitzungen und Warteschlangen
Dieses Beispiel veranschaulicht, wie ein Satz zusammengehöriger Nachrichten bei der Kommunikation unter Verwendung von Warteschlangen über den MSMQ-Transport (Message Queuing) gesendet und empfangen wird. In diesem Beispiel wird die `netMsmqBinding`-Bindung verwendet. Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet. Der Dienst empfängt Nachrichten aus der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.  
  
 Manchmal sendet ein Client eine Reihe von Nachrichten, die in einer Gruppe zusammengehören. Wenn Nachrichten zusammen oder in einer angegebenen Reihenfolge verarbeitet werden müssen, können Sie mithilfe einer Warteschlange zwecks Verarbeitung durch eine einzige Empfangsanwendung zusammengefasst werden. Dies ist besonders wichtig, wenn in einer Gruppe von Servern mehrere Empfangsanwendungen vorhanden sind und sichergestellt werden muss, dass eine Gruppe von Nachrichten von derselben empfangenden Anwendung verarbeitet wird. Warteschlangensitzungen sind ein Mechanismus zum Senden und Empfangen eines Satzes zusammengehöriger Nachrichten, die alle zusammen verarbeitet werden müssen. Damit Warteschlangensitzungen dieses Muster bieten, ist eine Transaktion erforderlich.  
  
 Im vorliegenden Beispiel sendet der Client im Rahmen einer Sitzung innerhalb des Bereichs einer einzigen Transaktion eine Reihe von Nachrichten an den Dienst.  
  
 Der Dienstvertrag ist `IOrderTaker`, der einen unidirektionalen Dienst definiert, der für die Verwendung mit Warteschlangen geeignet ist. Der in dem Vertrag im folgenden Beispielcode verwendete <xref:System.ServiceModel.SessionMode> zeigt an, dass die Nachrichten zu der Sitzung gehören.  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```

 Der Dienst definiert Dienstvorgänge so, dass der erste Vorgang in einer Transaktion eingetragen, diese jedoch nicht automatisch abgeschlossen wird. Auch die nachfolgenden Vorgänge werden in derselben Transaktion eingetragen, die aber nicht automatisch abgeschlossen wird. Der letzte Vorgang in der Sitzung schließt die Transaktion automatisch ab. So wird die gleiche Transaktion für mehrere Vorgangsaufrufe im Dienstvertrag verwendet. Wenn einer der Vorgänge eine Ausnahme auslöst, wird ein Rollback der Transaktion ausgeführt und die Sitzung zurück in die Warteschlange gelegt. Nach erfolgreichem Abschluss des letzten Vorgangs wird ein Commit für die Transaktion ausgeführt. Der Dienst verwendet `PerSession` als <xref:System.ServiceModel.InstanceContextMode>, um sämtliche Nachrichten in einer Sitzung in derselben Instanz des Diensts zu empfangen.  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```

 Der Dienst ist selbst gehostet. Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden. Dies kann manuell erfolgen oder mithilfe eines Codes. In diesem Beispiel enthält der Dienst <xref:System.Messaging>-Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um sie andernfalls zu erstellen. Der Warteschlangenname wird mithilfe der <xref:System.Configuration.ConfigurationManager.AppSettings%2A>-Klasse aus der Konfigurationsdatei gelesen.  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();
    }  
}  
```

 Der MSMQ-Warteschlangenname wird im appSettings-Abschnitt der Konfigurationsdatei angegeben. Der Endpunkt für den Dienst wird im Abschnitt „system.serviceModel“ der Konfigurationsdatei definiert und gibt die `netMsmqBinding`-Bindung an.  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 Der Client erstellt einen Geltungsbereich für die Transaktion. Alle Nachrichten in der Sitzung werden an die Warteschlange innerhalb des Transaktionsbereichs gesendet, wo sie als eine unteilbare Einheit behandelt werden, so dass sämtliche Nachrichten entweder erfolgreich sind oder fehlschlagen. Das Commit für die Transaktion wird durch Aufrufen von <xref:System.Transactions.TransactionScope.Complete%2A> ausgeführt.  

```csharp
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();
  
    // Complete the transaction.  
    scope.Complete();  
}  
```

> [!NOTE]
> Sie können für sämtliche Nachrichten in der Sitzung nur eine einzige Transaktion verwenden, und alle Nachrichten in der Sitzung müssen vor deren Commit gesendet werden. Wenn der Client geschlossen wird, wird auch die Sitzung geschlossen. Daher muss der Client geschlossen werden, bevor die Transaktion abgeschlossen ist, um alle Nachrichten in der Sitzung an die Warteschlange zu senden.  
  
 Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt. Sie können sehen, wie der Dienst Nachrichten vom Client empfängt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen. Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen. Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.  
  
 Auf dem Client.  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 Beim Dienst.  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die c#-, C++-oder Visual Basic .NET-Edition der Projekt Mappe zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
 Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert. Es gibt zwei relevante Eigenschaften für die MSMQ <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> - <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` Transportsicherheit: Standardmäßig wird der Authentifizierungsmodus auf `Windows` und die Schutz Ebene auf `Sign`festgelegt. Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein. Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt  
  
1. Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie in der folgenden Beispielkonfiguration gezeigt.  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2. Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.  
  
    > [!NOTE]
    > Das Einstellen des Sicherheitsmodus auf `None` ist dasselbe, wie <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und `Message`-Sicherheit auf `None` zu setzen.  
