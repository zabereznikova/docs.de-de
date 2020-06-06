---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152566"
---
# \<securityTokenHandlerConfiguration>
Stellt die Konfiguration für die Auflistung von tokenhandlern bereit.  
  
[**\<configuration>**](../configuration-element.md)\
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
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|savebootstrapcontext|Gibt an, ob Bootstrap-Token in das Sitzungs Token eingeschlossen werden sollen. Der Wert kann auch für eine tokenhandlerauflistung festgelegt werden, indem das- `saveBootstrapContext` Attribut für das-Element festgelegt wird [\<identityConfiguration>](identityconfiguration.md) . Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.|  
|maximumclockschiefe|Eine <xref:System.TimeSpan> , die die maximal zulässige Takt Neigung angibt. Steuert die maximal zulässige Takt Neigung, wenn Zeit empfindliche Vorgänge durchgeführt werden, z. b. das Überprüfen der Ablaufzeit einer Anmelde Sitzung. Der Standardwert ist 5 Minuten, "00:05:00". Weitere Informationen zum Angeben von <xref:System.TimeSpan> Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)). Die maximale Takt Abweichung kann auch auf Dienst Ebene festgelegt werden, indem das- `maximumClockSkew` Attribut für das-Element festgelegt wird [\<identityConfiguration>](identityconfiguration.md) . Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<audienceUris>](audienceuris.md)|Gibt den Satz von URIs an, die akzeptable Bezeichner dieser vertrauenden Seite sind. (Optional)|  
|[\<caches>](caches.md)|Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. (Optional)|  
|[\<certificateValidation>](certificatevalidation.md)|Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist. (Optional)|  
|[\<issuerNameRegistry>](issuernameregistry.md)|Konfiguriert die Aussteller Namen Registrierung, die von Handlern in der Auflistung der Tokenhandler verwendet wird. (Optional)|  
|[\<issuerTokenResolver>](issuertokenresolver.md)|Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird. Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen. (Optional)|  
|[\<serviceTokenResolver>](servicetokenresolver.md)|Registriert den diensttokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird. Der diensttokenresolver wird verwendet, um das Verschlüsselungs Token für eingehende Token und Nachrichten aufzulösen. (Optional)|  
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. (Optional)|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Bemerkungen  
 In diesem Abschnitt werden Eigenschaftswerte für ein-Objekt bereitstellt <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> . Die in diesem Abschnitt konfigurierten Einstellungen überschreiben die für den Dienst konfigurierten Einstellungen. Einige dieser Einstellungen können wiederum durch Einstellungen überschrieben werden, die beim Hinzufügen eines Handlers zur Auflistung der Sicherheitstokenhandler angegeben werden.  
  
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
