---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 35af7f5e10594617807384c20ab706ad675d11ef
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="99bb3-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="99bb3-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="99bb3-103">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99bb3-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="99bb3-104">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="99bb3-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="99bb3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99bb3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="99bb3-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="99bb3-106">\<bindings></span></span>  
<span data-ttu-id="99bb3-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99bb3-107">\<customBinding></span></span>  
<span data-ttu-id="99bb3-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="99bb3-108">\<binding></span></span>  
<span data-ttu-id="99bb3-109">\<UseManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="99bb3-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99bb3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="99bb3-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99bb3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="99bb3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="99bb3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="99bb3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99bb3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="99bb3-113">Attributes</span></span>  
 <span data-ttu-id="99bb3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="99bb3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99bb3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99bb3-115">Child Elements</span></span>  
 <span data-ttu-id="99bb3-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="99bb3-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99bb3-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="99bb3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="99bb3-118">Element</span><span class="sxs-lookup"><span data-stu-id="99bb3-118">Element</span></span>|<span data-ttu-id="99bb3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99bb3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99bb3-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="99bb3-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="99bb3-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="99bb3-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99bb3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99bb3-122">Remarks</span></span>  
 <span data-ttu-id="99bb3-123">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99bb3-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="99bb3-124">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="99bb3-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bb3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99bb3-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="99bb3-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="99bb3-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="99bb3-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="99bb3-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="99bb3-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="99bb3-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="99bb3-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="99bb3-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
