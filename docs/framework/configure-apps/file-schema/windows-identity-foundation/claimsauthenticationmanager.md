---
title: '&lt;Komponente "ClaimsAuthenticationManager"&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48581824"
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="22060-102">&lt;Komponente "ClaimsAuthenticationManager"&gt;</span><span class="sxs-lookup"><span data-stu-id="22060-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="22060-103">Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="22060-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="22060-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="22060-104">\<system.identityModel></span></span>  
<span data-ttu-id="22060-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="22060-105">\<identityConfiguration></span></span>  
<span data-ttu-id="22060-106">\<Komponente "ClaimsAuthenticationManager" ></span><span class="sxs-lookup"><span data-stu-id="22060-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22060-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="22060-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22060-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="22060-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22060-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="22060-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22060-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="22060-110">Attributes</span></span>  
  
|<span data-ttu-id="22060-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="22060-111">Attribute</span></span>|<span data-ttu-id="22060-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22060-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22060-113">Typ</span><span class="sxs-lookup"><span data-stu-id="22060-113">type</span></span>|<span data-ttu-id="22060-114">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="22060-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="22060-115">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="22060-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22060-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22060-116">Child Elements</span></span>  
 <span data-ttu-id="22060-117">Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` Element nimmt keine untergeordneten Elemente, aber von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthenticationManager> können untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="22060-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22060-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="22060-118">Parent Elements</span></span>  
  
|<span data-ttu-id="22060-119">Element</span><span class="sxs-lookup"><span data-stu-id="22060-119">Element</span></span>|<span data-ttu-id="22060-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22060-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22060-121">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="22060-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="22060-122">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="22060-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22060-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22060-123">Remarks</span></span>  
 <span data-ttu-id="22060-124">Das Standardverhalten durch die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse gibt, die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="22060-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="22060-125">Wenn kein `type` -Attribut angegeben ist oder wenn die `type` -Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` Element nimmt keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="22060-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="22060-126">Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus den <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="22060-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="22060-127">Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthenticationManager>` Element durch das Überschreiben der <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="22060-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="22060-128">Das Schema für die untergeordneten Elemente definiert ist, bis zu den Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="22060-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="22060-129">Die `<claimsAuthenticationManager>` Elementgruppen die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="22060-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22060-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22060-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
