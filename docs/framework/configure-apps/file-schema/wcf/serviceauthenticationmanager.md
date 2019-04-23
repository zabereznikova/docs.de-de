---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 0940248364488bb38a329c5e461d72463c574e74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192042"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="c5097-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="c5097-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="c5097-102">Stellt ein Workflowkonfigurationselement bereit, das die Gültigkeit einer Übertragung, Meldung oder eines Absenders auf Dienstebene festlegt.</span><span class="sxs-lookup"><span data-stu-id="c5097-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="c5097-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c5097-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c5097-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c5097-104">\<behaviors></span></span>  
<span data-ttu-id="c5097-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c5097-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c5097-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c5097-106">\<behavior></span></span>  
<span data-ttu-id="c5097-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="c5097-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5097-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5097-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5097-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c5097-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c5097-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5097-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5097-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c5097-111">Attributes</span></span>  
  
|<span data-ttu-id="c5097-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c5097-112">Attribute</span></span>|<span data-ttu-id="c5097-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5097-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5097-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="c5097-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="c5097-115">Eine Zeichenfolge, die den Typ der Authentifizierungsrichtlinie für das aktuelle Verhalten angibt.</span><span class="sxs-lookup"><span data-stu-id="c5097-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5097-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5097-116">Child Elements</span></span>  
 <span data-ttu-id="c5097-117">Keine</span><span class="sxs-lookup"><span data-stu-id="c5097-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5097-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5097-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c5097-119">Element</span><span class="sxs-lookup"><span data-stu-id="c5097-119">Element</span></span>|<span data-ttu-id="c5097-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5097-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5097-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c5097-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c5097-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="c5097-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5097-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5097-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
