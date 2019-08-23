---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 1ad05fd9125ecc8b3d5797e0dd335adbf808db84
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933841"
---
# <a name="peertransport"></a><span data-ttu-id="b6741-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="b6741-101">\<peerTransport></span></span>
<span data-ttu-id="b6741-102">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="b6741-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="b6741-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6741-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b6741-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b6741-104">\<bindings></span></span>  
<span data-ttu-id="b6741-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b6741-105">\<customBinding></span></span>  
<span data-ttu-id="b6741-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b6741-106">\<binding></span></span>  
<span data-ttu-id="b6741-107">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="b6741-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6741-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6741-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6741-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6741-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b6741-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6741-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6741-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6741-111">Attributes</span></span>  
  
|<span data-ttu-id="b6741-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="b6741-112">Attribute</span></span>|<span data-ttu-id="b6741-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6741-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6741-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="b6741-114">listenIpAddress</span></span>|<span data-ttu-id="b6741-115">Eine Zeichenfolge mit einer IP-Adresse, die der Peerknoten auf TCP-Nachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="b6741-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="b6741-116">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="b6741-116">The default is `null`.</span></span>|  
|<span data-ttu-id="b6741-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="b6741-117">maxBufferPoolSize</span></span>|<span data-ttu-id="b6741-118">Eine positive ganze Zahl, die die maximale Pufferpoolgröße angibt.</span><span class="sxs-lookup"><span data-stu-id="b6741-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="b6741-119">Der Standard ist 524288.</span><span class="sxs-lookup"><span data-stu-id="b6741-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="b6741-120">Viele Bereiche von WCF verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="b6741-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="b6741-121">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="b6741-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="b6741-122">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="b6741-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="b6741-123">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="b6741-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="b6741-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="b6741-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="b6741-125">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Byte, einschließlich Header, festlegt.</span><span class="sxs-lookup"><span data-stu-id="b6741-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="b6741-126">Der Absender einer Nachricht erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="b6741-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="b6741-127">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="b6741-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="b6741-128">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="b6741-128">The default is 65536.</span></span>|  
|<span data-ttu-id="b6741-129">Port</span><span class="sxs-lookup"><span data-stu-id="b6741-129">port</span></span>|<span data-ttu-id="b6741-130">Eine ganze Zahl, die den Netzwerk-Schnittstellenanschluss angibt, an dem diese Bindung TCP-Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b6741-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="b6741-131">Dabei muss es sich um einen Wert zwischen <xref:System.Net.IPEndPoint.MinPort> und <xref:System.Net.IPEndPoint.MaxPort> handeln.</span><span class="sxs-lookup"><span data-stu-id="b6741-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="b6741-132">Die Standardeinstellung ist 0.</span><span class="sxs-lookup"><span data-stu-id="b6741-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6741-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6741-133">Child Elements</span></span>  
  
|<span data-ttu-id="b6741-134">Element</span><span class="sxs-lookup"><span data-stu-id="b6741-134">Element</span></span>|<span data-ttu-id="b6741-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6741-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6741-136">\<security></span><span class="sxs-lookup"><span data-stu-id="b6741-136">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="b6741-137">Definiert die Sicherheitseinstellungen für diesen Transport.</span><span class="sxs-lookup"><span data-stu-id="b6741-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="b6741-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b6741-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6741-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6741-139">Parent Elements</span></span>  
  
|<span data-ttu-id="b6741-140">Element</span><span class="sxs-lookup"><span data-stu-id="b6741-140">Element</span></span>|<span data-ttu-id="b6741-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6741-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6741-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="b6741-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b6741-143">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="b6741-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6741-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6741-144">Remarks</span></span>  
 <span data-ttu-id="b6741-145">Dieser Transport kann nicht mit Verträgen verwendet werden, die Anforderungs-/Antwortvorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="b6741-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6741-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6741-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b6741-147">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="b6741-147">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b6741-148">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="b6741-148">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b6741-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b6741-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b6741-150">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="b6741-150">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b6741-151">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="b6741-151">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b6741-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b6741-152">\<customBinding></span></span>](custombinding.md)
