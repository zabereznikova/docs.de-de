---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 65488c34931f6d7c424ece58a4855e746ea455bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936415"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="5a3b1-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="5a3b1-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="5a3b1-102">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="5a3b1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5a3b1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5a3b1-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="5a3b1-104">\<behaviors></span></span>  
<span data-ttu-id="5a3b1-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5a3b1-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5a3b1-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5a3b1-106">\<behavior></span></span>  
<span data-ttu-id="5a3b1-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="5a3b1-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3b1-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a3b1-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a3b1-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a3b1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5a3b1-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a3b1-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a3b1-111">Attributes</span></span>  
  
|<span data-ttu-id="5a3b1-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="5a3b1-112">Attribute</span></span>|<span data-ttu-id="5a3b1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a3b1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a3b1-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="5a3b1-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="5a3b1-115">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a3b1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a3b1-116">Child Elements</span></span>  
 <span data-ttu-id="5a3b1-117">Keine</span><span class="sxs-lookup"><span data-stu-id="5a3b1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a3b1-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a3b1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5a3b1-119">Element</span><span class="sxs-lookup"><span data-stu-id="5a3b1-119">Element</span></span>|<span data-ttu-id="5a3b1-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a3b1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a3b1-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5a3b1-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5a3b1-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="5a3b1-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a3b1-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a3b1-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
