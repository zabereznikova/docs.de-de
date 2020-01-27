---
title: Beispiel für Ankündigungen
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: c3824fb0dc7ab4169c309d1a5154127d6bc3b78f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746996"
---
# <a name="announcements-sample"></a>Beispiel für Ankündigungen

In diesem Beispiel wird die Verwendung der Ankündigungsfunktionalität der Discovery-Funktion erläutert. Ankündigungen ermöglichen es Diensten, Ankündigungsmeldungen mit Metadaten zum Dienst zu senden. Standardmäßig wird als Ankündigung "hello" gesendet, wenn der Dienst startet, und "bye", wenn der Dienst beendet wird. Diese Ankündigungen können per Multicast oder von Punkt zu Punkt gesendet werden. Das folgende Beispiel besteht aus zwei Projekten, Service und Client.

## <a name="service"></a>Dienst

Dieses Projekt enthält einen selbst gehosteten Rechnerdienst. In der `Main`-Methode wird ein Diensthost erstellt, dem ein Dienstendpunkt hinzugefügt wird. Danach wird ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> erstellt. Um Ankündigungen zu aktivieren, muss dem <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> ein Ankündigungsendpunkt hinzugefügt werden. In diesem Fall wird als Ankündigungsendpunkt ein Standardendpunkt mithilfe von UDP-Multicast hinzugefügt. Dadurch werden die Ankündigungen über eine bekannte UDP-Adresse übertragen.

```csharp
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);

     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();

     // Announce the availability of the service over UDP multicast
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());

    // Make the service discoverable over UDP multicast.
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());
    serviceHost.Open();
    // ...
}
```

## <a name="client"></a>Client

Beachten Sie in diesem Projekt, dass der Client einen <xref:System.ServiceModel.Discovery.AnnouncementService> hostet. Darüber hinaus werden zwei Delegaten bei Ereignissen registriert. Diese Ereignisse geben vor, wie der Client vorgeht, wenn Online- und Offlineankündigungen empfangen werden.

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

Die `OnOnlineEvent`-Methode und die `OnOfflineEvent`-Methode behandeln die entsprechenden Ankündigungen "hello" und "bye".

```csharp
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}
```

#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel

1. In diesem Beispiel werden HTTP-Endpunkte verwendet. Zur Ausführung des Beispiels müssen die richtigen URL-ACLs hinzugefügt werden. Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](../feature-details/configuring-http-and-https.md). Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt. Es empfiehlt sich, die Domäne und den Benutzernamen durch die folgenden Argumente zu ersetzen, wenn der Befehl nicht funktioniert. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. Erstellen Sie die Projektmappe.

3. Führen Sie die CLIENT.EXE-Anwendung aus.

4. Führen Sie die SERVICE.EXE-Anwendung aus. Beachten Sie, dass der Client eine Onlineankündigung empfängt.

5. Schließen Sie die SERVICE.EXE-Anwendung. Beachten Sie, dass der Client eine Offlineankündigung empfängt.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
