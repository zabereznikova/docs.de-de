---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 819639eabf0332a34d6a7250159d24e42552f874
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423094"
---
# <a name="namedpipetransport"></a><span data-ttu-id="ad40b-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="ad40b-101">\<namedPipeTransport></span></span>
<span data-ttu-id="ad40b-102">Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ad40b-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="ad40b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ad40b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="ad40b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ad40b-104">\<bindings></span></span>  
<span data-ttu-id="ad40b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ad40b-105">\<customBinding></span></span>  
<span data-ttu-id="ad40b-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="ad40b-106">\<binding></span></span>  
<span data-ttu-id="ad40b-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="ad40b-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad40b-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad40b-108">Syntax</span></span>  
  
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
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad40b-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ad40b-109">Attributes and Elements</span></span>  
<span data-ttu-id="ad40b-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad40b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad40b-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ad40b-111">Attributes</span></span>  
<span data-ttu-id="ad40b-112">Keine</span><span class="sxs-lookup"><span data-stu-id="ad40b-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad40b-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad40b-113">Child Elements</span></span>  
  
|<span data-ttu-id="ad40b-114">Element</span><span class="sxs-lookup"><span data-stu-id="ad40b-114">Element</span></span>|<span data-ttu-id="ad40b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad40b-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad40b-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="ad40b-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="ad40b-117">Ruft ab oder legt einen <xref:System.TimeSpan> , bestimmt die maximale Zeit, die ein Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="ad40b-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="ad40b-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="ad40b-118">ConnectionBufferSize</span></span>|<span data-ttu-id="ad40b-119">Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad40b-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="ad40b-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="ad40b-120">hostNameComparisonMode</span></span>|<span data-ttu-id="ad40b-121">Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad40b-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="ad40b-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="ad40b-122">manualAddressing</span></span>|<span data-ttu-id="ad40b-123">Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="ad40b-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="ad40b-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ad40b-124">maxBufferPoolSize</span></span>|<span data-ttu-id="ad40b-125">Übernimmt oder bestimmt die maximale Größe in Byte von Pufferpools, die vom Transport verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad40b-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="ad40b-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="ad40b-126">maxBufferSize</span></span>|<span data-ttu-id="ad40b-127">Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="ad40b-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="ad40b-128">Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ad40b-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="ad40b-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="ad40b-129">maxOutputDelay</span></span>|<span data-ttu-id="ad40b-130">Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad40b-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="ad40b-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="ad40b-131">maxPendingAccepts</span></span>|<span data-ttu-id="ad40b-132">Übernimmt oder bestimmt die maximale Anzahl von Kanälen, die einen Dienst auf einen Listener anbieten kann für die Verarbeitung von eingehenden Verbindungen mit dem Dienst warten.</span><span class="sxs-lookup"><span data-stu-id="ad40b-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="ad40b-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="ad40b-133">maxPendingConnections</span></span>|<span data-ttu-id="ad40b-134">Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.</span><span class="sxs-lookup"><span data-stu-id="ad40b-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="ad40b-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ad40b-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="ad40b-136">Ermittelt und definiert die maximale zulässige Nachrichtengröße in Bytes, die empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="ad40b-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="ad40b-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="ad40b-137">transferMode</span></span>|<span data-ttu-id="ad40b-138">Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="ad40b-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="ad40b-139">\<ConnectionPoolSettings > von \<NamedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="ad40b-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="ad40b-140">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="ad40b-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad40b-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad40b-141">Parent Elements</span></span>  
  
|<span data-ttu-id="ad40b-142">Element</span><span class="sxs-lookup"><span data-stu-id="ad40b-142">Element</span></span>|<span data-ttu-id="ad40b-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad40b-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad40b-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="ad40b-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ad40b-145">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ad40b-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad40b-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad40b-146">Remarks</span></span>  
<span data-ttu-id="ad40b-147">Dieser Transport verwendet URIs im Format "net.pipe://hostname/path".</span><span class="sxs-lookup"><span data-stu-id="ad40b-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="ad40b-148">Andere URI-Komponenten sind optional.</span><span class="sxs-lookup"><span data-stu-id="ad40b-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="ad40b-149">Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="ad40b-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="ad40b-150">Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad40b-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad40b-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad40b-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ad40b-152">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="ad40b-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="ad40b-153">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="ad40b-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ad40b-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ad40b-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ad40b-155">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ad40b-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ad40b-156">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ad40b-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ad40b-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ad40b-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
