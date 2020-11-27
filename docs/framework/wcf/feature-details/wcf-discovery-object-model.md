---
title: Objektmodell der WCF-Suche
ms.date: 03/30/2017
ms.assetid: 8365a152-eacd-4779-9130-bbc48fa5c5d9
ms.openlocfilehash: 06984766fa8199a18197255c57492863a888e3aa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281936"
---
# <a name="wcf-discovery-object-model"></a>Objektmodell der WCF-Suche

Die WCF-Suche besteht aus einem Satz von Typen, die zusammen ein einheitliches Programmiermodell bereitstellen. Damit können Sie Dienste schreiben, die zur Laufzeit erkennbar sind, sowie Clients, die nach diesen Diensten suchen und diese verwenden.  
  
## <a name="making-a-service-discoverable-and-finding-services"></a>Erkennbarmachen eines Diensts und Suchen nach Diensten  

 Um einen WCF-Dienst erkennbar zu machen, fügen Sie dem <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt des Diensthosts ein <xref:System.ServiceModel.Description.ServiceDescription> sowie einen Suchendpunkt hinzu. Wenn ein Dienst so konfiguriert wird, dass er Ankündigungsnachrichten sendet (durch das Hinzufügen eines <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>-Objekts), wird die Ankündigung jeweils gesendet, wenn der Diensthost geöffnet oder geschlossen wird.  
  
 Ein Client, der eine Überwachung auf Ankündigungsnachrichten von Diensten durchführt, hostet einen Ankündigungsdienst und fügt einen oder mehrere Ankündigungsendpunkte hinzu. Der Ankündigungsdienst empfängt Ankündigungsnachrichten und löst Ankündigungsereignisse aus.  
  
 Ein Client verwendet die <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse, um nach verfügbaren Diensten zu suchen. Die Clientanwendung instanziiert die <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse, indem sie einen Suchendpunkt übergibt. Dieser Suchendpunkt gibt an, wohin die Suchnachrichten gesendet werden sollen. Der Client ruft die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode auf, die eine `Probe`-Anforderung sendet. Dienste, die eine Überwachung auf Suchnachrichten durchführen, empfangen diese `Probe`-Anforderung. Falls der Dienst die unter `Probe` angegebenen Kriterien erfüllt, sendet er eine `ProbeMatch`-Nachricht zurück an den Client.  
  
## <a name="object-model"></a>Objektmodell  

 Die API der WCF-Suche definiert die folgenden Klassen:  
  
- <xref:System.ServiceModel.Discovery.AnnouncementClient>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.AnnouncementService>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryClient>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryMessageSequenceGenerator>  
  
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryProxy>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryService>  
  
- <xref:System.ServiceModel.Discovery.DiscoveryVersion>  
  
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
  
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>  
  
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>  
  
- <xref:System.ServiceModel.Discovery.FindCriteria>  
  
- <xref:System.ServiceModel.Discovery.FindRequestContext>  
  
- <xref:System.ServiceModel.Discovery.FindResponse>  
  
- <xref:System.ServiceModel.Discovery.ResolveCriteria>  
  
- <xref:System.ServiceModel.Discovery.ResolveResponse>  
  
- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>  

- <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>  
  
- <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>  
  
## <a name="announcementclient"></a>AnnouncementClient  

 Die <xref:System.ServiceModel.Discovery.AnnouncementClient>-Klasse stellt synchrone und asynchrone Methoden zum Senden von Ankündigungsnachrichten bereit. Es gibt zwei Typen von Ankündigungsnachrichten: "Hello" und "Bye". Eine Hello-Nachricht wird gesendet, um anzugeben, dass ein Dienst verfügbar geworden ist, und eine Bye-Nachricht wird gesendet, um anzugeben, dass ein vorhandener Dienst nicht mehr verfügbar ist. Der Entwickler erstellt eine <xref:System.ServiceModel.Discovery.AnnouncementClient>-Instanz und übergibt eine Instanz von <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> als Konstruktorparameter.  
  
## <a name="announcementendpoint"></a>AnnouncementEndpoint  

 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint> stellt einen Standardendpunkt mit einem festen Ankündigungsvertrag dar. Dieser wird von einem Dienst oder Client zum Senden und Empfangen von Ankündigungsnachrichten verwendet. Standardmäßig ist für die <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>-Klasse festgelegt, dass sie die Protokollversion "WS_Discovery 11" verwendet.  
  
## <a name="announcementservice"></a>AnnouncementService  

 <xref:System.ServiceModel.Discovery.AnnouncementService> ist eine vom System bereitgestellte Implementierung eines Ankündigungsdiensts, der Ankündigungsnachrichten empfängt und verarbeitet. Wenn eine Hello- oder Bye-Nachricht empfangen wird, ruft die <xref:System.ServiceModel.Discovery.AnnouncementService>-Instanz die entsprechende virtuelle <xref:System.ServiceModel.Discovery.AnnouncementService.OnBeginOnlineAnnouncement%2A>- oder <xref:System.ServiceModel.Discovery.AnnouncementService.OnBeginOfflineAnnouncement%2A>-Methode auf, die Ankündigungsereignisse auslös.  
  
