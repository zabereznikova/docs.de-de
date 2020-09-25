---
title: <extensions> Sektions
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: f3eb5d446291dfa6b7c8e0f1ee2b6a5cf53c2162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185781"
---
# <a name="extensions-section"></a><span data-ttu-id="ae6c6-102">\<extensions> Sektions</span><span class="sxs-lookup"><span data-stu-id="ae6c6-102">\<extensions> section</span></span>

<span data-ttu-id="ae6c6-103">Dieser Konfigurationsabschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte der Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="ae6c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae6c6-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae6c6-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae6c6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ae6c6-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae6c6-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae6c6-107">Attributes</span></span>  

 <span data-ttu-id="ae6c6-108">Keine</span><span class="sxs-lookup"><span data-stu-id="ae6c6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae6c6-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae6c6-109">Child Elements</span></span>  
  
|<span data-ttu-id="ae6c6-110">Element</span><span class="sxs-lookup"><span data-stu-id="ae6c6-110">Element</span></span>|<span data-ttu-id="ae6c6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae6c6-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="ae6c6-112">Dieser Abschnitt enthält Unterelemente mit Verhaltenserweiterungen, die es dem Benutzer ermöglichen, das Verhalten eines Diensts oder Endpunkts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="ae6c6-113">Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="ae6c6-114">Dieser Abschnitt enthält Unterelemente mit Bindungserweiterungen, die es dem Benutzer ermöglichen, Bindungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="ae6c6-115">Dieser Abschnitt enthält untergeordnete Elemente, die Standardendpunkte registrieren.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae6c6-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae6c6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ae6c6-117">Element</span><span class="sxs-lookup"><span data-stu-id="ae6c6-117">Element</span></span>|<span data-ttu-id="ae6c6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae6c6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae6c6-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ae6c6-119">system.ServiceModel</span></span>|<span data-ttu-id="ae6c6-120">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="ae6c6-120">The root element of all WCF configuration elements.</span></span>|
