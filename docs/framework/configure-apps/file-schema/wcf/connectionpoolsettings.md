---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400472"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="31215-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="31215-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="31215-102">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="31215-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
<span data-ttu-id="31215-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="31215-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="31215-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="31215-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="31215-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="31215-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="31215-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="31215-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="31215-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="31215-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="31215-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedPipeTransport->** ](namedpipetransport.md)</span><span class="sxs-lookup"><span data-stu-id="31215-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)</span></span>\
<span data-ttu-id="31215-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionpoolsettings->**</span><span class="sxs-lookup"><span data-stu-id="31215-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31215-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="31215-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31215-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="31215-111">Attributes and Elements</span></span>  
 <span data-ttu-id="31215-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31215-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31215-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="31215-113">Attributes</span></span>  
  
|<span data-ttu-id="31215-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="31215-114">Attribute</span></span>|<span data-ttu-id="31215-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31215-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="31215-116">Eine Zeichenfolge, die den Namen des Verbindungspools für ausgehende Kanäle definiert.</span><span class="sxs-lookup"><span data-stu-id="31215-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="31215-117">Im Streammodus werden keine Verbindungen freigegeben, was bedeutet, dass Verbindungspooling deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="31215-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="31215-118">Der Standardwert ist eine "standardmäßige" Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="31215-118">The default is a "default" string.</span></span> <span data-ttu-id="31215-119">Sie können diesen Wert ändern, um die Verbindungen für einen bestimmten Client in separate Gruppen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="31215-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="31215-120">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, in der sich die Verbindung im Leerlauf befinden kann, bevor sie unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="31215-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="31215-121">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="31215-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="31215-122">Eine positive ganze Zahl, die die maximale Anzahl von Verbindungen zu einem Remoteendpunkt angibt, die vom Dienst initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="31215-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="31215-123">Verbindungen oberhalb des Limits werden in eine Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="31215-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="31215-124">`idleTimeout` schränkt die Dauer ein, in der Verbindungen in der Warteschlange bleiben können, bevor eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="31215-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="31215-125">Der Standard ist 10.</span><span class="sxs-lookup"><span data-stu-id="31215-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="31215-126">Dieses Attribut beschränkt die Anzahl gleichzeitiger aktiver Verbindungen vom Client zu einem bestimmten Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="31215-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="31215-127">Wenn dieser Wert durch zusätzliche aktive Clientverbindungen überstiegen wird, antwortet der Dienst dem Client möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="31215-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="31215-128">In diesem Fall sollte dieser Wert angepasst werden, um die maximale Anzahl der erwarteten gleichzeitigen Clientverbindungen in einem bestimmten Endpunkt zu übertreffen.</span><span class="sxs-lookup"><span data-stu-id="31215-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31215-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31215-129">Child Elements</span></span>  
 <span data-ttu-id="31215-130">Keine</span><span class="sxs-lookup"><span data-stu-id="31215-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31215-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="31215-131">Parent Elements</span></span>  
  
|<span data-ttu-id="31215-132">Element</span><span class="sxs-lookup"><span data-stu-id="31215-132">Element</span></span>|<span data-ttu-id="31215-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="31215-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31215-134">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="31215-134">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="31215-135">Definiert einen Transport, der bewirkt, dass ein Kanal Nachrichten mithilfe von benannten Pipes überträgt.</span><span class="sxs-lookup"><span data-stu-id="31215-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31215-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31215-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="31215-137">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="31215-137">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="31215-138">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="31215-138">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="31215-139">Bindungen</span><span class="sxs-lookup"><span data-stu-id="31215-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="31215-140">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="31215-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="31215-141">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="31215-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="31215-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="31215-142">\<customBinding></span></span>](custombinding.md)
