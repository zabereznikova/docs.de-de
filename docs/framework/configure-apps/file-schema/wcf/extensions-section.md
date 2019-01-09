---
title: '&lt;extensions&gt;-Abschnitt'
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 92dd3c528290344d9537c51fccf7c13c74c1984a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145314"
---
# <a name="ltextensionsgt-section"></a><span data-ttu-id="c07e1-102">&lt;extensions&gt;-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c07e1-102">&lt;extensions&gt; section</span></span>
<span data-ttu-id="c07e1-103">Dieser Konfigurationsabschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte der Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="c07e1-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="c07e1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c07e1-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c07e1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c07e1-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c07e1-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c07e1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c07e1-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c07e1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c07e1-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="c07e1-108">Attributes</span></span>  
 <span data-ttu-id="c07e1-109">Keine</span><span class="sxs-lookup"><span data-stu-id="c07e1-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c07e1-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c07e1-110">Child Elements</span></span>  
  
|<span data-ttu-id="c07e1-111">Element</span><span class="sxs-lookup"><span data-stu-id="c07e1-111">Element</span></span>|<span data-ttu-id="c07e1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c07e1-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c07e1-113">\<BehaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="c07e1-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="c07e1-114">Dieser Abschnitt enthält Unterelemente mit Verhaltenserweiterungen, die es dem Benutzer ermöglichen, das Verhalten eines Diensts oder Endpunkts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c07e1-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="c07e1-115">\<BindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="c07e1-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="c07e1-116">Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c07e1-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="c07e1-117">\<BindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="c07e1-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="c07e1-118">Dieser Abschnitt enthält Unterelemente mit Bindungserweiterungen, die es dem Benutzer ermöglichen, Bindungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="c07e1-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="c07e1-119">\<EndpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="c07e1-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="c07e1-120">Dieser Abschnitt enthält untergeordnete Elemente, die Standardendpunkte registrieren.</span><span class="sxs-lookup"><span data-stu-id="c07e1-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c07e1-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c07e1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c07e1-122">Element</span><span class="sxs-lookup"><span data-stu-id="c07e1-122">Element</span></span>|<span data-ttu-id="c07e1-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c07e1-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c07e1-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c07e1-124">system.ServiceModel</span></span>|<span data-ttu-id="c07e1-125">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="c07e1-125">The root element of all WCF configuration elements.</span></span>|
