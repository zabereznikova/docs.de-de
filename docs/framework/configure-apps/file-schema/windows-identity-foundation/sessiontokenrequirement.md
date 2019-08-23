---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943675"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="f865f-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f865f-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="f865f-102">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="f865f-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="f865f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f865f-103">\<system.identityModel></span></span>  
<span data-ttu-id="f865f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f865f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f865f-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="f865f-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f865f-106">\<add></span><span class="sxs-lookup"><span data-stu-id="f865f-106">\<add></span></span>  
<span data-ttu-id="f865f-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f865f-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f865f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f865f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f865f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f865f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f865f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f865f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f865f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="f865f-111">Attributes</span></span>  
  
|<span data-ttu-id="f865f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="f865f-112">Attribute</span></span>|<span data-ttu-id="f865f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f865f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f865f-114">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="f865f-114">lifetime</span></span>|<span data-ttu-id="f865f-115">Gibt die Lebensdauer von Sitzungs Token an.</span><span class="sxs-lookup"><span data-stu-id="f865f-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f865f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f865f-116">Child Elements</span></span>  
 <span data-ttu-id="f865f-117">None</span><span class="sxs-lookup"><span data-stu-id="f865f-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f865f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f865f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f865f-119">Element</span><span class="sxs-lookup"><span data-stu-id="f865f-119">Element</span></span>|<span data-ttu-id="f865f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f865f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f865f-121">\<add></span><span class="sxs-lookup"><span data-stu-id="f865f-121">\<add></span></span>](add.md)|<span data-ttu-id="f865f-122">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="f865f-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f865f-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f865f-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