## <a name="discoveryclient"></a>DiscoveryClient  

 Die <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse wird von einer Clientanwendung verwendet, um verfügbare Dienste zu suchen und aufzulösen. Sie stellt synchrone und asynchrone Methoden zum Suchen nach und zum Auflösen von Diensten bereit, die auf dem angegebenen <xref:System.ServiceModel.Discovery.FindCriteria>-Objekt oder <xref:System.ServiceModel.Discovery.ResolveCriteria>-Objekt basieren. Der Entwickler erstellt eine <xref:System.ServiceModel.Discovery.DiscoveryClient>-Instanz und stellt eine Instanz von <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> als Konstruktorparameter bereit.  
  
 Zum Suchen nach einem Dienst ruft der Entwickler die synchrone oder asynchrone `Find`-Methode auf, die eine <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz mit den zu verwendenden Suchkriterien bereitstellt. Das <xref:System.ServiceModel.Discovery.DiscoveryClient>-Objekt erstellt eine `Probe`-Nachricht mit den entsprechenden Headern und sendet die Suchanforderung. Da es gleichzeitig mehr als eine ausstehende `Find`-Anforderung geben kann, korreliert der Client die empfangenen Antworten und überprüft jeweils die Antwort. Anschließend werden die Ergebnisse mithilfe von `Find` an den Aufrufer des <xref:System.ServiceModel.Discovery.FindResponse>-Vorgangs übermittelt.  
  
 Um einen bekannten Dienst aufzulösen, ruft der Entwickler die synchrone oder asynchrone `Resolve`-Methode auf, die eine Instanz von <xref:System.ServiceModel.Discovery.ResolveCriteria> bereitstellt, die wiederum das <xref:System.ServiceModel.EndpointAddress>-Objekt des bekannten Diensts enthält. Das <xref:System.ServiceModel.Discovery.DiscoveryClient>-Objekt erstellt eine `Resolve`-Nachricht mit den entsprechenden Headern und sendet die Auflösungsanforderung. Die empfangene Antwort wird mit den ausstehenden Auflösungsanforderungen korreliert, und das Ergebnis wird mithilfe von `Resolve` an den Aufrufer des <xref:System.ServiceModel.Discovery.ResolveResponse>-Vorgangs übermittelt.  
  
 Wenn im Netzwerk ein Suchproxy vorhanden ist und der <xref:System.ServiceModel.Discovery.DiscoveryClient> die Suchanforderung im Multicastformat sendet, kann der Suchproxy per Multicastunterdrückung mit Hello-Nachricht antworten. Der <xref:System.ServiceModel.Discovery.DiscoveryClient> löst das `ProxyAvailable`-Ereignis aus, wenn er Hello-Nachrichten als Antwort auf ausstehende `Find`- oder `Resolve`-Anforderungen empfängt. Das `ProxyAvailable`-Ereignis enthält die <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> zum Suchproxy. Der Entwickler kann entscheiden, ob er diese Informationen zum Wechseln vom Ad-hoc-Modus in den Modus "Verwaltet" verwendet.  
  
## <a name="discoveryendpoint"></a>DiscoveryEndpoint  

 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> stellt einen Standardendpunkt mit einem festen Suchvertrag dar. Er wird von einem Dienst oder einem Client verwendet, um Suchnachrichten zu senden oder zu empfangen. Standardmäßig wird <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> festgelegt, um den <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode.Managed?displayProperty=nameWithType>-Modus und die Version "WSDiscovery11" der WS-Suche zu verwenden.  
  
## <a name="discoverymessagesequencegenerator"></a>DiscoveryMessageSequenceGenerator  

 <xref:System.ServiceModel.Discovery.DiscoveryMessageSequenceGenerator> wird verwendet, um ein <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence>-Objekt zu generieren, wenn der Dienst Such- oder Ankündigungsnachrichten sendet.  
  
## <a name="discoveryservice"></a>DiscoveryService  

 Die abstrakte <xref:System.ServiceModel.Discovery.DiscoveryService>-Klasse stellt ein Framework zum Empfangen und Verarbeiten von `Probe`- und `Resolve`-Nachrichten bereit. Wenn eine `Probe`-Nachricht empfangen wird, erstellt <xref:System.ServiceModel.Discovery.DiscoveryService> basierend auf der eingehenden Meldung eine Instanz von <xref:System.ServiceModel.Discovery.FindRequestContext> und ruft die virtuelle <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginFind%2A>-Methode auf. Wenn eine `Resolve`-Nachricht empfangen wird, ruft <xref:System.ServiceModel.Discovery.DiscoveryService> die virtuelle <xref:System.ServiceModel.Discovery.DiscoveryService.OnBeginResolve%2A>-Methode auf. Sie können von dieser Klasse erben, um eine benutzerdefinierte Suchdienstimplementierung bereitzustellen.  
  
