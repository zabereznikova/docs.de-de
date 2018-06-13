---
title: '&lt;add&gt; von &lt;allowedAudienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: cfd18d6af5248e680b9520069fb34c412ee12b3f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746627"
---
# <a name="ltaddgt-of-ltallowedaudienceurisgt"></a>&lt;add&gt; von &lt;allowedAudienceUris&gt;
Fügt einen Ziel-URI hinzu, für den das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass dieser von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<serviceCredentials>  
\<IssuedTokenAuthentication >  
\<AllowedAudienceUris >  
\<Hinzufügen >-Element für \<AllowedAudienceUris >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<allowedAudienceUris>   
   <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|allowedAudienceUri|Eine Zeichenfolge, die eine Ziel-URI enthält, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft wird.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<AllowedAudienceUris >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)|Stellt eine Auflistung von Ziel-URIs dar, für die das <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken verwendet werden kann, sodass diese von einer <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>-Instanz als gültig eingestuft werden.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Auflistung in einer Verbundanwendung, die einen Sicherheitstokendienst (Security Token Service, STS) nutzt, der <xref:System.IdentityModel.Tokens.SamlSecurityToken>-Sicherheitstoken ausstellt. Wenn der STS das Sicherheitstoken ausstellt, kann er den URI des Webdiensts angeben, für den das Sicherheitstoken verwendet werden soll, indem <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> dem Sicherheitstoken hinzugefügt wird. Der <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> für den Webdienst kann so überprüfen, ob das ausgestellte Sicherheitstoken für diesen Webdienst ausgelegt ist, indem diese Überprüfung durchgeführt wird. Führen Sie hierzu die folgenden Schritte aus:  
  
-   Legen Sie das `audienceUriMode`-Attribut für `<issuedTokenAuthentication>` auf <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> oder <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> fest.  
  
-   Geben Sie den Satz gültiger URIs an, indem Sie die URIs dieser Auflistung hinzufügen.  
  
 Weitere Informationen finden Sie unter <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.  
  
 Weitere Informationen zur Verwendung dieses Konfigurationselements finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [\<AllowedAudienceUris >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowedaudienceuris.md)  
 [\<IssuedTokenAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
