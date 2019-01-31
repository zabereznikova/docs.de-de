---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275573"
---
# <a name="routing"></a><span data-ttu-id="8c118-101">\<routing></span><span class="sxs-lookup"><span data-stu-id="8c118-101">\<routing></span></span>

<span data-ttu-id="8c118-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="8c118-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="8c118-103">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="8c118-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="8c118-104">&nbsp;&nbsp;**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="8c118-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8c118-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c118-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c118-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8c118-106">Attributes and elements</span></span>

<span data-ttu-id="8c118-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c118-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c118-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="8c118-108">Attributes</span></span>

<span data-ttu-id="8c118-109">Keine</span><span class="sxs-lookup"><span data-stu-id="8c118-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c118-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c118-110">Child elements</span></span>

|     | <span data-ttu-id="8c118-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c118-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8c118-112">**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="8c118-112">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="8c118-113">Enthält einen Satz von routingfiltern, die bestimmen, dass der Typ des Windows Communication Foundation (WCF)-MessageFilter beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c118-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="8c118-114">**\<filterTables>**</span><span class="sxs-lookup"><span data-stu-id="8c118-114">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="8c118-115">Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8c118-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="8c118-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c118-116">Parent elements</span></span>

|     | <span data-ttu-id="8c118-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c118-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="8c118-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="8c118-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="8c118-119">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="8c118-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8c118-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c118-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
