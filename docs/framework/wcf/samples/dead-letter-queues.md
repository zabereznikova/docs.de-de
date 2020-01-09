---
title: Warteschlangen für unzustellbare Meldungen
ms.date: 03/30/2017
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
ms.openlocfilehash: d493aba9a3f7a51824243fe8d06441ab563b2261
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344538"
---
# <a name="dead-letter-queues"></a>Warteschlangen für unzustellbare Meldungen
Dieses Beispiel veranschaulicht das Behandeln und Verarbeiten von Nachrichten mit Fehlern bei der Zustellung. Es basiert auf dem [transaktiven MSMQ-Bindungs](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) Beispiel. In diesem Beispiel wird die `netMsmqBinding`-Bindung verwendet. Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

> [!NOTE]
> Dieses Beispiel veranschaulicht jede Warteschlange für unzustellbare Nachrichten, die nur unter Windows Vista verfügbar ist. Das Beispiel kann so geändert werden, dass die standardmäßigen systemweiten Warteschlangen für MSMQ 3,0 unter Windows Server 2003 und [!INCLUDE[wxp](../../../../includes/wxp-md.md)]verwendet werden.

 In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet. Der Dienst empfängt Nachrichten aus der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.

 Da die Kommunikation über Warteschlangen zu einer gewissen Verzögerung führen kann, können Sie der Nachricht eine Gültigkeitsdauer zuweisen, um sicherzustellen, dass die Nachricht nach Ablauf der Gültigkeit nicht mehr an die Anwendung gesendet wird. Es gibt auch Fälle, in denen eine Anwendung informiert werden muss, wenn eine Nachricht nicht zugestellt werden konnte. In derartigen Fällen, wenn beispielsweise die Gültigkeitsdauer der Nachricht abgelaufen ist, oder wenn die Nachricht nicht zugestellt werden konnte, werden die Nachrichten in der Warteschlange für unzustellbare Nachrichten abgelegt. Die sendende Anwendung kann die Nachricht daraufhin in der Warteschlange für unzustellbare Nachrichten lesen und Korrekturmaßnahmen ergreifen. Diese reichen von keiner Maßnahme bis zur Behebung der Ursache für die Unzustellbarkeit der Nachricht und erneuter Sendung.

 Die Warteschlange für unzustellbare Nachrichten in der `NetMsmqBinding`-Bindung wird in den folgenden Eigenschaften ausgedrückt:

- <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>-Eigenschaft, um die vom Client benötigte Art der Warteschlange für unzustellbare Nachrichten auszudrücken. Diese Enumeration verfügt über folgende Werte:

- `None`: Für den Client ist keine Warteschlange für unzustellbare Nachrichten erforderlich.

- `System`: Die Systemwarteschlange für unzustellbare Nachrichten wird verwendet, um unzustellbare Nachrichten zu speichern. Die Systemwarteschlange für unzustellbare Nachrichten wird von allen Anwendungen verwendet, die auf dem Computer ausgeführt werden.

- `Custom`: Die in der <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>-Eigenschaft angegebene benutzerdefinierte Warteschlange für unzustellbare Nachrichten wird verwendet, um unzustellbare Nachrichten zu speichern. Diese Funktion ist nur unter Windows Vista verfügbar. Dieser Wert wird verwendet, wenn die Anwendung ihre eigene Warteschlange für unzustellbare Nachrichten verwenden muss und diese nicht mit anderen Anwendungen auf dem gleichen Computer gemeinsam verwenden kann.

- <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>-Eigenschaft, um die spezifische Warteschlange für unzustellbare Nachrichten anzugeben. Diese ist nur in Windows Vista verfügbar.

 In diesem Beispiel sendet der Client einen Stapel von Nachrichten aus dem Bereich der Transaktion an den Dienst und legt einen willkürlichen niedrigen Wert für die Gültigkeitsdauer für diese Nachrichten fest (ca. 2 Sekunden). Der Client gibt auch eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten an, in der abgelaufene Nachrichten abgelegt werden.

 Die Clientanwendung kann die Nachrichten in der Warteschlange für unzustellbare Nachrichten lesen und entweder versuchen, diese erneut zu senden, oder den Fehler beheben, der dazu führte, dass die Nachricht in der Warteschlange für unzustellbare Nachrichten abgelegt wurde, und die Nachricht dann senden. Im Beispiel zeigt der Client eine Fehlermeldung an.

 Der Dienstvertrag lautet `IOrderProcessor`, wie im folgenden Beispielcode gezeigt.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Der Dienst Code im Beispiel ist der der [transaktiven MSMQ-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).

 Die Kommunikation mit dem Dienst findet innerhalb des Bereichs der Transaktion statt. Der Dienst liest die Nachrichten in der Warteschlange, führt den Vorgang aus und zeigt anschließend die Ergebnisse des Vorgangs an. Die Anwendung erstellt auch eine Warteschlange für unzustellbare Nachrichten.

