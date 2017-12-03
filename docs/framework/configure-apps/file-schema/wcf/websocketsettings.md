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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71ed2fc6e4e5407cdf8c3e2334dcc0c16a00cf83
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="bda7c-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="bda7c-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="bda7c-103">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="bda7c-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="bda7c-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bda7c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bda7c-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="bda7c-105">\<bindings></span></span>  
<span data-ttu-id="bda7c-106">\<NetHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="bda7c-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda7c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bda7c-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bda7c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bda7c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bda7c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bda7c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bda7c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bda7c-110">Attributes</span></span>  
  
|<span data-ttu-id="bda7c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="bda7c-111">Attribute</span></span>|<span data-ttu-id="bda7c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bda7c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bda7c-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="bda7c-113">createNotificationOnConnection</span></span>|<span data-ttu-id="bda7c-114">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="bda7c-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="bda7c-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="bda7c-115">disablePayloadMasking</span></span>|<span data-ttu-id="bda7c-116">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bda7c-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="bda7c-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="bda7c-117">keepAliveInterval</span></span>|<span data-ttu-id="bda7c-118">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="bda7c-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="bda7c-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="bda7c-119">maxPendingConnections</span></span>|<span data-ttu-id="bda7c-120">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="bda7c-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="bda7c-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="bda7c-121">receiveBufferSize</span></span>|<span data-ttu-id="bda7c-122">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="bda7c-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="bda7c-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="bda7c-123">sendBufferSize</span></span>|<span data-ttu-id="bda7c-124">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="bda7c-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="bda7c-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="bda7c-125">subProtocol</span></span>|<span data-ttu-id="bda7c-126">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="bda7c-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="bda7c-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="bda7c-127">transportUsage</span></span>|<span data-ttu-id="bda7c-128">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bda7c-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="bda7c-129">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="bda7c-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="bda7c-130">Wert</span><span class="sxs-lookup"><span data-stu-id="bda7c-130">Value</span></span>|<span data-ttu-id="bda7c-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bda7c-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bda7c-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="bda7c-132">WhenDuplex</span></span>|<span data-ttu-id="bda7c-133">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="bda7c-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="bda7c-134">Always</span><span class="sxs-lookup"><span data-stu-id="bda7c-134">Always</span></span>|<span data-ttu-id="bda7c-135">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="bda7c-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="bda7c-136">Nie</span><span class="sxs-lookup"><span data-stu-id="bda7c-136">Never</span></span>|<span data-ttu-id="bda7c-137">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="bda7c-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bda7c-138">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bda7c-138">Child Elements</span></span>  
 <span data-ttu-id="bda7c-139">Keine</span><span class="sxs-lookup"><span data-stu-id="bda7c-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bda7c-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bda7c-140">Parent Elements</span></span>  
  
|<span data-ttu-id="bda7c-141">Element</span><span class="sxs-lookup"><span data-stu-id="bda7c-141">Element</span></span>|<span data-ttu-id="bda7c-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bda7c-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bda7c-143">\<NetHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="bda7c-143">\<netHttpBinding></span></span>|<span data-ttu-id="bda7c-144">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="bda7c-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bda7c-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bda7c-145">Example</span></span>  
 <span data-ttu-id="bda7c-146">Das folgende Beispiel zeigt, wie Sie die \<WebSocketSettings > Element.</span><span class="sxs-lookup"><span data-stu-id="bda7c-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bda7c-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bda7c-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="bda7c-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bda7c-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bda7c-149">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="bda7c-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="bda7c-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="bda7c-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="bda7c-151">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="bda7c-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
