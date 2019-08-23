---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 678e5c705181c55257b1ddb853690ada60ecd17a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942460"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="3b8b7-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3b8b7-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="3b8b7-102">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="3b8b7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3b8b7-103">\<system.identityModel></span></span>  
<span data-ttu-id="3b8b7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3b8b7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3b8b7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3b8b7-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8b7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b8b7-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b8b7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3b8b7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3b8b7-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b8b7-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="3b8b7-109">Attributes</span></span>  
  
|<span data-ttu-id="3b8b7-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="3b8b7-110">Attribute</span></span>|<span data-ttu-id="3b8b7-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b8b7-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b8b7-112">Name</span><span class="sxs-lookup"><span data-stu-id="3b8b7-112">name</span></span>|<span data-ttu-id="3b8b7-113">Gibt den Namen einer tokenhandlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="3b8b7-114">Die einzigen Werte, die vom Framework erkannt werden, sind "ACTAS" und "onbehalfof".</span><span class="sxs-lookup"><span data-stu-id="3b8b7-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="3b8b7-115">Wenn tokenhandlerauflistungen mit einem dieser Namen angegeben werden, wird die Auflistung verwendet, wenn ACTAS bzw. onbehalfof-Token verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b8b7-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b8b7-116">Child Elements</span></span>  
  
|<span data-ttu-id="3b8b7-117">Element</span><span class="sxs-lookup"><span data-stu-id="3b8b7-117">Element</span></span>|<span data-ttu-id="3b8b7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b8b7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b8b7-119">\<add></span><span class="sxs-lookup"><span data-stu-id="3b8b7-119">\<add></span></span>](add.md)|<span data-ttu-id="3b8b7-120">Fügt der tokenhandlerauflistung einen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="3b8b7-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="3b8b7-121">\<clear></span></span>](clear.md)|<span data-ttu-id="3b8b7-122">Löscht alle Sicherheitstokenhandler aus der Auflistung von tokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="3b8b7-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="3b8b7-123">\<remove></span></span>](remove.md)|<span data-ttu-id="3b8b7-124">Entfernt einen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="3b8b7-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3b8b7-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="3b8b7-126">Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b8b7-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3b8b7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3b8b7-128">Element</span><span class="sxs-lookup"><span data-stu-id="3b8b7-128">Element</span></span>|<span data-ttu-id="3b8b7-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b8b7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b8b7-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3b8b7-130">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="3b8b7-131">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b8b7-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3b8b7-132">Remarks</span></span>  
 <span data-ttu-id="3b8b7-133">Sie können eine oder mehrere benannte Sammlungen von Sicherheitstokenhandlern in einer Dienst Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="3b8b7-134">Mithilfe des `name` -Attributs können Sie einen Namen für eine Sammlung angeben.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="3b8b7-135">Die einzigen Namen, die das Framework behandelt, sind "ACTAS" und "onbehalfof".</span><span class="sxs-lookup"><span data-stu-id="3b8b7-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="3b8b7-136">Wenn Handler in diesen Auflistungen vorhanden sind, werden Sie bei der Verarbeitung `ActAs` von-und- `OnBehalfOf` Token von einem Sicherheitstokendienst (STS) anstelle von Standard Handlern verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="3b8b7-137">Standardmäßig wird die Auflistung mit den folgenden Handlertypen aufgefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="3b8b7-138">Sie können die Sammlung mithilfe der `<add>`Elemente, `<remove>`und `<clear>` ändern.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="3b8b7-139">Sie müssen sicherstellen, dass nur ein einzelner Handler eines bestimmten Typs in der Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="3b8b7-140">Wenn Sie z. b. einen Handler von der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> -Klasse ableiten, kann entweder der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Handler oder der in einer einzelnen Auflistung konfiguriert werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="3b8b7-141">Verwenden Sie `<securityTokenHandlerConfiguration>` das-Element, um Konfigurationseinstellungen für die Handler in der Auflistung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="3b8b7-142">Durch dieses Element angegebene Einstellungen überschreiben die für den Dienst angegebenen Einstellungen über das [ \<identityconfiguration->](identityconfiguration.md) Element.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="3b8b7-143">Einige Handler (einschließlich mehrerer integrierter Handlertypen) können zusätzliche Konfigurationen durch ein untergeordnetes Element des `<add>` -Elements unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="3b8b7-144">Die Einstellungen, die für einen Handler angegeben werden, überschreiben die in der Auflistung oder dem Dienst angegebenen entsprechenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3b8b7-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
