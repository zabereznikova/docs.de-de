---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 9f5e0c5ded3d750a1102492c7a506e6d5643b2d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942751"
---
# <a name="identityconfiguration"></a>\<identityConfiguration>

Gibt Identitäts Einstellungen auf Dienst Ebene an.

 \<system.identityModel>\
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
|Name|Der Name des Identitäts Konfigurations Abschnitts. Sie können diesen Namen verwenden, um auf einen bestimmten Konfigurations Abschnitt zu verweisen. Wenn kein `name` Attribut angegeben wird, definiert der Abschnitt die Standardkonfiguration. Die Standardkonfiguration wird immer für passive Verbund Szenarien verwendet. Weitere Informationen finden Sie unter dem [ \<Element federationconfiguration >](federationconfiguration.md) .|
|saveBootstrapContext|Gibt an, ob Bootstrap-Token in das Sitzungs Token eingeschlossen werden sollen. Der Wert kann auch für eine tokenhandlerauflistung festgelegt werden `saveBootstrapContext` , indem das-Attribut für das [ \<securitytokenhandlerconfiguration->](securitytokenhandlerconfiguration.md) Element festgelegt wird. Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.|
|maximumclockschiefe|Eine <xref:System.TimeSpan> , die die maximal zulässige Takt Neigung angibt. Steuert die maximal zulässige Takt Neigung, wenn Zeit empfindliche Vorgänge durchgeführt werden, z. b. das Überprüfen der Ablaufzeit einer Anmelde Sitzung. Der Standardwert ist 5 Minuten, "00:05:00". Weitere Informationen zum angeben <xref:System.TimeSpan> von Werten finden Sie unter [TimeSpan Values (TimeSpan-Werte](../windows-workflow-foundation/index.md)). Die maximale Takt Abweichung kann auch für eine tokenhandlerauflistung festgelegt werden, `maximumClockSkew` indem das-Attribut für das [ \<securitytokenhandlerconfiguration->](securitytokenhandlerconfiguration.md) Element festgelegt wird. Ein für die tokenhandlerauflistung fest gelegder Wert überschreibt den für den Dienst festgelegten Wert.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<caches>](caches.md)|Registriert die Caches, die für Sitzungs Token und tokenwiedergabe-Erkennung verwendet werden. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. Optional.|
|[\<certificateValidation>](certificatevalidation.md)|Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. Optional.|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche. Optional.|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|Registriert einen Anspruchs Autorisierungs-Manager für die eingehenden Ansprüche. Optional.|
|[\<claimTypeRequired>](claimtyperequired.md)|Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an. Optional.|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandlern an. Es können keine oder mehrere Auflistungen von Sicherheitstokenhandlern angegeben werden. Optional.|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Aktiviert die Erkennung von tokenwiedergabe und gibt die Ablaufzeit für Token an. Kann auf Dienst Ebene oder in einer Auflistung von Sicherheitstokenhandlern angegeben werden. Optional.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|Stellt die Konfiguration zum Aktivieren von WIF-Optionen (Windows Identity Foundation) in-Anwendungen bereit.|

## <a name="remarks"></a>Hinweise

Es können mehrere Identitäts Konfigurationen definiert werden, von denen jede einen eindeutigen Namen hat. Das Verhalten sieht wie folgt aus:

1. , Wenn `<identityConfiguration>` kein-Element angegeben ist. Eine standardmäßige Identitäts Konfiguration wird zur Laufzeit erstellt und mit Standardwerten aufgefüllt.

2. , Wenn ein `<identityConfiguration>` einzelnes-Element angegeben wird. Dabei handelt es sich um die Standardkonfiguration für die Identität. Es spielt keine Rolle, ob Sie benannt oder unbenannt ist.

3. , Wenn `<identityConfiguration>` mehrere Elemente angegeben werden. Das unbenannte-Element gibt die Standardkonfiguration für die Identität an. Es wird empfohlen, dass Sie bei der `<identityConfiguration>` Angabe mehrerer Elemente unbenannt sein sollten.

> [!WARNING]
> Wenn Sie mehrere `<identityConfiguration>` Elemente angeben, sollte eines von Ihnen unbenannt sein. Das unbenannte Element ist die Standardkonfiguration für die Identität.

 Einige der im `<identityConfiguration>` -Element angegebenen Einstellungen können durch Einstellungen in einer Auflistung von Sicherheitstokenhandlern oder durch Einstellungen in einzelnen Sicherheitstokenhandlern überschrieben werden.

> [!IMPORTANT]
> Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> die-Klasse verwenden, um eine Anspruchs basierte Zugriffs Steuerung im Code bereitzustellen, konfiguriert die Identitäts Konfiguration `<federationConfiguration>` , auf die das-Element verweist, den anspruchsautorisierungs-Manager und die Richtlinie, die verwendet wird, um Autorisierungs Entscheidungen. Dies gilt auch für Szenarien, bei denen es sich nicht um passive Webszenarien handelt, z. b. Windows Communication Foundation (WCF)-Anwendungen oder eine nicht webbasierte Anwendung. Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, werden das [ \<> Element ClaimsAuthorizationManager](claimsauthorizationmanager.md) (und ggf. die untergeordneten Richtlinien Elemente) der referenzierten Identitäts Konfiguration die einzigen Einstellungen angewendet. Alle anderen Einstellungen werden ignoriert. Weitere Informationen finden Sie unter dem [ \<Element federationconfiguration >](federationconfiguration.md) .

Das `<identityConfiguration>` -Element wird durch die <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> -Klasse dargestellt. Ein Identitäts Konfigurations Abschnitt wird durch die <xref:System.IdentityModel.Configuration.IdentityConfiguration> -Klasse dargestellt.

> [!IMPORTANT]
> Die Angabe der folgenden Elemente als untergeordnete Elemente `<identityConfiguration>` des-Elements wurde als veraltet markiert, obwohl das Verhalten weiterhin aus Gründen der Abwärtskompatibilität unterstützt wird. Diese Elemente sollten stattdessen unter dem [ \<Element securitytokenhandlerconfiguration >](securitytokenhandlerconfiguration.md) angegeben werden.
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

## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