## <a name="discoveryproxy"></a>DiscoveryProxy  

 Die abstrakte <xref:System.ServiceModel.Discovery.DiscoveryProxy>-Klasse stellt ein Framework zum Empfangen und Verarbeiten von Suche- und Ankündigungsnachrichten bereit. Sie erben von dieser Klasse, wenn Sie einen benutzerdefinierten Suchproxy implementieren. Wenn eine `Probe`-Nachricht per Multicast empfangen wird, ruft die <xref:System.ServiceModel.Discovery.DiscoveryProxy>-Klasse die virtuelle `BeginShouldRedirectFind`-Methode auf, um zu ermitteln, ob eine Multicastunterdrückungsnachricht gesendet werden soll. Wenn sich der Entwickler gegen das Senden einer Multicastunterdrückungsnachricht entscheidet oder wenn die `Probe`-Nachricht per Unicast empfangen wurde, wird basierend auf der eingehenden Nachricht eine Instanz der <xref:System.ServiceModel.Discovery.FindRequestContext>-Klasse erstellt und die virtuelle `OnBeginFind`-Methode aufgerufen. Wenn eine `Resolve`-Nachricht per Multicast empfangen wird, ruft die <xref:System.ServiceModel.Discovery.DiscoveryProxy>-Klasse die virtuelle `ShouldRedirectResolve`-Methode auf, um zu ermitteln, ob eine Multicastunterdrückungsnachricht gesendet werden soll. Wenn sich der Entwickler gegen das Senden einer Multicastunterdrückungsnachricht entscheidet oder wenn die `Resolve`-Nachricht per Unicast empfangen wurde, wird basierend auf der eingehenden Nachricht eine Instanz der <xref:System.ServiceModel.Discovery.ResolveCriteria>-Klasse erstellt und die virtuelle `OnBeginResolve`-Methode aufgerufen. Wenn eine Hello- oder Bye-Nachricht empfangen wird, ruft <xref:System.ServiceModel.Discovery.DiscoveryProxy> die entsprechende virtuelle Methode (`OnBeginOnlineAnnouncement` oder `OnBeingOfflineAnnouncement`) auf, die Ankündigungsereignisse auslöst.  
  
## <a name="discoveryversion"></a>DiscoveryVersion  

 Die <xref:System.ServiceModel.Discovery.DiscoveryVersion>-Klasse stellt die zu verwendende Suchprotokollversion dar.  
  
## <a name="endpointdiscoverybehavior"></a>EndpointDiscoveryBehavior  

 Die <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>-Klasse wird verwendet, um die Ermittelbarkeit eines Endpunkts zu steuern und um die Erweiterungen, zusätzliche Vertragstypnamen und die dem Endpunkt zugeordneten Bereiche anzugeben. Dieses Verhalten wird einem Anwendungsendpunkt hinzugefügt, um seine <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> zu konfigurieren. Wenn das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> dem Diensthost hinzugefügt wird, werden alle vom Diensthost gehosteten Anwendungsendpunkte standardmäßig erkennbar. Der Entwickler kann die Suche für einen bestimmten Endpunkt deaktivieren, indem er die <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior.Enabled%2A>-Eigenschaft auf `false` festlegt.  
  
## <a name="endpointdiscoverymetadata"></a>EndpointDiscoveryMetadata  

 Die <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>-Klasse stellt eine versionsunabhängige Darstellung eines Endpunkts bereit, der vom Dienst veröffentlicht wurde. Sie enthält Endpunktadressen, Abhör-URIs, Vertragstypnamen, Bereiche, Metadatenversion und Erweiterungen, die vom Dienstentwickler angegeben wurden. Das vom Client während eines <xref:System.ServiceModel.Discovery.FindCriteria>-Vorgangs gesendete `Probe`-Objekt wid mit dem <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>-Objekt verglichen. Wenn die Kriterien übereinstimmen, wird das <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>-Objekt an den Client zurückgegeben. Die Endpunktadresse in <xref:System.ServiceModel.Discovery.ResolveCriteria> wird mit der Endpunktadresse von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> verglichen. Wenn die Kriterien übereinstimmen, wird das <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>-Objekt an den Client zurückgegeben.  
  
