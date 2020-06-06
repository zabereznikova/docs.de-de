---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400472"
---
# \<connectionPoolSettings>
<span data-ttu-id="b51d5-101">Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.</span><span class="sxs-lookup"><span data-stu-id="b51d5-101">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="b51d5-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b51d5-102">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b51d5-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b51d5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b51d5-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b51d5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b51d5-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b51d5-105">Attributes</span></span>  
  
|<span data-ttu-id="b51d5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b51d5-106">Attribute</span></span>|<span data-ttu-id="b51d5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b51d5-107">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="b51d5-108">Eine Zeichenfolge, die den Namen des Verbindungspools für ausgehende Kanäle definiert.</span><span class="sxs-lookup"><span data-stu-id="b51d5-108">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="b51d5-109">Im Streammodus werden keine Verbindungen freigegeben, was bedeutet, dass Verbindungspooling deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="b51d5-109">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="b51d5-110">Der Standardwert ist eine "standardmäßige" Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b51d5-110">The default is a "default" string.</span></span> <span data-ttu-id="b51d5-111">Sie können diesen Wert ändern, um die Verbindungen für einen bestimmten Client in separate Gruppen zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="b51d5-111">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="b51d5-112">Eine positive <xref:System.TimeSpan>, die die maximale Zeit angibt, in der sich die Verbindung im Leerlauf befinden kann, bevor sie unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="b51d5-112">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="b51d5-113">Der Standardwert ist 00:02:00.</span><span class="sxs-lookup"><span data-stu-id="b51d5-113">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="b51d5-114">Eine positive ganze Zahl, die die maximale Anzahl von Verbindungen zu einem Remoteendpunkt angibt, die vom Dienst initiiert werden.</span><span class="sxs-lookup"><span data-stu-id="b51d5-114">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="b51d5-115">Verbindungen oberhalb des Limits werden in eine Warteschlange gestellt, bis unterhalb des Limits Speicherplatz verfügbar wird.</span><span class="sxs-lookup"><span data-stu-id="b51d5-115">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="b51d5-116">`idleTimeout` schränkt die Dauer ein, in der Verbindungen in der Warteschlange bleiben können, bevor eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b51d5-116">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="b51d5-117">Der Standardwert ist 10.</span><span class="sxs-lookup"><span data-stu-id="b51d5-117">The default is 10.</span></span><br /><br /> <span data-ttu-id="b51d5-118">Dieses Attribut beschränkt die Anzahl gleichzeitiger aktiver Verbindungen vom Client zu einem bestimmten Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="b51d5-118">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="b51d5-119">Wenn dieser Wert durch zusätzliche aktive Clientverbindungen überstiegen wird, antwortet der Dienst dem Client möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="b51d5-119">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="b51d5-120">In diesem Fall sollte dieser Wert angepasst werden, um die maximale Anzahl der erwarteten gleichzeitigen Clientverbindungen in einem bestimmten Endpunkt zu übertreffen.</span><span class="sxs-lookup"><span data-stu-id="b51d5-120">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b51d5-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b51d5-121">Child Elements</span></span>  
 <span data-ttu-id="b51d5-122">Keine</span><span class="sxs-lookup"><span data-stu-id="b51d5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b51d5-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b51d5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b51d5-124">Element</span><span class="sxs-lookup"><span data-stu-id="b51d5-124">Element</span></span>|<span data-ttu-id="b51d5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b51d5-125">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="b51d5-126">Definiert einen Transport, der bewirkt, dass ein Kanal Nachrichten mithilfe von benannten Pipes überträgt.</span><span class="sxs-lookup"><span data-stu-id="b51d5-126">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b51d5-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b51d5-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b51d5-128">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="b51d5-128">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="b51d5-129">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="b51d5-129">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="b51d5-130">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b51d5-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b51d5-131">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="b51d5-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b51d5-132">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="b51d5-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
