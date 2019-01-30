---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 298bf27b171772bb039b11b5e5de70e7d45b061d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258442"
---
# <a name="websocketsettings"></a><span data-ttu-id="d488e-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="d488e-101">\<webSocketSettings></span></span>
<span data-ttu-id="d488e-102">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d488e-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="d488e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d488e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d488e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d488e-104">\<bindings></span></span>  
<span data-ttu-id="d488e-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d488e-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d488e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d488e-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d488e-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d488e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d488e-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d488e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d488e-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d488e-109">Attributes</span></span>  
  
|<span data-ttu-id="d488e-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="d488e-110">Attribute</span></span>|<span data-ttu-id="d488e-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d488e-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d488e-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="d488e-112">createNotificationOnConnection</span></span>|<span data-ttu-id="d488e-113">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="d488e-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="d488e-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="d488e-114">disablePayloadMasking</span></span>|<span data-ttu-id="d488e-115">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d488e-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="d488e-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="d488e-116">keepAliveInterval</span></span>|<span data-ttu-id="d488e-117">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="d488e-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="d488e-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d488e-118">maxPendingConnections</span></span>|<span data-ttu-id="d488e-119">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="d488e-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="d488e-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="d488e-120">receiveBufferSize</span></span>|<span data-ttu-id="d488e-121">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="d488e-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="d488e-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="d488e-122">sendBufferSize</span></span>|<span data-ttu-id="d488e-123">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="d488e-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="d488e-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="d488e-124">subProtocol</span></span>|<span data-ttu-id="d488e-125">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="d488e-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="d488e-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="d488e-126">transportUsage</span></span>|<span data-ttu-id="d488e-127">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d488e-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="d488e-128">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="d488e-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="d488e-129">Wert</span><span class="sxs-lookup"><span data-stu-id="d488e-129">Value</span></span>|<span data-ttu-id="d488e-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d488e-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d488e-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="d488e-131">WhenDuplex</span></span>|<span data-ttu-id="d488e-132">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="d488e-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="d488e-133">Always</span><span class="sxs-lookup"><span data-stu-id="d488e-133">Always</span></span>|<span data-ttu-id="d488e-134">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="d488e-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="d488e-135">Nie</span><span class="sxs-lookup"><span data-stu-id="d488e-135">Never</span></span>|<span data-ttu-id="d488e-136">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="d488e-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d488e-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d488e-137">Child Elements</span></span>  
 <span data-ttu-id="d488e-138">Keine</span><span class="sxs-lookup"><span data-stu-id="d488e-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d488e-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d488e-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d488e-140">Element</span><span class="sxs-lookup"><span data-stu-id="d488e-140">Element</span></span>|<span data-ttu-id="d488e-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d488e-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d488e-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d488e-142">\<netHttpBinding></span></span>|<span data-ttu-id="d488e-143">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="d488e-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d488e-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d488e-144">Example</span></span>  
 <span data-ttu-id="d488e-145">Das folgende Beispiel zeigt, wie Sie mit der \<WebSocketSettings > Element.</span><span class="sxs-lookup"><span data-stu-id="d488e-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d488e-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d488e-146">See also</span></span>
- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="d488e-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d488e-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="d488e-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="d488e-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d488e-149">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d488e-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d488e-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="d488e-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
