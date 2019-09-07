---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399963"
---
# <a name="routing"></a><span data-ttu-id="a6656-101">\<routing></span><span class="sxs-lookup"><span data-stu-id="a6656-101">\<routing></span></span>

<span data-ttu-id="a6656-102">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a6656-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="a6656-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a6656-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a6656-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a6656-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a6656-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="a6656-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="a6656-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6656-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6656-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a6656-107">Attributes and elements</span></span>

<span data-ttu-id="a6656-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6656-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a6656-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="a6656-109">Attributes</span></span>

<span data-ttu-id="a6656-110">None</span><span class="sxs-lookup"><span data-stu-id="a6656-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="a6656-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6656-111">Child elements</span></span>

|     | <span data-ttu-id="a6656-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6656-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a6656-113"> **\<filters>** </span><span class="sxs-lookup"><span data-stu-id="a6656-113">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="a6656-114">Enthält einen Satz von Routing filtern, die den Typ der Windows Communication Foundation (WCF)-MessageFilter bestimmen, der beim Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6656-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="a6656-115"> **\<filterTables>** </span><span class="sxs-lookup"><span data-stu-id="a6656-115">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="a6656-116">Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6656-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="a6656-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6656-117">Parent elements</span></span>

|     | <span data-ttu-id="a6656-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6656-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="a6656-119">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="a6656-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="a6656-120">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="a6656-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a6656-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6656-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
