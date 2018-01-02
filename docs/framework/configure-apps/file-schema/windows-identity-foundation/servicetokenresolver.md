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
ms.workload: dotnet
ms.openlocfilehash: cd981c8e48f003060c74787fdd2f29557c07901d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="b8006-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="b8006-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="b8006-103">Registriert die Dienst-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8006-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b8006-104">Die Dienst-tokenresolver dient zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b8006-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b8006-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="b8006-105">\<system.identityModel></span></span>  
<span data-ttu-id="b8006-106">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b8006-106">\<identityConfiguration></span></span>  
<span data-ttu-id="b8006-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b8006-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b8006-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b8006-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b8006-109">\<ServiceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="b8006-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8006-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8006-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8006-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b8006-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b8006-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8006-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8006-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b8006-113">Attributes</span></span>  
  
|<span data-ttu-id="b8006-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b8006-114">Attribute</span></span>|<span data-ttu-id="b8006-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8006-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8006-116">Typ</span><span class="sxs-lookup"><span data-stu-id="b8006-116">type</span></span>|<span data-ttu-id="b8006-117">Gibt den Typ des Diensts token Konfliktlösers.</span><span class="sxs-lookup"><span data-stu-id="b8006-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="b8006-118">Entweder die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b8006-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="b8006-119">Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="b8006-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="b8006-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b8006-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8006-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8006-121">Child Elements</span></span>  
 <span data-ttu-id="b8006-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="b8006-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8006-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8006-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b8006-124">Element</span><span class="sxs-lookup"><span data-stu-id="b8006-124">Element</span></span>|<span data-ttu-id="b8006-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8006-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8006-126">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b8006-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b8006-127">Ermöglicht die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b8006-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8006-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8006-128">Remarks</span></span>  
 <span data-ttu-id="b8006-129">Die Dienst-tokenresolver kann zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8006-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="b8006-130">Es dient zum Abrufen des Schlüssels, der zum Entschlüsseln der eingehender Tokens verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8006-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="b8006-131">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="b8006-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="b8006-132">Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="b8006-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b8006-133">Einige Tokenhandler können Sie tokenresolver diensteinstellungen in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="b8006-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="b8006-134">Einstellungen für einzelne Tokenhandler überschreiben für die Sicherheit Tokenhandler Auflistung angegebenen.</span><span class="sxs-lookup"><span data-stu-id="b8006-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8006-135">Angeben der `<serviceTokenResolver>` Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber noch für die Abwärtskompatibilität unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b8006-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b8006-136">Einstellungen auf der `<securityTokenHandlerConfiguration>` Element, überschreiben Sie die auf die `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="b8006-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8006-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8006-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
