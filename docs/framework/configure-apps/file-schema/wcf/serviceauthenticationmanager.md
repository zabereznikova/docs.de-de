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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2385b96460e0a3d53efb62054fb7da334ddd2d49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="08bbb-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="08bbb-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="08bbb-103">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="08bbb-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>  
  
<span data-ttu-id="08bbb-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="08bbb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="08bbb-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="08bbb-105">\<behaviors></span></span>  
<span data-ttu-id="08bbb-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="08bbb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="08bbb-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="08bbb-107">\<behavior></span></span>  
<span data-ttu-id="08bbb-108">\<ServiceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="08bbb-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08bbb-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="08bbb-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08bbb-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="08bbb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="08bbb-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08bbb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08bbb-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="08bbb-112">Attributes</span></span>  
  
|<span data-ttu-id="08bbb-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="08bbb-113">Attribute</span></span>|<span data-ttu-id="08bbb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08bbb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08bbb-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="08bbb-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="08bbb-116">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="08bbb-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08bbb-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08bbb-117">Child Elements</span></span>  
 <span data-ttu-id="08bbb-118">Keine</span><span class="sxs-lookup"><span data-stu-id="08bbb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="08bbb-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="08bbb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="08bbb-120">Element</span><span class="sxs-lookup"><span data-stu-id="08bbb-120">Element</span></span>|<span data-ttu-id="08bbb-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08bbb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08bbb-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="08bbb-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="08bbb-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="08bbb-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08bbb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08bbb-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
