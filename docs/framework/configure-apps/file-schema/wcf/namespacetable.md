---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933169"
---
# <a name="namespacetable"></a><span data-ttu-id="f0b26-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="f0b26-101">\<namespaceTable></span></span>

<span data-ttu-id="f0b26-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f0b26-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="f0b26-103">**\<system.serviceModel>**  </span><span class="sxs-lookup"><span data-stu-id="f0b26-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="f0b26-104">&nbsp;&nbsp; **\<Routing >**  </span><span class="sxs-lookup"><span data-stu-id="f0b26-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="f0b26-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<namespacetable->**</span><span class="sxs-lookup"><span data-stu-id="f0b26-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f0b26-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0b26-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0b26-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f0b26-107">Attributes and elements</span></span>

<span data-ttu-id="f0b26-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f0b26-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f0b26-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f0b26-109">Attributes</span></span>

<span data-ttu-id="f0b26-110">None</span><span class="sxs-lookup"><span data-stu-id="f0b26-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="f0b26-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0b26-111">Child elements</span></span>

|     | <span data-ttu-id="f0b26-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0b26-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f0b26-113"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="f0b26-113">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="f0b26-114">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="f0b26-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="f0b26-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f0b26-115">Parent elements</span></span>

|     | <span data-ttu-id="f0b26-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0b26-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f0b26-117"> **\<Routing >** </span><span class="sxs-lookup"><span data-stu-id="f0b26-117">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="f0b26-118">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f0b26-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f0b26-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0b26-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
