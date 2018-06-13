---
title: Beispiel für Ankündigungen
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: ee58a2fef970fa3e7936e2fc26a9e7fd31633347
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33500037"
---
# <a name="announcements-sample"></a><span data-ttu-id="29e48-102">Beispiel für Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="29e48-102">Announcements Sample</span></span>
<span data-ttu-id="29e48-103">In diesem Beispiel wird die Verwendung der Ankündigungsfunktionalität der Discovery-Funktion erläutert.</span><span class="sxs-lookup"><span data-stu-id="29e48-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="29e48-104">Ankündigungen ermöglichen es Diensten, Ankündigungsmeldungen mit Metadaten zum Dienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="29e48-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="29e48-105">Standardmäßig wird als Ankündigung "hello" gesendet, wenn der Dienst startet, und "bye", wenn der Dienst beendet wird.</span><span class="sxs-lookup"><span data-stu-id="29e48-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="29e48-106">Diese Ankündigungen können per Multicast oder von Punkt zu Punkt gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="29e48-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="29e48-107">Das folgende Beispiel besteht aus zwei Projekten, Service und Client.</span><span class="sxs-lookup"><span data-stu-id="29e48-107">This sample consists of two projects service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="29e48-108">Dienst</span><span class="sxs-lookup"><span data-stu-id="29e48-108">Service</span></span>  
 <span data-ttu-id="29e48-109">Dieses Projekt enthält einen selbst gehosteten Rechnerdienst.</span><span class="sxs-lookup"><span data-stu-id="29e48-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="29e48-110">In der `Main`-Methode wird ein Diensthost erstellt, dem ein Dienstendpunkt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="29e48-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="29e48-111">Danach wird ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> erstellt.</span><span class="sxs-lookup"><span data-stu-id="29e48-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="29e48-112">Um Ankündigungen zu aktivieren, muss dem <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> ein Ankündigungsendpunkt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="29e48-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="29e48-113">In diesem Fall wird als Ankündigungsendpunkt ein Standardendpunkt mithilfe von UDP-Multicast hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="29e48-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="29e48-114">Dadurch werden die Ankündigungen über eine bekannte UDP-Adresse übertragen.</span><span class="sxs-lookup"><span data-stu-id="29e48-114">This broadcasts the announcements over a well-known UDP address.</span></span>  
  
```  
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
  
## <a name="client"></a><span data-ttu-id="29e48-115">Client</span><span class="sxs-lookup"><span data-stu-id="29e48-115">Client</span></span>  
 <span data-ttu-id="29e48-116">Beachten Sie in diesem Projekt, dass der Client einen <xref:System.ServiceModel.Discovery.AnnouncementService> hostet.</span><span class="sxs-lookup"><span data-stu-id="29e48-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="29e48-117">Darüber hinaus werden zwei Delegaten bei Ereignissen registriert.</span><span class="sxs-lookup"><span data-stu-id="29e48-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="29e48-118">Diese Ereignisse geben vor, wie der Client vorgeht, wenn Online- und Offlineankündigungen empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="29e48-118">These events dictate what the client does when online and offline announcements are received.</span></span>  
  
```  
// Create an AnnouncementService instance  
AnnouncementService announcementService = new AnnouncementService();  
  
// Subscribe the announcement events  
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;  
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;  
```  
  
 <span data-ttu-id="29e48-119">Die `OnOnlineEvent`-Methode und die `OnOfflineEvent`-Methode behandeln die entsprechenden Ankündigungen "hello" und "bye".</span><span class="sxs-lookup"><span data-stu-id="29e48-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>  
  
```  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="29e48-120">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="29e48-120">To use this sample</span></span>  
  
1.  <span data-ttu-id="29e48-121">Dieses Beispiel verwendet die HTTP-Endpunkte und Ausführung dieser Beispiele, die richtige URL-ACLs hinzugefügt werden ausführliche Informationen finden Sie [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) Details.</span><span class="sxs-lookup"><span data-stu-id="29e48-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added see [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="29e48-122">Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="29e48-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="29e48-123">Es empfiehlt sich, die Domäne und den Benutzernamen durch die folgenden Argumente zu ersetzen, wenn der Befehl nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="29e48-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`  
  
2.  <span data-ttu-id="29e48-124">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="29e48-124">Build the solution.</span></span>  
  
3.  <span data-ttu-id="29e48-125">Führen Sie die CLIENT.EXE-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="29e48-125">Run the client.exe application.</span></span>  
  
4.  <span data-ttu-id="29e48-126">Führen Sie die SERVICE.EXE-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="29e48-126">Run the service.exe application.</span></span> <span data-ttu-id="29e48-127">Beachten Sie, dass der Client eine Onlineankündigung empfängt.</span><span class="sxs-lookup"><span data-stu-id="29e48-127">Note the client receives an online announcement.</span></span>  
  
5.  <span data-ttu-id="29e48-128">Schließen Sie die SERVICE.EXE-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="29e48-128">Close the service.exe application.</span></span> <span data-ttu-id="29e48-129">Beachten Sie, dass der Client eine Offlineankündigung empfängt.</span><span class="sxs-lookup"><span data-stu-id="29e48-129">Note the client receives an offline announcement.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="29e48-130">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="29e48-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="29e48-131">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="29e48-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="29e48-132">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="29e48-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="29e48-133">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="29e48-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`  
  
## <a name="see-also"></a><span data-ttu-id="29e48-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29e48-134">See Also</span></span>
