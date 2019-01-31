---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: 1134c4d5f18f60bb2986f4239a788b836fa9113e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287247"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="80311-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="80311-101">\<useManagedPresentation></span></span>
<span data-ttu-id="80311-102">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80311-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="80311-103">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="80311-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="80311-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="80311-104">\<system.serviceModel></span></span>  
<span data-ttu-id="80311-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="80311-105">\<bindings></span></span>  
<span data-ttu-id="80311-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="80311-106">\<customBinding></span></span>  
<span data-ttu-id="80311-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="80311-107">\<binding></span></span>  
<span data-ttu-id="80311-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="80311-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80311-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="80311-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80311-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="80311-110">Attributes and Elements</span></span>  
 <span data-ttu-id="80311-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80311-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80311-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="80311-112">Attributes</span></span>  
 <span data-ttu-id="80311-113">Keine</span><span class="sxs-lookup"><span data-stu-id="80311-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="80311-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80311-114">Child Elements</span></span>  
 <span data-ttu-id="80311-115">Keine</span><span class="sxs-lookup"><span data-stu-id="80311-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80311-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="80311-116">Parent Elements</span></span>  
  
|<span data-ttu-id="80311-117">Element</span><span class="sxs-lookup"><span data-stu-id="80311-117">Element</span></span>|<span data-ttu-id="80311-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="80311-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80311-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="80311-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="80311-120">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="80311-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80311-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80311-121">Remarks</span></span>  
 <span data-ttu-id="80311-122">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80311-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="80311-123">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="80311-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80311-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80311-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="80311-125">Bindungen</span><span class="sxs-lookup"><span data-stu-id="80311-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="80311-126">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="80311-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="80311-127">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="80311-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="80311-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="80311-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
