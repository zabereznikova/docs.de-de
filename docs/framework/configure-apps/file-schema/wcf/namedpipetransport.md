---
title: '&lt;namedPipeTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d2d4be08012c1d33341ddd17713903782027c31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="d02cd-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="d02cd-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="d02cd-103">Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d02cd-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="d02cd-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d02cd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d02cd-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="d02cd-105">\<bindings></span></span>  
<span data-ttu-id="d02cd-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="d02cd-106">\<customBinding></span></span>  
<span data-ttu-id="d02cd-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="d02cd-107">\<binding></span></span>  
<span data-ttu-id="d02cd-108">\<NamePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="d02cd-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d02cd-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="d02cd-109">Syntax</span></span>  
  
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
                          idleTimeout"TimeSpan"  
                          maxOutboundConnectionsPerEndpopint="Integer" />  
</namedPipeTransport>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d02cd-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d02cd-110">Attributes and Elements</span></span>  
<span data-ttu-id="d02cd-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d02cd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d02cd-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="d02cd-112">Attributes</span></span>  
<span data-ttu-id="d02cd-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="d02cd-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d02cd-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d02cd-114">Child Elements</span></span>  
  
|<span data-ttu-id="d02cd-115">Element</span><span class="sxs-lookup"><span data-stu-id="d02cd-115">Element</span></span>|<span data-ttu-id="d02cd-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d02cd-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d02cd-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="d02cd-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="d02cd-118">Ruft ab oder legt einen <xref:System.TimeSpan> , bestimmt die maximale Zeit, die ein Kanal kann in den Initialisierungsstatus sein, bevor Sie unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="d02cd-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="d02cd-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="d02cd-119">ConnectionBufferSize</span></span>|<span data-ttu-id="d02cd-120">Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d02cd-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="d02cd-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="d02cd-121">hostNameComparisonMode</span></span>|<span data-ttu-id="d02cd-122">Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d02cd-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="d02cd-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="d02cd-123">manualAddressing</span></span>|<span data-ttu-id="d02cd-124">Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="d02cd-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="d02cd-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="d02cd-125">maxBufferPoolSize</span></span>|<span data-ttu-id="d02cd-126">Ruft ab oder legt die maximale Größe des Pufferpools, die vom Transport in Bytes.</span><span class="sxs-lookup"><span data-stu-id="d02cd-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="d02cd-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="d02cd-127">maxBufferSize</span></span>|<span data-ttu-id="d02cd-128">Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="d02cd-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="d02cd-129">Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="d02cd-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="d02cd-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="d02cd-130">maxOutputDelay</span></span>|<span data-ttu-id="d02cd-131">Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="d02cd-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="d02cd-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="d02cd-132">maxPendingAccepts</span></span>|<span data-ttu-id="d02cd-133">Ruft ab oder legt die maximale Anzahl von Kanälen, die einen Dienst warten auf einen Listener für die Verarbeitung von eingehenden Verbindungen zu dem Dienst haben kann.</span><span class="sxs-lookup"><span data-stu-id="d02cd-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="d02cd-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d02cd-134">maxPendingConnections</span></span>|<span data-ttu-id="d02cd-135">Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.</span><span class="sxs-lookup"><span data-stu-id="d02cd-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="d02cd-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d02cd-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="d02cd-137">Ermittelt und definiert die maximale zulässige Nachrichtengröße in Bytes, die empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="d02cd-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="d02cd-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="d02cd-138">transferMode</span></span>|<span data-ttu-id="d02cd-139">Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="d02cd-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="d02cd-140">\<ConnectionPoolSettings > von \<NamedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="d02cd-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="d02cd-141">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="d02cd-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d02cd-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d02cd-142">Parent Elements</span></span>  
  
|<span data-ttu-id="d02cd-143">Element</span><span class="sxs-lookup"><span data-stu-id="d02cd-143">Element</span></span>|<span data-ttu-id="d02cd-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d02cd-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d02cd-145">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="d02cd-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d02cd-146">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="d02cd-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d02cd-147">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d02cd-147">Remarks</span></span>  
<span data-ttu-id="d02cd-148">Dieser Transport verwendet URIs im Format "net.pipe://hostname/path".</span><span class="sxs-lookup"><span data-stu-id="d02cd-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="d02cd-149">Andere URI-Komponenten sind optional.</span><span class="sxs-lookup"><span data-stu-id="d02cd-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="d02cd-150">Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="d02cd-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="d02cd-151">Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="d02cd-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02cd-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d02cd-152">See Also</span></span>  
<span data-ttu-id="d02cd-153"><xref:System.ServiceModel.Configuration.NamedPipeTransportElement></span><span class="sxs-lookup"><span data-stu-id="d02cd-153"><xref:System.ServiceModel.Configuration.NamedPipeTransportElement></span></span>   
<span data-ttu-id="d02cd-154"><xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement></span><span class="sxs-lookup"><span data-stu-id="d02cd-154"><xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement></span></span>   
<span data-ttu-id="d02cd-155"><xref:System.ServiceModel.Channels.TransportBindingElement></span><span class="sxs-lookup"><span data-stu-id="d02cd-155"><xref:System.ServiceModel.Channels.TransportBindingElement></span></span>   
<span data-ttu-id="d02cd-156"><xref:System.ServiceModel.Channels.CustomBinding></span><span class="sxs-lookup"><span data-stu-id="d02cd-156"><xref:System.ServiceModel.Channels.CustomBinding></span></span>   
<span data-ttu-id="d02cd-157">[Transporte](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="d02cd-157">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="d02cd-158">[Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="d02cd-158">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="d02cd-159">[Bindungen](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="d02cd-159">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="d02cd-160">[Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="d02cd-160">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="d02cd-161">[Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="d02cd-161">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="d02cd-162">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="d02cd-162">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
