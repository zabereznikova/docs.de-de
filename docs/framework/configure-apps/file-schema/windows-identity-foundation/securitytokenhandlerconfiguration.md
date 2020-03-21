---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152566"
---
# <a name="securitytokenhandlerconfiguration"></a>\<securityTokenHandlerConfiguration>
Stellt die Konfiguration für die Auflistung von Tokenhandlern bereit.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|SaveBootstrapContext|Gibt an, ob Bootstrap-Token in das Sitzungstoken eingeschlossen werden sollen. Der Wert kann auch für eine Tokenhandlerauflistung festgelegt werden, indem das `saveBootstrapContext` Attribut für das [ \<identityConfiguration>-Element](identityconfiguration.md) festgelegt wird. Ein wertfürst, der für die Tokenhandlerauflistung festgelegt ist, überschreibt den für den Dienst festgelegten Wert.|  
|maximumClockSkew|A, <xref:System.TimeSpan> das die maximal zulässige Taktschiefe angibt. Steuert die maximal zulässige Taktneigung beim Ausführen zeitabhängiger Vorgänge, z. B. das Überprüfen der Ablaufzeit einer Anmeldesitzung. Der Standardwert ist 5 Minuten, "00:05:00". Weitere Informationen zum Angeben <xref:System.TimeSpan> von Werten finden Sie unter [Zeitspannenwerte](../windows-workflow-foundation/index.md). Die maximale Taktneigung kann auch auf Serviceebene `maximumClockSkew` festgelegt werden, indem das Attribut für das [ \<identityConfiguration>-Element](identityconfiguration.md) festgelegt wird. Ein wertfürst, der für die Tokenhandlerauflistung festgelegt ist, überschreibt den für den Dienst festgelegten Wert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<PublikumUris>](audienceuris.md)|Gibt den Satz von URIs an, die akzeptable Bezeichner dieser vertrauenden Partei sind. Optional.|  
|[\<Caches>](caches.md)|Registriert die Caches, die für Sitzungstoken und Token-Wiedergabeerkennung verwendet werden. Kann auf Serviceebene oder in einer Sicherheitstokenhandlerauflistung angegeben werden. Optional.|  
|[\<certificateValidation>](certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler zum Überprüfen von Zertifikaten verwenden. Kann auf Serviceebene oder in einer Sicherheitstokenhandlerauflistung angegeben werden. Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validator konfiguriert ist. Optional.|  
|[\<IssuerNameRegistry>](issuernameregistry.md)|Konfiguriert die Ausstellernamenregistrierung, die von Handlern in der Tokenhandlerauflistung verwendet wird. Optional.|  
|[\<IssuerTokenResolver>](issuertokenresolver.md)|Registriert den Ausstellertokenlöser, der von Handlern in der Tokenhandlerauflistung verwendet wird. Der Ausstellertokenlöser wird verwendet, um das Signaturtoken für eingehende Token und Nachrichten zu beheben. Optional.|  
|[\<dienstTokenResolver>](servicetokenresolver.md)|Registriert den Diensttoken-Resolver, der von Handlern in der Tokenhandlerauflistung verwendet wird. Der Diensttokenlöser wird verwendet, um das Verschlüsselungstoken für eingehende Token und Nachrichten aufzulösen. Optional.|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Aktiviert die Token-Wiedergabeerkennung und gibt die Ablaufzeit für Token an. Kann auf Serviceebene oder in einer Sicherheitstokenhandlerauflistung angegeben werden. Optional.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieser Abschnitt stellt Eigenschaftswerte für ein <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> Objekt bereit. Die in diesem Abschnitt konfigurierten Einstellungen überschreiben die für den Dienst konfigurierten Einstellungen. Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben werden, die angegeben werden, wenn ein Handler zur Sicherheitstokenhandlerauflistung hinzugefügt wird.  
  
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
