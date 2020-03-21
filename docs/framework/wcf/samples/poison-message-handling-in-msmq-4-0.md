---
title: Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0
ms.date: 03/30/2017
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
ms.openlocfilehash: 4b662094923c85e825edcc9025a73f1a1b42cb9b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144239"
---
# <a name="poison-message-handling-in-msmq-40"></a>Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0
In diesem Beispiel wird veranschaulicht, wie die Handhabung nicht verarbeitbarer Nachrichten in einem Dienst erfolgen soll. Dieses Beispiel basiert auf dem [Beispiel für die TRANSacted MSMQ-Bindung.](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) In diesem Beispiel wird der `netMsmqBinding` verwendet. Der Dienst ist eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.

 In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet. Der Dienst empfängt Nachrichten aus der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.

 Eine nicht verarbeitbare Nachricht ist eine Nachricht, die wiederholt aus einer Warteschlange eingelesen wird, wenn der Dienst, der die Nachricht liest, diese nicht verarbeiten kann und daher die Transaktion abbricht, unter der die Nachricht gelesen wird. In solchen Fällen wird erneut versucht, die Nachricht zu verarbeiten. Dies kann theoretisch ewig so weitergehen, wenn ein Problem mit der Nachricht vorliegt. Dies kann nur auftreten, wenn Sie Transaktionen verwenden, um aus der Warteschlange zu lesen und den Dienstvorgang aufzurufen.

 Je nach MSMQ-Version unterstützt NetMsmqBinding eingeschränkte bis vollständige Erkennung von nicht verarbeitbaren Nachrichten. Nachdem die Nachricht als nicht verarbeitbar erkannt wurde, kann sie auf verschiedene Weisen gehandhabt werden. Wiederum in Abhängigkeit von der MSMQ-Version unterstützt NetMsmqBinding die eingeschränkte bis vollständige Handhabung von nicht verarbeitbaren Nachrichten.

 In diesem Beispiel werden die begrenzten Giftfunktionen auf Windows Server 2003 und Windows XP-Plattformen sowie die vollständigen Giftfunktionen unter Windows Vista veranschaulicht. In beiden Beispielen besteht das Ziel darin, die Giftnachricht aus der Warteschlange in eine andere Warteschlange zu verschieben. Diese Warteschlange kann dann von einem Giftnachrichtendienst bedient werden.

## <a name="msmq-v40-poison-handling-sample"></a>MSMQ v4.0 &#8211; Beispiel für Handhabung nicht verarbeitbarer Nachrichten
 In Windows Vista bietet MSMQ eine Gift-Subqueue-Funktion, die zum Speichern von Giftnachrichten verwendet werden kann. In diesem Beispiel wird die bewährte Methode für den Umgang mit Giftnachrichten unter Windows Vista veranschaulicht.

 Die Giftnachrichtenerkennung in Windows Vista ist ausgeklügelt. Es gibt 3 Eigenschaften, die bei der Erkennung behilflich sind. <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> gibt an, wie oft eine bestimmte Nachricht erneut aus der Warteschlange gelesen und zur Verarbeitung an die Anwendung übergeben wird. Eine Nachricht wird erneut aus der Warteschlange eingelesen, wenn sie wieder in die Warteschlange eingestellt wurde, weil sie nicht an die Anwendung übergeben werden konnte oder weil die Anwendung die Transaktion im Dienstvorgang zurücksetzt. <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> gibt an, wie oft die Nachricht in die Wiederholungswarteschlange verschoben wird. Wenn <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> erreicht wird, wird die Nachricht in die Wiederholungswarteschlange verschoben. Die Eigenschaft <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> ist die Zeitverzögerung, nach der die Nachricht aus der Wiederholungswarteschlange zurück in die Hauptwarteschlange verschoben wird. <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> wird auf 0 zurückgesetzt. Es wird ein erneuter Versuch gestartet. Wenn alle Versuche, die Nachricht zu lesen, fehlgeschlagen sind, wird die Nachricht als nicht verarbeitbar markiert.

 Sobald eine Nachricht als nicht verarbeitbar markiert wurde, wird damit gemäß den Einstellungen in der <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>-Enumeration verfahren. So können Sie die möglichen Werte erneut durchlaufen:

- "Fault" (Standard): Versetzt den Listener und auch den Diensthost in den Fehlerzustand.

- „Drop“: Verwirft die Nachricht.

- Verschieben: Um die Nachricht in die Unterwarteschlange der Giftnachricht zu verschieben. Dieser Wert ist nur unter Windows Vista verfügbar.

