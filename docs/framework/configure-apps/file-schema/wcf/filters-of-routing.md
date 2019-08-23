---
title: <filters> von <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925620"
---
# <a name="filters-of-routing"></a><span data-ttu-id="2727a-102">\<filtert > \<der Routing ></span><span class="sxs-lookup"><span data-stu-id="2727a-102">\<filters> of \<routing></span></span>

<span data-ttu-id="2727a-103">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2727a-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="2727a-104">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="2727a-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="2727a-105">&nbsp;&nbsp;[ **\<Routing >** ](routing.md) </span><span class="sxs-lookup"><span data-stu-id="2727a-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="2727a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="2727a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="2727a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2727a-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2727a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2727a-108">Attributes and elements</span></span>

<span data-ttu-id="2727a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2727a-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2727a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2727a-110">Attributes</span></span>

<span data-ttu-id="2727a-111">None</span><span class="sxs-lookup"><span data-stu-id="2727a-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="2727a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2727a-112">Child elements</span></span>

|     | <span data-ttu-id="2727a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2727a-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2727a-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="2727a-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="2727a-115">Enthält einen Routing Filter, der den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2727a-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="2727a-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2727a-116">Parent elements</span></span>

|     | <span data-ttu-id="2727a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2727a-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="2727a-118"> **\<Routing >** </span><span class="sxs-lookup"><span data-stu-id="2727a-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="2727a-119">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2727a-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2727a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2727a-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
