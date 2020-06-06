---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738790"
---
# \<oneWay>
<span data-ttu-id="987ea-101">Aktiviert Paketrouting und die Verwendung von unidirektionalen Methoden für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="987ea-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="987ea-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="987ea-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="987ea-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="987ea-103">Attributes and Elements</span></span>  
 <span data-ttu-id="987ea-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="987ea-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="987ea-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="987ea-105">Attributes</span></span>  
  
|<span data-ttu-id="987ea-106">attribute</span><span class="sxs-lookup"><span data-stu-id="987ea-106">Attribute</span></span>|<span data-ttu-id="987ea-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="987ea-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="987ea-108">Ein boolescher Wert, der angibt, ob Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="987ea-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="987ea-109">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="987ea-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="987ea-110">Eine ganze Zahl, die die maximale Anzahl an Kanälen angibt, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="987ea-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="987ea-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="987ea-111">Child Elements</span></span>  
  
|<span data-ttu-id="987ea-112">Element</span><span class="sxs-lookup"><span data-stu-id="987ea-112">Element</span></span>|<span data-ttu-id="987ea-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="987ea-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="987ea-114">Ein <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>-Objekt, das Eigenschaften des Kanalpools für den aktuellen Kanal enthält.</span><span class="sxs-lookup"><span data-stu-id="987ea-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="987ea-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="987ea-115">Parent Elements</span></span>  
  
|<span data-ttu-id="987ea-116">Element</span><span class="sxs-lookup"><span data-stu-id="987ea-116">Element</span></span>|<span data-ttu-id="987ea-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="987ea-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="987ea-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="987ea-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="987ea-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="987ea-119">Remarks</span></span>  
 <span data-ttu-id="987ea-120">Zum Aktivieren von Paketrouting ist eine unidirektionale Konvertierungsebene erforderlich, die von diesem Element bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="987ea-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="987ea-121">Ein Benutzer kann eine benutzerdefinierte Bindung erstellen, die diese Bindung über einen sitzungsfähigen oder Anforderungs-/Antworttransport schichtet, damit er für das Paketrouting aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="987ea-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="987ea-122">Das Element ist auch nützlich, wenn Sie unidirektionale Methoden auf systemeigenere Weise verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="987ea-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="987ea-123">Auf diese Schickt können weitere Transformationen angewendet werden, zum Beispiel Composite Duplex und Reliable Messaging.</span><span class="sxs-lookup"><span data-stu-id="987ea-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987ea-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="987ea-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="987ea-125">Bindungen</span><span class="sxs-lookup"><span data-stu-id="987ea-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="987ea-126">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="987ea-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="987ea-127">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="987ea-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
