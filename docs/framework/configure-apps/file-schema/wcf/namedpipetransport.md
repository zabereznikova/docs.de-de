---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 4582066098feaf50b33b083de56bcb8c3e04df0f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204618"
---
# \<namedPipeTransport>

<span data-ttu-id="02cc2-101">Definiert einen Transport, durch den ein Kanal Nachrichten mit benannten Pipes überträgt, wenn er in einer benutzerdefinierten Bindung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="02cc2-101">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="02cc2-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="02cc2-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02cc2-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="02cc2-103">Attributes and Elements</span></span>  

<span data-ttu-id="02cc2-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="02cc2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02cc2-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="02cc2-105">Attributes</span></span>  

<span data-ttu-id="02cc2-106">Keine</span><span class="sxs-lookup"><span data-stu-id="02cc2-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02cc2-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02cc2-107">Child Elements</span></span>  
  
|<span data-ttu-id="02cc2-108">Element</span><span class="sxs-lookup"><span data-stu-id="02cc2-108">Element</span></span>|<span data-ttu-id="02cc2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02cc2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02cc2-110">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="02cc2-110">ChannelInitializationTimeout</span></span>|<span data-ttu-id="02cc2-111">Ruft eine <xref:System.TimeSpan> ab, die maximale Zeit bestimmt, in der sich der Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-111">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="02cc2-112">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="02cc2-112">ConnectionBufferSize</span></span>|<span data-ttu-id="02cc2-113">Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="02cc2-113">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="02cc2-114">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="02cc2-114">hostNameComparisonMode</span></span>|<span data-ttu-id="02cc2-115">Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="02cc2-115">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="02cc2-116">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="02cc2-116">manualAddressing</span></span>|<span data-ttu-id="02cc2-117">Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-117">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="02cc2-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="02cc2-118">maxBufferPoolSize</span></span>|<span data-ttu-id="02cc2-119">Ruft die maximale Größe in Byte von Pufferpools ab, die vom Transport verwendet werden, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-119">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="02cc2-120">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="02cc2-120">maxBufferSize</span></span>|<span data-ttu-id="02cc2-121">Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-121">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="02cc2-122">Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="02cc2-122">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="02cc2-123">maxoutputdelay</span><span class="sxs-lookup"><span data-stu-id="02cc2-123">maxOutputDelay</span></span>|<span data-ttu-id="02cc2-124">Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.</span><span class="sxs-lookup"><span data-stu-id="02cc2-124">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="02cc2-125">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="02cc2-125">maxPendingAccepts</span></span>|<span data-ttu-id="02cc2-126">Ruft die maximale Anzahl von Channels ab, über die ein Dienst während des Wartens auf einen Listener zur Verarbeitung eingehender Verbindungen verfügen kann, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-126">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="02cc2-127">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="02cc2-127">maxPendingConnections</span></span>|<span data-ttu-id="02cc2-128">Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-128">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="02cc2-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="02cc2-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="02cc2-130">Ruft die maximal zulässige Nachrichtengröße in Byte ab, die empfangen werden kann, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="02cc2-130">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="02cc2-131">transferMode</span><span class="sxs-lookup"><span data-stu-id="02cc2-131">transferMode</span></span>|<span data-ttu-id="02cc2-132">Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="02cc2-132">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="02cc2-133">\<connectionPoolSettings> von \<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="02cc2-133">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="02cc2-134">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="02cc2-134">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02cc2-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="02cc2-135">Parent Elements</span></span>  
  
|<span data-ttu-id="02cc2-136">Element</span><span class="sxs-lookup"><span data-stu-id="02cc2-136">Element</span></span>|<span data-ttu-id="02cc2-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02cc2-137">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="02cc2-138">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="02cc2-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02cc2-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="02cc2-139">Remarks</span></span>  

<span data-ttu-id="02cc2-140">Dieser Transport verwendet URIs im Format "net.pipe://hostname/path".</span><span class="sxs-lookup"><span data-stu-id="02cc2-140">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="02cc2-141">Andere URI-Komponenten sind optional.</span><span class="sxs-lookup"><span data-stu-id="02cc2-141">Other URI components are optional.</span></span>  
  
<span data-ttu-id="02cc2-142">Das `namedPipeTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das Named Pipes-Transportprotokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="02cc2-142">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="02cc2-143">Dieser Transport wird für Windows Communication Foundation (WCF)-zu-WCF-Kommunikation auf dem Computer verwendet.</span><span class="sxs-lookup"><span data-stu-id="02cc2-143">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02cc2-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02cc2-144">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="02cc2-145">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="02cc2-145">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="02cc2-146">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="02cc2-146">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="02cc2-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="02cc2-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="02cc2-148">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="02cc2-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="02cc2-149">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="02cc2-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
