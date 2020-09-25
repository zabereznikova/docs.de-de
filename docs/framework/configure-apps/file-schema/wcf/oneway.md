---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 92cd6b280305c223ee125a45724691c5205ce3c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195011"
---
# \<oneWay>

<span data-ttu-id="87d0a-101">Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="87d0a-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="87d0a-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="87d0a-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87d0a-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="87d0a-103">Attributes and Elements</span></span>  

 <span data-ttu-id="87d0a-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87d0a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87d0a-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="87d0a-105">Attributes</span></span>  
  
|<span data-ttu-id="87d0a-106">attribute</span><span class="sxs-lookup"><span data-stu-id="87d0a-106">Attribute</span></span>|<span data-ttu-id="87d0a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87d0a-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="87d0a-108">Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="87d0a-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="87d0a-109">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="87d0a-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="87d0a-110">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="87d0a-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87d0a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87d0a-111">Child Elements</span></span>  
  
|<span data-ttu-id="87d0a-112">Element</span><span class="sxs-lookup"><span data-stu-id="87d0a-112">Element</span></span>|<span data-ttu-id="87d0a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87d0a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="87d0a-114">Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.</span><span class="sxs-lookup"><span data-stu-id="87d0a-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87d0a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="87d0a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="87d0a-116">Element</span><span class="sxs-lookup"><span data-stu-id="87d0a-116">Element</span></span>|<span data-ttu-id="87d0a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87d0a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="87d0a-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="87d0a-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87d0a-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="87d0a-119">Remarks</span></span>  

 <span data-ttu-id="87d0a-120">Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="87d0a-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="87d0a-121">Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs-/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="87d0a-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="87d0a-122">Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="87d0a-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="87d0a-123">Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="87d0a-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d0a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87d0a-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="87d0a-125">Bindungen</span><span class="sxs-lookup"><span data-stu-id="87d0a-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="87d0a-126">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="87d0a-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="87d0a-127">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="87d0a-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
