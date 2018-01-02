---
title: '&lt;useManagedPresentation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae9851794d77972066fb897aa76528fec86fd6f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="34841-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="34841-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="34841-103">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34841-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="34841-104">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="34841-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="34841-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="34841-105">\<system.serviceModel></span></span>  
<span data-ttu-id="34841-106">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="34841-106">\<bindings></span></span>  
<span data-ttu-id="34841-107">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="34841-107">\<customBinding></span></span>  
<span data-ttu-id="34841-108">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="34841-108">\<binding></span></span>  
<span data-ttu-id="34841-109">\<UseManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="34841-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34841-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="34841-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34841-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34841-111">Attributes and Elements</span></span>  
 <span data-ttu-id="34841-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34841-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34841-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="34841-113">Attributes</span></span>  
 <span data-ttu-id="34841-114">Keine</span><span class="sxs-lookup"><span data-stu-id="34841-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34841-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34841-115">Child Elements</span></span>  
 <span data-ttu-id="34841-116">Keiner</span><span class="sxs-lookup"><span data-stu-id="34841-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34841-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34841-117">Parent Elements</span></span>  
  
|<span data-ttu-id="34841-118">Element</span><span class="sxs-lookup"><span data-stu-id="34841-118">Element</span></span>|<span data-ttu-id="34841-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34841-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34841-120">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="34841-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="34841-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="34841-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34841-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34841-122">Remarks</span></span>  
 <span data-ttu-id="34841-123">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34841-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="34841-124">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="34841-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34841-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34841-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="34841-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="34841-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="34841-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="34841-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="34841-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="34841-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="34841-129">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="34841-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
