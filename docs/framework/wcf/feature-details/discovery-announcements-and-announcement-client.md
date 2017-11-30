---
title: "Suchankündigungen und Ankündigungsclient"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 426c6437-f8d2-4968-b23a-18afd671aa4b
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 36003933a9fb49fe4fe4f0b677ee584066d415ac
ms.sourcegitcommit: ea1fd4ff4c36169fc722ef263e24884c5cd431a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2017
---
# <a name="discovery-announcements-and-announcement-client"></a>Suchankündigungen und Ankündigungsclient
Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Suchfunktion aktiviert Komponenten, um ihre Verfügbarkeit anzukündigen. Bei entsprechender Konfiguration sendet ein Dienst Hello- und Bye-Ankündigungen. Clients oder andere Komponenten können eine Überwachung auf diese Ankündigungsnachrichten durchführen und dann reagieren. Dies stellt für Clients eine alternative Methode zum Erkennen von Diensten dar. Die Ankündigungsfunktion hat mehrere Verwendungen. Falls die Dienste ein Netzwerk z. B. häufig "betreten" und wieder verlassen, sind Ankündigungen ggf. eine bessere Möglichkeit als das Suchen nach Diensten. Bei diesem Ansatz wird der Netzwerkverkehr reduziert, und der Client ist über das Vorhandensein bzw. das Verlassen des Diensts informiert, sobald er die Ankündigungen empfangen hat.  
  
## <a name="discovery-announcements"></a>Suchankündigungen  
 Wenn ein für Ankündigungen konfigurierter Dienst ein Netzwerk in ein Netzwerk eintritt und erkennbar wird, sendet er eine Hello-Nachricht und kündigt den abhörenden Clients auf diese Weise seine Verfügbarkeit an. Die Nachricht enthält die Suche betreffende Informationen zum Dienst, z. B. Vertrag, Endpunktadresse und zugeordnete Bereiche. Sie können angeben, wohin die Ankündigungsnachricht gesendet wird, indem Sie die <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>-Klasse verwenden. Wenn der Ankündigungsendpunkt ein <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> ist, wird für Hello und Bye entsprechend ein Multicast durchgeführt. Wenn der Ankündigungsendpunkt das Unicast-Format aufweist, werden die Nachrichten direkt an den angegebenen Endpunkt gesendet.  
  
> [!NOTE]
>  Ankündigungen werden gesendet, wenn der Diensthost geöffnet oder geschlossen wird. Falls diese Aufrufe nicht ordnungsgemäß abgeschlossen werden, wird die Ankündigungsnachricht ggf. nicht gesendet. Tritt bei der Ausführung des Diensts z. B. ein Fehler auf, wird die Bye-Ankündigungsnachricht nicht gesendet.  
  
> [!TIP]
>  Sie können die Ankündigungsfunktion so anpassen, dass Sie Ankündigungen jederzeit senden können.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] definiert <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> und <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> als Standardendpunkte, damit Dienste und Clients auf einfache Weise Hello- und Bye-Ankündigungen senden können.  
  
### <a name="announcements-on-the-service"></a>Ankündigungen des Diensts  
 Um den Dienst für das Senden von Ankündigungen zu konfigurieren, fügen Sie ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt mit einem Ankündigungsendpunkt hinzu. Im folgenden Beispiel wird gezeigt, wie Sie dieses Verhalten dem Diensthost programmgesteuert hinzufügen. In diesem Beispiel wird `UdpAnnouncementEndpoint` verwendet. Dies bedeutet, dass die Ankündigungen per Multicast an einen Ort gesendet werden, der von diesem Standardendpunkt angegeben wird.  
  
```  
ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();
serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());
serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
```  
  
 Das Verhalten kann auch in der Konfigurationsdatei konfiguriert werden, wie im folgenden Beispiel gezeigt.  
  
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
  
 In den vorangehenden Beispielen wird ein Dienst so konfiguriert, dass er automatisch Ankündigungsnachrichten sendet. Mit der <xref:System.ServiceModel.Discovery.AnnouncementClient>-Klasse können Sie Ankündigungsnachrichten auch explizit senden.  
  
### <a name="announcements-on-the-client"></a>Ankündigungen auf dem Client  
 Eine Clientanwendung muss einen Ankündigungsdienst hosten, um auf die Hello- und Bye-Nachrichten reagieren und die Ereignisse <xref:System.ServiceModel.Discovery.AnnouncementService.OnlineAnnouncementReceived> und <xref:System.ServiceModel.Discovery.AnnouncementService.OfflineAnnouncementReceived> abonnieren zu können. Das folgende Beispiel zeigt die dazu erforderliche Vorgehensweise.  
  
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
  
 Wenn ein Hello- oder Bye-Nachricht empfangen wird, können Sie auf die Endpunkt-Suchmetadaten über <xref:System.ServiceModel.Discovery.AnnouncementEventArgs> zugreifen. Dies wird im folgenden Beispiel veranschaulicht.  
  
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
