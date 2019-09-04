---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251813"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Konfigurations Abschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp; **\<System. IdentityModel. Services->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 None  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, die die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> http <xref:System.IdentityModel.Services.SessionAuthenticationModule> -Module (wsfam) und (Sam) konfigurieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
 None  
  
## <a name="remarks"></a>Hinweise  
 Fügen Sie `<system.identityModel.services>` der Konfigurationsdatei Ihrer Anwendung einen Abschnitt hinzu, um die Einstellungen für Sam und wsfam bereitzustellen.  
  
> [!IMPORTANT]
> Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -Klasse <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> oder die-Klasse verwenden, um eine `<identityConfiguration>` Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen<xref:System.Security.Claims.ClaimsAuthorizationManager>, werden der anspruchsautorisierungs-Manager () und die Richtlinie, die für Autorisierungs Entscheidungen verwendet wird, über Element, das implizit oder explizit von einem `<federationConfiguration>` -Element in diesem Abschnitt referenziert wird. Weitere Informationen finden **Sie in den** Hinweisen unter dem [ \<Element federationconfiguration >](federationconfiguration.md) .  
  
 Der `<system.identityModel.services>` -Abschnitt wird durch die <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> -Klasse dargestellt. Die Auflistung der `<federationConfiguration>` untergeordneten Elemente, die im-Abschnitt konfiguriert wurden <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> , wird durch die-Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt, wie `<system.identityModel.services>` Sie einer Konfigurationsdatei einen-Abschnitt hinzufügen. Sie müssen zunächst Abschnitts Deklarationen für den `<system.identityModel.services>` Abschnitt und die `<system.identityModel>` Abschnitte hinzufügen. (Wenn Sie einen `<system.identityModel.services>` Abschnitt hinzufügen, sollten Sie auch eine Deklaration für den `<system.identityModel>` Abschnitt hinzufügen, um `<identityConfiguration>` sicherzustellen, dass ggf. ein Standardabschnitt von der Laufzeit erstellt werden kann.) Nachdem die Abschnitts Deklarationen hinzugefügt wurden, können Sie die Einstellungen für die Verbund Authentifizierung `<system.identityModel.services>` unter dem-Element konfigurieren.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
