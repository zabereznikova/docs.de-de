---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855097"
---
# \<namespaceTable>

<span data-ttu-id="baa76-101">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Elementen dar, die Namespace-/Präfix-Zuordnungen enthalten, die zu Routingzwecken in XPath-Filtern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="baa76-101">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**  
  
## <a name="syntax"></a><span data-ttu-id="baa76-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="baa76-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="baa76-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="baa76-103">Attributes and elements</span></span>

<span data-ttu-id="baa76-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="baa76-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="baa76-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="baa76-105">Attributes</span></span>

<span data-ttu-id="baa76-106">Keine</span><span class="sxs-lookup"><span data-stu-id="baa76-106">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="baa76-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baa76-107">Child elements</span></span>

|     | <span data-ttu-id="baa76-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="baa76-108">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="baa76-109">Definiert eine für XPath-Ausdrücke verwendete Namespace-/Präfix-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="baa76-109">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="baa76-110">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baa76-110">Parent elements</span></span>

|     | <span data-ttu-id="baa76-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="baa76-111">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="baa76-112">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="baa76-112">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="baa76-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="baa76-113">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
