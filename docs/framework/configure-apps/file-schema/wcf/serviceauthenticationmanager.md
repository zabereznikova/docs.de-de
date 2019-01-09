---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 3456ffa952372b014d579b5c420f7c44222fdad5
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145353"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="134ef-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="134ef-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="134ef-103">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="134ef-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="134ef-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="134ef-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="134ef-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="134ef-105">\<behaviors></span></span>  
<span data-ttu-id="134ef-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="134ef-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="134ef-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="134ef-107">\<behavior></span></span>  
<span data-ttu-id="134ef-108">\<ServiceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="134ef-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="134ef-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="134ef-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="134ef-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="134ef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="134ef-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="134ef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="134ef-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="134ef-112">Attributes</span></span>  
  
|<span data-ttu-id="134ef-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="134ef-113">Attribute</span></span>|<span data-ttu-id="134ef-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="134ef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="134ef-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="134ef-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="134ef-116">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="134ef-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="134ef-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="134ef-117">Child Elements</span></span>  
 <span data-ttu-id="134ef-118">Keine</span><span class="sxs-lookup"><span data-stu-id="134ef-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="134ef-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="134ef-119">Parent Elements</span></span>  
  
|<span data-ttu-id="134ef-120">Element</span><span class="sxs-lookup"><span data-stu-id="134ef-120">Element</span></span>|<span data-ttu-id="134ef-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="134ef-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="134ef-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="134ef-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="134ef-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="134ef-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="134ef-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="134ef-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
