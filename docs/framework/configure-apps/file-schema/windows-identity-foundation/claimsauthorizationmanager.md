---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ddbe8a862940272e4192a3f4c0abdc1f9e8b5d48
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252082"
---
# \<claimsAuthorizationManager>
Registriert einen Anspruchs Autorisierungs-Manager für die eingehenden Ansprüche.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|type|Ein benutzerdefinierter Typ, der von der-Klasse abgeleitet wird <xref:System.Security.Claims.ClaimsAuthorizationManager> . Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Wenn kein-Attribut vorhanden ist `type` , oder wenn das- `type` Attribut auf die- <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse verweist, nimmt das- `<claimsAuthorizationManager>` Element keine untergeordneten Elemente an. von abgeleitete Klassen können jedoch untergeordnete <xref:System.Security.Claims.ClaimsAuthorizationManager> Konfigurationselemente definieren.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das Standardverhalten, das durch die-Klasse bereitgestellt wird, <xref:System.Security.Claims.ClaimsAuthorizationManager> autorisiert immer eingehende Ansprüche. Wenn kein- `type` Attribut angegeben wird oder wenn das- `type` Attribut die- <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse angibt, nimmt das- `<claimsAuthorizationManager>` Element keine untergeordneten Elemente an. Sie können das `type` Attribut angeben, um einen von der-Klasse abgeleiteten Typ <xref:System.Security.Claims.ClaimsAuthorizationManager> zu registrieren, um benutzerdefiniertes Verhalten zu implementieren Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente des-Elements unterstützen `<claimsAuthorizationManager>` , indem Sie die- <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> Methode zum Verarbeiten dieser Elemente überschreiben. Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.  
  
> [!IMPORTANT]
> Wenn Sie die <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> -oder die-Klasse verwenden, <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> um eine Anspruchs basierte Zugriffs Steuerung in Ihrem Code bereitzustellen, konfiguriert die Identitäts Konfiguration, auf die das-Element verweist, `<federationConfiguration>` den anspruchsautorisierungs-Manager und die Richtlinie, die für Autorisierungs Entscheidungen verwendet werden. Dies gilt auch für Szenarien, bei denen es sich nicht um passive Webszenarien handelt, z. b. Windows Communication Foundation (WCF)-Anwendungen oder eine nicht webbasierte Anwendung. Wenn es sich bei der Anwendung nicht um eine passive Webanwendung handelt, `<claimsAuthorizationManager>` werden das-Element (und seine untergeordneten Richtlinien Elemente, falls vorhanden) der Identitäts Konfiguration, auf die verwiesen wird, als einzige Einstellung angewendet. Alle anderen Einstellungen werden ignoriert. Weitere Informationen finden Sie unter dem- [\<federationConfiguration>](federationconfiguration.md) Element.  
  
 Mit diesem Element wird die-Eigenschaft festgelegt <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> .  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt die Konfiguration für einen anspruchsautorisierungs-Manager, der eine Richtlinie implementiert, die aus Ressourcen Aktions Paaren besteht, von denen jede boolesche Kombinationen der Ansprüche angibt, die ein Anforderer besitzen muss, um die Aktion für die Ressource auszuführen. Der Code, der den Anspruchs Autorisierungs-Manager implementiert, der diese Richtlinie verwenden kann, finden Sie im `ClaimsBasedAuthorization` Beispiel.  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
