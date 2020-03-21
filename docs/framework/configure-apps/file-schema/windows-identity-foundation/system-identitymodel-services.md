---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152503"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Konfigurationsabschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
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
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<FederationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> mit denen die <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP-Module (WSFAM) und (SAM) konfiguriert werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
 Keine  
  
## <a name="remarks"></a>Bemerkungen  
 Fügen `<system.identityModel.services>` Sie der Konfigurationsdatei Ihrer Anwendung einen Abschnitt hinzu, um Einstellungen für SAM und WSFAM bereitzustellen.  
  
> [!IMPORTANT]
> Wenn Sie <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die Klasse verwenden, um anspruchsbasierte Zugriffssteuerung in Ihrem Code bereitzustellen, werden der Anspruchsautorisierungs-Manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) und die Richtlinie, die zum Vornehmen von Autorisierungsentscheidungen verwendet wird, über ein `<identityConfiguration>` Element konfiguriert, das implizit oder explizit aus einem `<federationConfiguration>` Element in diesem Abschnitt referenziert wird. Weitere Informationen finden Sie unter **Die Anmerkungen** unter dem [ \<federationConfiguration>-Element.](federationconfiguration.md)  
  
 Der `<system.identityModel.services>` Abschnitt wird <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> durch die Klasse dargestellt. Die Auflistung `<federationConfiguration>` der im Abschnitt konfigurierten untergeordneten Elemente wird durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code `<system.identityModel.services>` zeigt, wie Sie einer Konfigurationsdatei einen Abschnitt hinzufügen. Sie müssen zunächst Abschnittsdeklarationen sowohl für den `<system.identityModel.services>` Abschnitt als auch für die `<system.identityModel>` Abschnitte hinzufügen. (Wenn Sie `<system.identityModel.services>` einen Abschnitt hinzufügen, sollten Sie `<system.identityModel>` auch eine Deklaration für den Abschnitt hinzufügen, um sicherzustellen, dass ein Standardabschnitt `<identityConfiguration>` bei Bedarf von der Laufzeit erstellt werden kann.) Nachdem die Abschnittsdeklarationen hinzugefügt wurden, können Sie `<system.identityModel.services>` die Verbundauthentifizierungseinstellungen unter dem Element konfigurieren.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
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
  
</configuration>  
```
