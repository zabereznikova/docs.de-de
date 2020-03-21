---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152579"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="0d22e-101">\<dienstTokenResolver></span><span class="sxs-lookup"><span data-stu-id="0d22e-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="0d22e-102">Registriert den Diensttoken-Resolver, der von Handlern in der Tokenhandlerauflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d22e-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="0d22e-103">Der Diensttokenlöser wird verwendet, um das Verschlüsselungstoken für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="0d22e-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="0d22e-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0d22e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0d22e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0d22e-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0d22e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0d22e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0d22e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="0d22e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="0d22e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0d22e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="0d22e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dienstTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="0d22e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d22e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d22e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d22e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0d22e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0d22e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d22e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d22e-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="0d22e-113">Attributes</span></span>  
  
|<span data-ttu-id="0d22e-114">attribute</span><span class="sxs-lookup"><span data-stu-id="0d22e-114">Attribute</span></span>|<span data-ttu-id="0d22e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d22e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d22e-116">type</span><span class="sxs-lookup"><span data-stu-id="0d22e-116">type</span></span>|<span data-ttu-id="0d22e-117">Gibt den Typ des Diensttokenresolvers an.</span><span class="sxs-lookup"><span data-stu-id="0d22e-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="0d22e-118">Entweder <xref:System.IdentityModel.Selectors.SecurityTokenResolver> der Typ oder ein Typ, <xref:System.IdentityModel.Selectors.SecurityTokenResolver> der von der Klasse stammt.</span><span class="sxs-lookup"><span data-stu-id="0d22e-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="0d22e-119">Weitere Informationen zum Angeben `type` des Attributs finden Sie unter [Benutzerdefinierte Typreferenzen].</span><span class="sxs-lookup"><span data-stu-id="0d22e-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="0d22e-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d22e-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d22e-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d22e-121">Child Elements</span></span>  
 <span data-ttu-id="0d22e-122">Keine</span><span class="sxs-lookup"><span data-stu-id="0d22e-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d22e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d22e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0d22e-124">Element</span><span class="sxs-lookup"><span data-stu-id="0d22e-124">Element</span></span>|<span data-ttu-id="0d22e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d22e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d22e-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="0d22e-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="0d22e-127">Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="0d22e-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d22e-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0d22e-128">Remarks</span></span>  
 <span data-ttu-id="0d22e-129">Der Diensttokenlöser kann verwendet werden, um das Verschlüsselungstoken für eingehende Token und Nachrichten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="0d22e-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="0d22e-130">Es wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln eingehender Token verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d22e-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="0d22e-131">Sie müssen `type` das Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="0d22e-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="0d22e-132">Der angegebene Typ <xref:System.IdentityModel.Selectors.SecurityTokenResolver> kann entweder oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse abstammt.</span><span class="sxs-lookup"><span data-stu-id="0d22e-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="0d22e-133">Einige Tokenhandler ermöglichen es Ihnen, Diensttoken-Resolvereinstellungen in der Konfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d22e-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="0d22e-134">Einstellungen für einzelne Tokenhandler überschreiben die in der Sicherheitstokenhandlerauflistung angegebenen.</span><span class="sxs-lookup"><span data-stu-id="0d22e-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d22e-135">Die Angabe `<serviceTokenResolver>` des Elements als untergeordnetes Element der [ \<identityConfiguration>-Element](identityconfiguration.md) sprägiert, wird aber aus Gründen der Abwärtskompatibilität weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0d22e-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="0d22e-136">Einstellungen für `<securityTokenHandlerConfiguration>` das Element überschreiben die Einstellungen für das `<identityConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="0d22e-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d22e-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d22e-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
