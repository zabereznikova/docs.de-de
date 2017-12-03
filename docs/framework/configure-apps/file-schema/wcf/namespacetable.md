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
ms.openlocfilehash: 4a6646b94449a79c96a8720a798f48298ab32ee0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="4302f-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="4302f-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="4302f-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4302f-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="4302f-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="4302f-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="4302f-105">&nbsp;&nbsp;**\<Routing >** </span><span class="sxs-lookup"><span data-stu-id="4302f-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="4302f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NamespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="4302f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4302f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="4302f-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="4302f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4302f-108">Attributes and elements</span></span>

<span data-ttu-id="4302f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4302f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4302f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="4302f-110">Attributes</span></span>

<span data-ttu-id="4302f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="4302f-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="4302f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4302f-112">Child elements</span></span>

|     | <span data-ttu-id="4302f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4302f-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4302f-114">**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="4302f-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="4302f-115">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="4302f-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="4302f-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4302f-116">Parent elements</span></span>

|     | <span data-ttu-id="4302f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4302f-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4302f-118">**\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="4302f-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="4302f-119">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie zum Definieren von Routingtabellen mit den Zielendpunkten, an die Nachrichten bei Filterübereinstimmung gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4302f-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4302f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4302f-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
