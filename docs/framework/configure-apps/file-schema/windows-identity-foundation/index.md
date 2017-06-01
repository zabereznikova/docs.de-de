---
title: "Windows Identity Foundation-Konfigurationsschema | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Windows Identity Foundation-Konfigurationsschema
Die Themen in diesem Abschnitt enthalten Informationen über das Konfigurationsschema für die Windows\-Identität\-Foundation \(WIF\).  Sie können auch eine Anwendung durch das Framework verfügbar gemachten Klassen WIF verwenden konfigurieren.  Diese Klassen sind in den Abschnitten beschrieben, die entsprechenden Elemente im Schema zu behandeln.  Im folgenden veranschaulicht die grundlegende XML tag\-Struktur, die das Konfigurationsschema WIF verfügbar gemachten.  Attribute werden ausgelassen.  Markierte Kommentare zeigen die Hauptkomponenten des Schemas.  
  
```  
<system.identityModel>  
    <!-- Service Configuration -->  
    <identityConfiguration>  
        <caches>  
            <sessionSecurityTokenCache />  
            <tokenReplayCache />  
        </caches>  
  
        <certificateValidation>  
            <certificateValidator />   
        </certificateValidation>  
  
        <claimsAuthenticationManager />  
  
        <claimsAuthorizationManager>  
            <optionalConfigurationElement>  
        </claimsAuthorizationManager>  
  
        <claimTypeRequired>  
            <claimType />   
        </claimTypeRequired>  
  
        <tokenReplayDetection />  
  
        <!-- Security Token Handler Collection Configuration -->  
        <securityTokenHandlers>  
            <add>  
                <!-- Can take an optional configuration element which can be one of  
                     the following or a custom element -->  
                <samlSecurityTokenHandlerRequirement>  
                    <nameClaimType>  
                    <roleClaimType>   
                </samlSecurityTokenHandlerRequirement>  
  
                <sessionSecurityTokenHandlerRequirement />  
                <x509SecurityTokenHandlerRequirement />  
                <userNameSecurityTokenHandlerRequirement />  
            </add>  
            <clear />  
            <remove />  
            <securityTokenHandlerConfiguration>  
                <audienceUris>  
                    <add>  
                    <clear>  
                    <remove>  
                </audienceUris>  
  
                <caches>  
                    <sessionSecurityTokenCache />  
                    <tokenReplayCache />  
                </caches>  
  
                <certificateValidation>  
                    <certificateValidator>   
                </certificateValidation>  
  
                <issuerNameRegistry>  
                    <!-- Can take an optional configuration element which can be   
                         the <trustedIssuers> element to configure a configuration-based  
                         issuer name registry or can be a custom element -->  
                    <trustedIssuers>  
                        <add>  
                        <clear>  
                        <remove>  
                    </trustedIssuers>  
                </issuerNameRegistry>  
  
                <issuerTokenResolver />  
                <serviceTokenResolver />  
                <tokenReplayDetection />  
            </securityTokenHandlerConfiguration>  
        </securityTokenHandlers>  
    </identityConfiguration>  
</system.identityModel>  
  
<system.identityModel.services>  
    <!-- Federation Authentication Configuration -->  
    <federatedAuthentication>  
        <cookieHandler>  
            <chunkedCookieHandler />  
            <customCookieHandler />  
        </cookieHandler>  
  
        <serviceCertificate>  
            <certificateReference>  
        </serviceCertificate>  
  
        <wsFederation />  
    </federatedAuthentication>  
</system.identityModel.services>  
```  
  
## In diesem Abschnitt  
 [\<system.identityModel\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)Stellt die Konfiguration für das Aktivieren von WIF\-Optionen in Anwendungen.  
  
 [\<system.identityModel.services\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)Ermöglicht die Konfiguration für den passiven Verbund mit WIF.  Konfiguriert das Modul für die Authentifizierung der Sitzung \(SAM\) und die Verbundauthentifizierung\-Modul \(WSFAM\).  
  
## Verwandte Abschnitte  
 [Configuration, Administration, And Management](http://msdn.microsoft.com/de-de/1e03c389-de2c-4096-aaff-86b087e1bea0)Beschreibt das Konfigurieren und Verwalten von WIF\-Anwendungen und Dienste.