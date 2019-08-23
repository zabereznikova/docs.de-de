---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923110"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="3a025-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="3a025-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="3a025-102">Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a025-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="3a025-103">Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="3a025-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="3a025-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3a025-104">\<system.identityModel></span></span>  
<span data-ttu-id="3a025-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a025-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3a025-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3a025-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3a025-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a025-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="3a025-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="3a025-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a025-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a025-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a025-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a025-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3a025-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a025-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a025-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a025-112">Attributes</span></span>  
  
|<span data-ttu-id="3a025-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3a025-113">Attribute</span></span>|<span data-ttu-id="3a025-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a025-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a025-115">Typ</span><span class="sxs-lookup"><span data-stu-id="3a025-115">type</span></span>|<span data-ttu-id="3a025-116">Gibt den Typ des diensttokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="3a025-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="3a025-117">Entweder der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3a025-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="3a025-118">Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [Custom Type References].</span><span class="sxs-lookup"><span data-stu-id="3a025-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="3a025-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3a025-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a025-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a025-120">Child Elements</span></span>  
 <span data-ttu-id="3a025-121">None</span><span class="sxs-lookup"><span data-stu-id="3a025-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a025-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a025-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3a025-123">Element</span><span class="sxs-lookup"><span data-stu-id="3a025-123">Element</span></span>|<span data-ttu-id="3a025-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a025-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a025-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3a025-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="3a025-126">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="3a025-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a025-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a025-127">Remarks</span></span>  
 <span data-ttu-id="3a025-128">Der diensttokenresolver kann verwendet werden, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="3a025-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="3a025-129">Sie wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln eingehender Token verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a025-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="3a025-130">Sie müssen das `type` -Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="3a025-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="3a025-131">Der angegebene Typ kann entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3a025-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="3a025-132">Mit einigen tokenhandlern können Sie Einstellungen für den diensttokenresolver in der Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="3a025-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="3a025-133">Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.</span><span class="sxs-lookup"><span data-stu-id="3a025-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3a025-134">Die Angabe `<serviceTokenResolver>` des-Elements als untergeordnetes Element [ \<des identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3a025-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="3a025-135">Die Einstellungen für `<securityTokenHandlerConfiguration>` das-Element überschreiben `<identityConfiguration>` die für das-Element.</span><span class="sxs-lookup"><span data-stu-id="3a025-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a025-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a025-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
