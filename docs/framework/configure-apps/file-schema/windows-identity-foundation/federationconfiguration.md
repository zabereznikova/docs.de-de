---
title: '&lt;federationConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 66fa16992d779b08ee8c55598efc98f8f5267656
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48245035"
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
Konfiguriert die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) bei Verwendung von Verbundauthentifizierung über das WS-Verbund-Protokoll. Konfiguriert die <xref:System.Security.Claims.ClaimsAuthorizationManager> bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung bereitzustellen.  
  
 \<system.identityModel.services >  
\<FederationConfiguration >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Der Name dieses Verbund-Konfigurationselements. Dieses Attribut stellt einen Erweiterungspunkt in erster Linie für zukünftigen Protokolle. Dies ist optional.|  
|identityConfigurationName|Der Name des Konfigurationsabschnitts Identität gemäß einer [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element verwenden. Wenn dieses Attribut nicht angegeben ist, wird der Standard-Identity-Konfigurationsabschnitt verwendet. Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<CookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Den von SAM verwendeten cookiehandler wird konfiguriert. Dies ist optional.|  
|[\<ServiceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird. Dies ist optional.|  
|[\<WsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Konfiguriert das WS-Verbund-Authentifizierungsmodul (WSFAM). Dies ist optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Der Konfigurationsabschnitt für die Authentifizierung mit dem WS-Verbund-Protokoll.|  
  
## <a name="remarks"></a>Hinweise  
 Die \<FederationConfiguration >-Element stellt die Einstellungen in zwei verschiedene Szenarien bereit:  
  
-   Bei Verwendung von WS-Verbund in einer passiven Webanwendung wird das Element enthält Einstellungen, die die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Es enthält außerdem die identitätskonfiguration verwendet werden, um Sicherheitstokenhandler und Zertifikate und Komponenten wie den anspruchsautorisierungs-Manager und den anspruchsauthentifizierungs-Manager zu konfigurieren.  
  
-   Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code bereitzustellen, das Element verweist auf die identitätskonfiguration, die konfiguriert werden, die anspruchsautorisierungs-Manager und die Richtlinie, mit der Autorisierung, Entscheidungen. Dies gilt, auch in Szenarien, die nicht passiven Szenarien mit Web sind; z. B. Anwendungen für Windows Communication Foundation (WCF) oder eine Anwendung, die nicht webbasierte ist. Wenn die Anwendung nicht mit einer passiven Webanwendung ist die [ \<"claimsauthorizationmanager" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) -Element (und seine untergeordneten Richtlinienelemente, sofern vorhanden) der identitätskonfiguration verwiesen die `<federationConfiguration>` Element Die einzigen Einstellungen werden angewendet werden. Alle anderen werden ignoriert.  
  
 Unabhängig vom Szenario gilt lädt die Runtime die Standardkonfiguration für den Verbund. Das Verhalten wird wie folgt definiert:  
  
1.  Es ist keine `<federationConfiguration>` -Element vorhanden ist, die Laufzeit eine Verbundkonfiguration erstellt und füllt sie mit den Standardwerten. Diese Standardkonfiguration für den Verbund wird die standardidentitätskonfiguration verwiesen.  
  
2.  Wenn ein einzelner `<federationConfiguration>` -Element vorhanden ist, ist die Standardkonfiguration für die verbundanmeldung unabhängig davon, ob sie mit dem Namen oder nicht benannt ist. Wenn die `identityConfiguration` -Attribut angegeben ist, die benannte identitätskonfiguration verwiesen wird; andernfalls wird die standardidentitätskonfiguration verwiesen.  
  
3.  Wenn ein unbenannter `<federationConfiguration>` -Element vorhanden ist, ist die Standardkonfiguration für den Verbund. Wenn die `identityConfiguration` -Attribut angegeben ist, die benannte identitätskonfiguration verwiesen wird; andernfalls wird die standardidentitätskonfiguration verwiesen.  
  
4.  Wenn mehrere Namen `<federationConfiguration>` Elemente sind vorhanden und keine unbenannten `<federationConfiguration>` -Element vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 In der Regel nur eine einzige `<federationConfiguration>` -Abschnitt definiert ist. Dieser Abschnitt ist die Standardkonfiguration für den Verbund. Sie können angeben, dass mehrere eindeutig benannte `<federationConfiguration>` Elemente jedoch in diesem Fall sollten Sie eine Verbundkonfiguration als der unbenannten zu laden, geben Sie einen Handler für das. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> Ereignis, und legen die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft innerhalb der Handler, der eine <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt mit Werten aus der entsprechenden initialisiert `<federationConfiguration>` Element in der Konfigurationsdatei.  
  
 Die `<federationConfiguration>` Element wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> Klasse. Das Konfigurationsobjekt selbst wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Klasse. Ein einzelnes <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Instanz wird festgelegt, auf die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft sowie Verbundkonfiguration für die Anwendung.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt ein `<federationConfiguration>` Element, das Einstellungen für das WSFAM gibt an, und gibt an, dass den standardcookiehandler (eine Instanz von der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse), der von SAM verwendet werden.  
  
> [!WARNING]
>  Weder die WSFAM den cookiehandler sind in diesem Beispiel zur Verwendung von HTTPS erforderlich. Grund hierfür ist, die `requireHttps` -Attribut für die `<wsFederation>` Element und die `requireSsl` -Attribut für die `<cookieHandlerElement>` sind `false`. Diese Einstellungen werden nicht für die meisten produktionsumgebungen empfohlen, wie sie ein Sicherheitsrisiko darstellen können.  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"   
      issuer="http://localhost:15839/wsFederationSTS/Issue"   
      realm="http://localhost:50969/" reply="http://localhost:50969/"   
      requireHttps="false"   
      signOutReply="http://localhost:50969/SignedOutPage.html"   
      signOutQueryString="Param1=value2&Param2=value2"   
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
