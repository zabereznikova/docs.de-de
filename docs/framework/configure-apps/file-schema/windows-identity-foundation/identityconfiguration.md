---
title: "&lt;identityConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# &lt;identityConfiguration&gt;
Gibt die von Service\-Level\-Identitätseinstellungen.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|name|Der Name des Konfigurationsabschnitts Identität.  Sie können diesen Namen verwenden, auf um einen bestimmten Konfigurationsabschnitt zu verweisen.  Wenn keine `name` Attribut angegeben ist, wird der Abschnitt definiert die Standardkonfiguration.  Die Standardkonfiguration wird immer für passive Verbundszenarios verwendet.  Weitere Informationen finden Sie unter dem [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)\-Element.|  
|saveBootstrapContext|Gibt an, ob bootstrap\-Token in den Sitzungstoken aufzunehmen.  Der Wert kann auch auf ein token Handler\-Auflistung festgelegt werden, durch Festlegen der `saveBootstrapContext` \-Attribut auf die [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element.  Ein Wert festgelegt, auf die Auflistung der Tokenhandler setzt den Wert für den Dienst festgelegt.|  
|maximumClockSkew|A <xref:System.TimeSpan> , gibt die maximale erlaubte taktverschiebung.  Steuert die maximale zulässige Zeitabweichung, Ausführung zeitkritische Operationen, z. B. die Ablaufzeit einer Sitzung überprüfen.  Der Standardwert ist 5 Minuten "00: 05".  Weitere Informationen zum Angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  Die maximale Zeitabweichung kann auch auf ein token Handler\-Auflistung festgelegt werden, durch Festlegen der `maximumClockSkew` \-Attribut auf die [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element.  Ein Wert festgelegt, auf die Auflistung der Tokenhandler setzt den Wert für den Dienst festgelegt.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches für Sitzung Tokens und Tokens Replay\-Erkennung verwendet.  Kann auf der Dienstebene oder auf eine Sicherheit Tokenhandler Auflistung angegeben werden.  Optional.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen.  Kann auf der Dienstebene oder auf eine Sicherheit Tokenhandler Auflistung angegeben werden.  Optional.|  
|[\<claimsAuthenticationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registriert einen Ansprüche Authentifizierungs\-Manager für die eingehenden Ansprüche.  Optional.|  
|[\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Registriert einen Ansprüche Autorisierungs\-Manager für die eingehenden Ansprüche.  Optional.|  
|[\<claimTypeRequired\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Gibt den Satz von Ansprüchen für eingehende Sicherheitstoken.  Optional.|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandler.  NULL oder mehr Sammlungen von Sicherheitstokenhandler können angegeben werden.  Optional.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Token Replay\-Erkennung aktiviert, und gibt die Ablaufzeit für Token.  Kann auf der Dienstebene oder auf eine Sicherheit Tokenhandler Auflistung angegeben werden.  Optional.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<system.identityModel\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Stellt die Konfiguration für das Aktivieren von Optionen für die Windows\-Identität\-Foundation \(WIF\) in Anwendungen.|  
  
## Hinweise  
 Mehrere Identitätsspeicher Konfigurationen definiert werden können, jede mit einem eindeutigen Namen.  Das Verhalten ist wie folgt:  
  
1.  Wenn keine `<identityConfiguration>` \-Element angegeben ist.  Eine Standardkonfiguration für die Identität wird zur Laufzeit erstellt und mit Standardwerten aufgefüllt.  
  
2.  Wenn ein einzelnes `<identityConfiguration>` \-Element angegeben ist.  Es ist die Standardkonfiguration für die Identität.  Es spielt keine Rolle, ob sie benannt oder unbenannt ist.  
  
3.  Wenn mehrere `<identityConfiguration>` Elemente angegeben werden.  Unbenannte Element gibt die Standardkonfiguration für die Identität.  Wird empfohlen, bei der Angabe von mehreren `<identityConfiguration>` Elemente, eine davon sollte unbenannt sein.  
  
> [!WARNING]
>  Wenn Sie mehrere `<identityConfiguration>` Elemente, eine davon sollte unbenannt sein.  Unbenannte Element wird die Standardkonfiguration für die Identität sein.  
  
 Einige der Einstellungen in der `<identityConfiguration>` von Einstellungen auf eine Auflistung der Sicherheit Tokenhandler oder durch Einstellungen auf einzelne Sicherheitstokenhandler Element überschrieben werden.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code die Identität\-Konfiguration die verwiesen wird die `<federationConfiguration>` \-Element konfiguriert die Ansprüche Autorisierungs\-Manager und die Richtlinie, die verwendet wird, um Autorisierungsentscheidungen treffen zu können.  Dies gilt, auch in Szenarien, die nicht passive Web\-Szenarien, z. B. Windows Communication Foundation \(WCF\)\-Anwendungen oder eine Anwendung, die nicht Web\-basiert ist.  Wenn die Anwendung nicht über eine passive Webanwendung ist die [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) Element \(und seine untergeordneten Richtlinienelemente, sofern vorhanden\) die referenzierte Identität\-Konfiguration sind die einzigen Einstellungen angewendet.  Alle anderen Einstellungen werden ignoriert.  Weitere Informationen finden Sie unter dem [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)\-Element.  
  
 Die `<identityConfiguration>` Element dargestellt durch die <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> Klasse.  Ein Konfigurationsabschnitt Identität wird dargestellt durch die <xref:System.IdentityModel.Configuration.IdentityConfiguration> Klasse.  
  
> [!IMPORTANT]
>  Angeben der folgenden Elemente als untergeordnete Elemente von der `<identityConfiguration>` Element ist veraltet, obwohl das Verhalten aus Kompatibilitätsgründen weiterhin unterstützt wird.  Diese Elemente sollten stattdessen angegeben werden, unter der [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element.  
>   
>  -   [\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## Beispiel  
 Das folgende Beispiel erstellt eine Identity\-Konfiguration mit dem Namen "AlternateConfiguration".  Die Identity\-Konfiguration gibt Standardeinstellungen.  
  
```  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>   
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>