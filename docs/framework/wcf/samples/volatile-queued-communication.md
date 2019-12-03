---
title: Flüchtige Kommunikation unter Verwendung von Warteschlangen
ms.date: 03/30/2017
ms.assetid: 0d012f64-51c7-41d0-8e18-c756f658ee3d
ms.openlocfilehash: 8ed10262d319664d404e6beb630593cb93748a7d
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715282"
---
# <a name="volatile-queued-communication"></a>Flüchtige Kommunikation unter Verwendung von Warteschlangen

In diesem Beispiel wird veranschaulicht, wie eine flüchtige Kommunikation unter Verwendung von Warteschlangen über Message Queuing (MSMQ)-Transport durchgeführt wird. In diesem Beispiel wird <xref:System.ServiceModel.NetMsmqBinding> verwendet. Der Dienst ist in diesem Fall eine selbst gehostete Konsolenanwendung, die es Ihnen ermöglicht, den Dienst beim Empfang von Nachrichten in der Warteschlange zu beobachten.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

In einer Warteschlangenkommunikation kommuniziert der Client über eine Warteschlange mit dem Dienst. Genauer ausgedrückt bedeutet dies, dass der Client Nachrichten an eine Warteschlange sendet. Der Dienst empfängt Nachrichten aus der Warteschlange. Folglich müssen der Dienst und der Client nicht gleichzeitig ausgeführt werden, um über eine Warteschlange zu kommunizieren.

Wenn Sie eine Nachricht ohne Zusicherungen senden, sendet MSMQ nur nach dem Best-Effort-Prinzip, im Gegensatz zu Exactly Once-Zusicherungen, bei denen MSMQ sicherstellt, dass die Nachricht zugestellt wird, oder Sie benachrichtigt werden, falls sie nicht zugestellt werden kann.

In bestimmten Szenarios senden Sie eventuell eine flüchtige Nachricht ohne Zusicherungen über eine Warteschlange, wenn eine schnelle Zustellung wichtiger ist, als Nachrichten zu verlieren. Flüchtige Nachrichten bleiben nach einem Absturz des Warteschlangen-Managers nicht erhalten. Wenn es daher zu einem Absturz des Warteschlangen-Managers kommt, bleibt die nicht transaktionale Warteschlange zum Speichern von flüchtigen Nachrichten erhalten, die Nachrichten selbst jedoch nicht, da sie nicht auf dem Datenträger gespeichert werden.

> [!NOTE]
> Sie können keine flüchtigen Nachrichten ohne Zusicherungen innerhalb des Bereichs einer Transaktion mit MSMQ senden. Sie müssen außerdem eine nicht transaktionale Warteschlange erstellen, um flüchtige Nachrichten zu senden.

Bei dem Dienstvertrag in diesem Beispiel handelt es sich um `IStockTicker`. Hier werden unidirektionale Dienste definiert, die für die Verwendung mit Warteschlangen am besten geeignet sind.

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
public interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void StockTick(string symbol, float price);
}
```

Der Dienstvorgang zeigt das Aktientickersymbol und den Preis an, wie im folgenden Beispielcode dargestellt:

```csharp
public class StockTickerService : IStockTicker
{
    public void StockTick(string symbol, float price)
    {
        Console.WriteLine("Stock Tick {0}:{1} ", symbol, price);
     }
     …
}
```

Der Dienst ist selbst gehostet. Bei Verwendung des MSMQ-Transports muss die Warteschlange im Voraus erstellt werden. Dies kann manuell erfolgen oder mithilfe eines Codes. In diesem Beispiel enthält der Dienst Code, um zu überprüfen, ob die Warteschlange bereits vorhanden ist, und um die Warteschlange gegebenenfalls zu erstellen. Der Warteschlangenname wird aus der Konfigurationsdatei gelesen. Die Basisadresse wird vom [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, um den Proxy für den Dienst zu generieren.

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get MSMQ queue name from app settings in configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];

    // Create the transacted MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName);

    // Create a ServiceHost for the StockTickerService type.
    using (ServiceHost serviceHost = new ServiceHost(typeof(StockTickerService)))
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

> [!NOTE]
> Im Warteschlangennamen wird ein Punkt (.) für den lokalen Computer verwendet, und in der Pfadangabe werden umgekehrte Schrägstriche als Trennzeichen verwendet, wenn eine Warteschlange mithilfe von <xref:System.Messaging> erstellt wird. Die Windows Communication Foundation (WCF)-Endpunkt Adresse gibt ein net. MSMQ:-Schema an und verwendet "localhost" für den lokalen Computer und Schrägstriche im Pfad.

Die Zusicherungen und die Dauerhaftigkeit oder Flüchtigkeit von Nachrichten werden ebenfalls in der Konfiguration angegeben.

```xml
<appSettings>
  <!-- use appSetting to configure MSMQ queue name -->
  <add key="queueName" value=".\private$\ServiceModelSamplesVolatile" />
