---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772410"
---
# <a name="namespacetable"></a><span data-ttu-id="bb99f-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="bb99f-101">\<namespaceTable></span></span>

<span data-ttu-id="bb99f-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bb99f-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="bb99f-103">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="bb99f-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="bb99f-104">&nbsp;&nbsp;**\<routing>** </span><span class="sxs-lookup"><span data-stu-id="bb99f-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="bb99f-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="bb99f-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="bb99f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb99f-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb99f-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb99f-107">Attributes and elements</span></span>

<span data-ttu-id="bb99f-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb99f-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bb99f-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb99f-109">Attributes</span></span>

<span data-ttu-id="bb99f-110">Keiner</span><span class="sxs-lookup"><span data-stu-id="bb99f-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="bb99f-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb99f-111">Child elements</span></span>

|     | <span data-ttu-id="bb99f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb99f-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bb99f-113">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="bb99f-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="bb99f-114">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="bb99f-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="bb99f-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb99f-115">Parent elements</span></span>

|     | <span data-ttu-id="bb99f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb99f-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="bb99f-117">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="bb99f-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="bb99f-118">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="bb99f-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="bb99f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb99f-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
