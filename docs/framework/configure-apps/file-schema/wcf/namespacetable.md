---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855097"
---
# <a name="namespacetable"></a><span data-ttu-id="47382-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="47382-101">\<namespaceTable></span></span>

<span data-ttu-id="47382-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="47382-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="47382-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="47382-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="47382-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="47382-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="47382-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="47382-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="47382-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namespacetable->**</span><span class="sxs-lookup"><span data-stu-id="47382-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47382-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="47382-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47382-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="47382-108">Attributes and elements</span></span>

<span data-ttu-id="47382-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="47382-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="47382-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="47382-110">Attributes</span></span>

<span data-ttu-id="47382-111">None</span><span class="sxs-lookup"><span data-stu-id="47382-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="47382-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47382-112">Child elements</span></span>

|     | <span data-ttu-id="47382-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47382-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="47382-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="47382-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="47382-115">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="47382-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="47382-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="47382-116">Parent elements</span></span>

|     | <span data-ttu-id="47382-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="47382-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="47382-118"> **\<Routing >** </span><span class="sxs-lookup"><span data-stu-id="47382-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="47382-119">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="47382-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="47382-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47382-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