```csharp
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.

//Client implementation code.
class Client
{
    static void Main()
    {
        // Get MSMQ queue name from app settings in configuration
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];

        // Create the transacted MSMQ queue for storing dead message if necessary.
        if (!MessageQueue.Exists(deadLetterQueueName))
            MessageQueue.Create(deadLetterQueueName, true);

        // Create a proxy with given client endpoint configuration
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");

        // Create the purchase order
        PurchaseOrder po = new PurchaseOrder();
        po.CustomerId = "somecustomer.com";
        po.PONumber = Guid.NewGuid().ToString();

        PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
        lineItem1.ProductId = "Blue Widget";
        lineItem1.Quantity = 54;
        lineItem1.UnitCost = 29.99F;

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
            // Make a queued call to submit the purchase order
            client.SubmitPurchaseOrder(po);
            // Complete the transaction.
            scope.Complete();
        }

        client.Close();

        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate client.");
        Console.ReadLine();
    }
}
```

 Die Konfiguration des Clients gibt eine kurze Zeitspanne an, während derer die Nachricht den Dienst erreichen muss. Wenn die Nachricht innerhalb der festgelegten Zeitspanne nicht übermittelt werden kann, läuft die Nachricht ab und wird in die Warteschlange für unzustellbare Nachrichten verschoben.

> [!NOTE]
> Der Client kann die Nachricht innerhalb der angegebenen Zeitspanne an die Dienstwarteschlange übermitteln. Um sicherzustellen, dass Sie die Ausführung des Diensts für unzustellbare Nachrichten beobachten können, sollten Sie den Client vor dem Start des Diensts ausführen. Die Nachricht überschreitet das Zeitlimit und wird an den Dienst für unzustellbaren Nachrichten übermittelt.

 Die Anwendung muss definieren, welche der Warteschlangen als Warteschlange für unzustellbare Nachrichten verwendet werden soll. Wenn keine Warteschlange angegeben wird, wird die systemweite Standardtransaktionswarteschlange für unzustellbare Nachrichten verwendet. In diesem Beispiel gibt die Clientanwendung ihre eigene Anwendungswarteschlange für unzustellbare Nachrichten an.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>
  </appSettings>

  <system.serviceModel>
    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                binding="netMsmqBinding"
                bindingConfiguration="PerAppDLQBinding"
                contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="PerAppDLQBinding"
                 deadLetterQueue="Custom"
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                 timeToLive="00:00:02"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>

</configuration>
```

 Der Dienst für unzustellbare Nachrichten liest Nachrichten aus der Warteschlange für unzustellbare Nachrichten. Der Dienst für unzustellbare Nachrichten implementiert den `IOrderProcessor`-Vertrag. Seine Implementierung dient jedoch nicht der Verarbeitung von Aufträgen. Der Dienst für unzustellbare Nachrichten ist ein Clientdienst und besitzt keine Funktion für die Verarbeitung von Aufträgen.

> [!NOTE]
> Die Warteschlange für unzustellbare Nachrichten ist eine Clientwarteschlange und befindet sich lokal zum Clientwarteschlangen-Manager.

 Die Implementierung des Dienst für unzustellbare Nachrichten überprüft die Ursache für die fehlgeschlagene Zustellung und ergreift Abhilfemaßnahmen. Die Ursache für die fehlgeschlagene Zustellung wird in zwei Enumerationen, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> und <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>, aufgezeichnet. Sie können die <xref:System.ServiceModel.Channels.MsmqMessageProperty> vom <xref:System.ServiceModel.OperationContext> abrufen, wie im folgenden Beispiel dargestellt:

```csharp
public void SubmitPurchaseOrder(PurchaseOrder po)
{
    Console.WriteLine("Submitting purchase order did not succeed ", po);
    MsmqMessageProperty mqProp =
                  OperationContext.Current.IncomingMessageProperties[
                  MsmqMessageProperty.Name] as MsmqMessageProperty;
    Console.WriteLine("Message Delivery Status: {0} ",
                                                mqProp.DeliveryStatus);
    Console.WriteLine("Message Delivery Failure: {0}",
                                               mqProp.DeliveryFailure);
    Console.WriteLine();
    …
}
```

 Nachrichten in der Warteschlange für unzustellbare Nachrichten sind Nachrichten, die an den Dienst adressiert sind, der die Nachricht verarbeitet. Wenn der Dienst für unzustellbare Nachrichten Nachrichten aus der Warteschlange liest, findet daher die Windows Communication Foundation (WCF)-Kanal Ebene die nicht Übereinstimmung in Endpunkten und versendet die Nachricht nicht. In diesem Fall ist die Nachricht an den Auftragsverarbeitungsdienst adressiert, wird jedoch vom Dienst für unzustellbare Nachrichten empfangen. Um Nachrichten zu empfangen, die an einen anderen Endpunkt adressiert sind, wird im `ServiceBehavior` ein Adressfilter für alle Adressen angegeben. Dies ist erforderlich, um Nachrichten, die aus der Warteschlange für unzustellbare Nachrichten gelesen werden, erfolgreich zu verarbeiten.

 In diesem Beispiel sendet der Nachrichtendienst für unzustellbare Nachrichten die Nachricht erneut, wenn der Grund für den Fehler darin besteht, dass die Nachricht abgelaufen ist. Aus allen anderen Gründen wird der Übermittlungs Fehler angezeigt, wie im folgenden Beispielcode gezeigt:

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]
public class PurchaseOrderDLQService : IOrderProcessor
{
    OrderProcessorClient orderProcessorService;
    public PurchaseOrderDLQService()
    {
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Submitting purchase order did not succeed ", po);
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;

        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);
        Console.WriteLine();

        // resend the message if timed out
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)
        {
            // re-send
            Console.WriteLine("Purchase order Time To Live expired");
            Console.WriteLine("Trying to resend the message");

            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue
            orderProcessorService.SubmitPurchaseOrder(po);
            Console.WriteLine("Purchase order resent");
        }
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Create a ServiceHost for the PurchaseOrderDLQService type.
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))
        {
            // Open the ServiceHostBase to create listeners and start listening for messages.
            serviceHost.Open();

            // The service can now be accessed.
            Console.WriteLine("The dead letter service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
```

 Im folgenden Beispiel wird die Konfiguration für eine unzustellbare Nachricht veranschaulicht:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                  binding="netMsmqBinding"
                  bindingConfiguration="DefaultBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                 binding="netMsmqBinding"
                 bindingConfiguration="SystemDLQBinding"
                 contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="DefaultBinding" />
        <binding name="SystemDLQBinding"
                 deadLetterQueue="System"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

 Wenn das Beispiel ausgeführt wird, müssen drei Programmdateien ausgeführt werden, um zu beobachten, wie die Warteschlange für unzustellbare Nachrichten für jede Anwendung funktioniert. Der Client, der Dienst und ein Dienst für unzustellbare Nachrichten, der in allen Anwendungen in der Warteschlange für unzustellbare Nachrichten liest und die Nachricht erneut an den Dienst sendet. Alle sind Konsolenanwendungen mit Ausgabe in Konsolenfenster.

