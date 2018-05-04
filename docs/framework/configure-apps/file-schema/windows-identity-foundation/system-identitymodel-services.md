---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;system.identityModel.services&gt;
Der Konfigurationsabschnitt für die Authentifizierung mit dem WS-Verbund-Protokoll.  
  
 \<system.identityModel.services >  
  
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
 Keiner  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält die Einstellungen zur Konfiguration der <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP-Module.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
 Keiner  
  
## <a name="remarks"></a>Hinweise  
 Hinzufügen einer `<system.identityModel.services>` Abschnitt aus, um Sie in der Konfigurationsdatei Ihrer Anwendung das SAM und WSFAM Einstellungen bereit.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> -Klasse, anspruchsbasierte Zugriffssteuerung in Ihrem Code, den Ansprüche Autorisierungs-Manager bereitzustellen (<xref:System.Security.Claims.ClaimsAuthorizationManager>) und die Richtlinie, die verwendet wird, um autorisierungsentscheidungen zu treffen sind so konfiguriert, über ein `<identityConfiguration>` Element, das implizit oder explizit verwiesen wird, aus einer `<federationConfiguration>` Element in diesem Abschnitt. Weitere Informationen finden Sie unter der **"Hinweise"** unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.  
  
 Die `<system.identityModel.services>` Abschnitt wird dargestellt, indem die <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> Klasse. Die Auflistung untergeordneter `<federationConfiguration>` Elemente, die den im Abschnitt konfigurierten wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt das Hinzufügen einer `<system.identityModel.services>` Abschnitt aus, um eine Konfigurationsdatei. Sie müssen zunächst Abschnitt Deklarationen für beide Hinzufügen der `<system.identityModel.services>` Abschnitt und der `<system.identityModel>` Abschnitte. (Beim Hinzufügen einer `<system.identityModel.services>` Abschnitt, sollten Sie auch eine Deklaration für Hinzufügen der `<system.identityModel>` Abschnitt aus, um sicherzustellen, dass auf den Standardwert `<identityConfiguration>` Abschnitt bei Bedarf von der Laufzeit erstellt werden.) Nachdem die Abschnitt Deklarationen hinzugefügt wurden, können Sie konfigurieren, dass Verbundauthentifizierung Einstellungen unter dem `<system.identityModel.services>` Element.  
  
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
