---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 9e099b8de486631702548b8a035a46a7e0f4eb30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158473"
---
# \<claimsAuthenticationManager>

<span data-ttu-id="b037b-101">Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="b037b-101">Registers a claims authentication manager for the incoming claims.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
## <a name="syntax"></a><span data-ttu-id="b037b-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b037b-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b037b-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b037b-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b037b-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b037b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b037b-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b037b-105">Attributes</span></span>  
  
|<span data-ttu-id="b037b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b037b-106">Attribute</span></span>|<span data-ttu-id="b037b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b037b-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b037b-108">type</span><span class="sxs-lookup"><span data-stu-id="b037b-108">type</span></span>|<span data-ttu-id="b037b-109">Gibt einen benutzerdefinierten Typ an, der von der-Klasse abgeleitet wird <xref:System.Security.Claims.ClaimsAuthenticationManager> .</span><span class="sxs-lookup"><span data-stu-id="b037b-109">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="b037b-110">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="b037b-110">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b037b-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b037b-111">Child Elements</span></span>  

 <span data-ttu-id="b037b-112">Wenn kein-Attribut vorhanden ist `type` , oder wenn das- `type` Attribut auf die- <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse verweist, nimmt das- `<claimsAuthenticationManager>` Element keine untergeordneten Elemente an. von abgeleitete Klassen können jedoch untergeordnete <xref:System.Security.Claims.ClaimsAuthenticationManager> Konfigurationselemente definieren.</span><span class="sxs-lookup"><span data-stu-id="b037b-112">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b037b-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b037b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="b037b-114">Element</span><span class="sxs-lookup"><span data-stu-id="b037b-114">Element</span></span>|<span data-ttu-id="b037b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b037b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="b037b-116">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="b037b-116">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b037b-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b037b-117">Remarks</span></span>  

 <span data-ttu-id="b037b-118">Das von der-Klasse bereitgestellte Standardverhalten gibt <xref:System.Security.Claims.ClaimsAuthenticationManager> die eingehenden Ansprüche wieder.</span><span class="sxs-lookup"><span data-stu-id="b037b-118">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="b037b-119">Wenn kein- `type` Attribut angegeben wird oder wenn das- `type` Attribut die- <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse angibt, nimmt das- `<claimsAuthenticationManager>` Element keine untergeordneten Elemente an.</span><span class="sxs-lookup"><span data-stu-id="b037b-119">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="b037b-120">Sie können das `type` Attribut angeben, um einen von der-Klasse abgeleiteten Typ <xref:System.Security.Claims.ClaimsAuthenticationManager> zu registrieren, um benutzerdefiniertes Verhalten zu implementieren</span><span class="sxs-lookup"><span data-stu-id="b037b-120">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="b037b-121">Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente des-Elements unterstützen `<claimsAuthenticationManager>` , indem Sie die- <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Methode zum Verarbeiten dieser Elemente überschreiben.</span><span class="sxs-lookup"><span data-stu-id="b037b-121">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="b037b-122">Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b037b-122">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="b037b-123">Das- `<claimsAuthenticationManager>` Element legt die- <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="b037b-123">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b037b-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b037b-124">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
