---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347511"
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="baa0a-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="baa0a-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="baa0a-103">Registriert die Service-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="baa0a-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="baa0a-104">Dienst-tokenresolvers wird verwendet, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="baa0a-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="baa0a-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="baa0a-105">\<system.identityModel></span></span>  
<span data-ttu-id="baa0a-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="baa0a-106">\<identityConfiguration></span></span>  
<span data-ttu-id="baa0a-107">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="baa0a-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="baa0a-108">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="baa0a-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="baa0a-109">\<ServiceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="baa0a-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baa0a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="baa0a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="baa0a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="baa0a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="baa0a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="baa0a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="baa0a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="baa0a-113">Attributes</span></span>  
  
|<span data-ttu-id="baa0a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="baa0a-114">Attribute</span></span>|<span data-ttu-id="baa0a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="baa0a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="baa0a-116">Typ</span><span class="sxs-lookup"><span data-stu-id="baa0a-116">type</span></span>|<span data-ttu-id="baa0a-117">Gibt den Typ des Dienst-tokenresolvers.</span><span class="sxs-lookup"><span data-stu-id="baa0a-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="baa0a-118">Entweder die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="baa0a-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="baa0a-119">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="baa0a-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="baa0a-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="baa0a-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="baa0a-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baa0a-121">Child Elements</span></span>  
 <span data-ttu-id="baa0a-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="baa0a-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="baa0a-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="baa0a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="baa0a-124">Element</span><span class="sxs-lookup"><span data-stu-id="baa0a-124">Element</span></span>|<span data-ttu-id="baa0a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="baa0a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="baa0a-126">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="baa0a-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="baa0a-127">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="baa0a-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baa0a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="baa0a-128">Remarks</span></span>  
 <span data-ttu-id="baa0a-129">Der Dienst-tokenresolver kann verwendet werden, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="baa0a-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="baa0a-130">Es wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln der eingehender Tokens verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="baa0a-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="baa0a-131">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="baa0a-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="baa0a-132">Der angegebene Typ kann es sich entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="baa0a-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="baa0a-133">Einige Tokenhandler können Sie Sicherheitstoken-Resolver-diensteinstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="baa0a-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="baa0a-134">Einstellungen für einzelne Tokenhandler außer Kraft setzen auf der Sicherheitstoken-Handlerauflistung angegeben.</span><span class="sxs-lookup"><span data-stu-id="baa0a-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="baa0a-135">Angeben der `<serviceTokenResolver>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="baa0a-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="baa0a-136">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="baa0a-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baa0a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="baa0a-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
