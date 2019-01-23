---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: cdb2863ff376a92f7c4b679f4812b895ac3f2234
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518838"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="866bf-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="866bf-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="866bf-103">Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="866bf-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="866bf-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="866bf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="866bf-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="866bf-105">\<bindings></span></span>  
<span data-ttu-id="866bf-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="866bf-106">\<customBinding></span></span>  
<span data-ttu-id="866bf-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="866bf-107">\<binding></span></span>  
<span data-ttu-id="866bf-108">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="866bf-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="866bf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="866bf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="866bf-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="866bf-110">Attributes and Elements</span></span>  
<span data-ttu-id="866bf-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="866bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="866bf-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="866bf-112">Attributes</span></span>  
<span data-ttu-id="866bf-113">Keine</span><span class="sxs-lookup"><span data-stu-id="866bf-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="866bf-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="866bf-114">Child Elements</span></span>  
  
|<span data-ttu-id="866bf-115">Element</span><span class="sxs-lookup"><span data-stu-id="866bf-115">Element</span></span>|<span data-ttu-id="866bf-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="866bf-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="866bf-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="866bf-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="866bf-118">Ruft ab oder legt einen <xref:System.TimeSpan> , bestimmt die maximale Zeit, die ein Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="866bf-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="866bf-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="866bf-119">ConnectionBufferSize</span></span>|<span data-ttu-id="866bf-120">Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="866bf-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="866bf-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="866bf-121">hostNameComparisonMode</span></span>|<span data-ttu-id="866bf-122">Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="866bf-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="866bf-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="866bf-123">manualAddressing</span></span>|<span data-ttu-id="866bf-124">Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="866bf-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="866bf-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="866bf-125">maxBufferPoolSize</span></span>|<span data-ttu-id="866bf-126">Übernimmt oder bestimmt die maximale Größe in Byte von Pufferpools, die vom Transport verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="866bf-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="866bf-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="866bf-127">maxBufferSize</span></span>|<span data-ttu-id="866bf-128">Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="866bf-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="866bf-129">Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="866bf-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="866bf-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="866bf-130">maxOutputDelay</span></span>|<span data-ttu-id="866bf-131">Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="866bf-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="866bf-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="866bf-132">maxPendingAccepts</span></span>|<span data-ttu-id="866bf-133">Übernimmt oder bestimmt die maximale Anzahl von Kanälen, die einen Dienst auf einen Listener anbieten kann für die Verarbeitung von eingehenden Verbindungen mit dem Dienst warten.</span><span class="sxs-lookup"><span data-stu-id="866bf-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="866bf-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="866bf-134">maxPendingConnections</span></span>|<span data-ttu-id="866bf-135">Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.</span><span class="sxs-lookup"><span data-stu-id="866bf-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="866bf-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="866bf-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="866bf-137">Ermittelt und definiert die maximale zulässige Nachrichtengröße in Bytes, die empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="866bf-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="866bf-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="866bf-138">transferMode</span></span>|<span data-ttu-id="866bf-139">Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="866bf-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="866bf-140">\<ConnectionPoolSettings > von \<NamedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="866bf-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="866bf-141">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="866bf-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="866bf-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="866bf-142">Parent Elements</span></span>  
  
|<span data-ttu-id="866bf-143">Element</span><span class="sxs-lookup"><span data-stu-id="866bf-143">Element</span></span>|<span data-ttu-id="866bf-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="866bf-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="866bf-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="866bf-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="866bf-146">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="866bf-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="866bf-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="866bf-147">Remarks</span></span>  
<span data-ttu-id="866bf-148">Dieser Transport verwendet URIs im Format "net.pipe://hostname/path".</span><span class="sxs-lookup"><span data-stu-id="866bf-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="866bf-149">Andere URI-Komponenten sind optional.</span><span class="sxs-lookup"><span data-stu-id="866bf-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="866bf-150">Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="866bf-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="866bf-151">Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="866bf-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="866bf-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="866bf-152">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="866bf-153">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="866bf-153">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="866bf-154">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="866bf-154">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="866bf-155">Bindungen</span><span class="sxs-lookup"><span data-stu-id="866bf-155">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="866bf-156">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="866bf-156">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="866bf-157">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="866bf-157">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="866bf-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="866bf-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
