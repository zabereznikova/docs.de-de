---
title: <filters> von <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855240"
---
# <a name="filters-of-routing"></a><span data-ttu-id="32284-102">\<filters> von \<routing></span><span class="sxs-lookup"><span data-stu-id="32284-102">\<filters> of \<routing></span></span>

<span data-ttu-id="32284-103">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="32284-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**  
  
## <a name="syntax"></a><span data-ttu-id="32284-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32284-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32284-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32284-105">Attributes and elements</span></span>

<span data-ttu-id="32284-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32284-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="32284-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="32284-107">Attributes</span></span>

<span data-ttu-id="32284-108">Keine</span><span class="sxs-lookup"><span data-stu-id="32284-108">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="32284-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32284-109">Child elements</span></span>

|     | <span data-ttu-id="32284-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32284-110">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="32284-111">Enthält einen Routing Filter, der den Typ des Windows Communication Foundation (WCF) bestimmt, der <xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="32284-111">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="32284-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32284-112">Parent elements</span></span>

|     | <span data-ttu-id="32284-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32284-113">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="32284-114">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="32284-114">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="32284-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32284-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
