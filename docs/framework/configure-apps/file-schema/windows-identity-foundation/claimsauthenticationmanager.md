---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152748"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="75a68-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="75a68-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="75a68-102">Registriert einen Anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="75a68-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="75a68-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="75a68-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="75a68-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="75a68-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="75a68-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="75a68-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="75a68-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span><span class="sxs-lookup"><span data-stu-id="75a68-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a68-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="75a68-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75a68-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75a68-108">Attributes and Elements</span></span>  
 <span data-ttu-id="75a68-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75a68-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75a68-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="75a68-110">Attributes</span></span>  
  
|<span data-ttu-id="75a68-111">attribute</span><span class="sxs-lookup"><span data-stu-id="75a68-111">Attribute</span></span>|<span data-ttu-id="75a68-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75a68-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75a68-113">type</span><span class="sxs-lookup"><span data-stu-id="75a68-113">type</span></span>|<span data-ttu-id="75a68-114">Gibt einen benutzerdefinierten Typ an, <xref:System.Security.Claims.ClaimsAuthenticationManager> der von der Klasse abstammt.</span><span class="sxs-lookup"><span data-stu-id="75a68-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="75a68-115">Weitere Informationen zum Angeben `type` des Attributs finden Sie unter [Benutzerdefinierte Typreferenzen].</span><span class="sxs-lookup"><span data-stu-id="75a68-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75a68-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75a68-116">Child Elements</span></span>  
 <span data-ttu-id="75a68-117">Wenn `type` kein Attribut vorhanden ist `type` oder <xref:System.Security.Claims.ClaimsAuthenticationManager> das Attribut `<claimsAuthenticationManager>` auf die Klasse verweist, nimmt das Element keine untergeordneten Elemente an. Von Klassen abgeleitete Klassen <xref:System.Security.Claims.ClaimsAuthenticationManager> können jedoch untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="75a68-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75a68-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75a68-118">Parent Elements</span></span>  
  
|<span data-ttu-id="75a68-119">Element</span><span class="sxs-lookup"><span data-stu-id="75a68-119">Element</span></span>|<span data-ttu-id="75a68-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75a68-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75a68-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="75a68-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="75a68-122">Gibt Identitätseinstellungen auf Dienstebene an.</span><span class="sxs-lookup"><span data-stu-id="75a68-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75a68-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="75a68-123">Remarks</span></span>  
 <span data-ttu-id="75a68-124">Das Standardverhalten, <xref:System.Security.Claims.ClaimsAuthenticationManager> das über die Klasse bereitgestellt wird, spiegelt die eingehenden Ansprüche wider.</span><span class="sxs-lookup"><span data-stu-id="75a68-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="75a68-125">Wenn `type` kein Attribut angegeben `type` ist oder <xref:System.Security.Claims.ClaimsAuthenticationManager> wenn das `<claimsAuthenticationManager>` Attribut die Klasse angibt, nimmt das Element keine untergeordneten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="75a68-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="75a68-126">Sie können `type` das Attribut angeben, um <xref:System.Security.Claims.ClaimsAuthenticationManager> einen von der Klasse abgeleiteten Typ zu registrieren, um benutzerdefiniertes Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="75a68-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="75a68-127">Abgeleitete Klassen können die Konfiguration `<claimsAuthenticationManager>` über untergeordnete <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Elemente des Elements unterstützen, indem die Methode zum Behandeln dieser Elemente überschreibt wird.</span><span class="sxs-lookup"><span data-stu-id="75a68-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="75a68-128">Das für die untergeordneten Elemente definierte Schema hängt vom Designer der Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="75a68-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="75a68-129">Das `<claimsAuthenticationManager>` Element <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> legt die Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="75a68-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a68-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75a68-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
