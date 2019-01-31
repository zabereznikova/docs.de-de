---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 76b8a0feaf51b39c9c988d853db7e3bf96244905
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284582"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="fc4fd-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="fc4fd-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="fc4fd-102">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="fc4fd-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fc4fd-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fc4fd-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fc4fd-104">\<bindings></span></span>  
<span data-ttu-id="fc4fd-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fc4fd-105">\<customBinding></span></span>  
<span data-ttu-id="fc4fd-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="fc4fd-106">\<binding></span></span>  
<span data-ttu-id="fc4fd-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="fc4fd-107">\<namePipeTransport></span></span>  
<span data-ttu-id="fc4fd-108">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="fc4fd-108">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4fd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc4fd-109">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc4fd-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc4fd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fc4fd-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc4fd-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc4fd-112">Attributes</span></span>  
  
|<span data-ttu-id="fc4fd-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fc4fd-113">Attribute</span></span>|<span data-ttu-id="fc4fd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc4fd-114">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="fc4fd-115">Eine Zeichenfolge, die den Namen des Verbindungspools für ausgehende Kanäle definiert.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-115">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="fc4fd-116">Im Streammodus werden keine Verbindungen freigegeben, was bedeutet, dass Verbindungspooling deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-116">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="fc4fd-117">Der Standardwert ist eine "standardmäßige" Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-117">The default is a "default" string.</span></span> <span data-ttu-id="fc4fd-118">Sie können diesen Wert ändern, um die Verbindungen für einen bestimmten Client in separate Gruppen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-118">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="fc4fd-119">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, in der sich die Verbindung im Leerlauf befinden kann, bevor sie unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-119">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="fc4fd-120">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-120">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="fc4fd-121">Eine positive ganze Zahl, die die maximale Anzahl von Verbindungen zu einem Remoteendpunkt angibt, die vom Dienst initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="fc4fd-122">Verbindungen oberhalb des Limits werden in eine Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="fc4fd-123">`idleTimeout` schränkt die Dauer ein, in der Verbindungen in der Warteschlange bleiben können, bevor eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="fc4fd-124">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="fc4fd-125">Dieses Attribut beschränkt die Anzahl gleichzeitiger aktiver Verbindungen vom Client zu einem bestimmten Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="fc4fd-126">Wenn dieser Wert durch zusätzliche aktive Clientverbindungen überstiegen wird, antwortet der Dienst dem Client möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="fc4fd-127">In diesem Fall sollte dieser Wert angepasst werden, um die maximale Anzahl der erwarteten gleichzeitigen Clientverbindungen in einem bestimmten Endpunkt zu übertreffen.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc4fd-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc4fd-128">Child Elements</span></span>  
 <span data-ttu-id="fc4fd-129">Keine</span><span class="sxs-lookup"><span data-stu-id="fc4fd-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc4fd-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc4fd-130">Parent Elements</span></span>  
  
|<span data-ttu-id="fc4fd-131">Element</span><span class="sxs-lookup"><span data-stu-id="fc4fd-131">Element</span></span>|<span data-ttu-id="fc4fd-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fc4fd-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc4fd-133">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="fc4fd-133">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="fc4fd-134">Definiert einen Transport, der bewirkt, dass ein Kanal Nachrichten mithilfe von benannten Pipes überträgt.</span><span class="sxs-lookup"><span data-stu-id="fc4fd-134">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc4fd-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc4fd-135">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fc4fd-136">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="fc4fd-136">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="fc4fd-137">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="fc4fd-137">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="fc4fd-138">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc4fd-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fc4fd-139">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc4fd-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fc4fd-140">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fc4fd-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fc4fd-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fc4fd-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
