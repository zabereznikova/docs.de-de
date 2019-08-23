---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940323"
---
# <a name="websocketsettings"></a><span data-ttu-id="03f13-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="03f13-101">\<webSocketSettings></span></span>
<span data-ttu-id="03f13-102">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="03f13-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="03f13-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03f13-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="03f13-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="03f13-104">\<bindings></span></span>  
<span data-ttu-id="03f13-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="03f13-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f13-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="03f13-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03f13-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="03f13-107">Attributes and Elements</span></span>  
 <span data-ttu-id="03f13-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03f13-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03f13-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="03f13-109">Attributes</span></span>  
  
|<span data-ttu-id="03f13-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="03f13-110">Attribute</span></span>|<span data-ttu-id="03f13-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03f13-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03f13-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="03f13-112">createNotificationOnConnection</span></span>|<span data-ttu-id="03f13-113">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="03f13-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="03f13-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="03f13-114">disablePayloadMasking</span></span>|<span data-ttu-id="03f13-115">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="03f13-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="03f13-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="03f13-116">keepAliveInterval</span></span>|<span data-ttu-id="03f13-117">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="03f13-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="03f13-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="03f13-118">maxPendingConnections</span></span>|<span data-ttu-id="03f13-119">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="03f13-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="03f13-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="03f13-120">receiveBufferSize</span></span>|<span data-ttu-id="03f13-121">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="03f13-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="03f13-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="03f13-122">sendBufferSize</span></span>|<span data-ttu-id="03f13-123">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="03f13-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="03f13-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="03f13-124">subProtocol</span></span>|<span data-ttu-id="03f13-125">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="03f13-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="03f13-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="03f13-126">transportUsage</span></span>|<span data-ttu-id="03f13-127">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03f13-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="03f13-128">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="03f13-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="03f13-129">Wert</span><span class="sxs-lookup"><span data-stu-id="03f13-129">Value</span></span>|<span data-ttu-id="03f13-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03f13-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="03f13-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="03f13-131">WhenDuplex</span></span>|<span data-ttu-id="03f13-132">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="03f13-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="03f13-133">Always</span><span class="sxs-lookup"><span data-stu-id="03f13-133">Always</span></span>|<span data-ttu-id="03f13-134">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="03f13-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="03f13-135">Nie</span><span class="sxs-lookup"><span data-stu-id="03f13-135">Never</span></span>|<span data-ttu-id="03f13-136">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="03f13-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03f13-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03f13-137">Child Elements</span></span>  
 <span data-ttu-id="03f13-138">None</span><span class="sxs-lookup"><span data-stu-id="03f13-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03f13-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03f13-139">Parent Elements</span></span>  
  
|<span data-ttu-id="03f13-140">Element</span><span class="sxs-lookup"><span data-stu-id="03f13-140">Element</span></span>|<span data-ttu-id="03f13-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03f13-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03f13-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="03f13-142">\<netHttpBinding></span></span>|<span data-ttu-id="03f13-143">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="03f13-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03f13-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03f13-144">Example</span></span>  
 <span data-ttu-id="03f13-145">Im folgenden Beispiel wird gezeigt, wie das \<websocketsettings >-Element verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03f13-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03f13-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03f13-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="03f13-147">Bindungen</span><span class="sxs-lookup"><span data-stu-id="03f13-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="03f13-148">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="03f13-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="03f13-149">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="03f13-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="03f13-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="03f13-150">\<binding></span></span>](../../../misc/binding.md)
