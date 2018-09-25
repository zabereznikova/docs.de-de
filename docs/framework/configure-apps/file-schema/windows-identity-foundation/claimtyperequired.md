---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: df4494de6b76943849db2bedef8f43ad894b6bd1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084227"
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="17f8e-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="17f8e-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="17f8e-103">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="17f8e-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="17f8e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="17f8e-104">\<system.identityModel></span></span>  
<span data-ttu-id="17f8e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="17f8e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="17f8e-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="17f8e-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f8e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="17f8e-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17f8e-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="17f8e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="17f8e-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="17f8e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17f8e-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="17f8e-110">Attributes</span></span>  
 <span data-ttu-id="17f8e-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="17f8e-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="17f8e-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="17f8e-112">Child Elements</span></span>  
  
|<span data-ttu-id="17f8e-113">Element</span><span class="sxs-lookup"><span data-stu-id="17f8e-113">Element</span></span>|<span data-ttu-id="17f8e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17f8e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17f8e-115">\<"ClaimType" ></span><span class="sxs-lookup"><span data-stu-id="17f8e-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="17f8e-116">Gibt einen einzelnen erforderliche oder optionale Anspruch eingehender Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="17f8e-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17f8e-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="17f8e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="17f8e-118">Element</span><span class="sxs-lookup"><span data-stu-id="17f8e-118">Element</span></span>|<span data-ttu-id="17f8e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17f8e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17f8e-120">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="17f8e-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="17f8e-121">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="17f8e-121">Specifies service-level identity settings.</span></span>|