> [!NOTE]
> Aufgrund der Verwendung einer Warteschlange müssen der Client und der Dienst nicht gleichzeitig ausgeführt werden. Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt. Sie sollten den Dienst starten und wieder schließen, damit die Warteschlange erstellt werden kann.

 Wenn der Client ausgeführt wird, zeigt er die folgende Nachricht an:

```console
Press <ENTER> to terminate client.
```

 Der Client hat versucht, die Nachricht zu senden, aufgrund des kurzen Zeitlimits ist die Nachricht jedoch abgelaufen und befindet sich jetzt in der Warteschlange für unzustellbare Nachrichten für jede Anwendung.

 Anschließend führen Sie den Dienst für unzustellbare Nachrichten aus, der die Nachrichten liest, den Fehlercode anzeigt und die Nachricht zurück an den Dienst sendet.

```console
The dead letter service is ready.
Press <ENTER> to terminate service.

Submitting purchase order did not succeed
Message Delivery Status: InDoubt
Message Delivery Failure: ReachQueueTimeout

Purchase order Time To Live expired
Trying to resend the message
Purchase order resent
```

 Der Dienst startet, liest dann die erneut gesendeten Nachrichten und verarbeitet sie.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist. Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt. Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen. Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:

    1. Öffnen Sie Server-Manager in Visual Studio 2012.

    2. Erweitern Sie die Registerkarte **Features** .

    3. Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**

    4. Aktivieren Sie das Kontrollkästchen **transaktional** .

    5. Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.

3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

4. Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, ändern Sie die Warteschlangen Namen entsprechend, indem Sie localhost durch den vollständigen Namen des Computers ersetzen, und befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>So führen Sie das Beispiel auf einem Computer aus, der zu einer Arbeitsgruppe gehört

1. Wenn Ihr Computer nicht zu einer Domäne gehört, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` festlegen, wie in der folgenden Beispielkonfiguration gezeigt.

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     Stellen Sie sicher, dass der Endpunkt der Bindung zugeordnet ist, indem Sie das `bindingConfiguration`-Attribut des Endpunkts festlegen.

2. Ändern Sie die Konfiguration auf dem DeadLetterService, dem Server und dem Client, bevor Sie das Beispiel ausführen.

    > [!NOTE]
    > Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von `MsmqAuthenticationMode`, `MsmqProtectionLevel` und der `Message`-Sicherheit auf `None`.

## <a name="comments"></a>Comments
 Standardmäßig wird mit der `netMsmqBinding`-Bindung die Transportsicherheit aktiviert. Der Typ der Transportsicherheit wird durch zwei Eigenschaften festgelegt: `MsmqAuthenticationMode` und `MsmqProtectionLevel`. Standardmäßig wird der Authentifizierungsmodus auf `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt. Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es ein Teil einer Domäne sein. Wenn Sie dieses Beispiel auf einem Computer ausführen, der nicht Teil einer Domäne ist, wird folgende Fehlermeldung ausgegeben: "Das interne Message Queuing-Zertifikat für diesen Benutzer ist nicht vorhanden".

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
