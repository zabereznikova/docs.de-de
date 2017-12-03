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
ms.openlocfilehash: 077878ae1746008532c3bee6b12913f98afc343f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="35cd4-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="35cd4-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="35cd4-103">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="35cd4-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="35cd4-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="35cd4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="35cd4-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="35cd4-105">\<behaviors></span></span>  
<span data-ttu-id="35cd4-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="35cd4-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="35cd4-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="35cd4-107">\<behavior></span></span>  
<span data-ttu-id="35cd4-108">\<ServiceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="35cd4-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cd4-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="35cd4-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35cd4-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="35cd4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35cd4-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="35cd4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35cd4-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="35cd4-112">Attributes</span></span>  
  
|<span data-ttu-id="35cd4-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="35cd4-113">Attribute</span></span>|<span data-ttu-id="35cd4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35cd4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35cd4-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="35cd4-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="35cd4-116">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="35cd4-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35cd4-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35cd4-117">Child Elements</span></span>  
 <span data-ttu-id="35cd4-118">Keine</span><span class="sxs-lookup"><span data-stu-id="35cd4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35cd4-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="35cd4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="35cd4-120">Element</span><span class="sxs-lookup"><span data-stu-id="35cd4-120">Element</span></span>|<span data-ttu-id="35cd4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35cd4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35cd4-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="35cd4-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="35cd4-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="35cd4-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="35cd4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35cd4-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
