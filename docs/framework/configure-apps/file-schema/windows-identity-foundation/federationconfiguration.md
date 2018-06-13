---
title: '&lt;federationConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 44014d620dcd03e055eb58b50a1428b8e1b41186
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759386"
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
Konfiguriert die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) bei Verwendung federated Authentication über das WS-Verbund-Protokoll. Konfiguriert die <xref:System.Security.Claims.ClaimsAuthorizationManager> bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> -Klasse, anspruchsbasierte Zugriffssteuerung bereitzustellen.  
  
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
|Name|Der Name dieses Konfigurationselements Verbund. Dieses Attribut stellt einen Erweiterbarkeitspunkt in erster Linie für zukünftige Protokolle. Dies ist optional.|  
|identityConfigurationName|Der Name des Konfigurationsabschnitts Identität gemäß einer [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element zu verwenden. Wenn dieses Attribut nicht angegeben ist, wird der Standardabschnitt von Identity-Konfiguration verwendet. Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<"cookiehandler" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguriert die Cookie-Handler von SAM verwendet. Dies ist optional.|  
|[\<ServiceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird. Dies ist optional.|  
|[\<WsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Konfiguriert die WS-Verbund-Authentifizierungsmodul (WSFAM). Dies ist optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Der Konfigurationsabschnitt für die Authentifizierung mit dem WS-Verbund-Protokoll.|  
  
## <a name="remarks"></a>Hinweise  
 Die \<FederationConfiguration >-Element stellt die Einstellungen in zwei verschiedene Szenarien bereit:  
  
-   Bei Verwendung von WS-Verbund in einer passiven Webanwendung wird das Element enthält Einstellungen zur Konfiguration der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). Außerdem verweist er auf die identitätskonfiguration verwendet werden soll, Sicherheitstokenhandler und Zertifikate und Komponenten, wie die Ansprüche Autorisierungs-Manager und Ansprüche Authentifizierungs-Manager konfigurieren.  
  
-   Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code bereitzustellen, das Element verweist auf die identitätskonfiguration, die die Ansprüche Autorisierungs-Manager und die Richtlinie, die verwendet wird, um die Autorisierung stellen konfiguriert Entscheidungen. Dies ist "true" auch in Szenarien, die nicht passiven Web Szenarien sind; Windows Communication Foundation (WCF)-Anwendungen oder eine Anwendung, die nicht webbasierte ist. Wenn die Anwendung nicht auf einem passiven Webanwendung ist der [ \<ClaimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) -Element (und der untergeordneten Richtlinienelemente, falls vorhanden) der identitätskonfiguration verweist die `<federationConfiguration>` Element Die einzigen Einstellungen werden angewendet werden. Alle anderen werden ignoriert.  
  
 Unabhängig von dem Szenario lädt die Common Language Runtime die Standardkonfiguration für den Verbund. Das Verhalten wird wie folgt definiert:  
  
1.  Es ist keine `<federationConfiguration>` Element vorhanden ist, die Common Language Runtime erstellt eine Verbund-Konfiguration und füllt sie mit Standardwerten. Diese Standardkonfiguration für den Verbund wird die standardidentitätskonfiguration verweisen.  
  
2.  Wenn ein einzelner `<federationConfiguration>` Element vorhanden ist, wird die Standardkonfiguration Verbund, unabhängig davon, ob sie mit dem Namen oder nicht benannt ist. Wenn ihre `identityConfiguration` -Attribut angegeben ist, wird die benannte identitätskonfiguration verwiesen wird; andernfalls wird die standardidentitätskonfiguration verwiesen.  
  
3.  Wenn eine unbenannte `<federationConfiguration>` Element vorhanden ist, wird die Standardkonfiguration für den Verbund. Wenn ihre `identityConfiguration` -Attribut angegeben ist, wird die benannte identitätskonfiguration verwiesen wird; andernfalls wird die standardidentitätskonfiguration verwiesen.  
  
4.  Wenn mehrere benannte `<federationConfiguration>` Elemente sind vorhanden und keine unbenannten `<federationConfiguration>` -Element vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 In der Regel nur einen einzigen `<federationConfiguration>` Abschnitt definiert ist. In diesem Abschnitt wird die Standardkonfiguration für den Verbund. Sie können angeben, dass mehrere eindeutig benannt `<federationConfiguration>` Elemente jedoch in diesem Fall, wenn Sie eine Verbund-Konfiguration als dem unbenannten laden möchten, müssen Sie angeben einen Handler für das. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> Ereignis, und legen die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft innerhalb der Handler, der eine <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt initialisiert wurde, mit Werten aus der entsprechenden `<federationConfiguration>` Element in der Konfigurationsdatei.  
  
 Die `<federationConfiguration>` Element dargestellt ist, durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> Klasse. Das Konfigurationsobjekt selbst wird dargestellt, indem die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Klasse. Ein einzelnes <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> -Instanzensatz auf die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft und stellt verbundenen Konfiguration für die Anwendung.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt ein `<federationConfiguration>` Element, gibt die Einstellungen für die WSFAM und gibt an, dass, der Cookie-Standardhandler (eine Instanz von der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse) von SAM verwendet werden.  
  
> [!WARNING]
>  Weder die Cookie-Handler noch WSFAM sind in diesem Beispiel zur Verwendung von HTTPS erforderlich. Grund hierfür ist, die `requireHttps` -Attribut auf die `<wsFederation>` Element und die `requireSsl` -Attribut auf die `<cookieHandlerElement>` sind `false`. Diese Einstellungen werden für die meisten produktionsumgebungen nicht empfohlen, wie sie ein Sicherheitsrisiko vorhanden sein können.  
  
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