- "Reject": Lehnt die Nachricht ab und sendet sie zurück in die Warteschlange für unzustellbare Nachrichten des Absenders. Dieser Wert ist nur unter Windows Vista verfügbar.

 Im Beispiel wird die Verwendung der `Move`-Disposition für die nicht verarbeitbare Nachricht veranschaulicht. `Move`bewirkt, dass die Nachricht in die Gift-Subwarteschlange verschoben wird.

 Der Dienstvertrag ist `IOrderProcessor`, der einen unidirektionalen Dienst definiert, der für die Verwendung mit Warteschlangen geeignet ist.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 Der Dienstvorgang zeigt eine Nachricht an, die angibt, dass der Auftrag verarbeitet wird. Um die Giftnachrichtenfunktionalität `SubmitPurchaseOrder` zu demonstrieren, löst der Dienstvorgang eine Ausnahme aus, um die Transaktion bei einem zufälligen Aufruf des Dienstes zurückzuschlagen. Dadurch wird die Nachricht in die Warteschlange zurückgestellt. Schließlich wird die Nachricht als nicht verarbeitbar markiert. Die Konfiguration ist so eingestellt, dass die Giftnachricht in die Gift-Subwarteschlange verschoben wird.

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    static Random r = new Random(137);

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {

        int randomNumber = r.Next(10);

        if (randomNumber % 2 == 0)
        {
            Orders.Add(po);
            Console.WriteLine("Processing {0} ", po);
        }
        else
        {
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);
            Console.WriteLine();
            throw new Exception("Cannot process purchase order: " + po.PONumber);
        }
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted");
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Get MSMQ queue name from app settings in configuration.
        string queueName = ConfigurationManager.AppSettings["queueName"];

        // Create the transacted MSMQ queue if necessary.
        if (!System.Messaging.MessageQueue.Exists(queueName))
            System.Messaging.MessageQueue.Create(queueName, true);

        // Get the base address that is used to listen for WS-MetaDataExchange requests.
        // This is useful to generate a proxy for the client.
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        // Open the ServiceHostBase to create listeners and start listening for messages.
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        if(serviceHost.State != CommunicationState.Faulted) {
            serviceHost.Close();
        }

    }
}
```

 Die Dienstkonfiguration beinhaltet folgende Eigenschaften für nicht verarbeitbare Nachrichten: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay` und `receiveErrorHandling`, wie in der folgenden Konfigurationsdatei gezeigt.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>
  </appSettings>
  <system.serviceModel>
    <services>
      <service
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"
                  binding="netMsmqBinding"
                  bindingConfiguration="PoisonBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <bindings>
      <netMsmqBinding>
        <binding name="PoisonBinding"
                 receiveRetryCount="0"
                 maxRetryCycles="1"
                 retryCycleDelay="00:00:05"
                 receiveErrorHandling="Move">
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="processing-messages-from-the-poison-message-queue"></a>Verarbeiten von Nachrichten aus der Warteschlange für potenziell schädliche Nachrichten
 Der Dienst für nicht verarbeitbare Nachrichten liest Nachrichten aus der endgültigen Warteschlange für potenziell schädliche Nachrichten und verarbeitet sie.

 Nachrichten in der Warteschlange für potenziell schädliche Nachrichten sind Nachrichten, die an den Dienst adressiert sind, der die Nachricht verarbeitet; dieser kann vom Dienst-Endpunkt für nicht verarbeitbare Nachrichten abweichen. Wenn der Giftnachrichtendienst Nachrichten aus der Warteschlange liest, findet die WCF-Kanalschicht die Nichtübereinstimmung in Endpunkten und sendet die Nachricht nicht aus. In diesem Fall ist die Nachricht an den Auftragsverarbeitungsdienst adressiert, wird jedoch vom Dienst für nicht verarbeitete Nachrichten empfangen. Damit die Nachricht empfangen wird, selbst wenn sie an einen anderen Endpunkt adressiert ist, muss `ServiceBehavior` zum Filtern von Adressen hinzugefügt werden, wobei das Übereinstimmungskriterium darin besteht, mit jedem Dienst-Endpunkt übereinzustimmen, an den die Nachricht adressiert ist. Dies ist erforderlich, um Nachrichten, die aus der Warteschlange für potenziell schädliche Nachrichten gelesen werden, erfolgreich zu verarbeiten.

 Die Implementierung des Diensts für nicht verarbeitbare Nachrichten selbst weist große Ähnlichkeiten mit der Dienstimplementierung auf. Sie implementiert den Vertrag und verarbeitet die Aufträge. Hier das Codebeispiel.

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }

    public static void OnServiceFaulted(object sender, EventArgs e)
    {
        Console.WriteLine("Service Faulted...exiting app");
        Environment.Exit(1);
    }

    // Host the service within this EXE console application.
    public static void Main()
    {

        // Create a ServiceHost for the OrderProcessorService type.
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));

        // Hook on to the service host faulted events.
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);

        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The poison message service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();

        // Close the ServiceHostBase to shutdown the service.
        if(serviceHost.State != CommunicationState.Faulted)
        {
            serviceHost.Close();
        }
    }
