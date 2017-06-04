---
title: "&lt;securityTokenHandlerConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;securityTokenHandlerConfiguration&gt;
Stellt die Konfiguration für die Auflistung der Tokenhandler.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|saveBootstrapContext|Gibt an, ob bootstrap\-Token in den Sitzungstoken aufzunehmen.  Der Wert kann auch auf ein token Handler\-Auflistung festgelegt werden, durch Festlegen der `saveBootstrapContext` \-Attribut auf die [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.  Ein Wert festgelegt, auf die Auflistung der Tokenhandler setzt den Wert für den Dienst festgelegt.|  
|maximumClockSkew|A <xref:System.TimeSpan> , gibt die maximale erlaubte taktverschiebung.  Steuert die maximale zulässige Zeitabweichung, Ausführung zeitkritische Operationen, z. B. die Ablaufzeit einer Sitzung überprüfen.  Der Standardwert ist 5 Minuten "00: 05".  Weitere Informationen zum Angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  Die maximale Zeitabweichung kann auch auf Dienstebene festgelegt werden, durch Festlegen der `maximumClockSkew` \-Attribut auf die [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.  Ein Wert festgelegt, auf die Auflistung der Tokenhandler setzt den Wert für den Dienst festgelegt.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Gibt den Satz der URIs, die zulässigen Bezeichner der relying Party sind.  Optional.|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches für Sitzung Tokens und Tokens Replay\-Erkennung verwendet.  Kann auf der Dienstebene oder auf eine Sicherheit Tokenhandler Auflistung angegeben werden.  Optional.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen.  Kann auf der Dienstebene oder auf eine Sicherheit Tokenhandler Auflistung angegeben werden.  Diese Einstellungen werden überschrieben, wenn Sie ein bestimmten Handler mit eigenen Validator konfiguriert ist.  Optional.|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Wird die Aussteller Namen Registrierung, mit der Handler in der Auflistung Tokenhandler konfiguriert.  Optional.|  
|[\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registriert den token Aussteller\-Konfliktlöser, der vom Handler in der Tokenhandler\-Auflistung verwendet wird.  Der token Aussteller\-Resolver wird verwendet, um Signaturtoken auf eingehende Tokens und Nachrichten zu beheben.  Optional.|  
|[\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registriert den token Service\-Konfliktlöser, der vom Handler in der Tokenhandler\-Auflistung verwendet wird.  Der Service\-token\-Resolver wird verwendet, zum Auflösen des Tokens Verschlüsselung auf eingehende Tokens und Nachrichten.  Optional.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Token Replay\-Erkennung aktiviert, und gibt die Ablaufzeit für Token.  Kann auf der Dienstebene oder auf eine Sicherheit Tokenhandler Auflistung angegeben werden.  Optional.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandler, die mit dem Endpunkt registriert sind.|  
  
## Hinweise  
 Dieser Abschnitt enthält die Eigenschaftenwerte für ein <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt.  In diesem Abschnitt konfigurierte Einstellungen überschreiben, die auf den Dienst konfiguriert.  Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben, die angegeben werden, wenn der Security token Handler\-Auflistung ein Handler hinzugefügt wird.  
  
## Beispiel  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```