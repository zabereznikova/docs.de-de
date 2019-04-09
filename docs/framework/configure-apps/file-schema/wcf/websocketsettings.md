---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 1101d021f3c7436c4f45a22a48e50f6d1553f753
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226871"
---
# <a name="websocketsettings"></a><span data-ttu-id="24332-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="24332-101">\<webSocketSettings></span></span>
<span data-ttu-id="24332-102">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="24332-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="24332-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="24332-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="24332-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="24332-104">\<bindings></span></span>  
<span data-ttu-id="24332-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="24332-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24332-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="24332-106">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24332-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="24332-107">Attributes and Elements</span></span>  
 <span data-ttu-id="24332-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24332-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24332-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="24332-109">Attributes</span></span>  
  
|<span data-ttu-id="24332-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="24332-110">Attribute</span></span>|<span data-ttu-id="24332-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24332-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24332-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="24332-112">createNotificationOnConnection</span></span>|<span data-ttu-id="24332-113">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="24332-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="24332-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="24332-114">disablePayloadMasking</span></span>|<span data-ttu-id="24332-115">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="24332-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="24332-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="24332-116">keepAliveInterval</span></span>|<span data-ttu-id="24332-117">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="24332-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="24332-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="24332-118">maxPendingConnections</span></span>|<span data-ttu-id="24332-119">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="24332-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="24332-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="24332-120">receiveBufferSize</span></span>|<span data-ttu-id="24332-121">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="24332-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="24332-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="24332-122">sendBufferSize</span></span>|<span data-ttu-id="24332-123">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="24332-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="24332-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="24332-124">subProtocol</span></span>|<span data-ttu-id="24332-125">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="24332-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="24332-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="24332-126">transportUsage</span></span>|<span data-ttu-id="24332-127">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="24332-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="24332-128">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="24332-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="24332-129">Wert</span><span class="sxs-lookup"><span data-stu-id="24332-129">Value</span></span>|<span data-ttu-id="24332-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24332-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="24332-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="24332-131">WhenDuplex</span></span>|<span data-ttu-id="24332-132">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="24332-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="24332-133">Always</span><span class="sxs-lookup"><span data-stu-id="24332-133">Always</span></span>|<span data-ttu-id="24332-134">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="24332-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="24332-135">Nie</span><span class="sxs-lookup"><span data-stu-id="24332-135">Never</span></span>|<span data-ttu-id="24332-136">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="24332-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24332-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24332-137">Child Elements</span></span>  
 <span data-ttu-id="24332-138">Keiner</span><span class="sxs-lookup"><span data-stu-id="24332-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24332-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24332-139">Parent Elements</span></span>  
  
|<span data-ttu-id="24332-140">Element</span><span class="sxs-lookup"><span data-stu-id="24332-140">Element</span></span>|<span data-ttu-id="24332-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24332-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24332-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="24332-142">\<netHttpBinding></span></span>|<span data-ttu-id="24332-143">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="24332-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="24332-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24332-144">Example</span></span>  
 <span data-ttu-id="24332-145">Das folgende Beispiel zeigt, wie Sie mit der \<WebSocketSettings > Element.</span><span class="sxs-lookup"><span data-stu-id="24332-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="24332-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24332-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="24332-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="24332-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="24332-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="24332-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="24332-149">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="24332-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="24332-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="24332-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
