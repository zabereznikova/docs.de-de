---
title: '&lt;auf "sessiontokenrequirement"&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4d5d2348f04ace7596a3a513c5106ea612dc17b7
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792928"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="6b6e8-102">&lt;auf "sessiontokenrequirement"&gt;</span><span class="sxs-lookup"><span data-stu-id="6b6e8-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="6b6e8-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse oder abgeleitete Klassen.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="6b6e8-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6b6e8-104">\<system.identityModel></span></span>  
<span data-ttu-id="6b6e8-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b6e8-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6b6e8-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="6b6e8-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6b6e8-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6b6e8-107">\<add></span></span>  
<span data-ttu-id="6b6e8-108">\<auf "sessiontokenrequirement" ></span><span class="sxs-lookup"><span data-stu-id="6b6e8-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6e8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6e8-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b6e8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6e8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6b6e8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b6e8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6b6e8-112">Attributes</span></span>  
  
|<span data-ttu-id="6b6e8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="6b6e8-113">Attribute</span></span>|<span data-ttu-id="6b6e8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6e8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b6e8-115">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="6b6e8-115">lifetime</span></span>|<span data-ttu-id="6b6e8-116">Gibt die Lebensdauer des Sitzungstoken.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b6e8-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6e8-117">Child Elements</span></span>  
 <span data-ttu-id="6b6e8-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="6b6e8-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b6e8-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6b6e8-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6b6e8-120">Element</span><span class="sxs-lookup"><span data-stu-id="6b6e8-120">Element</span></span>|<span data-ttu-id="6b6e8-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b6e8-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b6e8-122">\<add></span><span class="sxs-lookup"><span data-stu-id="6b6e8-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="6b6e8-123">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="6b6e8-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6b6e8-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b6e8-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
