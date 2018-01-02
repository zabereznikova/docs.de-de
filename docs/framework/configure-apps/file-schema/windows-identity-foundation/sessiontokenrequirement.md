---
title: '&lt;auf "sessiontokenrequirement"&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 5a141dd83cb7ef1271906871097eb68da174d22f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="e005a-102">&lt;auf "sessiontokenrequirement"&gt;</span><span class="sxs-lookup"><span data-stu-id="e005a-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="e005a-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="e005a-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="e005a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="e005a-104">\<system.identityModel></span></span>  
<span data-ttu-id="e005a-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e005a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e005a-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e005a-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e005a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="e005a-107">\<add></span></span>  
<span data-ttu-id="e005a-108">\<auf "sessiontokenrequirement" ></span><span class="sxs-lookup"><span data-stu-id="e005a-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e005a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e005a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e005a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e005a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e005a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e005a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e005a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e005a-112">Attributes</span></span>  
  
|<span data-ttu-id="e005a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e005a-113">Attribute</span></span>|<span data-ttu-id="e005a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e005a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e005a-115">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="e005a-115">lifetime</span></span>|<span data-ttu-id="e005a-116">Gibt die Lebensdauer der Sitzungstoken.</span><span class="sxs-lookup"><span data-stu-id="e005a-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e005a-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e005a-117">Child Elements</span></span>  
 <span data-ttu-id="e005a-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="e005a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e005a-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e005a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e005a-120">Element</span><span class="sxs-lookup"><span data-stu-id="e005a-120">Element</span></span>|<span data-ttu-id="e005a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e005a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e005a-122">\<add></span><span class="sxs-lookup"><span data-stu-id="e005a-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="e005a-123">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e005a-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e005a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e005a-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
