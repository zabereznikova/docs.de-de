---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 00631ad88d771ed8f45638f28c84df05917fd3a0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736583"
---
# <a name="namedpipetransport"></a><span data-ttu-id="0c141-101">\<namedPipeTransport-></span><span class="sxs-lookup"><span data-stu-id="0c141-101">\<namedPipeTransport></span></span>
<span data-ttu-id="0c141-102">Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0c141-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="0c141-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0c141-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0c141-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="0c141-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0c141-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0c141-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0c141-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="0c141-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="0c141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="0c141-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0c141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namedPipeTransport >**</span><span class="sxs-lookup"><span data-stu-id="0c141-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c141-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c141-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c141-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0c141-110">Attributes and Elements</span></span>  
<span data-ttu-id="0c141-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0c141-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c141-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="0c141-112">Attributes</span></span>  
<span data-ttu-id="0c141-113">Keine</span><span class="sxs-lookup"><span data-stu-id="0c141-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c141-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c141-114">Child Elements</span></span>  
  
|<span data-ttu-id="0c141-115">Element</span><span class="sxs-lookup"><span data-stu-id="0c141-115">Element</span></span>|<span data-ttu-id="0c141-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c141-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c141-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="0c141-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="0c141-118">Ruft einen <xref:System.TimeSpan> ab oder legt ihn fest, der die maximale Zeit bestimmt, die ein Kanal im Initialisierungs Status sein kann, bevor er getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="0c141-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="0c141-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="0c141-119">ConnectionBufferSize</span></span>|<span data-ttu-id="0c141-120">Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c141-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="0c141-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="0c141-121">hostNameComparisonMode</span></span>|<span data-ttu-id="0c141-122">Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c141-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="0c141-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="0c141-123">manualAddressing</span></span>|<span data-ttu-id="0c141-124">Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="0c141-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="0c141-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="0c141-125">maxBufferPoolSize</span></span>|<span data-ttu-id="0c141-126">Ruft die maximale Größe (in Bytes) aller Pufferpools ab, die vom Transport verwendet werden, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="0c141-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="0c141-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="0c141-127">maxBufferSize</span></span>|<span data-ttu-id="0c141-128">Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="0c141-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="0c141-129">Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="0c141-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="0c141-130">maxoutputdelay</span><span class="sxs-lookup"><span data-stu-id="0c141-130">maxOutputDelay</span></span>|<span data-ttu-id="0c141-131">Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="0c141-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="0c141-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="0c141-132">maxPendingAccepts</span></span>|<span data-ttu-id="0c141-133">Ruft die maximale Anzahl von Kanälen ab, die ein Dienst auf einen Listener warten kann, um eingehende Verbindungen mit dem Dienst zu verarbeiten, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="0c141-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="0c141-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="0c141-134">maxPendingConnections</span></span>|<span data-ttu-id="0c141-135">Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.</span><span class="sxs-lookup"><span data-stu-id="0c141-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="0c141-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="0c141-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="0c141-137">Ruft die maximal zulässige Nachrichtengröße in Byte ab, die empfangen werden kann, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="0c141-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="0c141-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="0c141-138">transferMode</span></span>|<span data-ttu-id="0c141-139">Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0c141-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="0c141-140">\<connectionpoolsettings-> \<namedPipeTransport-></span><span class="sxs-lookup"><span data-stu-id="0c141-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="0c141-141">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="0c141-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c141-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0c141-142">Parent Elements</span></span>  
  
|<span data-ttu-id="0c141-143">Element</span><span class="sxs-lookup"><span data-stu-id="0c141-143">Element</span></span>|<span data-ttu-id="0c141-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c141-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c141-145">\<binding ></span><span class="sxs-lookup"><span data-stu-id="0c141-145">\<binding></span></span>](bindings.md)|<span data-ttu-id="0c141-146">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="0c141-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c141-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c141-147">Remarks</span></span>  
<span data-ttu-id="0c141-148">Dieser Transport verwendet URIs im Format "net.pipe://hostname/path".</span><span class="sxs-lookup"><span data-stu-id="0c141-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="0c141-149">Andere URI-Komponenten sind optional.</span><span class="sxs-lookup"><span data-stu-id="0c141-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="0c141-150">Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="0c141-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="0c141-151">Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c141-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c141-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c141-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0c141-153">Transporte</span><span class="sxs-lookup"><span data-stu-id="0c141-153">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="0c141-154">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="0c141-154">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="0c141-155">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0c141-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0c141-156">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="0c141-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0c141-157">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="0c141-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0c141-158">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="0c141-158">\<customBinding></span></span>](custombinding.md)
