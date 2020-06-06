---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 0fa8c574fd5663606cf081f1000a24884306edfe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251992"
---
# \<identityConfiguration>

Gibt Identitäts Einstellungen auf Dienst Ebene an.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

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

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|name|Der Name des Identitäts Konfigurations Abschnitts. Sie können diesen Namen verwenden, um auf einen bestimmten Konfigurations Abschnitt zu verweisen. Wenn kein `name` Attribut angegeben wird, definiert der Abschnitt die Standardkonfiguration. Die Standardkonfiguration wird immer für passive Verbund Szenarien verwendet. Weitere Informationen finden Sie unter dem- [\<federationConfiguration>](federationconfiguration.md) Element.|
|savebootstrapcontext|Gibt an, ob Bootstrap-Token in das Sitzungs Token eingeschlossen werden sollen. Der Wert kann auch für eine tokenhandlerauflistung festgelegt werden, indem das- `saveBootstrapContext` Attribut für das-Element festgelegt wird [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) . Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.|
|maximumclockschiefe|Eine <xref:System.TimeSpan> , die die maximal zulässige Takt Neigung angibt. Steuert die maximal zulässige Takt Neigung, wenn Zeit empfindliche Vorgänge durchgeführt werden, z. b. das Überprüfen der Ablaufzeit einer Anmelde Sitzung. Der Standardwert ist 5 Minuten, "00:05:00". Weitere Informationen zum Angeben von <xref:System.TimeSpan> Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)). Die maximale Takt Abweichung kann auch für eine tokenhandlerauflistung festgelegt werden, indem das- `maximumClockSkew` Attribut für das-Element festgelegt wird [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) . Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<caches>](caches.md)|Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. (Optional)|
|[\<certificateValidation>](certificatevalidation.md)|Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. (Optional)|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche. (Optional)|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|Registriert einen Anspruchs Autorisierungs-Manager für die eingehenden Ansprüche. (Optional)|
|[\<claimTypeRequired>](claimtyperequired.md)|Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an. (Optional)|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandlern an. Es können keine oder mehrere Auflistungen von Sicherheitstokenhandlern angegeben werden. (Optional)|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. (Optional)|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|Stellt die Konfiguration zum Aktivieren von WIF-Optionen (Windows Identity Foundation) in-Anwendungen bereit.|

## <a name="remarks"></a>Bemerkungen

Es können mehrere Identitäts Konfigurationen definiert werden, von denen jede einen eindeutigen Namen hat. Das Verhalten sieht wie folgt aus:

1. , Wenn kein- `<identityConfiguration>` Element angegeben ist. Eine standardmäßige Identitäts Konfiguration wird zur Laufzeit erstellt und mit Standardwerten aufgefüllt.

2. , Wenn ein einzelnes- `<identityConfiguration>` Element angegeben wird. Dabei handelt es sich um die Standardkonfiguration für die Identität. Es spielt keine Rolle, ob Sie benannt oder unbenannt ist.

3. , Wenn mehrere `<identityConfiguration>` Elemente angegeben werden. Das unbenannte-Element gibt die Standardkonfiguration für die Identität an. Es wird empfohlen, dass Sie bei der Angabe mehrerer `<identityConfiguration>` Elemente unbenannt sein sollten.

> [!WARNING]
> Wenn Sie mehrere `<identityConfiguration>` Elemente angeben, sollte eines von Ihnen unbenannt sein. Das unbenannte Element ist die Standardkonfiguration für die Identität.

 Einige der im-Element angegebenen Einstellungen `<identityConfiguration>` können durch Einstellungen in einer Auflistung von Sicherheitstokenhandlern oder durch Einstellungen in einzelnen Sicherheitstokenhandlern überschrieben werden.

> [!IMPORTANT]
> Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -oder die-Klasse verwenden, <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> um eine Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen, konfiguriert die Identitäts Konfiguration, auf die das-Element verweist, `<federationConfiguration>` den anspruchsautorisierungs-Manager und die Richtlinie, die für Autorisierungs Entscheidungen verwendet werden. Dies gilt auch für Szenarien, bei denen es sich nicht um passive Webszenarien handelt, z. b. Windows Communication Foundation (WCF)-Anwendungen oder eine nicht webbasierte Anwendung. Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) werden das-Element (und seine untergeordneten Richtlinien Elemente, falls vorhanden) der Identitäts Konfiguration, auf die verwiesen wird, als einzige Einstellung angewendet. Alle anderen Einstellungen werden ignoriert. Weitere Informationen finden Sie unter dem- [\<federationConfiguration>](federationconfiguration.md) Element.

Das- `<identityConfiguration>` Element wird durch die- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> Klasse dargestellt. Ein Identitäts Konfigurations Abschnitt wird durch die- <xref:System.IdentityModel.Configuration.IdentityConfiguration> Klasse dargestellt.

> [!IMPORTANT]
> Die Angabe der folgenden Elemente als untergeordnete Elemente des-Elements wurde als `<identityConfiguration>` veraltet markiert, obwohl das Verhalten weiterhin aus Gründen der Abwärtskompatibilität unterstützt wird. Diese Elemente sollten stattdessen unter dem-Element angegeben werden [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) .
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Identitäts Konfiguration mit dem Namen "", "Alternativen", erstellt. Die Identitäts Konfiguration gibt die Standardeinstellungen an.

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
