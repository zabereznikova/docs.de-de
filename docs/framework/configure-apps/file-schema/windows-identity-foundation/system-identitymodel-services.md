---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: c7261d20ae2379ad33679cadecdef484f2afdecf
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778076"
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;system.identityModel.services&gt;
Der Konfigurationsabschnitt für die Authentifizierung mit dem WS-Verbund-Protokoll.  
  
 \<system.identityModel.services >  
  
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
 Keiner  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Enthält Einstellungen, konfigurieren die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) und die <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)-HTTP-Module.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
 Keiner  
  
## <a name="remarks"></a>Hinweise  
 Hinzufügen einer `<system.identityModel.services>` Abschnitt aus, um Sie in der Konfigurationsdatei der Anwendung der Einstellungen für das SAM und das WSFAM bereitstellen.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code den anspruchsautorisierungs-Manager bereitzustellen (<xref:System.Security.Claims.ClaimsAuthorizationManager>) und die Richtlinie, die verwendet wird, um autorisierungsentscheidungen zu treffen sind so konfiguriert, über eine `<identityConfiguration>` Element, das implizit oder explizit, von verwiesen wird einem `<federationConfiguration>` Element in diesem Abschnitt. Weitere Informationen finden Sie unter den **"Hinweise"** unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.  
  
 Die `<system.identityModel.services>` Abschnitt wird dargestellt, durch die <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> Klasse. Die Auflistung untergeordneter `<federationConfiguration>` Elemente, die im Abschnitt konfiguriert wurden, wird durch dargestellt die <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt, wie Sie das Hinzufügen einer `<system.identityModel.services>` Abschnitt einer Konfigurationsdatei. Sie müssen zuerst Abschnitt Deklarationen für beide Hinzufügen der `<system.identityModel.services>` Abschnitt und die `<system.identityModel>` Abschnitte. (Beim Hinzufügen einer `<system.identityModel.services>` Abschnitt sollten Sie auch eine Deklaration für Hinzufügen der `<system.identityModel>` Abschnitt aus, um sicherzustellen, dass auf den Standardwert `<identityConfiguration>` Abschnitt kann von der Runtime erstellt werden, falls erforderlich.) Nachdem die Deklarationen Abschnitt hinzugefügt wurden, können Sie konfigurieren, dass Verbundauthentifizierung Einstellungen unter dem `<system.identityModel.services>` Element.  
  
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
