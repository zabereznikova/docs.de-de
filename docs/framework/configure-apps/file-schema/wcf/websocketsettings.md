---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732557"
---
# <a name="websocketsettings"></a><span data-ttu-id="9f37b-101">\<websocketsettings ></span><span class="sxs-lookup"><span data-stu-id="9f37b-101">\<webSocketSettings></span></span>
<span data-ttu-id="9f37b-102">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9f37b-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="9f37b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9f37b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9f37b-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9f37b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9f37b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9f37b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9f37b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9f37b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="9f37b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="9f37b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9f37b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<websocketsettings >**</span><span class="sxs-lookup"><span data-stu-id="9f37b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f37b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f37b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f37b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f37b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9f37b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f37b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f37b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f37b-112">Attributes</span></span>  
  
|<span data-ttu-id="9f37b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9f37b-113">Attribute</span></span>|<span data-ttu-id="9f37b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f37b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f37b-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="9f37b-115">createNotificationOnConnection</span></span>|<span data-ttu-id="9f37b-116">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f37b-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="9f37b-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="9f37b-117">disablePayloadMasking</span></span>|<span data-ttu-id="9f37b-118">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9f37b-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="9f37b-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="9f37b-119">keepAliveInterval</span></span>|<span data-ttu-id="9f37b-120">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="9f37b-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="9f37b-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="9f37b-121">maxPendingConnections</span></span>|<span data-ttu-id="9f37b-122">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="9f37b-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="9f37b-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="9f37b-123">receiveBufferSize</span></span>|<span data-ttu-id="9f37b-124">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="9f37b-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="9f37b-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="9f37b-125">sendBufferSize</span></span>|<span data-ttu-id="9f37b-126">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="9f37b-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="9f37b-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="9f37b-127">subProtocol</span></span>|<span data-ttu-id="9f37b-128">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="9f37b-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="9f37b-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="9f37b-129">transportUsage</span></span>|<span data-ttu-id="9f37b-130">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f37b-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="9f37b-131">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="9f37b-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="9f37b-132">Wert</span><span class="sxs-lookup"><span data-stu-id="9f37b-132">Value</span></span>|<span data-ttu-id="9f37b-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f37b-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9f37b-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="9f37b-134">WhenDuplex</span></span>|<span data-ttu-id="9f37b-135">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="9f37b-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="9f37b-136">Always</span><span class="sxs-lookup"><span data-stu-id="9f37b-136">Always</span></span>|<span data-ttu-id="9f37b-137">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="9f37b-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="9f37b-138">Nie</span><span class="sxs-lookup"><span data-stu-id="9f37b-138">Never</span></span>|<span data-ttu-id="9f37b-139">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="9f37b-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f37b-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f37b-140">Child Elements</span></span>  
 <span data-ttu-id="9f37b-141">Keiner</span><span class="sxs-lookup"><span data-stu-id="9f37b-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f37b-142">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f37b-142">Parent Elements</span></span>  
  
|<span data-ttu-id="9f37b-143">Element</span><span class="sxs-lookup"><span data-stu-id="9f37b-143">Element</span></span>|<span data-ttu-id="9f37b-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f37b-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f37b-145">\<">".</span><span class="sxs-lookup"><span data-stu-id="9f37b-145">\<netHttpBinding></span></span>|<span data-ttu-id="9f37b-146">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="9f37b-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9f37b-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f37b-147">Example</span></span>  
 <span data-ttu-id="9f37b-148">Im folgenden Beispiel wird gezeigt, wie das \<websocketsettings >-Element verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9f37b-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9f37b-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f37b-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="9f37b-150">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f37b-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9f37b-151">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f37b-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9f37b-152">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9f37b-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9f37b-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="9f37b-153">\<binding></span></span>](bindings.md)
