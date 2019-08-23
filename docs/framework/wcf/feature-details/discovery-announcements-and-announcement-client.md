---
title: Suchankündigungen und Ankündigungsclient
ms.date: 03/30/2017
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
ms.openlocfilehash: 74362343dc1fd5df6d1b91537f7fed5bc08f8fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968819"
---
# <a name="discovery-announcements-and-announcement-client"></a><span data-ttu-id="e1971-102">Suchankündigungen und Ankündigungsclient</span><span class="sxs-lookup"><span data-stu-id="e1971-102">Discovery Announcements and Announcement Client</span></span>
<span data-ttu-id="e1971-103">Mit der WCF-Ermittlungsfunktion können Komponenten ihre Verfügbarkeit ankündigen.</span><span class="sxs-lookup"><span data-stu-id="e1971-103">The WCF discovery feature enables components to announce their availability.</span></span> <span data-ttu-id="e1971-104">Bei entsprechender Konfiguration sendet ein Dienst Hello- und Bye-Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="e1971-104">If configured to do so, a service sends Hello and Bye announcements.</span></span> <span data-ttu-id="e1971-105">Clients oder andere Komponenten können eine Überwachung auf diese Ankündigungsnachrichten durchführen und dann reagieren.</span><span class="sxs-lookup"><span data-stu-id="e1971-105">Clients or other components can listen for such announcement messages and act on them.</span></span> <span data-ttu-id="e1971-106">Dies stellt für Clients eine alternative Methode zum Erkennen von Diensten dar.</span><span class="sxs-lookup"><span data-stu-id="e1971-106">This provides an alternative method for clients to be aware of services.</span></span> <span data-ttu-id="e1971-107">Die Ankündigungsfunktion hat mehrere Verwendungen. Falls die Dienste ein Netzwerk z. B. häufig "betreten" und wieder verlassen, sind Ankündigungen ggf. eine bessere Möglichkeit als das Suchen nach Diensten.</span><span class="sxs-lookup"><span data-stu-id="e1971-107">Announcement functionality has several uses, for example, if the services enter and leave a network frequently, announcements may be a better alternative than searching for services.</span></span> <span data-ttu-id="e1971-108">Bei diesem Ansatz wird der Netzwerkverkehr reduziert, und der Client ist über das Vorhandensein bzw. das Verlassen des Diensts informiert, sobald er die Ankündigungen empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="e1971-108">With this approach, the network traffic is reduced and the client can learn about the presence or departure of the service as soon as announcements are received.</span></span>  
  
## <a name="discovery-announcements"></a><span data-ttu-id="e1971-109">Suchankündigungen</span><span class="sxs-lookup"><span data-stu-id="e1971-109">Discovery Announcements</span></span>  
 <span data-ttu-id="e1971-110">Wenn ein für Ankündigungen konfigurierter Dienst ein Netzwerk in ein Netzwerk eintritt und erkennbar wird, sendet er eine Hello-Nachricht und kündigt den abhörenden Clients auf diese Weise seine Verfügbarkeit an.</span><span class="sxs-lookup"><span data-stu-id="e1971-110">When a service configured for announcements joins a network and becomes discoverable, it sends a Hello message announcing its availability to listening clients.</span></span> <span data-ttu-id="e1971-111">Die Nachricht enthält die Suche betreffende Informationen zum Dienst, z. B. Vertrag, Endpunktadresse und zugeordnete Bereiche.</span><span class="sxs-lookup"><span data-stu-id="e1971-111">The message contains discovery related information about the service, such as its contract, endpoint address and associated scopes.</span></span> <span data-ttu-id="e1971-112">Sie können angeben, wohin die Ankündigungsnachricht gesendet wird, indem Sie die <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1971-112">You can specify where the announcement message is sent with the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> class.</span></span> <span data-ttu-id="e1971-113">Wenn der Ankündigungsendpunkt ein <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> ist, wird für Hello und Bye entsprechend ein Multicast durchgeführt. Wenn der Ankündigungsendpunkt das Unicast-Format aufweist, werden die Nachrichten direkt an den angegebenen Endpunkt gesendet.</span><span class="sxs-lookup"><span data-stu-id="e1971-113">If the announcement endpoint is a <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> then the Hello and Bye are multicast appropriately, or if the announcement endpoint is unicast, the messages are sent directly to the specified endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1971-114">Ankündigungen werden gesendet, wenn der Diensthost geöffnet oder geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="e1971-114">Announcements are sent when the service host opens and closes.</span></span> <span data-ttu-id="e1971-115">Falls diese Aufrufe nicht ordnungsgemäß abgeschlossen werden, wird die Ankündigungsnachricht ggf. nicht gesendet. Tritt bei der Ausführung des Diensts z. B. ein Fehler auf, wird die Bye-Ankündigungsnachricht nicht gesendet.</span><span class="sxs-lookup"><span data-stu-id="e1971-115">If these calls do not finish properly the announcement message may not be sent out. For example if the service faults, then the Bye announcement message is not sent.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="e1971-116">Sie können die Ankündigungsfunktion so anpassen, dass Sie Ankündigungen jederzeit senden können.</span><span class="sxs-lookup"><span data-stu-id="e1971-116">You can customize the announcement functionality, allowing you to send announcements whenever you choose.</span></span>  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="e1971-117">definiert <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> und <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> als Standardendpunkte, damit Dienste und Clients auf einfache Weise Hello- und Bye-Ankündigungen senden können.</span><span class="sxs-lookup"><span data-stu-id="e1971-117">defines the <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> and <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> as standard endpoints to allow services and clients to easily send Hello and Bye announcements.</span></span>  
  
