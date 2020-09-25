---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: 602e25240ddbd337543efa8c4097d4da9e5c25e9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201628"
---
# \<allowedAudienceUris>

<span data-ttu-id="86ac7-101">Stellt eine Auflistung von Ziel-URIs dar, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="86ac7-101">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowedAudienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="86ac7-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="86ac7-102">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86ac7-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86ac7-103">Attributes and Elements</span></span>  

 <span data-ttu-id="86ac7-104">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86ac7-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86ac7-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="86ac7-105">Attributes</span></span>  

 <span data-ttu-id="86ac7-106">Keine</span><span class="sxs-lookup"><span data-stu-id="86ac7-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86ac7-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86ac7-107">Child Elements</span></span>  
  
|<span data-ttu-id="86ac7-108">Element</span><span class="sxs-lookup"><span data-stu-id="86ac7-108">Element</span></span>|<span data-ttu-id="86ac7-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86ac7-109">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-allowedaudienceuris.md)|<span data-ttu-id="86ac7-110">Fügt einen Ziel-URI hinzu, für den das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass dieser von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="86ac7-110">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86ac7-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86ac7-111">Parent Elements</span></span>  
  
|<span data-ttu-id="86ac7-112">Element</span><span class="sxs-lookup"><span data-stu-id="86ac7-112">Element</span></span>|<span data-ttu-id="86ac7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86ac7-113">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="86ac7-114">Gibt ein Token an, das als Dienstanmeldeinformation ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="86ac7-114">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86ac7-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="86ac7-115">Remarks</span></span>  

 <span data-ttu-id="86ac7-116">Verwenden Sie diese Auflistung in einer Verbundanwendung, die einen Sicherheitstokendienst (Security Token Service, STS) nutzt, der <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="86ac7-116">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="86ac7-117">Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> dem Sicherheitstoken hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="86ac7-117">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="86ac7-118">Der <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="86ac7-118">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="86ac7-119">Legen Sie das `audienceUriMode`-Attribut für `<issuedTokenAuthentication>` auf <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> oder <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> fest.</span><span class="sxs-lookup"><span data-stu-id="86ac7-119">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="86ac7-120">Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86ac7-120">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="86ac7-121">Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="86ac7-121">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="86ac7-122">Weitere Informationen zur Verwendung dieses Konfigurations Elements finden Sie unter Vorgehens [Weise: Konfigurieren von Anmelde Informationen auf einem Verbunddienst](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span><span class="sxs-lookup"><span data-stu-id="86ac7-122">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ac7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86ac7-123">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [\<add>](add-of-allowedaudienceuris.md)
- [<span data-ttu-id="86ac7-124">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="86ac7-124">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="86ac7-125">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="86ac7-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="86ac7-126">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="86ac7-126">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
