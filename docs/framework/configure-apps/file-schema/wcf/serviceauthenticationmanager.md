---
title: '&lt;serviceAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 34c50e0e8c259190d3f66aa7ad1369befc629d44
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154077"
---
# <a name="ltserviceauthenticationmanagergt"></a><span data-ttu-id="ce1c5-102">&lt;serviceAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="ce1c5-102">&lt;serviceAuthenticationManager&gt;</span></span>
<span data-ttu-id="ce1c5-103">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="ce1c5-103">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="ce1c5-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ce1c5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ce1c5-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ce1c5-105">\<behaviors></span></span>  
<span data-ttu-id="ce1c5-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ce1c5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ce1c5-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="ce1c5-107">\<behavior></span></span>  
<span data-ttu-id="ce1c5-108">\<ServiceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="ce1c5-108">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce1c5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce1c5-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce1c5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce1c5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ce1c5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce1c5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce1c5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce1c5-112">Attributes</span></span>  
  
|<span data-ttu-id="ce1c5-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce1c5-113">Attribute</span></span>|<span data-ttu-id="ce1c5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce1c5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce1c5-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="ce1c5-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="ce1c5-116">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="ce1c5-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce1c5-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce1c5-117">Child Elements</span></span>  
 <span data-ttu-id="ce1c5-118">Keine</span><span class="sxs-lookup"><span data-stu-id="ce1c5-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce1c5-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce1c5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ce1c5-120">Element</span><span class="sxs-lookup"><span data-stu-id="ce1c5-120">Element</span></span>|<span data-ttu-id="ce1c5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce1c5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce1c5-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="ce1c5-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="ce1c5-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="ce1c5-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce1c5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce1c5-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
