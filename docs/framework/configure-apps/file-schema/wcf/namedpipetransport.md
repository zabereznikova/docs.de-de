---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: bf9229411143345847247f36de07b5c014d3f259
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149599"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="aa436-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="aa436-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="aa436-103">Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="aa436-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="aa436-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aa436-104">\<system.serviceModel></span></span>  
<span data-ttu-id="aa436-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="aa436-105">\<bindings></span></span>  
<span data-ttu-id="aa436-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="aa436-106">\<customBinding></span></span>  
<span data-ttu-id="aa436-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="aa436-107">\<binding></span></span>  
<span data-ttu-id="aa436-108">\<NamePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="aa436-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa436-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa436-109">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa436-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa436-110">Attributes and Elements</span></span>  
<span data-ttu-id="aa436-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa436-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa436-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa436-112">Attributes</span></span>  
<span data-ttu-id="aa436-113">Keine</span><span class="sxs-lookup"><span data-stu-id="aa436-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa436-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa436-114">Child Elements</span></span>  
  
|<span data-ttu-id="aa436-115">Element</span><span class="sxs-lookup"><span data-stu-id="aa436-115">Element</span></span>|<span data-ttu-id="aa436-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa436-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa436-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="aa436-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="aa436-118">Ruft ab oder legt einen <xref:System.TimeSpan> , bestimmt die maximale Zeit, die ein Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="aa436-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="aa436-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="aa436-119">ConnectionBufferSize</span></span>|<span data-ttu-id="aa436-120">Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa436-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="aa436-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="aa436-121">hostNameComparisonMode</span></span>|<span data-ttu-id="aa436-122">Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa436-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="aa436-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="aa436-123">manualAddressing</span></span>|<span data-ttu-id="aa436-124">Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="aa436-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="aa436-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="aa436-125">maxBufferPoolSize</span></span>|<span data-ttu-id="aa436-126">Übernimmt oder bestimmt die maximale Größe in Byte von Pufferpools, die vom Transport verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa436-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="aa436-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="aa436-127">maxBufferSize</span></span>|<span data-ttu-id="aa436-128">Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="aa436-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="aa436-129">Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="aa436-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="aa436-130">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="aa436-130">maxOutputDelay</span></span>|<span data-ttu-id="aa436-131">Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa436-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="aa436-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="aa436-132">maxPendingAccepts</span></span>|<span data-ttu-id="aa436-133">Übernimmt oder bestimmt die maximale Anzahl von Kanälen, die einen Dienst auf einen Listener anbieten kann für die Verarbeitung von eingehenden Verbindungen mit dem Dienst warten.</span><span class="sxs-lookup"><span data-stu-id="aa436-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="aa436-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="aa436-134">maxPendingConnections</span></span>|<span data-ttu-id="aa436-135">Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.</span><span class="sxs-lookup"><span data-stu-id="aa436-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="aa436-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="aa436-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="aa436-137">Ermittelt und definiert die maximale zulässige Nachrichtengröße in Bytes, die empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="aa436-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="aa436-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="aa436-138">transferMode</span></span>|<span data-ttu-id="aa436-139">Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="aa436-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="aa436-140">\<ConnectionPoolSettings > von \<NamedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="aa436-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="aa436-141">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="aa436-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa436-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa436-142">Parent Elements</span></span>  
  
|<span data-ttu-id="aa436-143">Element</span><span class="sxs-lookup"><span data-stu-id="aa436-143">Element</span></span>|<span data-ttu-id="aa436-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa436-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa436-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="aa436-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="aa436-146">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="aa436-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa436-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa436-147">Remarks</span></span>  
<span data-ttu-id="aa436-148">Dieser Transport verwendet URIs im Format "net.pipe://hostname/path".</span><span class="sxs-lookup"><span data-stu-id="aa436-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="aa436-149">Andere URI-Komponenten sind optional.</span><span class="sxs-lookup"><span data-stu-id="aa436-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="aa436-150">Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="aa436-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="aa436-151">Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa436-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa436-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa436-152">See Also</span></span>  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
<span data-ttu-id="aa436-153">[Transporte](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="aa436-153">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="aa436-154">[Auswählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="aa436-154">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="aa436-155">[Bindungen](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="aa436-155">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="aa436-156">[Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="aa436-156">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="aa436-157">[Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="aa436-157">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="aa436-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="aa436-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
