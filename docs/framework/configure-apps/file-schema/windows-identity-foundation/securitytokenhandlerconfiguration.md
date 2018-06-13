---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 168bdc4fbf640b201ebc61462d04727c23f838f2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758424"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
Die Konfiguration für die Auflistung der Tokenhandler bereitstellt.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<SecurityTokenHandlers >  
\<SecurityTokenHandlerConfiguration >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|saveBootstrapContext|Gibt an, ob bootstrap-Token in das Sitzungstoken aufgenommen werden sollen. Der Wert kann auch auf eine Auflistung Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut auf die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element. Ein Wert festgelegt, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
|maximumClockSkew|Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt. Die maximal erlaubte taktverschiebung steuert die Ausführung zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine anmeldesitzung überprüfen. Der Standardwert beträgt 5 Minuten "00: 05:00". Weitere Informationen zum Angeben der <xref:System.TimeSpan> -Werte finden Sie in [Timespan Werte](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Die maximale taktverschiebung kann auch auf Dienstebene festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut auf die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element. Ein Wert festgelegt, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<AudienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden sind. Dies ist optional.|  
|[\<Speichert >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches für die Sitzungstoken und token-Replay-Erkennung verwendet. Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden. Dies ist optional.|  
|[\<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler verwenden, um Zertifikate zu überprüfen. Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden. Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist. Dies ist optional.|  
|[\<IssuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Konfiguriert die ausstellernamenregistration, die vom Handler in der Auflistung Tokenhandler verwendet wird. Dies ist optional.|  
|[\<IssuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registriert die Aussteller-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird. Die Aussteller-tokenresolver wird zum Auflösen von der signiertokens für eingehende Token und Nachrichten verwendet. Dies ist optional.|  
|[\<ServiceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registriert die Dienst-Resolver, die vom Handler in der Auflistung Tokenhandler verwendet wird. Die Dienst-tokenresolver dient zum Auflösen des Tokens Verschlüsselung auf eingehende Token und Nachrichten. Dies ist optional.|  
|[\<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Tokenwiedergabeerkennung aktiviert, und gibt die Ablaufzeit für Token. Kann auf der Dienstebene oder auf eine Auflistung der Sicherheit Tokenhandler angegeben werden. Dies ist optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Abschnitt enthält die Eigenschaftenwerte für eine <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt. In diesem Abschnitt konfigurierten Einstellungen außer Kraft für den Dienst konfiguriert. Einige dieser Einstellungen können wiederum von Einstellungen überschrieben werden, die angegeben werden, wenn die Sicherheit Tokenhandler-Auflistung ein Ereignishandler hinzugefügt wird.  
  
## <a name="example"></a>Beispiel  
  
```xml  
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
