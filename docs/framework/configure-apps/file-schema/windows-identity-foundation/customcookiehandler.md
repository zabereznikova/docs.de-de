---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 0129c63fe17b63889a77ea1a56c0d7e657def859
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223979"
---
# <a name="customcookiehandler"></a><span data-ttu-id="159bf-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="159bf-101">\<customCookieHandler></span></span>
<span data-ttu-id="159bf-102">Legt fest, den Handlertyp der benutzerdefinierten Cookies.</span><span class="sxs-lookup"><span data-stu-id="159bf-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="159bf-103">Dieses Element kann nur vorhanden sein, wenn die `mode` Attribut der `<cookieHandler>` Element ist "Custom".</span><span class="sxs-lookup"><span data-stu-id="159bf-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="159bf-104">Aus der benutzerdefinierte Typ abgeleitet werden die <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="159bf-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="159bf-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="159bf-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="159bf-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="159bf-106">\<federationConfiguration></span></span>  
<span data-ttu-id="159bf-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="159bf-107">\<cookieHandler></span></span>  
<span data-ttu-id="159bf-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="159bf-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159bf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="159bf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="159bf-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="159bf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="159bf-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="159bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="159bf-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="159bf-112">Attributes</span></span>  
  
|<span data-ttu-id="159bf-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="159bf-113">Attribute</span></span>|<span data-ttu-id="159bf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="159bf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="159bf-115">Typ</span><span class="sxs-lookup"><span data-stu-id="159bf-115">type</span></span>|<span data-ttu-id="159bf-116">Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="159bf-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="159bf-117">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="159bf-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="159bf-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="159bf-118">Child Elements</span></span>  
 <span data-ttu-id="159bf-119">Keiner</span><span class="sxs-lookup"><span data-stu-id="159bf-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="159bf-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="159bf-120">Parent Elements</span></span>  
  
|<span data-ttu-id="159bf-121">Element</span><span class="sxs-lookup"><span data-stu-id="159bf-121">Element</span></span>|<span data-ttu-id="159bf-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="159bf-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="159bf-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="159bf-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="159bf-124">Konfiguriert die <xref:System.IdentityModel.Services.CookieHandler> , die die <xref:System.IdentityModel.Services.SessionAuthenticationModule> zum Lesen und Schreiben von Cookies verwendet.</span><span class="sxs-lookup"><span data-stu-id="159bf-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="159bf-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="159bf-125">Remarks</span></span>  
 <span data-ttu-id="159bf-126">Wenn Sie einen benutzerdefinierten cookiehandler angeben, indem Sie festlegen der `mode` Attribut der `<cookieHandler>` Element in "Benutzerdefiniert", geben Sie den Typ des der benutzerdefinierten cookiehandler dazu eine `<customCookieHandler>` untergeordnetes Element, das den Cookie Handlertyp verweist.</span><span class="sxs-lookup"><span data-stu-id="159bf-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="159bf-127">Dieses Element nicht angegeben, wenn die `mode` -Attribut auf "Chunked" oder "Default" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="159bf-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="159bf-128">Benutzerdefiniertes Cookie Handler müssen abgeleitet werden, aus der <xref:System.IdentityModel.Services.CookieHandler> Klasse.</span><span class="sxs-lookup"><span data-stu-id="159bf-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="159bf-129">Die `<customCookieHandler>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="159bf-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="159bf-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="159bf-130">Example</span></span>  
 <span data-ttu-id="159bf-131">Im folgenden Beispiel wird das SAM um einen benutzerdefinierten cookiehandler des Typs verwenden `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="159bf-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="159bf-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="159bf-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
