---
title: <connectionPoolSettings> von <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 787b50296b7ed4f6fdceef244a99dffffae63c61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919397"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="417f1-102">\<connectionpoolsettings-> \<von TcpTransport ></span><span class="sxs-lookup"><span data-stu-id="417f1-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="417f1-103">Gibt zusätzliche Verbindungspooleinstellungen für einen TCP-Transport an.</span><span class="sxs-lookup"><span data-stu-id="417f1-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="417f1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="417f1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="417f1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="417f1-105">\<bindings></span></span>  
<span data-ttu-id="417f1-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="417f1-106">\<customBinding></span></span>  
<span data-ttu-id="417f1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="417f1-107">\<binding></span></span>  
<span data-ttu-id="417f1-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="417f1-108">\<tcpTransport></span></span>  
<span data-ttu-id="417f1-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="417f1-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="417f1-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="417f1-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="417f1-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="417f1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="417f1-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="417f1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="417f1-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="417f1-113">Attributes</span></span>  
  
|<span data-ttu-id="417f1-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="417f1-114">Attribute</span></span>|<span data-ttu-id="417f1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="417f1-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="417f1-116">Eine Zeichenfolge, die den Namen des Verbindungspools für ausgehende Kanäle definiert.</span><span class="sxs-lookup"><span data-stu-id="417f1-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="417f1-117">Im Streammodus werden keine Verbindungen freigegeben, was bedeutet, dass Verbindungspooling deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="417f1-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="417f1-118">Der Standardwert ist eine "standardmäßige" Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="417f1-118">The default is a "default" string.</span></span> <span data-ttu-id="417f1-119">Sie können diesen Wert ändern, um die Verbindungen für einen bestimmten Client in separate Gruppen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="417f1-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="417f1-120">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, in der sich die Verbindung im Leerlauf befinden kann, bevor sie unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="417f1-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="417f1-121">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="417f1-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="417f1-122">Eine <xref:System.TimeSpan>, die angibt, wann eine aktive Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="417f1-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="417f1-123">Der Standardwert ist 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="417f1-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="417f1-124">Eine Verbindung wird geschlossen, nachdem sie an den Verbindungscache zurückgegeben wurde, und nicht während einer aktiven Übertragung.</span><span class="sxs-lookup"><span data-stu-id="417f1-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="417f1-125">Der vom TCP-Transport verwendete Verbindungscache erstellt die für jeden Endpunkt erforderlichen neuen Verbindungen bis hin zu einem Cachelimit, das von `maxOutboundConnectionsPerEndpoint.` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="417f1-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="417f1-126">Eine positive ganze Zahl, die die maximale Anzahl von Verbindungen zu einem Remoteendpunkt angibt, die vom Dienst initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="417f1-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="417f1-127">Verbindungen oberhalb des Limits werden in eine Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="417f1-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="417f1-128">`idleTimeout` schränkt die Dauer ein, in der Verbindungen in der Warteschlange bleiben können, bevor eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="417f1-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="417f1-129">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="417f1-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="417f1-130">Dieses Attribut beschränkt die Anzahl gleichzeitiger aktiver Verbindungen vom Client zu einem bestimmten Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="417f1-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="417f1-131">Wenn dieser Wert durch zusätzliche aktive Clientverbindungen überstiegen wird, antwortet der Dienst dem Client möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="417f1-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="417f1-132">In diesem Fall sollte dieser Wert angepasst werden, um die maximale Anzahl der erwarteten gleichzeitigen Clientverbindungen in einem bestimmten Endpunkt zu übertreffen.</span><span class="sxs-lookup"><span data-stu-id="417f1-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="417f1-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="417f1-133">Child Elements</span></span>  
 <span data-ttu-id="417f1-134">Keine</span><span class="sxs-lookup"><span data-stu-id="417f1-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="417f1-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="417f1-135">Parent Elements</span></span>  
  
|<span data-ttu-id="417f1-136">Element</span><span class="sxs-lookup"><span data-stu-id="417f1-136">Element</span></span>|<span data-ttu-id="417f1-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="417f1-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="417f1-138">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="417f1-138">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="417f1-139">Definiert einen Transport, der bewirkt, dass ein Kanal Nachrichten mithilfe von benannten Pipes überträgt.</span><span class="sxs-lookup"><span data-stu-id="417f1-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="417f1-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="417f1-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="417f1-141">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="417f1-141">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="417f1-142">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="417f1-142">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="417f1-143">Bindungen</span><span class="sxs-lookup"><span data-stu-id="417f1-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="417f1-144">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="417f1-144">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="417f1-145">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="417f1-145">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="417f1-146">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="417f1-146">\<customBinding></span></span>](custombinding.md)
