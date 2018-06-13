---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 84aee31b6c15beb32732f89eae7c3d176f57971d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754836"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="e53c8-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="e53c8-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="e53c8-103">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e53c8-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="e53c8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e53c8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e53c8-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e53c8-105">\<bindings></span></span>  
<span data-ttu-id="e53c8-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e53c8-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e53c8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e53c8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e53c8-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e53c8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e53c8-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e53c8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e53c8-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e53c8-110">Attributes</span></span>  
  
|<span data-ttu-id="e53c8-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e53c8-111">Attribute</span></span>|<span data-ttu-id="e53c8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e53c8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e53c8-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="e53c8-113">createNotificationOnConnection</span></span>|<span data-ttu-id="e53c8-114">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="e53c8-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="e53c8-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="e53c8-115">disablePayloadMasking</span></span>|<span data-ttu-id="e53c8-116">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e53c8-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="e53c8-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="e53c8-117">keepAliveInterval</span></span>|<span data-ttu-id="e53c8-118">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="e53c8-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="e53c8-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="e53c8-119">maxPendingConnections</span></span>|<span data-ttu-id="e53c8-120">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="e53c8-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="e53c8-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="e53c8-121">receiveBufferSize</span></span>|<span data-ttu-id="e53c8-122">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="e53c8-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="e53c8-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="e53c8-123">sendBufferSize</span></span>|<span data-ttu-id="e53c8-124">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="e53c8-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="e53c8-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="e53c8-125">subProtocol</span></span>|<span data-ttu-id="e53c8-126">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="e53c8-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="e53c8-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="e53c8-127">transportUsage</span></span>|<span data-ttu-id="e53c8-128">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e53c8-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="e53c8-129">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="e53c8-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="e53c8-130">Wert</span><span class="sxs-lookup"><span data-stu-id="e53c8-130">Value</span></span>|<span data-ttu-id="e53c8-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e53c8-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e53c8-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="e53c8-132">WhenDuplex</span></span>|<span data-ttu-id="e53c8-133">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="e53c8-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="e53c8-134">Always</span><span class="sxs-lookup"><span data-stu-id="e53c8-134">Always</span></span>|<span data-ttu-id="e53c8-135">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e53c8-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="e53c8-136">Nie</span><span class="sxs-lookup"><span data-stu-id="e53c8-136">Never</span></span>|<span data-ttu-id="e53c8-137">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="e53c8-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e53c8-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e53c8-138">Child Elements</span></span>  
 <span data-ttu-id="e53c8-139">Keiner</span><span class="sxs-lookup"><span data-stu-id="e53c8-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e53c8-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e53c8-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e53c8-141">Element</span><span class="sxs-lookup"><span data-stu-id="e53c8-141">Element</span></span>|<span data-ttu-id="e53c8-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e53c8-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e53c8-143">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e53c8-143">\<netHttpBinding></span></span>|<span data-ttu-id="e53c8-144">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="e53c8-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e53c8-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e53c8-145">Example</span></span>  
 <span data-ttu-id="e53c8-146">Das folgende Beispiel zeigt, wie Sie die \<WebSocketSettings > Element.</span><span class="sxs-lookup"><span data-stu-id="e53c8-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e53c8-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e53c8-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="e53c8-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e53c8-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e53c8-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e53c8-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e53c8-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e53c8-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e53c8-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="e53c8-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
