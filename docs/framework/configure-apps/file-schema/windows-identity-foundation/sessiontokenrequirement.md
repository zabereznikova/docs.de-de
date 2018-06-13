---
title: '&lt;auf "sessiontokenrequirement"&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6c40948633eaf892db06e9bba756158dfc3c4a2e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754989"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="e0b5c-102">&lt;auf "sessiontokenrequirement"&gt;</span><span class="sxs-lookup"><span data-stu-id="e0b5c-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="e0b5c-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="e0b5c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e0b5c-104">\<system.identityModel></span></span>  
<span data-ttu-id="e0b5c-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e0b5c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e0b5c-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e0b5c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e0b5c-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e0b5c-107">\<add></span></span>  
<span data-ttu-id="e0b5c-108">\<auf "sessiontokenrequirement" ></span><span class="sxs-lookup"><span data-stu-id="e0b5c-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b5c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0b5c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0b5c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0b5c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e0b5c-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0b5c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0b5c-112">Attributes</span></span>  
  
|<span data-ttu-id="e0b5c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e0b5c-113">Attribute</span></span>|<span data-ttu-id="e0b5c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b5c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0b5c-115">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="e0b5c-115">lifetime</span></span>|<span data-ttu-id="e0b5c-116">Gibt die Lebensdauer der Sitzungstoken.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0b5c-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0b5c-117">Child Elements</span></span>  
 <span data-ttu-id="e0b5c-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="e0b5c-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0b5c-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0b5c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e0b5c-120">Element</span><span class="sxs-lookup"><span data-stu-id="e0b5c-120">Element</span></span>|<span data-ttu-id="e0b5c-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b5c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0b5c-122">\<add></span><span class="sxs-lookup"><span data-stu-id="e0b5c-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="e0b5c-123">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e0b5c-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0b5c-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0b5c-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
