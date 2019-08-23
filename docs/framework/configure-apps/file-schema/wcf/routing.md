---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 3c7e9cb1284ab55c8dd199d9fb47a223698814f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934126"
---
# <a name="routing"></a><span data-ttu-id="14807-101">\<routing></span><span class="sxs-lookup"><span data-stu-id="14807-101">\<routing></span></span>

<span data-ttu-id="14807-102">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="14807-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="14807-103">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="14807-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="14807-104">&nbsp;&nbsp; **\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="14807-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="14807-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="14807-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14807-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14807-106">Attributes and elements</span></span>

<span data-ttu-id="14807-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14807-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="14807-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="14807-108">Attributes</span></span>

<span data-ttu-id="14807-109">None</span><span class="sxs-lookup"><span data-stu-id="14807-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="14807-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14807-110">Child elements</span></span>

|     | <span data-ttu-id="14807-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14807-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="14807-112"> **\<filters>** </span><span class="sxs-lookup"><span data-stu-id="14807-112">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="14807-113">Enthält einen Satz von Routing filtern, die den Typ der Windows Communication Foundation (WCF)-MessageFilter bestimmen, der beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14807-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="14807-114"> **\<filterTables>** </span><span class="sxs-lookup"><span data-stu-id="14807-114">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="14807-115">Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14807-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="14807-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14807-116">Parent elements</span></span>

|     | <span data-ttu-id="14807-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14807-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="14807-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="14807-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="14807-119">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="14807-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="14807-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14807-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
