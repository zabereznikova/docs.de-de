---
title: <add> von <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: 64f0dd5c97ddfcd2fffd8ff4820d02af8c1ced54
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926894"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="f1920-102">\<Fügen Sie > \<von "zufüge-euris" hinzu ></span><span class="sxs-lookup"><span data-stu-id="f1920-102">\<add> of \<allowedAudienceUris></span></span>
<span data-ttu-id="f1920-103">Fügt einen Ziel-URI hinzu, für den das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass dieser von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="f1920-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="f1920-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f1920-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f1920-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f1920-105">\<behaviors></span></span>  
<span data-ttu-id="f1920-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f1920-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f1920-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f1920-107">\<behavior></span></span>  
<span data-ttu-id="f1920-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="f1920-108">\<serviceCredentials></span></span>  
<span data-ttu-id="f1920-109">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1920-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="f1920-110">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="f1920-110">\<allowedAudienceUris></span></span>  
<span data-ttu-id="f1920-111">\<Fügen Sie > Element \<für ' zufüwedaudienceuris ' hinzu ></span><span class="sxs-lookup"><span data-stu-id="f1920-111">\<add> element for \<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1920-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1920-112">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1920-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f1920-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f1920-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f1920-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1920-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="f1920-115">Attributes</span></span>  
  
|<span data-ttu-id="f1920-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="f1920-116">Attribute</span></span>|<span data-ttu-id="f1920-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1920-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1920-118">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="f1920-118">allowedAudienceUri</span></span>|<span data-ttu-id="f1920-119">Eine Zeichenfolge, die eine Ziel-URI enthält, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="f1920-119">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1920-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f1920-120">Child Elements</span></span>  
 <span data-ttu-id="f1920-121">Keine</span><span class="sxs-lookup"><span data-stu-id="f1920-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1920-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f1920-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f1920-123">Element</span><span class="sxs-lookup"><span data-stu-id="f1920-123">Element</span></span>|<span data-ttu-id="f1920-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1920-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1920-125">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="f1920-125">\<allowedAudienceUris></span></span>](allowedaudienceuris.md)|<span data-ttu-id="f1920-126">Stellt eine Auflistung von Ziel-URIs dar, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="f1920-126">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1920-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1920-127">Remarks</span></span>  
 <span data-ttu-id="f1920-128">Verwenden Sie diese Auflistung in einer Verbundanwendung, die einen Sicherheitstokendienst (Security Token Service, STS) nutzt, der <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="f1920-128">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="f1920-129">Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> dem Sicherheitstoken hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f1920-129">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="f1920-130">Der <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f1920-130">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="f1920-131">Legen Sie das `audienceUriMode`-Attribut für `<issuedTokenAuthentication>` auf <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> oder <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> fest.</span><span class="sxs-lookup"><span data-stu-id="f1920-131">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="f1920-132">Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f1920-132">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="f1920-133">Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="f1920-133">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="f1920-134">Weitere Informationen zur Verwendung dieses Konfigurations Elements finden [Sie unter Gewusst wie: Konfigurieren Sie die Anmelde Informationen](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)für einen Verbunddienst.</span><span class="sxs-lookup"><span data-stu-id="f1920-134">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1920-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1920-135">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="f1920-136">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="f1920-136">\<allowedAudienceUris></span></span>](allowedaudienceuris.md)
- [<span data-ttu-id="f1920-137">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="f1920-137">\<issuedTokenAuthentication></span></span>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="f1920-138">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="f1920-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f1920-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="f1920-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f1920-140">Vorgehensweise: Konfigurieren von Anmelde Informationen für eine Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="f1920-140">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
