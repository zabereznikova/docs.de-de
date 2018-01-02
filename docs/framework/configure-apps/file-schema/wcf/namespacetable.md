---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28bbeae9d1dbe43ad787c391ae461b44a8e85147
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="0e1af-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="0e1af-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="0e1af-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0e1af-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="0e1af-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="0e1af-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="0e1af-105">&nbsp;&nbsp;**\<Routing >** </span><span class="sxs-lookup"><span data-stu-id="0e1af-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="0e1af-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NamespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="0e1af-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0e1af-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e1af-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="0e1af-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0e1af-108">Attributes and elements</span></span>

<span data-ttu-id="0e1af-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e1af-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0e1af-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0e1af-110">Attributes</span></span>

<span data-ttu-id="0e1af-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="0e1af-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="0e1af-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e1af-112">Child elements</span></span>

|     | <span data-ttu-id="0e1af-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e1af-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0e1af-114">**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="0e1af-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="0e1af-115">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="0e1af-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="0e1af-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0e1af-116">Parent elements</span></span>

|     | <span data-ttu-id="0e1af-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e1af-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0e1af-118">**\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="0e1af-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="0e1af-119">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die bestimmen, welche [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die definieren, die Zielendpunkte zum Senden von Nachrichten, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="0e1af-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="0e1af-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e1af-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
