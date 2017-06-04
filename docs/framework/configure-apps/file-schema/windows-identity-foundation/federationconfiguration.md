---
title: "&lt;federationConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;federationConfiguration&gt;
Konfiguriert die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\), wenn Sie mit federated Authentifizierung über WS\-Federation\-Protokoll.  Konfiguriert die <xref:System.Security.Claims.ClaimsAuthorizationManager> bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um Claims\-based Access Control.  
  
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
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|name|Der Name dieses Konfigurationselements Föderation.  Dieses Attribut Erweiterungspunkt in erster Linie ein für zukünftige Protokolle.  Optional.|  
|identityConfigurationName|Der Name des Konfigurationsabschnitts Identität gemäß einer [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element verwenden.  Wenn dieses Attribut nicht angegeben ist, wird der Standard\-Identität\-Konfigurationsabschnitt verwendet.  Optional.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Konfiguriert den Cookie\-Handler von SAM verwendet.  Optional.|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.  Optional.|  
|[\<wsFederation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Konfiguriert das Modul für die Authentifizierung der WS\-Federation \(WSFAM\).  Optional.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<system.identityModel.services\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Der Konfigurationsabschnitt für die Authentifizierung mithilfe des Protokolls WS\-Federation.|  
  
## Hinweise  
 \<federationConfiguration\> Element enthält Einstellungen in zwei verschiedenen Szenarien:  
  
-   Mithilfe von WS\-Federation in einer passiven Web\-Anwendung das Element enthält Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).  Außerdem verweist er auf die Identity\-Konfiguration verwendet werden, um Sicherheitstokenhandler und Zertifikate und Komponenten wie Ansprüche Autorisierungs\-Manager und Ansprüche Authentifizierungs\-Manager konfigurieren.  
  
-   Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse Claims\-based Access Control in Ihrem Code bereitstellen, das Element verweist auf die Identität\-Konfiguration, die konfiguriert die Ansprüche Autorisierungs\-Manager und die Richtlinie, die verwendet wird, um Autorisierungsentscheidungen treffen zu können.  Dies gilt, auch in Szenarien, die nicht auf passive Webszenarios sind; Windows Communication Foundation \(WCF\)\-Anwendungen oder eine Anwendung, die nicht Web\-basiert ist.  Wenn die Anwendung nicht über eine passive Webanwendung ist die [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) Element \(und seine untergeordneten Richtlinienelemente, sofern vorhanden\) der Identität Konfiguration verweist die `<federationConfiguration>` Element sind die einzigen Einstellungen angewendet.  Alle anderen werden ignoriert.  
  
 Unabhängig von dem Szenario lädt die Common Language Runtime die Standardkonfiguration für die Föderation.  Das Verhalten ist wie folgt definiert:  
  
1.  Wenn es gibt keine `<federationConfiguration>` Element vorhanden, die Common Language Runtime erstellt eine Föderation\-Konfiguration und füllt es mit Standardwerten.  Diese Standardkonfiguration für die Föderation wird die Standardkonfiguration für die Identität verweisen.  
  
2.  Wenn ein einzelnes `<federationConfiguration>` Element vorhanden ist, ist die Standardkonfiguration für die Föderation unabhängig davon, ob sie benannt oder unbenannt ist.  Wenn ihre `identityConfiguration` \-Attribut angegeben ist, wird die Konfiguration benannte Identität verwiesen; Andernfalls wird die Standardkonfiguration für die Identität verwiesen.  
  
3.  Wenn Sie einen unbenannten `<federationConfiguration>` Element vorhanden ist, ist die Konfiguration des Verbunds.  Wenn ihre `identityConfiguration` \-Attribut angegeben ist, wird die Konfiguration benannte Identität verwiesen; Andernfalls wird die Standardkonfiguration für die Identität verwiesen.  
  
4.  Wenn mehrere Namen `<federationConfiguration>` Elemente sind vorhanden und keine unbenannten `<federationConfiguration>` Element vorhanden ist, wird eine Ausnahme ausgelöst.  
  
 In der Regel nur eine einzige `<federationConfiguration>` \-Abschnitt definiert ist.  In diesem Abschnitt wird die Konfiguration des Verbunds.  Sie können angeben, dass mehrere eindeutig benannte `<federationConfiguration>` Elemente; in diesem Fall, wenn Sie eine Föderation Konfiguration als die unbenannte laden möchten, Sie müssen allerdings bereitstellen einen Handler für das.  <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>Ereignis und setzen die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> Eigenschaft innerhalb der Handler, der ein <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Objekt mit den entsprechenden Werten initialisiert `<federationConfiguration>` Element in der Konfigurationsdatei.  
  
 Die `<federationConfiguration>` Element dargestellt durch die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> Klasse.  Das Configuration\-Objekt selbst wird dargestellt durch die <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Klasse.  Ein einzelnes <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> Instanz wird festgelegt, auf die <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> Eigenschaft und federated Konfiguration für die Anwendung bietet.  
  
## Beispiel  
 Das folgende XML zeigt eine `<federationConfiguration>` \-Element gibt die Einstellungen für die WSFAM und gibt an, dass der Standardhandler für das Cookie \(eine Instanz von der <xref:System.IdentityModel.Services.ChunkedCookieHandler> Klasse\) von der SAM verwendet werden.  
  
> [!WARNING]
>  Weder die Cookie\-Handler noch WSFAM sind in diesem Beispiel zur Verwendung von HTTPS erforderlich.  Dies liegt daran, die `requireHttps` \-Attribut auf die `<wsFederation>` Element und die `requireSsl` \-Attribut auf die `<cookieHandlerElement>` sind `false`.  Diese Einstellungen werden für die meisten Produktionsumgebungen nicht empfohlen, da sie ein Sicherheitsrisiko darstellen können.  
  
```  
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
  
## Siehe auch  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>   
 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)