</appSettings>

<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.StockTickerService"
             behaviorConfiguration="CalculatorServiceBehavior">
    ...
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                binding="netMsmqBinding"
                bindingConfiguration="volatileBinding"
                contract="Microsoft.ServiceModel.Samples.IStockTicker" />
    ...
    </service>
  </services>

  <bindings>
    <netMsmqBinding>
      <binding name="volatileBinding"
             durable="false"
           exactlyOnce="false"/>
    </netMsmqBinding>
  </bindings>
  ...
</system.serviceModel>
```

Da im Beispiel Nachrichten in der Warteschlange mithilfe einer nicht transaktionalen Warteschlange gesendet werden, können keine transaktiven Nachrichten an die Warteschlagen gesendet werden.

```csharp
// Create a client.
Random r = new Random(137);

StockTickerClient client = new StockTickerClient();

float price = 43.23F;
for (int i = 0; i < 10; i++)
{
    float increment = 0.01f * (r.Next(10));
    client.StockTick("zzz" + i, price + increment);
}

//Closing the client gracefully cleans up resources.
client.Close();
```

Wenn Sie das Beispiel ausführen, werden die Client- und Dienstaktivitäten sowohl im Dienst- als auch im Clientkonsolenfenster angezeigt. Sie können sehen, wie der Dienst Nachrichten vom Client empfängt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen. Beachten Sie, dass aufgrund der Verwendung einer Warteschlange der Client und der Dienst nicht gleichzeitig ausgeführt werden müssen. Sie können den Client ausführen, ihn schließen und anschließend den Dienst starten, der dann trotzdem noch die Nachrichten des Clients empfängt.

```console
The service is ready.
Press <ENTER> to terminate service.

Stock Tick zzz0:43.25
Stock Tick zzz1:43.23
Stock Tick zzz2:43.28
Stock Tick zzz3:43.3
Stock Tick zzz4:43.23
Stock Tick zzz5:43.25
Stock Tick zzz6:43.25
Stock Tick zzz7:43.24
Stock Tick zzz8:43.32
Stock Tick zzz9:43.3
```

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.

3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).

Standardmäßig wird mit <xref:System.ServiceModel.NetMsmqBinding> die Transportsicherheit aktiviert. Es gibt zwei relevante Eigenschaften für die MSMQ-Transportsicherheit, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> und <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>`.` standardmäßig ist der Authentifizierungsmodus auf `Windows` festgelegt, und die Schutz Ebene ist auf `Sign`festgelegt. Damit MSMQ die Authentifizierungs- und Signierungsfunktion bereitstellt, muss es Teil einer Domäne sein, und die Active Directory-Integrationsoption für MSMQ muss installiert sein. Wenn Sie dieses Beispiel auf einem Computer ausführen, der diese Kriterien nicht erfüllt, tritt ein Fehler auf.

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>So führen Sie das Beispiel auf einem Computer aus, der sich in einer Arbeitsgruppe befindet oder über keine Active Directory-Integration verfügt

1. Wenn Ihr Computer nicht zu einer Domäne gehört oder auf ihm keine Active Directory-Integration installiert ist, deaktivieren Sie die Transportsicherheit, indem Sie den Authentifizierungsmodus und die Schutzebene auf `None` festlegen, wie im folgenden Beispiel für einen Konfigurationscode gezeigt.

    ```xml
    <system.serviceModel>
        <services>
          <service name="Microsoft.ServiceModel.Samples.StockTickerService"
                   behaviorConfiguration="StockTickerServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>

            <!-- Define NetMsmqEndpoint -->
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesVolatile"
                      binding="netMsmqBinding"
                      bindingConfiguration="volatileBinding"
                      contract="Microsoft.ServiceModel.Samples.IStockTicker" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />

          </service>
        </services>

        <bindings>
          <netMsmqBinding>
            <binding name="volatileBinding"
                  durable="false"
                  exactlyOnce="false">
              <security mode="None" />
            </binding>
          </netMsmqBinding>
        </bindings>

        <behaviors>
          <serviceBehaviors>
            <behavior name="StockTickerServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. Ändern Sie die Konfiguration sowohl auf dem Server als auch auf dem Client, bevor Sie das Beispiel ausführen.

    > [!NOTE]
    > Das Festlegen von `security mode` auf `None` entspricht dem Festlegen von <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> und der `Message`-Sicherheit auf `None`.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Volatile`
