---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 6765259f290047a4199a422b4ad0cced2ffee9ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783350"
---
# <a name="peertransport"></a><span data-ttu-id="d987c-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="d987c-101">\<peerTransport></span></span>
<span data-ttu-id="d987c-102">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="d987c-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="d987c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d987c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="d987c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d987c-104">\<bindings></span></span>  
<span data-ttu-id="d987c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d987c-105">\<customBinding></span></span>  
<span data-ttu-id="d987c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="d987c-106">\<binding></span></span>  
<span data-ttu-id="d987c-107">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="d987c-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d987c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d987c-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d987c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d987c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d987c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d987c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d987c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d987c-111">Attributes</span></span>  
  
|<span data-ttu-id="d987c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d987c-112">Attribute</span></span>|<span data-ttu-id="d987c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d987c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d987c-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="d987c-114">listenIpAddress</span></span>|<span data-ttu-id="d987c-115">Eine Zeichenfolge mit einer IP-Adresse, die der Peerknoten auf TCP-Nachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="d987c-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="d987c-116">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="d987c-116">The default is `null`.</span></span>|  
|<span data-ttu-id="d987c-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="d987c-117">maxBufferPoolSize</span></span>|<span data-ttu-id="d987c-118">Eine positive ganze Zahl, die die maximale Pufferpoolgröße angibt.</span><span class="sxs-lookup"><span data-stu-id="d987c-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="d987c-119">Der Standard ist 524288.</span><span class="sxs-lookup"><span data-stu-id="d987c-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="d987c-120">Viele Bereiche von WCF verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="d987c-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="d987c-121">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="d987c-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="d987c-122">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="d987c-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="d987c-123">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="d987c-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="d987c-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="d987c-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="d987c-125">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Byte, einschließlich Header, festlegt.</span><span class="sxs-lookup"><span data-stu-id="d987c-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="d987c-126">Der Absender einer Nachricht erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="d987c-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="d987c-127">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="d987c-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="d987c-128">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="d987c-128">The default is 65536.</span></span>|  
|<span data-ttu-id="d987c-129">Port</span><span class="sxs-lookup"><span data-stu-id="d987c-129">port</span></span>|<span data-ttu-id="d987c-130">Eine ganze Zahl, die den Netzwerk-Schnittstellenanschluss angibt, an dem diese Bindung TCP-Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d987c-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="d987c-131">Dabei muss es sich um einen Wert zwischen <xref:System.Net.IPEndPoint.MinPort> und <xref:System.Net.IPEndPoint.MaxPort> handeln.</span><span class="sxs-lookup"><span data-stu-id="d987c-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="d987c-132">Der Standard ist 0.</span><span class="sxs-lookup"><span data-stu-id="d987c-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d987c-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d987c-133">Child Elements</span></span>  
  
|<span data-ttu-id="d987c-134">Element</span><span class="sxs-lookup"><span data-stu-id="d987c-134">Element</span></span>|<span data-ttu-id="d987c-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d987c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d987c-136">\<security></span><span class="sxs-lookup"><span data-stu-id="d987c-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="d987c-137">Definiert die Sicherheitseinstellungen für diesen Transport.</span><span class="sxs-lookup"><span data-stu-id="d987c-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="d987c-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d987c-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d987c-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d987c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d987c-140">Element</span><span class="sxs-lookup"><span data-stu-id="d987c-140">Element</span></span>|<span data-ttu-id="d987c-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d987c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d987c-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="d987c-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d987c-143">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="d987c-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d987c-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d987c-144">Remarks</span></span>  
 <span data-ttu-id="d987c-145">Dieser Transport kann nicht mit Verträgen verwendet werden, die Anforderungs-/Antwortvorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="d987c-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d987c-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d987c-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d987c-147">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="d987c-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="d987c-148">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="d987c-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="d987c-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d987c-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d987c-150">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d987c-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d987c-151">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d987c-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d987c-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d987c-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
