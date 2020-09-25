---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a8ee23ac6facaea18cd7f1820616cb9b16afa336
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189850"
---
# \<customCookieHandler>

<span data-ttu-id="70151-101">Legt den Typ des benutzerdefinierten Cookie-Handlers fest.</span><span class="sxs-lookup"><span data-stu-id="70151-101">Sets the custom cookie handler type.</span></span> <span data-ttu-id="70151-102">Dieses Element kann nur vorhanden sein, wenn das- `mode` Attribut des- `<cookieHandler>` Elements "Custom" ist.</span><span class="sxs-lookup"><span data-stu-id="70151-102">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="70151-103">Der benutzerdefinierte Typ muss von der- <xref:System.IdentityModel.Services.CookieHandler> Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="70151-103">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a><span data-ttu-id="70151-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70151-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70151-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="70151-105">Attributes and Elements</span></span>  

 <span data-ttu-id="70151-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="70151-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70151-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="70151-107">Attributes</span></span>  
  
|<span data-ttu-id="70151-108">attribute</span><span class="sxs-lookup"><span data-stu-id="70151-108">Attribute</span></span>|<span data-ttu-id="70151-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="70151-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70151-110">type</span><span class="sxs-lookup"><span data-stu-id="70151-110">type</span></span>|<span data-ttu-id="70151-111">Gibt einen benutzerdefinierten Typ an, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="70151-111">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="70151-112">Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="70151-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70151-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70151-113">Child Elements</span></span>  

 <span data-ttu-id="70151-114">Keine</span><span class="sxs-lookup"><span data-stu-id="70151-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70151-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="70151-115">Parent Elements</span></span>  
  
|<span data-ttu-id="70151-116">Element</span><span class="sxs-lookup"><span data-stu-id="70151-116">Element</span></span>|<span data-ttu-id="70151-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70151-117">Description</span></span>|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|<span data-ttu-id="70151-118">Konfiguriert den <xref:System.IdentityModel.Services.CookieHandler> , der <xref:System.IdentityModel.Services.SessionAuthenticationModule> von verwendet wird, um Cookies zu lesen und zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="70151-118">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70151-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="70151-119">Remarks</span></span>  

 <span data-ttu-id="70151-120">Wenn Sie einen benutzerdefinierten cookiehandler angeben, indem Sie das- `mode` Attribut des- `<cookieHandler>` Elements auf "Custom" festlegen, müssen Sie den Typ des benutzerdefinierten cookiehandlers angeben, indem Sie ein untergeordnetes- `<customCookieHandler>` Element einschließen, das auf den Typ der</span><span class="sxs-lookup"><span data-stu-id="70151-120">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="70151-121">Dieses Element kann nicht angegeben werden, wenn das- `mode` Attribut auf "Chunked" oder "Default" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="70151-121">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="70151-122">Benutzerdefinierte Cookie-Handler müssen von der-Klasse abgeleitet werden <xref:System.IdentityModel.Services.CookieHandler> .</span><span class="sxs-lookup"><span data-stu-id="70151-122">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="70151-123">Das- `<customCookieHandler>` Element wird durch die- <xref:System.IdentityModel.Configuration.CustomTypeElement> Klasse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70151-123">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70151-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70151-124">Example</span></span>  

 <span data-ttu-id="70151-125">Im folgenden Beispiel wird Sam für die Verwendung eines benutzerdefinierten cookiehandlers vom Typ konfiguriert `MyNamespace.MyCustomCookieHandler` .</span><span class="sxs-lookup"><span data-stu-id="70151-125">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70151-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70151-126">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
