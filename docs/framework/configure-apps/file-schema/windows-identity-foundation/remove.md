---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251929"
---
# <a name="remove"></a><span data-ttu-id="39bc8-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="39bc8-101">\<remove></span></span>
<span data-ttu-id="39bc8-102">Entfernt den angegebenen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="39bc8-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="39bc8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39bc8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39bc8-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="39bc8-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="39bc8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="39bc8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="39bc8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="39bc8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="39bc8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<entfernen >**</span><span class="sxs-lookup"><span data-stu-id="39bc8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39bc8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="39bc8-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39bc8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39bc8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="39bc8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39bc8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39bc8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="39bc8-111">Attributes</span></span>  
  
|<span data-ttu-id="39bc8-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="39bc8-112">Attribute</span></span>|<span data-ttu-id="39bc8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39bc8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39bc8-114">Typ</span><span class="sxs-lookup"><span data-stu-id="39bc8-114">type</span></span>|<span data-ttu-id="39bc8-115">Der CLR-Typname des tokenhandlers, der entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39bc8-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="39bc8-116">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="39bc8-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="39bc8-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="39bc8-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39bc8-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39bc8-118">Child Elements</span></span>  
 <span data-ttu-id="39bc8-119">None</span><span class="sxs-lookup"><span data-stu-id="39bc8-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39bc8-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39bc8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="39bc8-121">Element</span><span class="sxs-lookup"><span data-stu-id="39bc8-121">Element</span></span>|<span data-ttu-id="39bc8-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39bc8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39bc8-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="39bc8-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="39bc8-124">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="39bc8-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="39bc8-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39bc8-125">Example</span></span>  
 <span data-ttu-id="39bc8-126">Der folgende XML `<add>` -Code zeigt die Verwendung des `<remove>` -Elements und des-Elements, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler</span><span class="sxs-lookup"><span data-stu-id="39bc8-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="39bc8-127">Der XML-Code stammt aus `ClaimsAwareWebFarm` dem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="39bc8-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
