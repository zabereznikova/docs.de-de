---
title: '&lt;identityConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 7c20f3d00b71eacbf8409c3f848d550445468e5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513099"
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
Gibt die identitätseinstellungen der Servicelevel.  
  
 \<system.identityModel>  
\<identityConfiguration>  
  
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
|Name|Der Name des Konfigurationsabschnitts Identität. Sie können diesen Namen verwenden, um auf um einen bestimmten Konfigurationsabschnitt zu verweisen. Wenn kein `name` -Attribut angegeben ist, im Abschnitt definiert die Standardkonfiguration. Die Standardkonfiguration wird immer für passiven Verbund-Szenarien verwendet werden. Weitere Informationen finden Sie unter den [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.|  
|saveBootstrapContext|Gibt an, ob bootstrap-Token in das Sitzungstoken, das enthalten sein sollen. Der Wert kann auch auf eine Auflistung der Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut für die [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element. Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
|maximumClockSkew|Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt. Steuert die maximal erlaubte uhrabweichung, beim Durchführen von zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine Anmeldung überprüfen. Der Standardwert ist 5 Minuten, "00: 05:00". Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Die maximale uhrabweichung kann auch auf eine Auflistung der Tokenhandler festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut für die [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element. Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet. Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden. Dies ist optional.|  
|[\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden. Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden. Dies ist optional.|  
|[\<claimsAuthenticationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche. Dies ist optional.|  
|[\<claimsAuthorizationManager>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Registriert einen anspruchsautorisierungs-Manager für die eingehenden Ansprüche. Dies ist optional.|  
|[\<claimTypeRequired>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken. Dies ist optional.|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von sicherheitstokenhandlern. NULL oder mehr Auflistungen der Sicherheitstokenhandler können angegeben werden. Dies ist optional.|  
|[\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token. Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden. Dies ist optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Ermöglicht die Konfiguration für Windows Identity Foundation (WIF)-Optionen in Anwendungen zu aktivieren.|  
  
## <a name="remarks"></a>Hinweise  
 Mehrere Identitätsspeicher Konfigurationen definiert werden können, jeweils mit einem eindeutigen Namen. Das Verhalten ist wie folgt aus:  
  
1.  Wenn kein `<identityConfiguration>` -Element angegeben ist. Eine Standardkonfiguration für die Identität wird zur Laufzeit erstellt und mit Standardwerten aufgefüllt wurden.  
  
2.  Wenn ein einzelner `<identityConfiguration>` -Element angegeben ist. Es ist die Standardkonfiguration für die Identität. Es spielt keine Rolle, ob er mit dem Namen oder nicht benannt ist.  
  
3.  Wenn mehrere `<identityConfiguration>` Elemente angegeben werden. Das unbenannte Element gibt die Standardkonfiguration für die Identität an. Es wird empfohlen, bei der Angabe von mehreren `<identityConfiguration>` Elemente, eine davon sollten unbenannt sein.  
  
> [!WARNING]
>  Bei Angabe mehrerer `<identityConfiguration>` Elemente, eine davon sollten unbenannt sein. Das unbenannte Element werden die Standardkonfiguration für die Identität.  
  
 Einige der Einstellungen in der `<identityConfiguration>` Element überschrieben werden kann, von den Einstellungen für einen Sicherheitstoken-Handlerauflistung oder von den Einstellungen für einzelne Sicherheitstokenhandler.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code die identitätskonfiguration bereitzustellen, auf die verweist, die `<federationConfiguration>` -Element konfiguriert die anspruchsautorisierungs-Manager und die Richtlinie, die verwendet wird, um sicherzustellen autorisierungsentscheidungen. Dies gilt, auch in Szenarien, die nicht passiven Webszenarien, z. B. Anwendungen für Windows Communication Foundation (WCF) oder eine Anwendung, die nicht webbasierte ist. Wenn die Anwendung nicht mit einer passiven Webanwendung ist die [ \<"claimsauthorizationmanager" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) -Element (und seine untergeordneten Richtlinienelemente, sofern vorhanden) der identitätskonfiguration verwiesen wird die einzigen Einstellungen, die angewendet werden. Alle anderen Einstellungen werden ignoriert. Weitere Informationen finden Sie unter den [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.  
  
 Die `<identityConfiguration>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> Klasse. Ein Konfigurationsabschnitt für die Identität wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IdentityConfiguration> Klasse.  
  
> [!IMPORTANT]
>  Die folgenden Elemente als untergeordnete Elemente angeben die `<identityConfiguration>` Element ist veraltet, obwohl das Verhalten für die Abwärtskompatibilität weiterhin unterstützt wird. Diese Elemente sollten stattdessen angegeben werden, unter dem [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element.  
>   
>  -   [\<audienceUris>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine identitätskonfiguration, die mit dem Namen "AlternateConfiguration". Die identitätskonfiguration gibt Standardeinstellungen.  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