## <a name="findcriteria"></a>FindCriteria  

 Die <xref:System.ServiceModel.Discovery.FindCriteria>-Klasse ist eine versionsunabhängige Klasse, mit der die Kriterien angegeben werden, die beim Suchen nach einem Dienst verwendet werden. Sie bietet eine vollständige Unterstützung der von der WS-Suche definierten Kriterien zum Vergleichen von Diensten. Außerdem verfügt sie über Erweiterungen, mit denen Entwickler benutzerdefinierte Werte angeben können, die während des Prozesses zur Ermittlung von Übereinstimmungen verwendet werden. Der Entwickler kann die Beendigungskriterien für den `Find`-Vorgang bereitstellen, indem er <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> angibt. Damit wird die Gesamtzahl der Dienste angegeben, nach denen der Entwickler sucht, oder <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>. Dies ist der Wert ist, der angibt, wie lange der Client auf Antworten wartet.  
  
## <a name="findrequestcontext"></a>FindRequestContext  

 Die <xref:System.ServiceModel.Discovery.FindRequestContext>-Klasse wird vom Suchdienst basierend auf der `Probe`-Nachricht instanziiert, die diese empfängt, wenn ein Client einen `Find`-Vorgang initiiert. Sie enthält eine Instanz des <xref:System.ServiceModel.Discovery.FindCriteria>-Objekts, das vom Client angegeben wurde.  
  
## <a name="findresponse"></a>FindResponse  

 Die <xref:System.ServiceModel.Discovery.FindResponse>-Klasse wird an den Aufrufer von <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> mit den Antworten des `Find`-Vorgangs zurückgegeben. Sie ist auch in <xref:System.ServiceModel.Discovery.FindCompletedEventArgs> enthalten. Darin ist eine Auflistung von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, wobei es sich um die Auflistung ermittelter Endpunkte und ein Wörterbuch für <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> und <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence> handelt.  
  
## <a name="resolvecriteria"></a>ResolveCriteria  

 Die <xref:System.ServiceModel.Discovery.ResolveCriteria>-Klasse ist eine versionsunabhängige Klasse, mit der die Kriterien angegeben werden, die beim Auflösen eines bereits bekannten Diensts verwendet werden. Sie enthält die Endpunktadresse des bekannten Diensts. Der Entwickler kann die Beendigungskriterien für den Auflösungsvorgang bereitstellen, indem er die <xref:System.ServiceModel.Discovery.ResolveCriteria.Duration%2A>-Eigenschaft angibt. Diese Eigenschaft legt fest, wie lange der Client auf Antworten wartet.  
  
## <a name="resolveresponse"></a>ResolveResponse  

 Das <xref:System.ServiceModel.Discovery.ResolveResponse>-Objekt wird mit der Antwort des <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A>-Vorgangs an den Aufrufer der `Resolve`-Methode zurückgegeben. Sie ist auch in <xref:System.ServiceModel.Discovery.ResolveCompletedEventArgs> enthalten. Darin ist eine Instanz von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> enthalten, wobei es sich um die ermittelten Endpunkte und eine Instanz von <xref:System.ServiceModel.Discovery.DiscoveryMessageSequence> handelt.  
  
## <a name="servicediscoverybehavior"></a>ServiceDiscoveryBehavior  

 Mithilfe der <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Klasse kann der Entwickler der Suchfunktion einen Dienst hinzufügen. Sie fügen dieses Verhalten dem <xref:System.ServiceModel.ServiceHost>-Objekt hinzu. Die <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Klasse durchläuft die Anwendungsendpunkte, die dem Diensthost hinzugefügt wurden, und erstellt aus den erkennbaren Endpunkten eine Auflistung von <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>. Alle Endpunkte sind standardmäßig erkennbar. Sie können die Erkennbarkeit eines bestimmten Endpunkts steuern, indem Sie dem jeweiligen Endpunkt <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> hinzufügen. Falls <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> Ankündigungsendpunkte hinzugefügt werden, wird die Ankündigung aller erkennbaren Endpunkte jeweils über jeden einzelnen Ankündigungsendpunkt gesendet, wenn der Diensthost geöffnet oder geschlossen wird.  
  
## <a name="udpannouncementendpoint"></a>UdpAnnouncementEndpoint  

 Die <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint>-Klasse ist ein standardmäßiger Ankündigungsendpunkt, der für die Ankündigung über eine UDP-Multicastbindung vorkonfiguriert ist. Standardmäßig ist <xref:System.ServiceModel.Discovery.UdpAnnouncementEndpoint> auf die Verwendung der WS_Discovery-Version "WSApril2005" festgelegt.  
  
## <a name="udpdiscoveryendpoint"></a>UdpDiscoveryEndpoint  

 Die <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>-Klasse ist ein Standardsuchendpunkt, der für die Suche über eine UDP-Multicastbindung vorkonfiguriert ist. Standardmäßig wird <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> so festgelegt, dass die Version "WSDiscovery11" der WS-Suche und der <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode.Adhoc?displayProperty=nameWithType>-Modus verwendet wird.
