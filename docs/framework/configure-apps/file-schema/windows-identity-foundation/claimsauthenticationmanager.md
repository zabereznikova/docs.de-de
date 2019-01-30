---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255184"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="1a4ae-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="1a4ae-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="1a4ae-102">Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="1a4ae-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1a4ae-103">\<system.identityModel></span></span>  
<span data-ttu-id="1a4ae-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1a4ae-104">\<identityConfiguration></span></span>  
<span data-ttu-id="1a4ae-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="1a4ae-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a4ae-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a4ae-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a4ae-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1a4ae-107">Attributes and Elements</span></span>  
 <span data-ttu-id="1a4ae-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a4ae-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="1a4ae-109">Attributes</span></span>  
  
|<span data-ttu-id="1a4ae-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="1a4ae-110">Attribute</span></span>|<span data-ttu-id="1a4ae-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a4ae-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a4ae-112">Typ</span><span class="sxs-lookup"><span data-stu-id="1a4ae-112">type</span></span>|<span data-ttu-id="1a4ae-113">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="1a4ae-114">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="1a4ae-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a4ae-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a4ae-115">Child Elements</span></span>  
 <span data-ttu-id="1a4ae-116">Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` Element nimmt keine untergeordneten Elemente, aber von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthenticationManager> können untergeordnete Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a4ae-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a4ae-117">Parent Elements</span></span>  
  
|<span data-ttu-id="1a4ae-118">Element</span><span class="sxs-lookup"><span data-stu-id="1a4ae-118">Element</span></span>|<span data-ttu-id="1a4ae-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a4ae-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a4ae-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1a4ae-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="1a4ae-121">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a4ae-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a4ae-122">Remarks</span></span>  
 <span data-ttu-id="1a4ae-123">Das Standardverhalten durch die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse gibt, die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="1a4ae-124">Wenn kein `type` -Attribut angegeben ist oder wenn die `type` -Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` Element nimmt keine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="1a4ae-125">Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus den <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="1a4ae-126">Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthenticationManager>` Element durch das Überschreiben der <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="1a4ae-127">Das Schema für die untergeordneten Elemente definiert ist, bis zu den Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="1a4ae-128">Die `<claimsAuthenticationManager>` Elementgruppen die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1a4ae-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a4ae-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a4ae-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
