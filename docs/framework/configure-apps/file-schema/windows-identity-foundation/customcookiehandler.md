---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942781"
---
# <a name="customcookiehandler"></a><span data-ttu-id="7fd2b-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="7fd2b-101">\<customCookieHandler></span></span>
<span data-ttu-id="7fd2b-102">Legt den Typ des benutzerdefinierten Cookie-Handlers fest.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="7fd2b-103">Dieses Element kann nur vorhanden sein, wenn `mode` das-Attribut `<cookieHandler>` des-Elements "Custom" ist.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="7fd2b-104">Der benutzerdefinierte Typ muss von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="7fd2b-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="7fd2b-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="7fd2b-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="7fd2b-106">\<federationConfiguration></span></span>  
<span data-ttu-id="7fd2b-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="7fd2b-107">\<cookieHandler></span></span>  
<span data-ttu-id="7fd2b-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="7fd2b-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd2b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fd2b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7fd2b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7fd2b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7fd2b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7fd2b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7fd2b-112">Attributes</span></span>  
  
|<span data-ttu-id="7fd2b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7fd2b-113">Attribute</span></span>|<span data-ttu-id="7fd2b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fd2b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7fd2b-115">Typ</span><span class="sxs-lookup"><span data-stu-id="7fd2b-115">type</span></span>|<span data-ttu-id="7fd2b-116">Gibt einen benutzerdefinierten Typ an, der <xref:System.IdentityModel.Services.CookieHandler> von der-Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="7fd2b-117">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="7fd2b-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7fd2b-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7fd2b-118">Child Elements</span></span>  
 <span data-ttu-id="7fd2b-119">None</span><span class="sxs-lookup"><span data-stu-id="7fd2b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7fd2b-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7fd2b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7fd2b-121">Element</span><span class="sxs-lookup"><span data-stu-id="7fd2b-121">Element</span></span>|<span data-ttu-id="7fd2b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7fd2b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7fd2b-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="7fd2b-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="7fd2b-124">Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , der <xref:System.IdentityModel.Services.SessionAuthenticationModule> von verwendet wird, um Cookies zu lesen und zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fd2b-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7fd2b-125">Remarks</span></span>  
 <span data-ttu-id="7fd2b-126">Wenn Sie einen benutzerdefinierten cookiehandler `mode` angeben, indem `<cookieHandler>` Sie das-Attribut des-Elements auf "Custom" festlegen, müssen Sie den Typ des Benutzer `<customCookieHandler>` definierten cookiehandlers angeben, indem Sie ein untergeordnetes-Element einschließen, das auf den Typ der</span><span class="sxs-lookup"><span data-stu-id="7fd2b-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="7fd2b-127">Dieses Element kann nicht angegeben werden, `mode` wenn das-Attribut auf "Chunked" oder "Default" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="7fd2b-128">Benutzerdefinierte Cookie-Handler müssen von der <xref:System.IdentityModel.Services.CookieHandler> -Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="7fd2b-129">Das `<customCookieHandler>` -Element wird durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> -Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7fd2b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7fd2b-130">Example</span></span>  
 <span data-ttu-id="7fd2b-131">Im folgenden Beispiel wird Sam für die Verwendung eines benutzerdefinierten cookiehandlers vom Typ `MyNamespace.MyCustomCookieHandler`konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="7fd2b-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7fd2b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fd2b-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
