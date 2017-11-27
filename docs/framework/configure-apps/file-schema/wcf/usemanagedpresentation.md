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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f99879ab80acddf1d50f5e5c734b8d6c975cb348
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="4792f-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="4792f-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="4792f-103">Ein Bindungselement, das zur Kommunikation mit einem CardSpace-Sicherheitstokendienst verwendet wird, der das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4792f-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="4792f-104">Dieses Element verfügt über kein Attribut und ist als leerer Schalter vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4792f-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="4792f-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4792f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4792f-106">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="4792f-106">\<bindings></span></span>  
<span data-ttu-id="4792f-107">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="4792f-107">\<customBinding></span></span>  
<span data-ttu-id="4792f-108">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="4792f-108">\<binding></span></span>  
<span data-ttu-id="4792f-109">\<UseManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="4792f-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4792f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4792f-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4792f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4792f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4792f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4792f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4792f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4792f-113">Attributes</span></span>  
 <span data-ttu-id="4792f-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="4792f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4792f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4792f-115">Child Elements</span></span>  
 <span data-ttu-id="4792f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="4792f-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4792f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4792f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4792f-118">Element</span><span class="sxs-lookup"><span data-stu-id="4792f-118">Element</span></span>|<span data-ttu-id="4792f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4792f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4792f-120">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="4792f-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4792f-121">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="4792f-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4792f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4792f-122">Remarks</span></span>  
 <span data-ttu-id="4792f-123">Dieses Element wird von einem Identitätsanbieter verwendet, um in der eigenen Richtlinie anzugeben, dass es das CardSpace-Profil von WS-Trust unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4792f-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="4792f-124">Identitätsanbieter, die solche Richtlinienassertionen veröffentlichen, sollten basierend auf diesem CardSpace-Profil Token ausstellen können.</span><span class="sxs-lookup"><span data-stu-id="4792f-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4792f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4792f-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="4792f-126">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4792f-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4792f-127">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="4792f-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4792f-128">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="4792f-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4792f-129">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="4792f-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
