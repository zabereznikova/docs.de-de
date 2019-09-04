---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251850"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="81c04-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="81c04-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="81c04-102">Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="81c04-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="81c04-103">Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="81c04-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="81c04-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81c04-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81c04-105">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="81c04-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="81c04-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="81c04-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="81c04-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="81c04-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="81c04-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration->** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="81c04-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="81c04-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicetokenresolver >**</span><span class="sxs-lookup"><span data-stu-id="81c04-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c04-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="81c04-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81c04-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="81c04-111">Attributes and Elements</span></span>  
 <span data-ttu-id="81c04-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="81c04-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81c04-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="81c04-113">Attributes</span></span>  
  
|<span data-ttu-id="81c04-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="81c04-114">Attribute</span></span>|<span data-ttu-id="81c04-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81c04-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81c04-116">Typ</span><span class="sxs-lookup"><span data-stu-id="81c04-116">type</span></span>|<span data-ttu-id="81c04-117">Gibt den Typ des diensttokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="81c04-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="81c04-118">Entweder der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="81c04-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="81c04-119">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="81c04-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="81c04-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81c04-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81c04-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="81c04-121">Child Elements</span></span>  
 <span data-ttu-id="81c04-122">None</span><span class="sxs-lookup"><span data-stu-id="81c04-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81c04-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="81c04-123">Parent Elements</span></span>  
  
|<span data-ttu-id="81c04-124">Element</span><span class="sxs-lookup"><span data-stu-id="81c04-124">Element</span></span>|<span data-ttu-id="81c04-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81c04-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81c04-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="81c04-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="81c04-127">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="81c04-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81c04-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81c04-128">Remarks</span></span>  
 <span data-ttu-id="81c04-129">Der diensttokenresolver kann verwendet werden, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="81c04-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="81c04-130">Sie wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln eingehender Token verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="81c04-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="81c04-131">Sie müssen das `type` -Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="81c04-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="81c04-132">Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="81c04-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="81c04-133">Mit einigen tokenhandlern können Sie Einstellungen für den diensttokenresolver in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="81c04-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="81c04-134">Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.</span><span class="sxs-lookup"><span data-stu-id="81c04-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="81c04-135">Die Angabe `<serviceTokenResolver>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81c04-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="81c04-136">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="81c04-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81c04-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81c04-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 