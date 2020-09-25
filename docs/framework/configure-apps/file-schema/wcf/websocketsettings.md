---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 6cfddfb9ebfc7c3447af977e14738baabebc8fe9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177850"
---
# \<webSocketSettings>

<span data-ttu-id="4beb4-101">Ein Konfigurationselement zum Angeben von WebSocket-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="4beb4-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="4beb4-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="4beb4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4beb4-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4beb4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="4beb4-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4beb4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4beb4-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="4beb4-105">Attributes</span></span>  
  
|<span data-ttu-id="4beb4-106">attribute</span><span class="sxs-lookup"><span data-stu-id="4beb4-106">Attribute</span></span>|<span data-ttu-id="4beb4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4beb4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4beb4-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="4beb4-108">createNotificationOnConnection</span></span>|<span data-ttu-id="4beb4-109">Gibt an, ob eine Benachrichtigung bei Zustandekommen einer Verbindung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4beb4-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="4beb4-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="4beb4-110">disablePayloadMasking</span></span>|<span data-ttu-id="4beb4-111">Gibt an, ob die WebSocket-Maske deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4beb4-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="4beb4-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="4beb4-112">keepAliveInterval</span></span>|<span data-ttu-id="4beb4-113">Gibt das Keep-Alive-Intervall an.</span><span class="sxs-lookup"><span data-stu-id="4beb4-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="4beb4-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="4beb4-114">maxPendingConnections</span></span>|<span data-ttu-id="4beb4-115">Gibt die maximale Anzahl von Verbindungen an, die im Dienst zum Verteilen bereitstehen.</span><span class="sxs-lookup"><span data-stu-id="4beb4-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="4beb4-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="4beb4-116">receiveBufferSize</span></span>|<span data-ttu-id="4beb4-117">Gibt die Größe des Empfangspuffers an.</span><span class="sxs-lookup"><span data-stu-id="4beb4-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="4beb4-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="4beb4-118">sendBufferSize</span></span>|<span data-ttu-id="4beb4-119">Gibt die Größe des Sendepuffers an.</span><span class="sxs-lookup"><span data-stu-id="4beb4-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="4beb4-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="4beb4-120">subProtocol</span></span>|<span data-ttu-id="4beb4-121">Gibt das WebSocket-Unterprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="4beb4-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="4beb4-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="4beb4-122">transportUsage</span></span>|<span data-ttu-id="4beb4-123">Gibt an, wann WebSockets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4beb4-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="4beb4-124">transportUsage-Attribut</span><span class="sxs-lookup"><span data-stu-id="4beb4-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="4beb4-125">Wert</span><span class="sxs-lookup"><span data-stu-id="4beb4-125">Value</span></span>|<span data-ttu-id="4beb4-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4beb4-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4beb4-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="4beb4-127">WhenDuplex</span></span>|<span data-ttu-id="4beb4-128">Verwendet das WebSocket-Protokoll bei einem Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="4beb4-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="4beb4-129">Always</span><span class="sxs-lookup"><span data-stu-id="4beb4-129">Always</span></span>|<span data-ttu-id="4beb4-130">Verwendet immer das WebSocket-Protokoll unabhängig vom Vertrag.</span><span class="sxs-lookup"><span data-stu-id="4beb4-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="4beb4-131">Nie</span><span class="sxs-lookup"><span data-stu-id="4beb4-131">Never</span></span>|<span data-ttu-id="4beb4-132">Verwendet niemals das WebSocket-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="4beb4-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4beb4-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4beb4-133">Child Elements</span></span>  

 <span data-ttu-id="4beb4-134">Keine</span><span class="sxs-lookup"><span data-stu-id="4beb4-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4beb4-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4beb4-135">Parent Elements</span></span>  
  
|<span data-ttu-id="4beb4-136">Element</span><span class="sxs-lookup"><span data-stu-id="4beb4-136">Element</span></span>|<span data-ttu-id="4beb4-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4beb4-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="4beb4-138">Gibt das NetHttpBinding-Element an.</span><span class="sxs-lookup"><span data-stu-id="4beb4-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4beb4-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4beb4-139">Example</span></span>  

 <span data-ttu-id="4beb4-140">Im folgenden Beispiel wird die Verwendung des \<webSocketSettings>-Elements veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4beb4-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4beb4-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4beb4-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="4beb4-142">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4beb4-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4beb4-143">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="4beb4-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4beb4-144">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4beb4-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
