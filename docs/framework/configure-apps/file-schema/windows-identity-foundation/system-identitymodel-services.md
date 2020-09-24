---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e909756a58d5008d917fca84af0e478fc4878d2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156809"
---
# \<system.identityModel.services>

Konfigurations Abschnitt für die Authentifizierung mit dem WS-Federation-Protokoll.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
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

 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Enthält die Einstellungen, die die <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> HTTP-Module (wsfam) und <xref:System.IdentityModel.Services.SessionAuthenticationModule> (Sam) konfigurieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  

 Keine  
  
## <a name="remarks"></a>Bemerkungen  

 Fügen Sie der `<system.identityModel.services>` Konfigurationsdatei Ihrer Anwendung einen Abschnitt hinzu, um die Einstellungen für Sam und wsfam bereitzustellen.  
  
> [!IMPORTANT]
> Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -Klasse oder die-Klasse verwenden, <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> um eine Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen, werden der anspruchsautorisierungs-Manager ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) und die Richtlinie, die zum Treffen von Autorisierungs Entscheidungen verwendet werden, über ein Element konfiguriert, `<identityConfiguration>` das implizit oder explizit von einem- `<federationConfiguration>` Element in diesem Abschnitt Weitere Informationen finden **Sie in den Hinweisen unter dem-** [\<federationConfiguration>](federationconfiguration.md) Element.  
  
 Der- `<system.identityModel.services>` Abschnitt wird durch die- <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> Klasse dargestellt. Die Auflistung der untergeordneten Elemente, die `<federationConfiguration>` im-Abschnitt konfiguriert wurden, wird durch die- <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> Klasse dargestellt.  
  
## <a name="example"></a>Beispiel  

 Der folgende XML-Code zeigt, wie Sie einer Konfigurationsdatei einen-Abschnitt hinzufügen `<system.identityModel.services>` . Sie müssen zunächst Abschnitts Deklarationen für den `<system.identityModel.services>` Abschnitt und die Abschnitte hinzufügen `<system.identityModel>` . (Wenn Sie einen Abschnitt hinzufügen `<system.identityModel.services>` , sollten Sie auch eine Deklaration für den Abschnitt hinzufügen, `<system.identityModel>` um sicherzustellen, dass `<identityConfiguration>` ggf. ein Standardabschnitt von der Laufzeit erstellt werden kann.) Nachdem die Abschnitts Deklarationen hinzugefügt wurden, können Sie die Einstellungen für die Verbund Authentifizierung unter dem- `<system.identityModel.services>` Element konfigurieren.  
  
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
