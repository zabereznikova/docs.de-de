---
title: <extensions>Sektions
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855354"
---
# <a name="extensions-section"></a><span data-ttu-id="a0be2-102">\<Erweiterungs > Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a0be2-102">\<extensions> section</span></span>
<span data-ttu-id="a0be2-103">Dieser Konfigurationsabschnitt enthält eine Auflistung von Erweiterungen, mit deren Hilfe der Benutzer benutzerdefinierte Bindungen, Verhalten und andere Aspekte der Erweiterungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="a0be2-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="a0be2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0be2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0be2-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a0be2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a0be2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Erweiterungen >**</span><span class="sxs-lookup"><span data-stu-id="a0be2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0be2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0be2-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0be2-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a0be2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a0be2-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a0be2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0be2-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a0be2-110">Attributes</span></span>  
 <span data-ttu-id="a0be2-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a0be2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0be2-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0be2-112">Child Elements</span></span>  
  
|<span data-ttu-id="a0be2-113">Element</span><span class="sxs-lookup"><span data-stu-id="a0be2-113">Element</span></span>|<span data-ttu-id="a0be2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0be2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0be2-115">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="a0be2-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="a0be2-116">Dieser Abschnitt enthält Unterelemente mit Verhaltenserweiterungen, die es dem Benutzer ermöglichen, das Verhalten eines Diensts oder Endpunkts anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a0be2-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="a0be2-117">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="a0be2-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="a0be2-118">Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a0be2-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="a0be2-119">\<bindingextensions-></span><span class="sxs-lookup"><span data-stu-id="a0be2-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="a0be2-120">Dieser Abschnitt enthält Unterelemente mit Bindungserweiterungen, die es dem Benutzer ermöglichen, Bindungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a0be2-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="a0be2-121">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="a0be2-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="a0be2-122">Dieser Abschnitt enthält untergeordnete Elemente, die Standardendpunkte registrieren.</span><span class="sxs-lookup"><span data-stu-id="a0be2-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0be2-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a0be2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0be2-124">Element</span><span class="sxs-lookup"><span data-stu-id="a0be2-124">Element</span></span>|<span data-ttu-id="a0be2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0be2-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0be2-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a0be2-126">system.ServiceModel</span></span>|<span data-ttu-id="a0be2-127">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="a0be2-127">The root element of all WCF configuration elements.</span></span>|
