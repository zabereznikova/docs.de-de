---
title: 'Transaktive Batchverarbeitung:'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc04f0ce1d303a32cbf2232c76bfc4ef1143c9ea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="transacted-batching"></a>Transaktive Batchverarbeitung:
In diesem Beispiel wird die Batchverarbeitung durchgeführter Lesevorgänge mithilfe von Message Queuing (MSMQ) veranschaulicht. Transaktive Batchverarbeitung ist eine Leistungsoptimierungsfunktion für durchgeführte Lesevorgänge in Kommunikation unter Verwendung von Warteschlangen.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet. Der Dienst empfängt Nachrichten aus der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.  
  
 Dieses Beispiel veranschaulicht transaktive Batchverarbeitung. Die transaktive Batchverarbeitung ist ein Verhalten, das beim Lesen und Verarbeiten einer großen Anzahl an Nachrichten in der Warteschlange die Verwendung einer einzelnen Transaktion ermöglicht.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist. Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt. Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen. Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:  
  
    1.  Öffnen Sie Server-Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Erweitern Sie die **Funktionen** Registerkarte.  
  
    3.  Mit der rechten Maustaste **Private Meldungswarteschlangen**, und wählen Sie **neu**, **Private Warteschlange**.  
  
    4.  Überprüfen Sie die **transaktional** Feld.  
  
    5.  Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange.  
  
    > [!NOTE]
    >  In diesem Beispiel sendet der Client Hunderte von Nachrichten als Teil des Batches. Es ist normal, dass die Verarbeitung durch die Dienstanwendung eine gewisse Zeit dauert.  
  
3.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
4.  Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt  
  
1.  Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert. Es gibt zwei relevante Eigenschaften für MSMQ-transportsicherheit <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> und <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` standardmäßig der Authentifizierungsmodus festgelegt ist, um `Windows` und die Schutzebene festgelegt ist, um `Sign`. Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein. Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.  
  
2.  Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` setzen, wie in der folgenden Beispielkonfiguration gezeigt.  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
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
  
    </system.serviceModel>  
    ```  
  
3.  Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.  
  
    > [!NOTE]
    >  Das Festlegen von `security``mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und der `Message`-Sicherheit auf `None`.  
  
4.  Um die Datenbank auf einem Remotecomputer auszuführen, ändern Sie die Verbindungszeichenfolge so, dass sie auf den Computer verweist, auf dem sich die Datenbank befindet.  
  
## <a name="requirements"></a>Anforderungen  
 Um dieses Beispiel auszuführen, muss MSMQ installiert sein, und SQL oder SQL Express ist erforderlich.  
  
## <a name="demonstrates"></a>Veranschaulicht  
 Das Beispiel veranschaulicht transaktives Batchverarbeitungsverhalten. Transaktive Batchverarbeitung ist eine Leistungsoptimierungsfunktion, die zusammen mit MSMQ-Wartenschlangentransport bereitgestellt wird.  
  
 Wenn Transaktionen verwendet werden, um Nachrichten zu senden und zu empfangen, gibt es genau genommen 2 separate Transaktionen. Wenn der Client innerhalb des Geltungsbereichs einer Transaktion Nachrichten sendet, gilt die Transaktion lokal für den Client und den Warteschlangen-Manager des Clients. Wenn der Dienst innerhalb des Geltungsbereichs der Transaktion Nachrichten empfängt, gilt die Transaktion lokal für den Dienst und den empfangenden Warteschlangen-Manager. Es ist wichtig, daran zu denken, dass der Client und der Dienst nicht an derselben Transaktion beteiligt sind, sondern zur Durchführung ihrer Vorgänge (wie Senden und Empfangen) über die Warteschlange verschiedene Transaktionen verwenden.  
  
 Im Beispiel wird eine einzelne Transaktion zur Ausführung mehrerer Dienstvorgänge verwendet. Diese dient lediglich als Leistungsoptimierungsfunktion und hat keine Auswirkungen auf die Semantik der Anwendung. Das Beispiel basiert auf [Binden von MSMQ transaktive](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).  
  
