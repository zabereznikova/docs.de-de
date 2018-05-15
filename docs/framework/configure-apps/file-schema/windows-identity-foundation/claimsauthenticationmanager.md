---
title: '&lt;Komponente "ClaimsAuthenticationManager"&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="c6949-102">&lt;Komponente "ClaimsAuthenticationManager"&gt;</span><span class="sxs-lookup"><span data-stu-id="c6949-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="c6949-103">Registriert einen Ansprüche Authentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="c6949-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="c6949-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c6949-104">\<system.identityModel></span></span>  
<span data-ttu-id="c6949-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c6949-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c6949-106">\<Komponente "ClaimsAuthenticationManager" ></span><span class="sxs-lookup"><span data-stu-id="c6949-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6949-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6949-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6949-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c6949-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c6949-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6949-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6949-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c6949-110">Attributes</span></span>  
  
|<span data-ttu-id="c6949-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c6949-111">Attribute</span></span>|<span data-ttu-id="c6949-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6949-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6949-113">Typ</span><span class="sxs-lookup"><span data-stu-id="c6949-113">type</span></span>|<span data-ttu-id="c6949-114">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c6949-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="c6949-115">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="c6949-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6949-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6949-116">Child Elements</span></span>  
 <span data-ttu-id="c6949-117">Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` akzeptiert Element untergeordneten Elementen nicht; allerdings von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthenticationManager> können untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="c6949-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6949-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c6949-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c6949-119">Element</span><span class="sxs-lookup"><span data-stu-id="c6949-119">Element</span></span>|<span data-ttu-id="c6949-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c6949-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6949-121">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c6949-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="c6949-122">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c6949-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6949-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6949-123">Remarks</span></span>  
 <span data-ttu-id="c6949-124">Das Standardverhalten über die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse wiederholt die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="c6949-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="c6949-125">Wenn kein `type` -Attribut angegeben ist oder, wenn die `type` Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` Element akzeptiert keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="c6949-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="c6949-126">Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus der <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c6949-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="c6949-127">Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthenticationManager>` Element durch Überschreiben der <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="c6949-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="c6949-128">Das Schema definiert die untergeordneten Elemente ist bis zu der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c6949-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="c6949-129">Die `<claimsAuthenticationManager>` Element legt die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c6949-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6949-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c6949-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
