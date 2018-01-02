---
title: '&lt;add&gt; von &lt;allowedAudienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b10a0ef5718197464ffa40126f0a013d82256dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltallowedaudienceurisgt"></a><span data-ttu-id="eacd2-102">&lt;add&gt; von &lt;allowedAudienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="eacd2-102">&lt;add&gt; of &lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="eacd2-103">Fügt einen Ziel-URI hinzu, für den das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass dieser von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="eacd2-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="eacd2-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eacd2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eacd2-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="eacd2-105">\<behaviors></span></span>  
<span data-ttu-id="eacd2-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="eacd2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="eacd2-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="eacd2-107">\<behavior></span></span>  
<span data-ttu-id="eacd2-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="eacd2-108">\<serviceCredentials></span></span>  
<span data-ttu-id="eacd2-109">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="eacd2-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="eacd2-110">\<AllowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="eacd2-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="eacd2-111">\<Hinzufügen >-Element für \<AllowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="eacd2-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eacd2-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="eacd2-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>   
   <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eacd2-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eacd2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="eacd2-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eacd2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eacd2-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="eacd2-115">Attributes</span></span>  
  
|<span data-ttu-id="eacd2-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="eacd2-116">Attribute</span></span>|<span data-ttu-id="eacd2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eacd2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eacd2-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="eacd2-118">allowedAudienceUri</span></span>|<span data-ttu-id="eacd2-119">Eine Zeichenfolge, die eine Ziel-URI enthält, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="eacd2-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eacd2-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eacd2-120">Child Elements</span></span>  
 <span data-ttu-id="eacd2-121">Keine</span><span class="sxs-lookup"><span data-stu-id="eacd2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eacd2-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eacd2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="eacd2-123">Element</span><span class="sxs-lookup"><span data-stu-id="eacd2-123">Element</span></span>|<span data-ttu-id="eacd2-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eacd2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eacd2-125">\<AllowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="eacd2-125">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|<span data-ttu-id="eacd2-126">Stellt eine Auflistung von Ziel-URIs dar, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="eacd2-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eacd2-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eacd2-127">Remarks</span></span>  
 <span data-ttu-id="eacd2-128">Verwenden Sie diese Auflistung in einer Verbundanwendung, die einen Sicherheitstokendienst (Security Token Service, STS) nutzt, der <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="eacd2-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="eacd2-129">Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> dem Sicherheitstoken hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="eacd2-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="eacd2-130">Der <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="eacd2-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="eacd2-131">Legen Sie das `audienceUriMode`-Attribut für `<issuedTokenAuthentication>` auf <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> oder <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> fest.</span><span class="sxs-lookup"><span data-stu-id="eacd2-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="eacd2-132">Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eacd2-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="eacd2-133">Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="eacd2-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="eacd2-134">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="eacd2-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eacd2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eacd2-135">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="eacd2-136">\<AllowedAudienceUris ></span><span class="sxs-lookup"><span data-stu-id="eacd2-136">\<allowedAudienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)  
 [<span data-ttu-id="eacd2-137">\<IssuedTokenAuthentication ></span><span class="sxs-lookup"><span data-stu-id="eacd2-137">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="eacd2-138">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="eacd2-138">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="eacd2-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="eacd2-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="eacd2-140">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="eacd2-140">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
