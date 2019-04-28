---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793769"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="e6d34-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e6d34-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="e6d34-102">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse oder abgeleitete Klassen.</span><span class="sxs-lookup"><span data-stu-id="e6d34-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="e6d34-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e6d34-103">\<system.identityModel></span></span>  
<span data-ttu-id="e6d34-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e6d34-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e6d34-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e6d34-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e6d34-106">\<add></span><span class="sxs-lookup"><span data-stu-id="e6d34-106">\<add></span></span>  
<span data-ttu-id="e6d34-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e6d34-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d34-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6d34-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6d34-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6d34-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e6d34-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6d34-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6d34-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6d34-111">Attributes</span></span>  
  
|<span data-ttu-id="e6d34-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="e6d34-112">Attribute</span></span>|<span data-ttu-id="e6d34-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6d34-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6d34-114">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="e6d34-114">lifetime</span></span>|<span data-ttu-id="e6d34-115">Gibt die Lebensdauer des Sitzungstoken.</span><span class="sxs-lookup"><span data-stu-id="e6d34-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6d34-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6d34-116">Child Elements</span></span>  
 <span data-ttu-id="e6d34-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="e6d34-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6d34-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6d34-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e6d34-119">Element</span><span class="sxs-lookup"><span data-stu-id="e6d34-119">Element</span></span>|<span data-ttu-id="e6d34-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6d34-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6d34-121">\<add></span><span class="sxs-lookup"><span data-stu-id="e6d34-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="e6d34-122">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="e6d34-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e6d34-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e6d34-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
