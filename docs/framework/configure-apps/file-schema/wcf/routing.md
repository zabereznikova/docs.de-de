---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399963"
---
# \<routing>

<span data-ttu-id="2401d-101">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2401d-101">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**
  
## <a name="syntax"></a><span data-ttu-id="2401d-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="2401d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2401d-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2401d-103">Attributes and elements</span></span>

<span data-ttu-id="2401d-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2401d-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2401d-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="2401d-105">Attributes</span></span>

<span data-ttu-id="2401d-106">Keine</span><span class="sxs-lookup"><span data-stu-id="2401d-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="2401d-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2401d-107">Child elements</span></span>

|     | <span data-ttu-id="2401d-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2401d-108">Description</span></span> |
| --- | ----------- |
| [**\<filters>**](filters-of-routing.md) | <span data-ttu-id="2401d-109">Enthält einen Satz von Routing filtern, die den Typ der Windows Communication Foundation (WCF)-MessageFilter bestimmen, der beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2401d-109">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [**\<filterTables>**](filtertables.md) | <span data-ttu-id="2401d-110">Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2401d-110">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="2401d-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2401d-111">Parent elements</span></span>

|     | <span data-ttu-id="2401d-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2401d-112">Description</span></span> |
| --- | ----------- |
| **\<system.ServiceModel>** | <span data-ttu-id="2401d-113">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="2401d-113">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2401d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2401d-114">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
