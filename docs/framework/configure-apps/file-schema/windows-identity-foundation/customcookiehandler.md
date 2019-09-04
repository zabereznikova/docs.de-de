---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252018"
---
# <a name="customcookiehandler"></a><span data-ttu-id="ba42c-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="ba42c-101">\<customCookieHandler></span></span>
<span data-ttu-id="ba42c-102">Legt den Typ des benutzerdefinierten Cookie-Handlers fest.</span><span class="sxs-lookup"><span data-stu-id="ba42c-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="ba42c-103">Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Custom" ist.</span><span class="sxs-lookup"><span data-stu-id="ba42c-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="ba42c-104">Der benutzerdefinierte Typ muss von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ba42c-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="ba42c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ba42c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ba42c-106">&nbsp;&nbsp;[ **\<System. IdentityModel. Services->** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="ba42c-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="ba42c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationconfiguration->** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ba42c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="ba42c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookiehandler->** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="ba42c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="ba42c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customcookiehandler->**</span><span class="sxs-lookup"><span data-stu-id="ba42c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba42c-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba42c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba42c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ba42c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ba42c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba42c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba42c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba42c-113">Attributes</span></span>  
  
|<span data-ttu-id="ba42c-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ba42c-114">Attribute</span></span>|<span data-ttu-id="ba42c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba42c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba42c-116">Typ</span><span class="sxs-lookup"><span data-stu-id="ba42c-116">type</span></span>|<span data-ttu-id="ba42c-117">Gibt einen benutzerdefinierten Typ an, der <xref:System.IdentityModel.Services.CookieHandler> von der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="ba42c-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="ba42c-118">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="ba42c-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba42c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba42c-119">Child Elements</span></span>  
 <span data-ttu-id="ba42c-120">None</span><span class="sxs-lookup"><span data-stu-id="ba42c-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba42c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ba42c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ba42c-122">Element</span><span class="sxs-lookup"><span data-stu-id="ba42c-122">Element</span></span>|<span data-ttu-id="ba42c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ba42c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba42c-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="ba42c-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="ba42c-125">Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , der <xref:System.IdentityModel.Services.SessionAuthenticationModule> von verwendet wird, um Cookies zu lesen und zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="ba42c-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba42c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba42c-126">Remarks</span></span>  
 <span data-ttu-id="ba42c-127">Wenn Sie einen benutzerdefinierten cookiehandler `mode` angeben, indem `<cookieHandler>` Sie das-Attribut des-Elements auf "Custom" festlegen, müssen Sie den Typ des Benutzer `<customCookieHandler>` definierten cookiehandlers angeben, indem Sie ein untergeordnetes-Element einschließen, das auf den Typ der</span><span class="sxs-lookup"><span data-stu-id="ba42c-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="ba42c-128">Dieses Element kann nicht angegeben werden, `mode` wenn das-Attribut auf "Chunked" oder "Default" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ba42c-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="ba42c-129">Benutzerdefinierte Cookie-Handler müssen von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="ba42c-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="ba42c-130">Das `<customCookieHandler>` -Element wird durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ba42c-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba42c-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba42c-131">Example</span></span>  
 <span data-ttu-id="ba42c-132">Im folgenden Beispiel wird Sam für die Verwendung eines benutzerdefinierten cookiehandlers vom Typ `MyNamespace.MyCustomCookieHandler`konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ba42c-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ba42c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba42c-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
