---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 68832c3a5bd4cc423642a6272e70cbecab86d6a8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181543"
---
# \<peerTransport>

<span data-ttu-id="ad5e9-101">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-101">Defines a peer transport for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="ad5e9-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad5e9-102">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad5e9-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ad5e9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ad5e9-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad5e9-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="ad5e9-105">Attributes</span></span>  
  
|<span data-ttu-id="ad5e9-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ad5e9-106">Attribute</span></span>|<span data-ttu-id="ad5e9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad5e9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad5e9-108">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="ad5e9-108">listenIpAddress</span></span>|<span data-ttu-id="ad5e9-109">Eine Zeichenfolge mit einer IP-Adresse, die der Peerknoten auf TCP-Nachrichten überwacht.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-109">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="ad5e9-110">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-110">The default is `null`.</span></span>|  
|<span data-ttu-id="ad5e9-111">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="ad5e9-111">maxBufferPoolSize</span></span>|<span data-ttu-id="ad5e9-112">Eine positive ganze Zahl, die die maximale Pufferpoolgröße angibt.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-112">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="ad5e9-113">Der Standard ist 524288.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-113">The default is 524288.</span></span><br /><br /> <span data-ttu-id="ad5e9-114">Viele Bereiche von WCF verwenden Puffer.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-114">Many parts of WCF use buffers.</span></span> <span data-ttu-id="ad5e9-115">Das Erstellen und Zerstören von Puffern bei jeder Verwendung ist kostspielig. Dasselbe gilt für die Garbage Collection für Puffer.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-115">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="ad5e9-116">Bei Pufferpools können Sie einen zu verwendenden Puffer aus dem Pool nehmen und ihn nach der Verwendung wieder dem Pool zuführen.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-116">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="ad5e9-117">So wird der Aufwand beim Erstellen und Zerstören von Puffern vermieden.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-117">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="ad5e9-118">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="ad5e9-118">maxReceivedMessageSize</span></span>|<span data-ttu-id="ad5e9-119">Eine positive ganze Zahl, die die maximale Nachrichtengröße in Byte, einschließlich Header, festlegt.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-119">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="ad5e9-120">Der Absender einer Nachricht erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-120">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="ad5e9-121">Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-121">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ad5e9-122">Der Standard ist 65536.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-122">The default is 65536.</span></span>|  
|<span data-ttu-id="ad5e9-123">port</span><span class="sxs-lookup"><span data-stu-id="ad5e9-123">port</span></span>|<span data-ttu-id="ad5e9-124">Eine ganze Zahl, die den Netzwerk-Schnittstellenanschluss angibt, an dem diese Bindung TCP-Peerkanalnachrichten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-124">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="ad5e9-125">Dabei muss es sich um einen Wert zwischen <xref:System.Net.IPEndPoint.MinPort> und <xref:System.Net.IPEndPoint.MaxPort> handeln.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-125">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="ad5e9-126">Die Standardeinstellung ist 0.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-126">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad5e9-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad5e9-127">Child Elements</span></span>  
  
|<span data-ttu-id="ad5e9-128">Element</span><span class="sxs-lookup"><span data-stu-id="ad5e9-128">Element</span></span>|<span data-ttu-id="ad5e9-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad5e9-129">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="ad5e9-130">Definiert die Sicherheitseinstellungen für diesen Transport.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-130">Defines the security settings for this transport.</span></span> <span data-ttu-id="ad5e9-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-131">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad5e9-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ad5e9-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ad5e9-133">Element</span><span class="sxs-lookup"><span data-stu-id="ad5e9-133">Element</span></span>|<span data-ttu-id="ad5e9-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad5e9-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="ad5e9-135">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-135">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad5e9-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ad5e9-136">Remarks</span></span>  

 <span data-ttu-id="ad5e9-137">Dieser Transport kann nicht mit Verträgen verwendet werden, die Anforderungs-/Antwortvorgänge enthalten.</span><span class="sxs-lookup"><span data-stu-id="ad5e9-137">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5e9-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad5e9-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ad5e9-139">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="ad5e9-139">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="ad5e9-140">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="ad5e9-140">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ad5e9-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ad5e9-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ad5e9-142">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ad5e9-142">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ad5e9-143">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ad5e9-143">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
