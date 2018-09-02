---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: e5f34dca83c8d3d08d27fb72bee5af2a89ac6b9f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416427"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="3a132-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="3a132-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="3a132-103">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3a132-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="3a132-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3a132-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3a132-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3a132-105">\<bindings></span></span>  
<span data-ttu-id="3a132-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3a132-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a132-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a132-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>  
  <binding>   
    <webSocketSettings createNotificationOnConnection="boolean" 
                       disablePayloadMasking="boolean" 
                       keepAliveInterval="TimeSpan" 
                       maxPendingConnections="Integer" 
                       receiveBufferSize="Integer" 
                       sendBufferSize="Integer" 
                       subProtocol="String" 
                       transportUsage="WhenDuplex/Always/Never"/>
  </binding>  
</netHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a132-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a132-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3a132-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a132-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a132-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a132-110">Attributes</span></span>  
  
|<span data-ttu-id="3a132-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="3a132-111">Attribute</span></span>|<span data-ttu-id="3a132-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a132-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a132-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="3a132-113">createNotificationOnConnection</span></span>|<span data-ttu-id="3a132-114">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a132-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="3a132-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="3a132-115">disablePayloadMasking</span></span>|<span data-ttu-id="3a132-116">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3a132-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="3a132-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="3a132-117">keepAliveInterval</span></span>|<span data-ttu-id="3a132-118">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="3a132-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="3a132-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="3a132-119">maxPendingConnections</span></span>|<span data-ttu-id="3a132-120">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="3a132-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="3a132-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="3a132-121">receiveBufferSize</span></span>|<span data-ttu-id="3a132-122">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="3a132-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="3a132-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="3a132-123">sendBufferSize</span></span>|<span data-ttu-id="3a132-124">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="3a132-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="3a132-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="3a132-125">subProtocol</span></span>|<span data-ttu-id="3a132-126">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="3a132-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="3a132-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="3a132-127">transportUsage</span></span>|<span data-ttu-id="3a132-128">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a132-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="3a132-129">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="3a132-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="3a132-130">Wert</span><span class="sxs-lookup"><span data-stu-id="3a132-130">Value</span></span>|<span data-ttu-id="3a132-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a132-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3a132-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="3a132-132">WhenDuplex</span></span>|<span data-ttu-id="3a132-133">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="3a132-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="3a132-134">Always</span><span class="sxs-lookup"><span data-stu-id="3a132-134">Always</span></span>|<span data-ttu-id="3a132-135">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="3a132-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="3a132-136">Nie</span><span class="sxs-lookup"><span data-stu-id="3a132-136">Never</span></span>|<span data-ttu-id="3a132-137">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="3a132-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a132-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a132-138">Child Elements</span></span>  
 <span data-ttu-id="3a132-139">Keiner</span><span class="sxs-lookup"><span data-stu-id="3a132-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a132-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a132-140">Parent Elements</span></span>  
  
|<span data-ttu-id="3a132-141">Element</span><span class="sxs-lookup"><span data-stu-id="3a132-141">Element</span></span>|<span data-ttu-id="3a132-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a132-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a132-143">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3a132-143">\<netHttpBinding></span></span>|<span data-ttu-id="3a132-144">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="3a132-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3a132-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a132-145">Example</span></span>  
 <span data-ttu-id="3a132-146">Das folgende Beispiel zeigt, wie Sie mit der \<WebSocketSettings > Element.</span><span class="sxs-lookup"><span data-stu-id="3a132-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a132-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a132-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="3a132-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3a132-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3a132-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3a132-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3a132-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3a132-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="3a132-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="3a132-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
