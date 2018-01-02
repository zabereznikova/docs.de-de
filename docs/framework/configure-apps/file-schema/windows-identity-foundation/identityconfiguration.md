---
title: '&lt;identityConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48f9eef329f5d2e0e751fd2a03b0d3af9ddc355c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
Gibt an, Service Level identitätseinstellungen.  
  
 \<system.identityModel >  
\<IdentityConfiguration >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Name|Der Name des Konfigurationsabschnitts für die Identität. Sie können diesen Namen verwenden, auf einen bestimmten Konfigurationsabschnitt verweisen. Wenn kein `name` -Attribut angegeben ist, wird im Abschnitt definiert die Standardkonfiguration. Die Standardkonfiguration wird immer für den passiven Verbund-Szenarien verwendet werden. Weitere Informationen finden Sie unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.|  
|saveBootstrapContext|Gibt an, ob bootstrap-Token in das Sitzungstoken aufgenommen werden sollen. Der Wert kann auch auf eine Auflistung Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut auf die [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element. Ein Wert festgelegt, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
|maximumClockSkew|Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt. Die maximal erlaubte taktverschiebung steuert die Ausführung zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine anmeldesitzung überprüfen. Der Standardwert beträgt 5 Minuten "00: 05:00". Weitere Informationen zum Angeben der <xref:System.TimeSpan> -Werte finden Sie in [Timespan Werte](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Die maximale taktverschiebung möglicherweise auch für eine Auflistung Tokenhandler festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut auf die [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element. Ein Wert festgelegt, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Speichert >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches für die Sitzungstoken und token-Replay-Erkennung verwendet. Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden. Dies ist optional.|  
|[\<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen. Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden. Dies ist optional.|  
|[\<Komponente "ClaimsAuthenticationManager" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registriert einen Ansprüche Authentifizierungs-Manager für die eingehenden Ansprüche. Dies ist optional.|  
|[\<ClaimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Registriert einen anspruchsautorisierungs-Manager für die eingehenden Ansprüche. Dies ist optional.|  
|[\<ClaimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken. Dies ist optional.|  
|[\<SecurityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von sicherheitstokenhandlern. 0 (null) oder mehrere Sammlungen von sicherheitstokenhandlern können angegeben werden. Dies ist optional.|  
|[\<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Tokenwiedergabeerkennung aktiviert, und gibt die Ablaufzeit für Token. Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden. Dies ist optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Ermöglicht die Konfiguration für Windows Identity Foundation (WIF)-Optionen in Anwendungen zu aktivieren.|  
  
## <a name="remarks"></a>Hinweise  
 Mehrere Identity-Konfigurationen definiert werden können, jeweils mit einem eindeutigen Namen. Das Verhalten ist wie folgt aus:  
  
1.  Wenn kein `<identityConfiguration>` -Element angegeben ist. Eine Identity-Standardkonfiguration ist zur Laufzeit erstellt und mit Standardwerten.  
  
2.  Wenn ein einzelner `<identityConfiguration>` -Element angegeben ist. Es ist die Standardkonfiguration für die Identität. Es ist unerheblich, ob sie mit dem Namen oder nicht benannt ist.  
  
3.  Wenn mehrere `<identityConfiguration>` Elemente angegeben werden. Das unbenannte Element gibt die Standardkonfiguration für die Identität. Es wird empfohlen, dass bei Angabe mehrerer `<identityConfiguration>` Elemente, eine davon sollten unbenannte sein.  
  
> [!WARNING]
>  Bei Angabe mehrerer `<identityConfiguration>` Elemente, eine davon sollten unbenannte sein. Das unbenannte Element wird die standardidentitätskonfiguration sein.  
  
 Einige der Einstellungen angegeben, der `<identityConfiguration>` Element überschrieben werden kann, indem Sie Einstellungen auf eine Auflistung der Security-Tokenhandler oder Einstellungen auf einzelne Sicherheitstokenhandler.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse anspruchsbasierte Zugriffssteuerung in Ihrem Code ab, die identitätskonfiguration bereitstellen, die vom verwiesen wird die `<federationConfiguration>` Element konfiguriert werden, die Ansprüche Autorisierungs-Manager und die Richtlinie, die verwendet wird, um Stellen autorisierungsentscheidungen. Dies ist "true" auch in Szenarien, die nicht passiven Web-Szenarien, z. B. Anwendungen für Windows Communication Foundation (WCF) oder eine Anwendung, die nicht webbasierte ist. Wenn die Anwendung nicht auf einem passiven Webanwendung ist der [ \<ClaimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) -Element (und der untergeordneten Richtlinienelemente, falls vorhanden) sind die einzigen Einstellungen die identitätskonfiguration verwiesen wird. Alle anderen Einstellungen werden ignoriert. Weitere Informationen finden Sie unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.  
  
 Die `<identityConfiguration>` Element dargestellt ist, durch die <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> Klasse. Ein Identität Konfigurationsabschnitt wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IdentityConfiguration> Klasse.  
  
> [!IMPORTANT]
>  Festlegen der folgenden Elemente als untergeordnete Elemente von der `<identityConfiguration>` Element ist veraltet, obwohl das Verhalten für die Abwärtskompatibilität weiterhin unterstützt wird. Diese Elemente sollten stattdessen angegeben werden, unter der [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element.  
>   
>  -   [\<AudienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<IssuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<IssuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<ServiceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine identitätskonfiguration mit dem Namen "AlternateConfiguration". Die identitätskonfiguration gibt die Standardeinstellungen an.  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
