---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271901"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="616b0-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="616b0-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="616b0-102">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse oder abgeleitete Klassen.</span><span class="sxs-lookup"><span data-stu-id="616b0-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="616b0-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="616b0-103">\<system.identityModel></span></span>  
<span data-ttu-id="616b0-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="616b0-104">\<identityConfiguration></span></span>  
<span data-ttu-id="616b0-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="616b0-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="616b0-106">\<add></span><span class="sxs-lookup"><span data-stu-id="616b0-106">\<add></span></span>  
<span data-ttu-id="616b0-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="616b0-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="616b0-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="616b0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="616b0-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="616b0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="616b0-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="616b0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="616b0-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="616b0-111">Attributes</span></span>  
  
|<span data-ttu-id="616b0-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="616b0-112">Attribute</span></span>|<span data-ttu-id="616b0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="616b0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="616b0-114">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="616b0-114">lifetime</span></span>|<span data-ttu-id="616b0-115">Gibt die Lebensdauer des Sitzungstoken.</span><span class="sxs-lookup"><span data-stu-id="616b0-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="616b0-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="616b0-116">Child Elements</span></span>  
 <span data-ttu-id="616b0-117">Keine</span><span class="sxs-lookup"><span data-stu-id="616b0-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="616b0-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="616b0-118">Parent Elements</span></span>  
  
|<span data-ttu-id="616b0-119">Element</span><span class="sxs-lookup"><span data-stu-id="616b0-119">Element</span></span>|<span data-ttu-id="616b0-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="616b0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="616b0-121">\<add></span><span class="sxs-lookup"><span data-stu-id="616b0-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="616b0-122">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="616b0-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="616b0-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="616b0-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
