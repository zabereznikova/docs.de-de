---
title: '&lt;securityTokenHandlers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3151ec3511bca598e5aaabc72b821bdd3aed0b7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlersgt"></a><span data-ttu-id="6ccf5-102">&lt;securityTokenHandlers&gt;</span><span class="sxs-lookup"><span data-stu-id="6ccf5-102">&lt;securityTokenHandlers&gt;</span></span>
<span data-ttu-id="6ccf5-103">Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-103">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="6ccf5-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="6ccf5-104">\<system.identityModel></span></span>  
<span data-ttu-id="6ccf5-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6ccf5-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6ccf5-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="6ccf5-106">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ccf5-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ccf5-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ccf5-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6ccf5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6ccf5-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ccf5-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ccf5-110">Attributes</span></span>  
  
|<span data-ttu-id="6ccf5-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6ccf5-111">Attribute</span></span>|<span data-ttu-id="6ccf5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ccf5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ccf5-113">Name</span><span class="sxs-lookup"><span data-stu-id="6ccf5-113">name</span></span>|<span data-ttu-id="6ccf5-114">Gibt den Namen einer Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="6ccf5-115">Erkannt, durch das Framework nur die Werte sind "ActAs" und "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="6ccf5-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="6ccf5-116">Wenn Tokenhandler Sammlungen mit einer dieser Namen angegeben sind, wird die Auflistung beim Verarbeiten von Actas- oder ein "onbehalfof" bzw. Token verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ccf5-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ccf5-117">Child Elements</span></span>  
  
|<span data-ttu-id="6ccf5-118">Element</span><span class="sxs-lookup"><span data-stu-id="6ccf5-118">Element</span></span>|<span data-ttu-id="6ccf5-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ccf5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ccf5-120">\<add></span><span class="sxs-lookup"><span data-stu-id="6ccf5-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="6ccf5-121">Fügt eine Sicherheitstokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="6ccf5-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="6ccf5-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="6ccf5-123">Löscht alle Sicherheitstokenhandler aus der Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="6ccf5-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="6ccf5-124">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="6ccf5-125">Entfernt eine Sicherheitstokenhandler aus der Tokenhandler-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="6ccf5-126">\<SecurityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6ccf5-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6ccf5-127">Die Konfiguration für die Auflistung der Tokenhandler bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ccf5-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ccf5-128">Parent Elements</span></span>  
  
|<span data-ttu-id="6ccf5-129">Element</span><span class="sxs-lookup"><span data-stu-id="6ccf5-129">Element</span></span>|<span data-ttu-id="6ccf5-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ccf5-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ccf5-131">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6ccf5-131">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="6ccf5-132">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ccf5-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ccf5-133">Remarks</span></span>  
 <span data-ttu-id="6ccf5-134">Sie können eine oder mehrere benannte Sammlungen von sicherheitstokenhandlern in einer Dienstkonfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="6ccf5-135">Sie können einen Namen für eine Sammlung angeben, mit der `name` Attribut.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="6ccf5-136">Die einzigen Namen, die das Framework verarbeitet werden "ActAs" und "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="6ccf5-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="6ccf5-137">Wenn Handler in diesen Sammlungen vorhanden sind, werden von verwendet ein Sicherheitstokendienst (STS) anstelle der Standardhandler bei der Verarbeitung von `ActAs` und `OnBehalfOf` Token.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="6ccf5-138">Standardmäßig wird die Auflistung mit folgende Handlertypen aufgefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="6ccf5-139">Sie können die Auflistung ändern, indem Sie mit der `<add>`, `<remove>`, und `<clear>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="6ccf5-140">Sie müssen sicherstellen, dass nur ein einzelner Handler keinen bestimmten Typ in der Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="6ccf5-141">Z. B., wenn Sie einen Handler von Ableiten der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> entweder die Klasse den Handler oder <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> kann in einer einzelnen Auflistung, aber nicht beides konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="6ccf5-142">Verwenden der `<securityTokenHandlerConfiguration>` Element Konfigurationseinstellungen für die Handler in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="6ccf5-143">Durch dieses Element angegebene Einstellungen außer Kraft angegeben wird, auf den Dienst über die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="6ccf5-144">Einige Handler (einschließlich einiger der integrierten Handlertypen) unterstützen zusätzliche Konfiguration über ein untergeordnetes Element von der `<add>` Element.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="6ccf5-145">Für einen Ereignishandler angegebene Einstellungen außer Kraft setzen entsprechende Einstellungen für die Auflistung oder den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="6ccf5-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
