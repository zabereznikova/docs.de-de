---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152735"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Konfiguriert das <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> und das (SAM) bei verwendung der Verbundauthentifizierung über das WS-Federation-Protokoll. Konfiguriert die, <xref:System.Security.Claims.ClaimsAuthorizationManager> wenn <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die Klasse verwendet wird, um anspruchsbasierte Zugriffssteuerung bereitzustellen.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<FederationConfiguration>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|name|Der Name dieses Verbund-Konfigurationselements. Dieses Attribut stellt in erster Linie einen Erweiterbarkeitspunkt für zukünftige Protokolle bereit. Optional.|  
|identityConfigurationName|Der Name des Identitätskonfigurationsabschnitts, wie in einem [ \<identityConfiguration->-Element](identityconfiguration.md) angegeben. Wenn dieses Attribut nicht angegeben ist, wird der Standard-Identitätskonfigurationsabschnitt verwendet. Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Konfiguriert den vom SAM verwendeten Cookiehandler. Optional.|  
|[\<serviceCertificate>](servicecertificate.md)|Konfiguriert das Zertifikat, das zum Ver- und Entschlüsseln von Token verwendet wird. Optional.|  
|[\<wsFöderation>](wsfederation.md)|Konfiguriert das WS-Federation Authentication Module (WSFAM). Optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Konfigurationsabschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das \<federationConfiguration>-Element stellt Einstellungen in zwei verschiedenen Szenarien bereit:  
  
- Wenn WS-Federation in einer passiven Webanwendung verwendet <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> wird, enthält das <xref:System.IdentityModel.Services.SessionAuthenticationModule> Element Einstellungen, die das (WSFAM) und das (SAM) konfigurieren. Außerdem wird auf die Identitätskonfiguration verwiesen, die zum Konfigurieren von Sicherheitstokenhandlern und Zertifikaten verwendet werden soll, sowie auf Komponenten wie den Anspruchsautorisierungs-Manager und den Anspruchsauthentifizierungs-Manager.  
  
- Wenn Sie <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die Klasse verwenden, um anspruchsbasierte Zugriffssteuerung in Ihrem Code bereitzustellen, verweist das Element auf die Identitätskonfiguration, die den Anspruchautorisierungs-Manager und die Richtlinie konfiguriert, die zum Vornehmen von Autorisierungsentscheidungen verwendet wird. Dies gilt auch in Szenarien, die keine passiven Webszenarien sind. Z. B. Windows Communication Foundation (WCF)-Anwendungen oder eine Anwendung, die nicht webbasiert ist. Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, sind die `<federationConfiguration>` [ \<claimsAuthorizationManager>-Elements](claimsauthorizationmanager.md) (und deren untergeordnete Richtlinienelemente, falls vorhanden) der Identitätskonfiguration, auf die das Element verweist, die einzigen angewendeten Einstellungen. Alle anderen werden ignoriert.  
  
 Unabhängig vom Szenario lädt die Laufzeit die Standardverbundkonfiguration. Das Verhalten ist wie folgt definiert:  
  
1. Wenn kein `<federationConfiguration>` Element vorhanden ist, erstellt die Laufzeit eine Verbundkonfiguration und füllt sie mit Standardwerten auf. Diese Standardverbundkonfiguration verweist auf die Standardidentitätskonfiguration.  
  
2. Wenn ein `<federationConfiguration>` einzelnes Element vorhanden ist, ist es die Standard-Verbundkonfiguration, unabhängig davon, ob es benannt oder unbenannt ist. Wenn `identityConfiguration` das Attribut angegeben ist, wird auf die benannte Identitätskonfiguration verwiesen. Andernfalls wird auf die Standardidentitätskonfiguration verwiesen.  
  
3. Wenn ein `<federationConfiguration>` unbenanntes Element vorhanden ist, ist es die Standard-Verbundkonfiguration. Wenn `identityConfiguration` das Attribut angegeben ist, wird auf die benannte Identitätskonfiguration verwiesen. Andernfalls wird auf die Standardidentitätskonfiguration verwiesen.  
  
4. Wenn mehrere `<federationConfiguration>` benannte Elemente vorhanden `<federationConfiguration>` sind und kein unbenanntes Element vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 In der Regel `<federationConfiguration>` wird nur ein einzelner Abschnitt definiert. Dieser Abschnitt ist die Standardkonfiguration des Verbunds. Sie können mehrere Elemente mit `<federationConfiguration>` eindeutigen Namen angeben. Wenn Sie jedoch in diesem Fall eine andere Verbundkonfiguration als die unbenannte laden möchten, müssen Sie einen Handler für die bereitstellen. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>ereignis und <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> legen Sie die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Eigenschaft innerhalb des Handlers `<federationConfiguration>` auf ein Objekt fest, das mit Werten aus dem entsprechenden Element in der Konfigurationsdatei initialisiert wurde.  
  
 Das `<federationConfiguration>` Element wird <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> durch die Klasse dargestellt. Das Konfigurationsobjekt selbst wird <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> durch die Klasse dargestellt. Eine <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> einzelne Instanz wird <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> für die Eigenschaft festgelegt und stellt eine Verbundkonfiguration für die Anwendung bereit.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt ein `<federationConfiguration>` Element, das Einstellungen für das WSFAM angibt und angibt, dass der Standardcookiehandler (eine Instanz der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse) vom SAM verwendet wird.  
  
> [!WARNING]
> In diesem Beispiel sind weder der Cookiehandler noch WSFAM erforderlich, um HTTPS zu verwenden. Dies liegt `requireHttps` daran, `<wsFederation>` dass `requireSsl` das Attribut `<cookieHandlerElement>` `false`für das Element und das Attribut auf der . Diese Einstellungen werden für die meisten Produktionsumgebungen nicht empfohlen, da sie möglicherweise ein Sicherheitsrisiko darstellen.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
