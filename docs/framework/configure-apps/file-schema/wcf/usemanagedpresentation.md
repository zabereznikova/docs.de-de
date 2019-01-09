---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: a60e1e16b9b41cc5df4ded51cc05d6109dd7b3dc
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147706"
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="99dd9-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="99dd9-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="99dd9-103">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99dd9-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="99dd9-104">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="99dd9-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="99dd9-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99dd9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="99dd9-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="99dd9-106">\<bindings></span></span>  
<span data-ttu-id="99dd9-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99dd9-107">\<customBinding></span></span>  
<span data-ttu-id="99dd9-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="99dd9-108">\<binding></span></span>  
<span data-ttu-id="99dd9-109">\<UseManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="99dd9-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99dd9-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="99dd9-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99dd9-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99dd9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99dd9-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99dd9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99dd9-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="99dd9-113">Attributes</span></span>  
 <span data-ttu-id="99dd9-114">Keine</span><span class="sxs-lookup"><span data-stu-id="99dd9-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99dd9-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99dd9-115">Child Elements</span></span>  
 <span data-ttu-id="99dd9-116">Keine</span><span class="sxs-lookup"><span data-stu-id="99dd9-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99dd9-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99dd9-117">Parent Elements</span></span>  
  
|<span data-ttu-id="99dd9-118">Element</span><span class="sxs-lookup"><span data-stu-id="99dd9-118">Element</span></span>|<span data-ttu-id="99dd9-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99dd9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99dd9-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="99dd9-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="99dd9-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="99dd9-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99dd9-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99dd9-122">Remarks</span></span>  
 <span data-ttu-id="99dd9-123">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99dd9-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="99dd9-124">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="99dd9-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99dd9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99dd9-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="99dd9-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="99dd9-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="99dd9-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="99dd9-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="99dd9-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="99dd9-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="99dd9-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99dd9-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
