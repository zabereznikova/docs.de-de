---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b974767aa86801bff234e200e1fce021bfc422c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755603"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="cf8e2-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="cf8e2-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="cf8e2-103">Legt die benutzerdefinierten cookiehandlertyp fest.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="cf8e2-104">Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut des der `<cookieHandler>` Element ist "Custom".</span><span class="sxs-lookup"><span data-stu-id="cf8e2-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="cf8e2-105">Der benutzerdefinierte Typ muss von abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="cf8e2-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="cf8e2-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="cf8e2-107">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cf8e2-107">\<federationConfiguration></span></span>  
<span data-ttu-id="cf8e2-108">\<"cookiehandler" ></span><span class="sxs-lookup"><span data-stu-id="cf8e2-108">\<cookieHandler></span></span>  
<span data-ttu-id="cf8e2-109">\<CustomCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="cf8e2-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8e2-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf8e2-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf8e2-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cf8e2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cf8e2-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf8e2-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="cf8e2-113">Attributes</span></span>  
  
|<span data-ttu-id="cf8e2-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="cf8e2-114">Attribute</span></span>|<span data-ttu-id="cf8e2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf8e2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cf8e2-116">Typ</span><span class="sxs-lookup"><span data-stu-id="cf8e2-116">type</span></span>|<span data-ttu-id="cf8e2-117">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="cf8e2-118">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="cf8e2-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf8e2-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf8e2-119">Child Elements</span></span>  
 <span data-ttu-id="cf8e2-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="cf8e2-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf8e2-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cf8e2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cf8e2-122">Element</span><span class="sxs-lookup"><span data-stu-id="cf8e2-122">Element</span></span>|<span data-ttu-id="cf8e2-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf8e2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cf8e2-124">\<"cookiehandler" ></span><span class="sxs-lookup"><span data-stu-id="cf8e2-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="cf8e2-125">Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf8e2-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf8e2-126">Remarks</span></span>  
 <span data-ttu-id="cf8e2-127">Beim Angeben von eines benutzerdefinierten Cookie-Handlers Festlegen der `mode` Attribut des der `<cookieHandler>` Element auf "Benutzerdefiniert", müssen Sie den Typ des benutzerdefinierten Cookie-Handlers angeben, indem z. B. eine `<customCookieHandler>` untergeordnetes Element, das die cookiehandlertyp verweist.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="cf8e2-128">Dieses Element nicht angegeben, wann die `mode` -Attribut auf "Chunked" oder "Default" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="cf8e2-129">Benutzerdefinierte Cookie Handler leiten sich aus der <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="cf8e2-130">Die `<customCookieHandler>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf8e2-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf8e2-131">Example</span></span>  
 <span data-ttu-id="cf8e2-132">Das folgende Beispiel konfiguriert die SAM um einen benutzerdefinierten Cookie-Handler des Typs verwenden `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="cf8e2-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf8e2-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf8e2-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
