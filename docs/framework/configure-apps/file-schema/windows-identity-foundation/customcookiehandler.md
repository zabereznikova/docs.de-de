---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47081590"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="6a70c-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="6a70c-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="6a70c-103">Legt fest, den Handlertyp der benutzerdefinierten Cookies.</span><span class="sxs-lookup"><span data-stu-id="6a70c-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="6a70c-104">Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut der `<cookieHandler>` Element ist "Custom".</span><span class="sxs-lookup"><span data-stu-id="6a70c-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="6a70c-105">Aus der benutzerdefinierte Typ abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6a70c-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="6a70c-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="6a70c-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="6a70c-107">\<FederationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6a70c-107">\<federationConfiguration></span></span>  
<span data-ttu-id="6a70c-108">\<CookieHandler ></span><span class="sxs-lookup"><span data-stu-id="6a70c-108">\<cookieHandler></span></span>  
<span data-ttu-id="6a70c-109">\<CustomCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="6a70c-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a70c-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a70c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a70c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6a70c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6a70c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a70c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a70c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="6a70c-113">Attributes</span></span>  
  
|<span data-ttu-id="6a70c-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="6a70c-114">Attribute</span></span>|<span data-ttu-id="6a70c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a70c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a70c-116">Typ</span><span class="sxs-lookup"><span data-stu-id="6a70c-116">type</span></span>|<span data-ttu-id="6a70c-117">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6a70c-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="6a70c-118">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6a70c-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a70c-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a70c-119">Child Elements</span></span>  
 <span data-ttu-id="6a70c-120">Keiner</span><span class="sxs-lookup"><span data-stu-id="6a70c-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a70c-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a70c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6a70c-122">Element</span><span class="sxs-lookup"><span data-stu-id="6a70c-122">Element</span></span>|<span data-ttu-id="6a70c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a70c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a70c-124">\<CookieHandler ></span><span class="sxs-lookup"><span data-stu-id="6a70c-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="6a70c-125">Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a70c-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a70c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a70c-126">Remarks</span></span>  
 <span data-ttu-id="6a70c-127">Wenn Sie einen benutzerdefinierten cookiehandler angeben, indem Sie festlegen der `mode` Attribut der `<cookieHandler>` Element in "Benutzerdefiniert", geben Sie den Typ des der benutzerdefinierten cookiehandler dazu eine `<customCookieHandler>` untergeordnetes Element, das den Cookie Handlertyp verweist.</span><span class="sxs-lookup"><span data-stu-id="6a70c-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="6a70c-128">Dieses Element nicht angegeben, wenn die `mode` -Attribut auf "Chunked" oder "Default" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6a70c-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="6a70c-129">Benutzerdefiniertes Cookie Handler müssen abgeleitet werden, aus der <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6a70c-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="6a70c-130">Die `<customCookieHandler>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="6a70c-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a70c-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6a70c-131">Example</span></span>  
 <span data-ttu-id="6a70c-132">Im folgenden Beispiel wird das SAM um einen benutzerdefinierten cookiehandler des Typs verwenden `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="6a70c-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a70c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a70c-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
