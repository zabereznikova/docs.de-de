---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 96490421addfadd9cef6b65bddaed0aae3370d15
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720274"
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="bd314-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="bd314-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="bd314-103">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd314-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="bd314-104">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bd314-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="bd314-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bd314-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bd314-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="bd314-106">\<bindings></span></span>  
<span data-ttu-id="bd314-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bd314-107">\<customBinding></span></span>  
<span data-ttu-id="bd314-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="bd314-108">\<binding></span></span>  
<span data-ttu-id="bd314-109">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="bd314-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd314-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd314-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd314-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bd314-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bd314-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bd314-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd314-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bd314-113">Attributes</span></span>  
 <span data-ttu-id="bd314-114">Keine</span><span class="sxs-lookup"><span data-stu-id="bd314-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd314-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd314-115">Child Elements</span></span>  
 <span data-ttu-id="bd314-116">Keine</span><span class="sxs-lookup"><span data-stu-id="bd314-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bd314-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bd314-117">Parent Elements</span></span>  
  
|<span data-ttu-id="bd314-118">Element</span><span class="sxs-lookup"><span data-stu-id="bd314-118">Element</span></span>|<span data-ttu-id="bd314-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd314-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd314-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="bd314-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="bd314-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="bd314-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd314-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd314-122">Remarks</span></span>  
 <span data-ttu-id="bd314-123">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bd314-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="bd314-124">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="bd314-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd314-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd314-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="bd314-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd314-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="bd314-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd314-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="bd314-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="bd314-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="bd314-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="bd314-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