```

 Im Gegensatz zum Auftragsverarbeitungsdienst, der Nachrichten aus der Auftragswarteschlange liest, liest der Giftnachrichtendienst Nachrichten aus der Giftunterwarteschlange. Die Giftwarteschlange ist eine Unterwarteschlange der Hauptwarteschlange, heißt "Gift" und wird automatisch von MSMQ generiert. Um darauf zuzugreifen, geben Sie den Hauptwarteschlangennamen gefolgt von einem ";" und dem Subqueue-Namen, in diesem Fall -"poison", an, wie in der folgenden Beispielkonfiguration gezeigt.

> [!NOTE]
> Im Beispiel für MSMQ v3.0 handelt es sich beim Namen der Warteschlange für potenziell schädliche Nachrichten ("poison") nicht um eine Unterwarteschlange, sondern vielmehr um die Warteschlange, in die die Nachricht verschoben wurde.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >
        </endpoint>
      </service>
    </services>

  </system.serviceModel>
</configuration>
```

 Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowie die Dienstaktivitäten für nicht verarbeitbare Nachrichten in Konsolenfenstern angezeigt. Sie können sehen, wie der Dienst Nachrichten vom Client empfängt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um die Dienste herunterzufahren.

 Der Dienst beginnt mit der Ausführung, verarbeitet Aufträge und beginnt zu einem nach dem Zufallsprinzip ausgewählten Zeitpunkt, die Verarbeitung abzubrechen. Wenn die Nachricht angibt, dass der Auftrag verarbeitet wurde, können Sie den Client erneut ausführen, um eine weitere Nachricht zu senden, bis Sie feststellen, dass der Dienst die Verarbeitung einer Nachricht tatsächlich abgebrochen hat. Gemäß den konfigurierten Einstellungen für nicht verarbeitbare Nachrichten wird noch einmal versucht, die Nachricht zu verarbeiten, bevor sie in die endgültige Warteschlange für potenziell schädliche Nachrichten ("poison") verschoben wird.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending

Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
```

 Starten Sie den Dienst für nicht verarbeitbare Nachrichten, um die nicht verarbeitbare Nachricht aus der Warteschlange für potenziell schädliche Nachrichten zu lesen. In diesem Beispiel liest der Dienst für nicht verarbeitbare Nachrichten die Nachricht und verarbeitet sie. Sie können sehen, dass die Bestellung, die abgebrochen und als nicht verarbeitbar gekennzeichnet wurde, vom Dienst für nicht verarbeitbare Nachrichten gelesen wird.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.

2. Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist. Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt. Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen. Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:

    1. Öffnen Sie den Server-Manager in Visual Studio 2012.

    2. Erweitern Sie die Registerkarte **Features.**

    3. Klicken Sie mit der rechten Maustaste auf **Private Message Queues**, und wählen Sie **Neue**, **Private Warteschlange**aus.

    4. Aktivieren Sie das Kontrollkästchen **Transaktional.**

    5. Geben `ServiceModelSamplesTransacted` Sie den Namen der neuen Warteschlange ein.

3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

4. Um das Beispiel in einer Einzel- oder Computerübergreifenden Konfiguration auszuführen, ändern Sie die Warteschlangennamen so, dass sie den tatsächlichen Hostnamen anstelle von localhost widerspiegeln, und befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

 Standardmäßig wird mit der `netMsmqBinding`-Bindung die Transportsicherheit aktiviert. Der Typ der Transportsicherheit wird durch zwei Eigenschaften festgelegt: `MsmqAuthenticationMode` und `MsmqProtectionLevel`. Standardmäßig wird der Authentifizierungsmodus als `Windows` festgelegt, und die Schutzebene wird auf `Sign` gesetzt. Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es ein Teil einer Domäne sein. Wenn Sie dieses Beispiel auf einem Computer ausführen, der nicht Teil einer Domäne ist, wird folgende Fehlermeldung ausgegeben: "Das interne Message Queuing-Zertifikat für diesen Benutzer ist nicht vorhanden".

#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>So führen Sie das Beispiel auf einem Computer aus, der zu einer Arbeitsgruppe gehört

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

     Stellen Sie sicher, dass der Endpunkt der Bindung zugeordnet wird, indem Sie das bindingConfiguration-Attribut des Endpunkts entsprechend festlegen.

2. Stellen Sie sicher, dass Sie die Konfiguration auf dem PoisonMessageServer, dem Server und dem Client ändern, bevor Sie das Beispiel ausführen.

    > [!NOTE]
    > Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von `MsmqAuthenticationMode`, `MsmqProtectionLevel` und der `Message`-Sicherheit auf `None`.  
  
3. Damit Meta Data Exchange funktionieren kann, registrieren Sie eine URL mit http-Bindung. Dazu muss der Dienst in einem Befehlsfenster auf Administratorebene ausgeführt werden. Andernfalls erhalten Sie eine Ausnahme `Unhandled Exception: System.ServiceModel.AddressAccessDeniedException: HTTP could not register URL http://+:8000/ServiceModelSamples/service/. Your process does not have access rights to this namespace (see https://go.microsoft.com/fwlink/?LinkId=70353 for details). ---> System.Net.HttpListenerException: Access is denied`wie: .  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`
