---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793808"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="12b29-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="12b29-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="12b29-102">Registriert die Service-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="12b29-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="12b29-103">Dienst-tokenresolvers wird verwendet, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="12b29-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="12b29-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="12b29-104">\<system.identityModel></span></span>  
<span data-ttu-id="12b29-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="12b29-105">\<identityConfiguration></span></span>  
<span data-ttu-id="12b29-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="12b29-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="12b29-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="12b29-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="12b29-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="12b29-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b29-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="12b29-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12b29-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12b29-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12b29-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12b29-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12b29-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="12b29-112">Attributes</span></span>  
  
|<span data-ttu-id="12b29-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="12b29-113">Attribute</span></span>|<span data-ttu-id="12b29-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12b29-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="12b29-115">Typ</span><span class="sxs-lookup"><span data-stu-id="12b29-115">type</span></span>|<span data-ttu-id="12b29-116">Gibt den Typ des Dienst-tokenresolvers.</span><span class="sxs-lookup"><span data-stu-id="12b29-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="12b29-117">Entweder die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="12b29-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="12b29-118">Weitere Informationen zur Vorgehensweise beim Angeben der `type` Attribut, finden Sie unter [benutzerdefinierte Typverweise].</span><span class="sxs-lookup"><span data-stu-id="12b29-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="12b29-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="12b29-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="12b29-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12b29-120">Child Elements</span></span>  
 <span data-ttu-id="12b29-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="12b29-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="12b29-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12b29-122">Parent Elements</span></span>  
  
|<span data-ttu-id="12b29-123">Element</span><span class="sxs-lookup"><span data-stu-id="12b29-123">Element</span></span>|<span data-ttu-id="12b29-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12b29-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12b29-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="12b29-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="12b29-126">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="12b29-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12b29-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12b29-127">Remarks</span></span>  
 <span data-ttu-id="12b29-128">Der Dienst-tokenresolver kann verwendet werden, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben.</span><span class="sxs-lookup"><span data-stu-id="12b29-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="12b29-129">Es wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln der eingehender Tokens verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="12b29-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="12b29-130">Sie müssen angeben, die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="12b29-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="12b29-131">Der angegebene Typ kann es sich entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.</span><span class="sxs-lookup"><span data-stu-id="12b29-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="12b29-132">Einige Tokenhandler können Sie Sicherheitstoken-Resolver-diensteinstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="12b29-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="12b29-133">Einstellungen für einzelne Tokenhandler außer Kraft setzen auf der Sicherheitstoken-Handlerauflistung angegeben.</span><span class="sxs-lookup"><span data-stu-id="12b29-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="12b29-134">Angeben der `<serviceTokenResolver>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="12b29-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="12b29-135">Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="12b29-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12b29-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12b29-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
