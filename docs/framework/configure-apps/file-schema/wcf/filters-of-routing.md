---
title: '&lt;filters&gt; von &lt;routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2687101aa868ae77ce0ae818afd9df906f8525c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="ed560-102">&lt;filters&gt; von &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="ed560-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="ed560-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der beim Auswerten eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ed560-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="ed560-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="ed560-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="ed560-105">&nbsp;&nbsp;[**\<Routing >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="ed560-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="ed560-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="ed560-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ed560-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed560-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ed560-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed560-108">Attributes and elements</span></span>

<span data-ttu-id="ed560-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed560-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ed560-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed560-110">Attributes</span></span>

<span data-ttu-id="ed560-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="ed560-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="ed560-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed560-112">Child elements</span></span>

|     | <span data-ttu-id="ed560-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed560-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ed560-114">**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="ed560-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="ed560-115">Enthält einen Routingfilter, der bestimmt, welche [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> werden beim Auswerten eingehender Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed560-115">Contains a routing filter that determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="ed560-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed560-116">Parent elements</span></span>

|     | <span data-ttu-id="ed560-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed560-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ed560-118">**\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="ed560-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="ed560-119">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die bestimmen, welche [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die definieren, die Zielendpunkte zum Senden von Nachrichten, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ed560-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ed560-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed560-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
