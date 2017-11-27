---
title: '&lt;webSocketSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2714b27916a47ae8e002ea857c93377736c4eff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="4b3b0-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="4b3b0-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="4b3b0-103">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="4b3b0-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4b3b0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4b3b0-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="4b3b0-105">\<bindings></span></span>  
<span data-ttu-id="4b3b0-106">\<NetHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4b3b0-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b3b0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b3b0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b3b0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b3b0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4b3b0-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b3b0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b3b0-110">Attributes</span></span>  
  
|<span data-ttu-id="4b3b0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="4b3b0-111">Attribute</span></span>|<span data-ttu-id="4b3b0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b3b0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b3b0-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="4b3b0-113">createNotificationOnConnection</span></span>|<span data-ttu-id="4b3b0-114">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="4b3b0-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="4b3b0-115">disablePayloadMasking</span></span>|<span data-ttu-id="4b3b0-116">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="4b3b0-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="4b3b0-117">keepAliveInterval</span></span>|<span data-ttu-id="4b3b0-118">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="4b3b0-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="4b3b0-119">maxPendingConnections</span></span>|<span data-ttu-id="4b3b0-120">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="4b3b0-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="4b3b0-121">receiveBufferSize</span></span>|<span data-ttu-id="4b3b0-122">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="4b3b0-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="4b3b0-123">sendBufferSize</span></span>|<span data-ttu-id="4b3b0-124">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="4b3b0-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="4b3b0-125">subProtocol</span></span>|<span data-ttu-id="4b3b0-126">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="4b3b0-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="4b3b0-127">transportUsage</span></span>|<span data-ttu-id="4b3b0-128">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="4b3b0-129">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="4b3b0-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="4b3b0-130">Wert</span><span class="sxs-lookup"><span data-stu-id="4b3b0-130">Value</span></span>|<span data-ttu-id="4b3b0-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b3b0-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4b3b0-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="4b3b0-132">WhenDuplex</span></span>|<span data-ttu-id="4b3b0-133">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="4b3b0-134">Always</span><span class="sxs-lookup"><span data-stu-id="4b3b0-134">Always</span></span>|<span data-ttu-id="4b3b0-135">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="4b3b0-136">Nie</span><span class="sxs-lookup"><span data-stu-id="4b3b0-136">Never</span></span>|<span data-ttu-id="4b3b0-137">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b3b0-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b3b0-138">Child Elements</span></span>  
 <span data-ttu-id="4b3b0-139">Keine</span><span class="sxs-lookup"><span data-stu-id="4b3b0-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b3b0-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b3b0-140">Parent Elements</span></span>  
  
|<span data-ttu-id="4b3b0-141">Element</span><span class="sxs-lookup"><span data-stu-id="4b3b0-141">Element</span></span>|<span data-ttu-id="4b3b0-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b3b0-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b3b0-143">\<NetHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4b3b0-143">\<netHttpBinding></span></span>|<span data-ttu-id="4b3b0-144">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4b3b0-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b3b0-145">Example</span></span>  
 <span data-ttu-id="4b3b0-146">Das folgende Beispiel zeigt, wie Sie die \<WebSocketSettings > Element.</span><span class="sxs-lookup"><span data-stu-id="4b3b0-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4b3b0-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b3b0-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="4b3b0-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4b3b0-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4b3b0-149">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4b3b0-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4b3b0-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4b3b0-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4b3b0-151">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="4b3b0-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
