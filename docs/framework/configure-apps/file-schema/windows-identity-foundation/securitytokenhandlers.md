---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251876"
---
# \<securityTokenHandlers>
<span data-ttu-id="9c810-101">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="9c810-101">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a><span data-ttu-id="9c810-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c810-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c810-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c810-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9c810-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c810-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c810-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c810-105">Attributes</span></span>  
  
|<span data-ttu-id="9c810-106">attribute</span><span class="sxs-lookup"><span data-stu-id="9c810-106">Attribute</span></span>|<span data-ttu-id="9c810-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9c810-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c810-108">name</span><span class="sxs-lookup"><span data-stu-id="9c810-108">name</span></span>|<span data-ttu-id="9c810-109">Gibt den Namen einer tokenhandlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="9c810-109">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="9c810-110">Die einzigen Werte, die vom Framework erkannt werden, sind "ACTAS" und "onbehalfof".</span><span class="sxs-lookup"><span data-stu-id="9c810-110">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="9c810-111">Wenn tokenhandlerauflistungen mit einem dieser Namen angegeben werden, wird die Auflistung verwendet, wenn ACTAS bzw. onbehalfof-Token verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9c810-111">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c810-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c810-112">Child Elements</span></span>  
  
|<span data-ttu-id="9c810-113">Element</span><span class="sxs-lookup"><span data-stu-id="9c810-113">Element</span></span>|<span data-ttu-id="9c810-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c810-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="9c810-115">Fügt der tokenhandlerauflistung einen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="9c810-115">Adds a security token handler to the token handler collection.</span></span>|  
|[\<clear>](clear.md)|<span data-ttu-id="9c810-116">Löscht alle Sicherheitstokenhandler aus der Auflistung von tokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="9c810-116">Clears all security token handlers from the token handler collection.</span></span>|  
|[\<remove>](remove.md)|<span data-ttu-id="9c810-117">Entfernt einen Sicherheitstokenhandler aus der tokenhandlerauflistung.</span><span class="sxs-lookup"><span data-stu-id="9c810-117">Removes a security token handler from the token handler collection.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9c810-118">Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.</span><span class="sxs-lookup"><span data-stu-id="9c810-118">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c810-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c810-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9c810-120">Element</span><span class="sxs-lookup"><span data-stu-id="9c810-120">Element</span></span>|<span data-ttu-id="9c810-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c810-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="9c810-122">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="9c810-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c810-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9c810-123">Remarks</span></span>  
 <span data-ttu-id="9c810-124">Sie können eine oder mehrere benannte Sammlungen von Sicherheitstokenhandlern in einer Dienst Konfiguration angeben.</span><span class="sxs-lookup"><span data-stu-id="9c810-124">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="9c810-125">Mithilfe des-Attributs können Sie einen Namen für eine Sammlung angeben `name` .</span><span class="sxs-lookup"><span data-stu-id="9c810-125">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="9c810-126">Die einzigen Namen, die das Framework behandelt, sind "ACTAS" und "onbehalfof".</span><span class="sxs-lookup"><span data-stu-id="9c810-126">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="9c810-127">Wenn Handler in diesen Auflistungen vorhanden sind, werden Sie bei der Verarbeitung von `ActAs` -und-Token von einem Sicherheitstokendienst (STS) anstelle von Standard Handlern verwendet `OnBehalfOf` .</span><span class="sxs-lookup"><span data-stu-id="9c810-127">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="9c810-128">Standardmäßig wird die Auflistung mit den folgenden Handlertypen aufgefüllt: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> und <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> .</span><span class="sxs-lookup"><span data-stu-id="9c810-128">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="9c810-129">Sie können die Sammlung mithilfe der `<add>` `<remove>` Elemente, und ändern `<clear>` .</span><span class="sxs-lookup"><span data-stu-id="9c810-129">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="9c810-130">Sie müssen sicherstellen, dass nur ein einzelner Handler eines bestimmten Typs in der Auflistung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9c810-130">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="9c810-131">Wenn Sie z. b. einen Handler von der- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse ableiten, kann entweder der Handler oder der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> in einer einzelnen Auflistung konfiguriert werden, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="9c810-131">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="9c810-132">Verwenden Sie das- `<securityTokenHandlerConfiguration>` Element, um Konfigurationseinstellungen für die Handler in der Auflistung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9c810-132">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="9c810-133">Durch dieses Element angegebene Einstellungen überschreiben die für den Dienst durch das-Element angegebenen Einstellungen [\<identityConfiguration>](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="9c810-133">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="9c810-134">Einige Handler (einschließlich mehrerer integrierter Handlertypen) können zusätzliche Konfigurationen durch ein untergeordnetes Element des-Elements unterstützen `<add>` .</span><span class="sxs-lookup"><span data-stu-id="9c810-134">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="9c810-135">Die Einstellungen, die für einen Handler angegeben werden, überschreiben die in der Auflistung oder dem Dienst angegebenen entsprechenden Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9c810-135">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
