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
# <a name="announcements-sample"></a><span data-ttu-id="5cb49-102">Beispiel für Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="5cb49-102">Announcements Sample</span></span>

<span data-ttu-id="5cb49-103">In diesem Beispiel wird die Verwendung der Ankündigungsfunktionalität der Discovery-Funktion erläutert.</span><span class="sxs-lookup"><span data-stu-id="5cb49-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="5cb49-104">Ankündigungen ermöglichen es Diensten, Ankündigungsmeldungen mit Metadaten zum Dienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="5cb49-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="5cb49-105">Standardmäßig wird als Ankündigung "hello" gesendet, wenn der Dienst startet, und "bye", wenn der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5cb49-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="5cb49-106">Diese Ankündigungen können per Multicast oder von Punkt zu Punkt gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="5cb49-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="5cb49-107">Das folgende Beispiel besteht aus zwei Projekten, Service und Client.</span><span class="sxs-lookup"><span data-stu-id="5cb49-107">This sample consists of two projects service and client.</span></span>

## <a name="service"></a><span data-ttu-id="5cb49-108">Dienst</span><span class="sxs-lookup"><span data-stu-id="5cb49-108">Service</span></span>

<span data-ttu-id="5cb49-109">Dieses Projekt enthält einen selbst gehosteten Rechnerdienst.</span><span class="sxs-lookup"><span data-stu-id="5cb49-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="5cb49-110">In der `Main`-Methode wird ein Diensthost erstellt, dem ein Dienstendpunkt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5cb49-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="5cb49-111">Danach wird ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> erstellt.</span><span class="sxs-lookup"><span data-stu-id="5cb49-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="5cb49-112">Um Ankündigungen zu aktivieren, muss dem <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> ein Ankündigungsendpunkt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5cb49-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="5cb49-113">In diesem Fall wird als Ankündigungsendpunkt ein Standardendpunkt mithilfe von UDP-Multicast hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5cb49-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="5cb49-114">Dadurch werden die Ankündigungen über eine bekannte UDP-Adresse übertragen.</span><span class="sxs-lookup"><span data-stu-id="5cb49-114">This broadcasts the announcements over a well-known UDP address.</span></span>

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

## <a name="client"></a><span data-ttu-id="5cb49-115">Client</span><span class="sxs-lookup"><span data-stu-id="5cb49-115">Client</span></span>

<span data-ttu-id="5cb49-116">Beachten Sie in diesem Projekt, dass der Client einen <xref:System.ServiceModel.Discovery.AnnouncementService> hostet.</span><span class="sxs-lookup"><span data-stu-id="5cb49-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="5cb49-117">Darüber hinaus werden zwei Delegaten bei Ereignissen registriert.</span><span class="sxs-lookup"><span data-stu-id="5cb49-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="5cb49-118">Diese Ereignisse geben vor, wie der Client vorgeht, wenn Online- und Offlineankündigungen empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="5cb49-118">These events dictate what the client does when online and offline announcements are received.</span></span>

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

<span data-ttu-id="5cb49-119">Die `OnOnlineEvent`-Methode und die `OnOfflineEvent`-Methode behandeln die entsprechenden Ankündigungen "hello" und "bye".</span><span class="sxs-lookup"><span data-stu-id="5cb49-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>

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

#### <a name="to-use-this-sample"></a><span data-ttu-id="5cb49-120">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="5cb49-120">To use this sample</span></span>

1. <span data-ttu-id="5cb49-121">In diesem Beispiel werden HTTP-Endpunkte verwendet. Zur Ausführung des Beispiels müssen die richtigen URL-ACLs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5cb49-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="5cb49-122">Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="5cb49-122">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="5cb49-123">Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5cb49-123">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="5cb49-124">Es empfiehlt sich, die Domäne und den Benutzernamen durch die folgenden Argumente zu ersetzen, wenn der Befehl nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5cb49-124">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="5cb49-125">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="5cb49-125">Build the solution.</span></span>

3. <span data-ttu-id="5cb49-126">Führen Sie die CLIENT.EXE-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="5cb49-126">Run the client.exe application.</span></span>

4. <span data-ttu-id="5cb49-127">Führen Sie die SERVICE.EXE-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="5cb49-127">Run the service.exe application.</span></span> <span data-ttu-id="5cb49-128">Beachten Sie, dass der Client eine Onlineankündigung empfängt.</span><span class="sxs-lookup"><span data-stu-id="5cb49-128">Note the client receives an online announcement.</span></span>

5. <span data-ttu-id="5cb49-129">Schließen Sie die SERVICE.EXE-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5cb49-129">Close the service.exe application.</span></span> <span data-ttu-id="5cb49-130">Beachten Sie, dass der Client eine Offlineankündigung empfängt.</span><span class="sxs-lookup"><span data-stu-id="5cb49-130">Note the client receives an offline announcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cb49-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5cb49-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5cb49-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5cb49-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5cb49-133">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5cb49-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5cb49-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5cb49-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
