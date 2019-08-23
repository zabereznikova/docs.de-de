---
title: <extensions>Sektions
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 4c8b5fe6eef1863ee3f02cb761a3aac61406e446
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918971"
---
# <a name="extensions-section"></a><span data-ttu-id="b123a-102">\<Erweiterungs > Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b123a-102">\<extensions> section</span></span>
<span data-ttu-id="b123a-103">Dieser Konfigurationsabschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte der Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="b123a-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="b123a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b123a-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b123a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b123a-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b123a-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b123a-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b123a-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b123a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b123a-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b123a-108">Attributes</span></span>  
 <span data-ttu-id="b123a-109">Keine</span><span class="sxs-lookup"><span data-stu-id="b123a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b123a-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b123a-110">Child Elements</span></span>  
  
|<span data-ttu-id="b123a-111">Element</span><span class="sxs-lookup"><span data-stu-id="b123a-111">Element</span></span>|<span data-ttu-id="b123a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b123a-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b123a-113">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="b123a-113">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="b123a-114">Dieser Abschnitt enthält Unterelemente mit Verhaltenserweiterungen, die es dem Benutzer ermöglichen, das Verhalten eines Diensts oder Endpunkts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b123a-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="b123a-115">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="b123a-115">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="b123a-116">Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b123a-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="b123a-117">\<bindingextensions-></span><span class="sxs-lookup"><span data-stu-id="b123a-117">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="b123a-118">Dieser Abschnitt enthält Unterelemente mit Bindungserweiterungen, die es dem Benutzer ermöglichen, Bindungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b123a-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="b123a-119">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="b123a-119">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="b123a-120">Dieser Abschnitt enthält untergeordnete Elemente, die Standardendpunkte registrieren.</span><span class="sxs-lookup"><span data-stu-id="b123a-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b123a-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b123a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b123a-122">Element</span><span class="sxs-lookup"><span data-stu-id="b123a-122">Element</span></span>|<span data-ttu-id="b123a-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b123a-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b123a-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b123a-124">system.ServiceModel</span></span>|<span data-ttu-id="b123a-125">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="b123a-125">The root element of all WCF configuration elements.</span></span>|
