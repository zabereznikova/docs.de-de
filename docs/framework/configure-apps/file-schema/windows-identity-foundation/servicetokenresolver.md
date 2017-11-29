---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="65661-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="65661-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="65661-103">Registriert die Dienst-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="65661-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="65661-104">Die Dienst-tokenresolver dient zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="65661-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="65661-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="65661-105">\<system.identityModel></span></span>  
<span data-ttu-id="65661-106">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="65661-106">\<identityConfiguration></span></span>  
<span data-ttu-id="65661-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="65661-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="65661-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="65661-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="65661-109">\<ServiceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="65661-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65661-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="65661-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65661-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="65661-111">Attributes and Elements</span></span>  
 <span data-ttu-id="65661-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65661-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65661-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="65661-113">Attributes</span></span>  
  
|<span data-ttu-id="65661-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="65661-114">Attribute</span></span>|<span data-ttu-id="65661-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65661-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65661-116">Typ</span><span class="sxs-lookup"><span data-stu-id="65661-116">type</span></span>|<span data-ttu-id="65661-117">Gibt den Typ des Diensts token Konfliktlösers.</span><span class="sxs-lookup"><span data-stu-id="65661-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="65661-118">Entweder die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="65661-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="65661-119">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="65661-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="65661-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="65661-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65661-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65661-121">Child Elements</span></span>  
 <span data-ttu-id="65661-122">Keine</span><span class="sxs-lookup"><span data-stu-id="65661-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65661-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65661-123">Parent Elements</span></span>  
  
|<span data-ttu-id="65661-124">Element</span><span class="sxs-lookup"><span data-stu-id="65661-124">Element</span></span>|<span data-ttu-id="65661-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65661-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65661-126">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="65661-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="65661-127">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="65661-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65661-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65661-128">Remarks</span></span>  
 <span data-ttu-id="65661-129">Die Dienst-tokenresolver kann zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="65661-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="65661-130">Es dient zum Abrufen des Schlüssels, der zum Entschlüsseln der eingehender Tokens verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65661-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="65661-131">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="65661-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="65661-132">Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="65661-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="65661-133">Einige Tokenhandler können Sie tokenresolver diensteinstellungen in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="65661-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="65661-134">Einstellungen für einzelne Tokenhandler überschreiben für die Sicherheit Tokenhandler Auflistung angegebenen.</span><span class="sxs-lookup"><span data-stu-id="65661-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65661-135">Angeben der `<serviceTokenResolver>` Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber noch für die Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="65661-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="65661-136">Einstellungen auf der `<securityTokenHandlerConfiguration>` Element, überschreiben Sie die auf die `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="65661-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65661-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65661-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
