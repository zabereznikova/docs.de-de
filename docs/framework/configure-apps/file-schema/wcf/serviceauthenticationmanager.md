---
title: '&lt;serviceAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b46df4f069259ae4bb2d2769e20c6ad9e6090c00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="a84f5-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="a84f5-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="a84f5-103">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="a84f5-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="a84f5-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a84f5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a84f5-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a84f5-105">\<behaviors></span></span>  
<span data-ttu-id="a84f5-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a84f5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a84f5-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a84f5-107">\<behavior></span></span>  
<span data-ttu-id="a84f5-108">\<ServiceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="a84f5-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84f5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a84f5-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a84f5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a84f5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a84f5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a84f5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a84f5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a84f5-112">Attributes</span></span>  
  
|<span data-ttu-id="a84f5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a84f5-113">Attribute</span></span>|<span data-ttu-id="a84f5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a84f5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a84f5-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="a84f5-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="a84f5-116">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="a84f5-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a84f5-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a84f5-117">Child Elements</span></span>  
 <span data-ttu-id="a84f5-118">Keine</span><span class="sxs-lookup"><span data-stu-id="a84f5-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a84f5-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a84f5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a84f5-120">Element</span><span class="sxs-lookup"><span data-stu-id="a84f5-120">Element</span></span>|<span data-ttu-id="a84f5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a84f5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a84f5-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a84f5-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a84f5-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="a84f5-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a84f5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a84f5-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
