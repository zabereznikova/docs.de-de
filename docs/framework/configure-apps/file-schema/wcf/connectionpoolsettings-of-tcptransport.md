---
title: <connectionPoolSettings> von <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398097"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="e91d7-102">\<connectionPoolSettings> von \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="e91d7-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="e91d7-103">Gibt zusätzliche Verbindungspooleinstellungen für einen TCP-Transport an.</span><span class="sxs-lookup"><span data-stu-id="e91d7-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="e91d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e91d7-104">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e91d7-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e91d7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e91d7-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e91d7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e91d7-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e91d7-107">Attributes</span></span>  
  
|<span data-ttu-id="e91d7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e91d7-108">Attribute</span></span>|<span data-ttu-id="e91d7-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e91d7-109">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="e91d7-110">Eine Zeichenfolge, die den Namen des Verbindungspools für ausgehende Kanäle definiert.</span><span class="sxs-lookup"><span data-stu-id="e91d7-110">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="e91d7-111">Im Streammodus werden keine Verbindungen freigegeben, was bedeutet, dass Verbindungspooling deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="e91d7-111">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="e91d7-112">Der Standardwert ist eine "standardmäßige" Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e91d7-112">The default is a "default" string.</span></span> <span data-ttu-id="e91d7-113">Sie können diesen Wert ändern, um die Verbindungen für einen bestimmten Client in separate Gruppen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="e91d7-113">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="e91d7-114">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, in der sich die Verbindung im Leerlauf befinden kann, bevor sie unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="e91d7-114">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="e91d7-115">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="e91d7-115">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="e91d7-116">Eine <xref:System.TimeSpan>, die angibt, wann eine aktive Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="e91d7-116">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="e91d7-117">Der Standardwert ist 00:05:00.</span><span class="sxs-lookup"><span data-stu-id="e91d7-117">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="e91d7-118">Eine Verbindung wird geschlossen, nachdem sie an den Verbindungscache zurückgegeben wurde, und nicht während einer aktiven Übertragung.</span><span class="sxs-lookup"><span data-stu-id="e91d7-118">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="e91d7-119">Der vom TCP-Transport verwendete Verbindungscache erstellt die für jeden Endpunkt erforderlichen neuen Verbindungen bis hin zu einem Cachelimit, das von `maxOutboundConnectionsPerEndpoint.` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e91d7-119">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="e91d7-120">Eine positive ganze Zahl, die die maximale Anzahl von Verbindungen zu einem Remoteendpunkt angibt, die vom Dienst initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="e91d7-120">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="e91d7-121">Verbindungen oberhalb des Limits werden in eine Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="e91d7-121">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="e91d7-122">`idleTimeout` schränkt die Dauer ein, in der Verbindungen in der Warteschlange bleiben können, bevor eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e91d7-122">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="e91d7-123">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="e91d7-123">The default is 10.</span></span><br /><br /> <span data-ttu-id="e91d7-124">Dieses Attribut beschränkt die Anzahl gleichzeitiger aktiver Verbindungen vom Client zu einem bestimmten Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="e91d7-124">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="e91d7-125">Wenn dieser Wert durch zusätzliche aktive Clientverbindungen überstiegen wird, antwortet der Dienst dem Client möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="e91d7-125">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="e91d7-126">In diesem Fall sollte dieser Wert angepasst werden, um die maximale Anzahl der erwarteten gleichzeitigen Clientverbindungen in einem bestimmten Endpunkt zu übertreffen.</span><span class="sxs-lookup"><span data-stu-id="e91d7-126">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e91d7-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e91d7-127">Child Elements</span></span>  
 <span data-ttu-id="e91d7-128">Keine</span><span class="sxs-lookup"><span data-stu-id="e91d7-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e91d7-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e91d7-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e91d7-130">Element</span><span class="sxs-lookup"><span data-stu-id="e91d7-130">Element</span></span>|<span data-ttu-id="e91d7-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e91d7-131">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="e91d7-132">Definiert einen Transport, der bewirkt, dass ein Kanal Nachrichten mithilfe von benannten Pipes überträgt.</span><span class="sxs-lookup"><span data-stu-id="e91d7-132">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e91d7-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e91d7-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e91d7-134">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="e91d7-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="e91d7-135">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="e91d7-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="e91d7-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e91d7-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e91d7-137">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="e91d7-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e91d7-138">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e91d7-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