## <a name="comments"></a>Kommentare  
 In diesem Beispiel sendet der Client einen Nachrichtenbatch aus dem Geltungsbereich einer Transaktion an den Dienst. Um die Leistungsoptimierung zu zeigen, wird eine große Anzahl von Nachrichten gesendet; in diesem Fall bis zu 2.500 Nachrichten.  
  
 Die an die Warteschlange gesendeten Nachrichten werden dann vom Dienst innerhalb des vom Dienst definierten Geltungsbereichs der Transaktion empfangen. Ohne Batchverarbeitung führt dies zu 2.500 Transaktionen für jeden Aufruf des Dienstvorgangs. Dadurch wird die Leistung des Systems beeinflusst. Da zwei Ressourcen-Manager beteiligt sind – die MSMQ-Warteschlange und die `Orders`-Datenbank – ist jede dieser Transaktionen eine DTC-Transaktion. Dieser Vorgang wurde wie folgt optimiert: Es wird eine wesentlich kleinere Anzahl an Transaktionen verwendet, indem sichergestellt wird, dass ein Batch an Nachrichten und Dienstvorgangsaufrufen in einer einzelnen Transaktion erfolgt.  
  
 Die Batchverarbeitungsfunktion wird wie folgt verwendet:  
  
-   Durch die Angabe von transaktivem Batchverarbeitungsverhalten in der Konfiguration.  
  
-   Durch die Angabe einer Batchgröße hinsichtlich der Anzahl der Nachrichten, die in einer einzelnen Transaktion gelesen werden sollen.  
  
-   Durch die Angabe der maximalen Anzahl gleichzeitig auszuführender Batches.  
  
 In diesem Beispiel werden Leistungssteigerungen durch die Verringerung von Transaktionen gezeigt, die dadurch erreicht werden kann, dass erst 100 Dienstvorgänge in einer einzelnen Transaktion aufgerufen werden, bevor der Commit für die Transaktion ausgeführt wird.  
  
 Das Dienstverhalten definiert ein Vorgangsverhalten, wobei `TransactionScopeRequired` auf `true` gesetzt ist. Auf diese Weise wird sichergestellt, dass alle Ressourcen-Manager, auf die diese Methode zugreift, denselben Geltungsbereich einer Transaktion verwenden, der auch zum Abrufen der Nachricht aus der Warteschlange verwendet wurde. In diesem Beispiel wird eine einfache Datenbank zum Speichern der in der Nachricht enthaltenen Bestellinformation verwendet werden. Des Weiteren wird durch den Transaktionsbereich gewährleistet, dass die Nachricht an die Warteschlange zurückgegeben wird, wenn die Methode eine Ausnahme auslöst. Ohne Festlegung dieses Vorgangsverhaltens erstellt ein in der Warteschlange stehender Kanal eine Transaktion, um die Nachricht aus der Warteschlange zu lesen, und führt automatisch vor der Verteilung der Nachricht dafür einen Commit aus, sodass die Nachricht verloren geht, falls der Vorgang fehlschlägt. Das häufigste Szenario betrifft Dienstvorgänge, die sich in der Transaktion eintragen, die zum Lesen der Nachricht aus der Warteschlange dient, wie im folgenden Code veranschaulicht.  
  
 Beachten Sie, dass `ReleaseServiceInstanceOnTransactionComplete` auf `false` gesetzt ist. Dies ist eine wichtige Anforderung für die Batchverarbeitung. Die Eigenschaft `ReleaseServiceInstanceOnTransactionComplete` für `ServiceBehaviorAttribute`gibt an, was nach Abschluss der Transaktion mit der Dienstinstanz geschehen soll. Standardmäßig wird die Dienstinstanz nach Abschluss der Transaktion freigegeben. Der wichtigste Aspekt bei der Batchverarbeitung ist die Verwendung einer einzelnen Transaktion zum Lesen und Verteilen einer großen Anazahl an Nachrichten in der Warteschlange. Die Freigabe des Diensts führt also zum Vorzeitigen Abschluss der Transaktion, wodurch der ganze Nutzen der Stapelverarbeitung hinfällig wird. Wenn diese Eigenschaft auf `true` gesetzt und transaktive Batchverarbeitung zum Endpunkt hinzugefügt wird, löst das Batchverarbeitungsverhalten eine Ausnahme aus.  
  
