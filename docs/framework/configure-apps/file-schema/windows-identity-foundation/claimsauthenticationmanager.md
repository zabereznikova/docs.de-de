---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252089"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="79f40-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="79f40-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="79f40-102">Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="79f40-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="79f40-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="79f40-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="79f40-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="79f40-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="79f40-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="79f40-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="79f40-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ClaimsAuthenticationManager->**</span><span class="sxs-lookup"><span data-stu-id="79f40-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79f40-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="79f40-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79f40-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="79f40-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79f40-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79f40-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79f40-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="79f40-110">Attributes</span></span>  
  
|<span data-ttu-id="79f40-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="79f40-111">Attribute</span></span>|<span data-ttu-id="79f40-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79f40-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79f40-113">Typ</span><span class="sxs-lookup"><span data-stu-id="79f40-113">type</span></span>|<span data-ttu-id="79f40-114">Gibt einen benutzerdefinierten Typ an, der <xref:System.Security.Claims.ClaimsAuthenticationManager> von der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="79f40-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="79f40-115">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="79f40-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79f40-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79f40-116">Child Elements</span></span>  
 <span data-ttu-id="79f40-117">Wenn kein `type` -Attribut vorhanden ist, oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> auf die- `<claimsAuthenticationManager>` Klasse verweist, nimmt das-Element keine untergeordneten Elemente an <xref:System.Security.Claims.ClaimsAuthenticationManager> . von abgeleitete Klassen können jedoch untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="79f40-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79f40-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79f40-118">Parent Elements</span></span>  
  
|<span data-ttu-id="79f40-119">Element</span><span class="sxs-lookup"><span data-stu-id="79f40-119">Element</span></span>|<span data-ttu-id="79f40-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79f40-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79f40-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="79f40-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="79f40-122">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="79f40-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79f40-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79f40-123">Remarks</span></span>  
 <span data-ttu-id="79f40-124">Das von der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse bereitgestellte Standardverhalten gibt die eingehenden Ansprüche wieder.</span><span class="sxs-lookup"><span data-stu-id="79f40-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="79f40-125">Wenn kein `type` -Attribut angegeben wird oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> die-Klasse `<claimsAuthenticationManager>` angibt, nimmt das-Element keine untergeordneten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="79f40-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="79f40-126">Sie können das `type` Attribut angeben, um einen von der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse abgeleiteten Typ zu registrieren, um benutzerdefiniertes Verhalten zu implementieren</span><span class="sxs-lookup"><span data-stu-id="79f40-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="79f40-127">Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente `<claimsAuthenticationManager>` des-Elements unter <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> stützen, indem Sie die-Methode zum Verarbeiten dieser Elemente überschreiben.</span><span class="sxs-lookup"><span data-stu-id="79f40-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="79f40-128">Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="79f40-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="79f40-129">Das `<claimsAuthenticationManager>` -Element legt <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> die-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="79f40-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79f40-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79f40-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
