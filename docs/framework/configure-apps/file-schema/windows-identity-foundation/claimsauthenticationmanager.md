---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 3602a4805e86833ba6070d801cef6758aaee8a5c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941828"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="df2ed-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="df2ed-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="df2ed-102">Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="df2ed-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="df2ed-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="df2ed-103">\<system.identityModel></span></span>  
<span data-ttu-id="df2ed-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="df2ed-104">\<identityConfiguration></span></span>  
<span data-ttu-id="df2ed-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="df2ed-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2ed-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="df2ed-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df2ed-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="df2ed-107">Attributes and Elements</span></span>  
 <span data-ttu-id="df2ed-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="df2ed-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df2ed-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="df2ed-109">Attributes</span></span>  
  
|<span data-ttu-id="df2ed-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="df2ed-110">Attribute</span></span>|<span data-ttu-id="df2ed-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df2ed-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df2ed-112">Typ</span><span class="sxs-lookup"><span data-stu-id="df2ed-112">type</span></span>|<span data-ttu-id="df2ed-113">Gibt einen benutzerdefinierten Typ an, der <xref:System.Security.Claims.ClaimsAuthenticationManager> von der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="df2ed-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="df2ed-114">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="df2ed-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df2ed-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df2ed-115">Child Elements</span></span>  
 <span data-ttu-id="df2ed-116">Wenn kein `type` -Attribut vorhanden ist, oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> auf die- `<claimsAuthenticationManager>` Klasse verweist, nimmt das-Element keine untergeordneten Elemente an <xref:System.Security.Claims.ClaimsAuthenticationManager> . von abgeleitete Klassen können jedoch untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="df2ed-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df2ed-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="df2ed-117">Parent Elements</span></span>  
  
|<span data-ttu-id="df2ed-118">Element</span><span class="sxs-lookup"><span data-stu-id="df2ed-118">Element</span></span>|<span data-ttu-id="df2ed-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="df2ed-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df2ed-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="df2ed-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="df2ed-121">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="df2ed-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df2ed-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df2ed-122">Remarks</span></span>  
 <span data-ttu-id="df2ed-123">Das von der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse bereitgestellte Standardverhalten gibt die eingehenden Ansprüche wieder.</span><span class="sxs-lookup"><span data-stu-id="df2ed-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="df2ed-124">Wenn kein `type` -Attribut angegeben wird oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> die-Klasse `<claimsAuthenticationManager>` angibt, nimmt das-Element keine untergeordneten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="df2ed-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="df2ed-125">Sie können das `type` Attribut angeben, um einen von der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse abgeleiteten Typ zu registrieren, um benutzerdefiniertes Verhalten zu implementieren</span><span class="sxs-lookup"><span data-stu-id="df2ed-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="df2ed-126">Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente `<claimsAuthenticationManager>` des-Elements unter <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> stützen, indem Sie die-Methode zum Verarbeiten dieser Elemente überschreiben.</span><span class="sxs-lookup"><span data-stu-id="df2ed-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="df2ed-127">Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="df2ed-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="df2ed-128">Das `<claimsAuthenticationManager>` -Element legt <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> die-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="df2ed-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df2ed-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df2ed-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
