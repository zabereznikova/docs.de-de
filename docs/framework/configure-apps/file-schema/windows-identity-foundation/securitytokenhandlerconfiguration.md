---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47206087"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a>&lt;securityTokenHandlerConfiguration&gt;
Ermöglicht die Konfiguration für die Sammlung von tokenhandlern.  
  
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
|saveBootstrapContext|Gibt an, ob bootstrap-Token in das Sitzungstoken, das enthalten sein sollen. Der Wert kann auch auf eine Auflistung der Tokenhandler festgelegt werden, durch Festlegen der `saveBootstrapContext` -Attribut für die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element. Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
|maximumClockSkew|Ein <xref:System.TimeSpan> , die die maximal erlaubte taktverschiebung angibt. Steuert die maximal erlaubte uhrabweichung, beim Durchführen von zeitkritischen Vorgängen, z. B. die Ablaufzeit für eine Anmeldung überprüfen. Der Standardwert ist 5 Minuten, "00: 05:00". Weitere Informationen zur Vorgehensweise beim angeben <xref:System.TimeSpan> Werte finden Sie unter [Timespan-Werten](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Die maximale uhrabweichung kann auch auf Dienstebene festgelegt werden, durch Festlegen der `maximumClockSkew` -Attribut für die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element. Ein Wert festgelegt wird, auf die Auflistung der Tokenhandler überschreibt den Wert für den Dienst festgelegt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<AudienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|Gibt den Satz von URIs, die akzeptable Bezeichner der vertrauenden sind. Dies ist optional.|  
|[\<Speichert >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet. Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden. Dies ist optional.|  
|[\<CertificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Steuert die Einstellungen, die token-Handler zum Überprüfen von Zertifikaten verwenden. Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden. Diese Einstellungen werden überschrieben, wenn ein bestimmten Handler mit der eine eigene Überprüfungsfunktion konfiguriert ist. Dies ist optional.|  
|[\<"issuerNameRegistry" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Konfiguriert die Ausstellernamen-Registrierung, die von Handlern in die Auflistung der Tokenhandler verwendet wird. Dies ist optional.|  
|[\<IssuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|Registriert die Aussteller-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird. Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten. Dies ist optional.|  
|[\<ServiceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|Registriert die Service-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird. Dienst-tokenresolvers wird verwendet, um das Verschlüsselungstoken der eingehenden Token und Nachrichten zu beheben. Dies ist optional.|  
|[\<TokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Ermöglicht die Erkennung einer tokenmehrfachverwendung, und gibt an, die Ablaufzeit für Token. Kann auf der Dienstebene oder auf einen Sicherheitstoken-Handlerauflistung angegeben werden. Dies ist optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Abschnitt enthält die Eigenschaftswerte für eine <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt. In diesem Abschnitt konfigurierten Einstellungen außer Kraft setzen, die auf den Dienst konfiguriert. Einige dieser Einstellungen können wiederum von Einstellungen überschrieben werden, die angegeben werden, wenn das Sicherheitstoken-Handlerauflistung ein Handler hinzugefügt wird.  
  
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
