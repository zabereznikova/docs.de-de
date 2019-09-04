---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 148b2f3e12fbfbf85b800f0ca7f5dc7dc1845d24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252000"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Konfiguriert den <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (wsfam) und den <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam), wenn die Verbund Authentifizierung über das WS-Verbund Protokoll verwendet wird. Konfiguriert den <xref:System.Security.Claims.ClaimsAuthorizationManager> , wenn die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -Klasse oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> die-Klasse zum Bereitstellen der Anspruchs basierten Zugriffs Steuerung verwendet wird.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel. Services->** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<federationconfiguration->**  
  
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
|Name|Der Name dieses Verbund Konfigurations Elements. Dieses Attribut stellt in erster Linie einen Erweiterbarkeits Punkt für künftige Protokolle bereit. Optional.|  
|identityConfigurationName|Der Name des Identitäts Konfigurations Abschnitts, der in einem [ \<identityconfiguration->](identityconfiguration.md) zu verwendenden Element angegeben ist. Wenn dieses Attribut nicht angegeben wird, wird der standardmäßige Identitäts Konfigurations Abschnitt verwendet. Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Konfiguriert den von Sam verwendeten cookiehandler. Optional.|  
|[\<serviceCertificate>](servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird. Optional.|  
|[\<wsFederation>](wsfederation.md)|Konfiguriert das WS-Federation-Authentifizierungs Modul (wsfam). Optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Konfigurations Abschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.|  
  
## <a name="remarks"></a>Hinweise  
 Das \<Element federationconfiguration > stellt Einstellungen in zwei verschiedenen Szenarien bereit:  
  
- Wenn Sie WS-Federation in einer passiven Webanwendung verwenden, enthält das-Element Einstellungen <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> , mit denen (wsfam <xref:System.IdentityModel.Services.SessionAuthenticationModule> ) und (Sam) konfiguriert werden. Außerdem wird auf die Identitäts Konfiguration verwiesen, die zum Konfigurieren von Sicherheitstokenhandlern und-Zertifikaten verwendet werden soll, sowie Komponenten wie der Anspruchs Autorisierungs-Manager und der anspruchsauthentifizierungs-Manager  
  
- Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -Klasse <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die-Klasse verwenden, um eine Anspruchs basierte Zugriffs Steuerung im Code bereitzustellen, verweist das-Element auf die Identitäts Konfiguration, die den anspruchsautorisierungs-Manager und die Richtlinie konfiguriert, die für die Autorisierung gefasst. Dies gilt auch für Szenarien, bei denen es sich nicht um passive Webszenarien handelt. beispielsweise Windows Communication Foundation (WCF)-Anwendungen oder eine Anwendung, die nicht webbasiert ist. Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, sind das [ \<ClaimsAuthorizationManager->](claimsauthorizationmanager.md) Element (und seine untergeordneten Richtlinien Elemente, falls vorhanden `<federationConfiguration>` ) der Identitäts Konfiguration, auf die das-Element verweist, die einzigen Einstellungen. verhängt. Alle anderen werden ignoriert.  
  
 Unabhängig vom Szenario lädt die Laufzeit die Standard Verbund Konfiguration. Das Verhalten wird wie folgt definiert:  
  
1. Wenn kein `<federationConfiguration>` -Element vorhanden ist, erstellt die Laufzeit eine Verbund Konfiguration und füllt sie mit Standardwerten. Diese Standard Verbund Konfiguration verweist auf die Standardkonfiguration für die Identität.  
  
2. Wenn ein einzelnes `<federationConfiguration>` Element vorhanden ist, ist es die Standard Verbund Konfiguration, unabhängig davon, ob Sie benannt oder unbenannt ist. Wenn das zugehörige- Attributangegebenist,wirdaufdieKonfigurationderbenanntenIdentitätverwiesen;andernfallswirdaufdiestandardmäßigeIdentitätsKonfigurationverwiesen.`identityConfiguration`  
  
3. Wenn ein unbenanntes `<federationConfiguration>` Element vorhanden ist, handelt es sich um die Standard Verbund Konfiguration. Wenn das zugehörige- Attributangegebenist,wirdaufdieKonfigurationderbenanntenIdentitätverwiesen;andernfallswirdaufdiestandardmäßigeIdentitätsKonfigurationverwiesen.`identityConfiguration`  
  
4. Wenn mehrere benannte `<federationConfiguration>` Elemente vorhanden sind und kein Unbenanntes `<federationConfiguration>` Element vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 In der Regel wird nur `<federationConfiguration>` ein einzelner Abschnitt definiert. Dieser Abschnitt ist die Standard Verbund Konfiguration. Sie können mehrere eindeutig benannte `<federationConfiguration>` Elemente angeben. in diesem Fall müssen Sie jedoch einen-Handler für das-Element bereitstellen, wenn Sie eine andere Verbund Konfiguration als die unbenannte erstellen möchten. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>und legen Sie die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> -Eigenschaft innerhalb des-Handlers auf ein <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> -Objekt fest, das `<federationConfiguration>` mit Werten aus dem entsprechenden-Element in der Konfigurationsdatei initialisiert wird.  
  
 Das `<federationConfiguration>` -Element wird durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> -Klasse dargestellt. Das Konfigurationsobjekt selbst wird durch die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> -Klasse dargestellt. Für die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> Eigenschaft wird eine einzelne Instanz festgelegt, und es wird eine Verbund Konfiguration für die Anwendung bereitstellt.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code `<federationConfiguration>` zeigt ein-Element, das Einstellungen für das wsfam angibt und angibt, dass der standardmäßige Cookie <xref:System.IdentityModel.Services.ChunkedCookieHandler> -Handler (eine Instanz der-Klasse) von Sam verwendet wird.  
  
> [!WARNING]
> In diesem Beispiel ist weder der cookiehandler noch wsfam für die Verwendung von HTTPS erforderlich. Dies liegt daran, `requireHttps` dass das- `<wsFederation>` Attribut für das `requireSsl` -Element und `<cookieHandlerElement>` `false`das-Attribut auf dem-Element ist. Diese Einstellungen werden für die meisten Produktionsumgebungen nicht empfohlen, da Sie ein Sicherheitsrisiko darstellen können.  
  
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

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
