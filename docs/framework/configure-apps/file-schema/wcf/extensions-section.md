---
title: <extensions>Sektions
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855354"
---
# <a name="extensions-section"></a><span data-ttu-id="fe641-102">\<extensions>Sektions</span><span class="sxs-lookup"><span data-stu-id="fe641-102">\<extensions> section</span></span>
<span data-ttu-id="fe641-103">Dieser Konfigurationsabschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte der Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="fe641-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**  
  
## <a name="syntax"></a><span data-ttu-id="fe641-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe641-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe641-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe641-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fe641-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe641-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe641-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe641-107">Attributes</span></span>  
 <span data-ttu-id="fe641-108">Keine</span><span class="sxs-lookup"><span data-stu-id="fe641-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fe641-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe641-109">Child Elements</span></span>  
  
|<span data-ttu-id="fe641-110">Element</span><span class="sxs-lookup"><span data-stu-id="fe641-110">Element</span></span>|<span data-ttu-id="fe641-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe641-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviorExtensions>](behaviorextensions.md)|<span data-ttu-id="fe641-112">Dieser Abschnitt enthält Unterelemente mit Verhaltenserweiterungen, die es dem Benutzer ermöglichen, das Verhalten eines Diensts oder Endpunkts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="fe641-112">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[\<bindingElementExtensions>](bindingelementextensions.md)|<span data-ttu-id="fe641-113">Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fe641-113">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[\<bindingExtensions>](bindingextensions.md)|<span data-ttu-id="fe641-114">Dieser Abschnitt enthält Unterelemente mit Bindungserweiterungen, die es dem Benutzer ermöglichen, Bindungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="fe641-114">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[\<endpointExtensions>](endpointextensions.md)|<span data-ttu-id="fe641-115">Dieser Abschnitt enthält untergeordnete Elemente, die Standardendpunkte registrieren.</span><span class="sxs-lookup"><span data-stu-id="fe641-115">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe641-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe641-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fe641-117">Element</span><span class="sxs-lookup"><span data-stu-id="fe641-117">Element</span></span>|<span data-ttu-id="fe641-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe641-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe641-119">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe641-119">system.ServiceModel</span></span>|<span data-ttu-id="fe641-120">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="fe641-120">The root element of all WCF configuration elements.</span></span>|
