---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="c9435-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="c9435-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="c9435-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c9435-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="c9435-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="c9435-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="c9435-105">&nbsp;&nbsp;**\<Routing >** </span><span class="sxs-lookup"><span data-stu-id="c9435-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="c9435-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NamespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="c9435-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c9435-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9435-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="c9435-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c9435-108">Attributes and elements</span></span>

<span data-ttu-id="c9435-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9435-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c9435-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c9435-110">Attributes</span></span>

<span data-ttu-id="c9435-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="c9435-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c9435-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9435-112">Child elements</span></span>

|     | <span data-ttu-id="c9435-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9435-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c9435-114">**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="c9435-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="c9435-115">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="c9435-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c9435-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9435-116">Parent elements</span></span>

|     | <span data-ttu-id="c9435-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9435-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c9435-118">**\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="c9435-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c9435-119">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) zu bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="c9435-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c9435-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9435-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