```  
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```  
  
 Die `Orders`-Klasse kapselt die Verarbeitung des Auftrags. Im Beispiel aktualisiert sie die Datenbank mit Bestellinformationen.  
  
```  
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```  
  
 Das Batchverarbeitungsverhalten und seine Konfiguration werden in der Dienstanwendungskonfiguration angegeben.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  Die Batchgröße ist ein Hinweis für das System. Wenn Sie beispielsweise die Batchgröße 20 angaben, werden 20 Nachrichten in einer einzelnen Transaktion gelesen und verteilt, und anschließend wird ein Commit für die Transaktion ausgeführt. Aber es gibt Fälle, in denen die Transaktion möglicherweise einen Commit für den Batch ausführt, bevor die Batchgröße erreicht wird.  
>   
>  Jeder Transaktion ist ein Timeout zugeordnet, das zu laufen beginnt, sobald die Transaktion erstellt wird. Wenn dieses Timeout abläuft, wird die Transaktion abgebrochen. Es ist sogar möglich, dass dieses Timeout abläuft, bevor die Batchgröße erreicht wird. Um zu vermeiden, dass der Batch aufgrund des Abbruchs erneut verarbeitet werden muss, überprüft `TransactedBatchingBehavior`, wie viel Zeit für die Transaktion noch übrig ist. Wenn 80 % des Transaktionstimeouts abgelaufen sind, wird ein Commit für die Transaktion ausgeführt.  
>   
>  Falls die Warteschlange keine weiteren Nachrichten mehr enthält, wird nicht weiter auf das Erreichen der Batchgröße gewartet, sondern <xref:System.ServiceModel.Description.TransactedBatchingBehavior> führt einen Commit für die Transaktion durch.  
>   
>  Die Auswahl der Batchgröße hängt von Ihrer Anwendung ab. Wenn die Batchgröße zu klein ist, wird möglicherweise nicht die gewünschte Leistung erreicht. Andererseits kann auch eine zu große Batchgröße zu Leistungseinbußen führen. Beispielsweise könnte die Transaktion länger erhalten bleiben und die Datenbank sperren, oder die Transaktion könnte blockiert werden, was dazu führen könnte, dass der Batch zurückgesetzt wird und die Arbeit wiederholt werden muss.  
  
 Der Client erstellt einen Geltungsbereich für die Transaktion. Die Kommunikation mit der Warteschlange findet innerhalb des Geltungsbereichs der Transaktion statt, sodass diese in der Folge als unteilbare Einheit behandelt wird, in der entweder alle oder keine Nachrichten an die Warteschlange gesendet werden. Für die Transaktion wird ein Commit ausgeführt, indem <xref:System.Transactions.TransactionScope.Complete%2A> im Geltungsbereich der Transaktion aufgerufen wird.  
  
```  
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
            PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();  
            lineItem2.ProductId = "Red Widget";  
            lineItem2.Quantity = 890;  
            lineItem2.UnitCost = 45.89F;  
  
            po.orderLineItems = new PurchaseOrderLineItem[2];  
            po.orderLineItems[0] = lineItem1;  
            po.orderLineItems[1] = lineItem2;  
  
            //Create a transaction scope.  
            using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
            {  
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt. Sie können sehen, wie der Dienst Nachrichten vom Client empfängt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen. Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen. Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt. Sie können eine rollende Ausgabe sehen, während Nachrichten in einen Batch eingelesen und verarbeitet werden.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a>Siehe auch
