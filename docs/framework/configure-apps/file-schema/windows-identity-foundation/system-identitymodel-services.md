---
title: "&lt;system.identityModel.services&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;system.identityModel.services&gt;
Der Konfigurationsabschnitt für die Authentifizierung mithilfe des Protokolls WS\-Federation.  
  
 \<system.identityModel.services\>  
  
## Syntax  
  
```  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 None  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält die Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) HTTP\-Module.|  
  
### Übergeordnete Elemente  
 None  
  
## Hinweise  
 Hinzufügen einer `<system.identityModel.services>` Abschnitt, um Sie in der Konfigurationsdatei der Anwendung, um Einstellungen für die SAM und WSFAM bereitzustellen.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code die Ansprüche Autorisierungs\-Manager \(<xref:System.Security.Claims.ClaimsAuthorizationManager>\) und Richtlinien, die verwendet wird, um Autorisierungsentscheidungen treffen konfiguriert sind, durch ein `<identityConfiguration>` Element, das implizit oder explizit vom verwiesen wird ein `<federationConfiguration>` Element in diesem Abschnitt.  Weitere Informationen finden Sie unter der  **Bemerkungen** unter den [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.  
  
 Die `<system.identityModel.services>` Abschnitt wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> Klasse.  Die Auflistung der untergeordneten `<federationConfiguration>` Elemente, die im Abschnitt konfiguriert wird dargestellt durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse.  
  
## Beispiel  
 Das folgende XML veranschaulicht das Hinzufügen einer `<system.identityModel.services>` Abschnitt einer Konfigurationsdatei.  Sie müssen zuerst hinzufügen Abschnitt Deklarationen für beide die `<system.identityModel.services>` Abschnitt und die `<system.identityModel>` Abschnitte.  \(Beim Hinzufügen einer `<system.identityModel.services>` Abschnitt, sollten auch Sie eine Deklaration für die `<system.identityModel>` Abschnitt, um sicherzustellen, dass einen Standard `<identityConfiguration>` Abschnitt kann von der Laufzeit erstellt werden, falls erforderlich.\) Nachdem die Deklarationen Abschnitt hinzugefügt wurden, können Sie Verbundauthentifizierung Einstellungen unter der `<system.identityModel.services>` Element.  
  
```  
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