### <a name="announcements-on-the-service"></a><span data-ttu-id="e1971-118">Ankündigungen des Diensts</span><span class="sxs-lookup"><span data-stu-id="e1971-118">Announcements on the Service</span></span>  
 <span data-ttu-id="e1971-119">Um den Dienst für das Senden von Ankündigungen zu konfigurieren, fügen Sie ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt mit einem Ankündigungsendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1971-119">To configure the service to send announcements, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> with an announcement endpoint.</span></span> <span data-ttu-id="e1971-120">Im folgenden Beispiel wird gezeigt, wie Sie dieses Verhalten dem Diensthost programmgesteuert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1971-120">The following example shows how to programmatically add this behavior to the service host.</span></span> <span data-ttu-id="e1971-121">In diesem Beispiel wird `UdpAnnouncementEndpoint` verwendet. Dies bedeutet, dass die Ankündigungen per Multicast an einen Ort gesendet werden, der von diesem Standardendpunkt angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e1971-121">This example uses the `UdpAnnouncementEndpoint`, which implies that the announcements are multicast to a location specified by that standard endpoint.</span></span>  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 <span data-ttu-id="e1971-122">Das Verhalten kann auch in der Konfigurationsdatei konfiguriert werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1971-122">The behavior can be configured in the configuration file as well, as shown in the following example.</span></span>  
  
```xml  
<services>
  <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">
    <!--Add Discovery Endpoint-->
    <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorBehavior">
      <!--Add Discovery behavior-->
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
 <span data-ttu-id="e1971-123">In den vorangehenden Beispielen wird ein Dienst so konfiguriert, dass er automatisch Ankündigungsnachrichten sendet.</span><span class="sxs-lookup"><span data-stu-id="e1971-123">The preceding examples configure a service to automatically send announcement messages.</span></span> <span data-ttu-id="e1971-124">Mit der <xref:System.ServiceModel.Discovery.AnnouncementClient>-Klasse können Sie Ankündigungsnachrichten auch explizit senden.</span><span class="sxs-lookup"><span data-stu-id="e1971-124">You can also send announcement messages explicitly by using the <xref:System.ServiceModel.Discovery.AnnouncementClient> class.</span></span>  
  
### <a name="announcements-on-the-client"></a><span data-ttu-id="e1971-125">Ankündigungen auf dem Client</span><span class="sxs-lookup"><span data-stu-id="e1971-125">Announcements on the Client</span></span>  
 <span data-ttu-id="e1971-126">Eine Clientanwendung muss einen Ankündigungsdienst hosten, um auf die Hello- und Bye-Nachrichten reagieren und die Ereignisse <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> und <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> abonnieren zu können.</span><span class="sxs-lookup"><span data-stu-id="e1971-126">A client application must host an announcement service to respond to the Hello and Bye messages and subscribe to the <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> and <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> events.</span></span> <span data-ttu-id="e1971-127">Das folgende Beispiel zeigt die dazu erforderliche Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="e1971-127">The following example shows how to do this.</span></span>  
  
```  
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();
  
// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
  
// Create ServiceHost for the AnnouncementService
using (ServiceHost announcementServiceHost = new ServiceHost(announcementService))
{  
    // Listen for the announcements sent over UDP multicast
    announcementServiceHost.AddServiceEndpoint(new UdpAnnouncementEndpoint());
    announcementServiceHost.Open();
  
    Console.WriteLine("Press <ENTER> to terminate.");
    Console.ReadLine();
}  
```  
  
 <span data-ttu-id="e1971-128">Wenn ein Hello- oder Bye-Nachricht empfangen wird, können Sie auf die Endpunkt-Suchmetadaten über <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> zugreifen. Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e1971-128">When a Hello or Bye message is received, you can access the endpoint discovery metadata through <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> as shown in the following example.</span></span>  
  
```  
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an online announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine("Received an offline announcement from {0}", 
e.EndpointDiscoveryMetadata.Address);
}
```
