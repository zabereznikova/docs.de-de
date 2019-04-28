---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: f758fc8e0934f56f9593246497d8aba5084c4a79
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673510"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="930e3-101">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="930e3-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="930e3-102">Stellt eine Auflistung von Ziel-URIs dar, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="930e3-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="930e3-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="930e3-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="930e3-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="930e3-104">\<behaviors></span></span>  
<span data-ttu-id="930e3-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="930e3-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="930e3-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="930e3-106">\<behavior></span></span>  
<span data-ttu-id="930e3-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="930e3-107">\<serviceCredentials></span></span>  
<span data-ttu-id="930e3-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="930e3-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="930e3-109">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="930e3-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="930e3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="930e3-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="930e3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="930e3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="930e3-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="930e3-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="930e3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="930e3-113">Attributes</span></span>  
 <span data-ttu-id="930e3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="930e3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="930e3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="930e3-115">Child Elements</span></span>  
  
|<span data-ttu-id="930e3-116">Element</span><span class="sxs-lookup"><span data-stu-id="930e3-116">Element</span></span>|<span data-ttu-id="930e3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="930e3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="930e3-118">\<add></span><span class="sxs-lookup"><span data-stu-id="930e3-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="930e3-119">Fügt einen Ziel-URI hinzu, für den das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass dieser von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="930e3-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="930e3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="930e3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="930e3-121">Element</span><span class="sxs-lookup"><span data-stu-id="930e3-121">Element</span></span>|<span data-ttu-id="930e3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="930e3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="930e3-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="930e3-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="930e3-124">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="930e3-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="930e3-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="930e3-125">Remarks</span></span>  
 <span data-ttu-id="930e3-126">Verwenden Sie diese Auflistung in einer Verbundanwendung, die einen Sicherheitstokendienst (Security Token Service, STS) nutzt, der <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="930e3-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="930e3-127">Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> dem Sicherheitstoken hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="930e3-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="930e3-128">Der <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="930e3-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="930e3-129">Legen Sie das `audienceUriMode`-Attribut für `<issuedTokenAuthentication>` auf <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> oder <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> fest.</span><span class="sxs-lookup"><span data-stu-id="930e3-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="930e3-130">Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="930e3-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="930e3-131">Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="930e3-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="930e3-132">Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="930e3-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="930e3-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="930e3-133">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="930e3-134">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="930e3-134">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="930e3-135">\<add></span><span class="sxs-lookup"><span data-stu-id="930e3-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)
- [<span data-ttu-id="930e3-136">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="930e3-136">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="930e3-137">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="930e3-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="930e3-138">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="930e3-138">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
