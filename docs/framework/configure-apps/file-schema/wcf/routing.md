---
title: '&lt;Routing&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 220c18ab8ea6222fcf7d9fb8a93950281c9de796
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145145"
---
# <a name="ltroutinggt"></a><span data-ttu-id="11566-102">&lt;Routing&gt;</span><span class="sxs-lookup"><span data-stu-id="11566-102">&lt;routing&gt;</span></span>

<span data-ttu-id="11566-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="11566-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="11566-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="11566-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="11566-105">&nbsp;&nbsp;**\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="11566-105">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="11566-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="11566-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11566-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="11566-107">Attributes and elements</span></span>

<span data-ttu-id="11566-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="11566-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="11566-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="11566-109">Attributes</span></span>

<span data-ttu-id="11566-110">Keine</span><span class="sxs-lookup"><span data-stu-id="11566-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="11566-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11566-111">Child elements</span></span>

|     | <span data-ttu-id="11566-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11566-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="11566-113">**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="11566-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="11566-114">Enthält einen Satz von routingfiltern, die bestimmen, dass der Typ des Windows Communication Foundation (WCF)-MessageFilter beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11566-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="11566-115">**\<FilterTables >**</span><span class="sxs-lookup"><span data-stu-id="11566-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="11566-116">Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11566-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="11566-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="11566-117">Parent elements</span></span>

|     | <span data-ttu-id="11566-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11566-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="11566-119">**\<System. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="11566-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="11566-120">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="11566-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="11566-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11566-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
