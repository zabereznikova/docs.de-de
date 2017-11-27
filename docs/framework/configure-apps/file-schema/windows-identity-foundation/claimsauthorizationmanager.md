---
title: '&lt;claimsAuthorizationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4b4d86204d5f7225f167be125ce017488c851e98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
Registriert einen anspruchsautorisierungs-Manager für die eingehenden Ansprüche.  
  
 \<system.identityModel >  
\<IdentityConfiguration >  
\<ClaimsAuthorizationManager >  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Ein benutzerdefinierter Typ, der von abgeleitet ist die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse. Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthorizationManager>` akzeptiert Element untergeordneten Elementen nicht; allerdings von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthorizationManager> können untergeordnete Konfigurationselemente definieren.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt an, Service Level identitätseinstellungen.|  
  
## <a name="remarks"></a>Hinweise  
 Das Standardverhalten über die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse immer die eingehenden Ansprüche autorisiert. Wenn kein `type` -Attribut angegeben ist oder, wenn die `type` Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthorizationManager> -Klasse, die `<claimsAuthorizationManager>` Element akzeptiert keine untergeordneten Elemente. Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus der <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren. Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthorizationManager>` Element durch Überschreiben der <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu behandeln. Das Schema definiert die untergeordneten Elemente ist bis zu der Designer der-Klasse.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse anspruchsbasierte Zugriffssteuerung in Ihrem Code ab, die identitätskonfiguration bereitstellen, die vom verwiesen wird die `<federationConfiguration>` Element konfiguriert werden, die Ansprüche Autorisierungs-Manager und die Richtlinie, die verwendet wird, um Stellen autorisierungsentscheidungen. Dies ist "true" auch in Szenarien, die nicht passiven Web-Szenarien, z. B. Anwendungen für Windows Communication Foundation (WCF) oder eine Anwendung, die nicht webbasierte ist. Wenn die Anwendung nicht auf einem passiven Webanwendung ist der `<claimsAuthorizationManager>` -Element (und der untergeordneten Richtlinienelemente, falls vorhanden) sind die einzigen Einstellungen die identitätskonfiguration verwiesen wird. Alle anderen Einstellungen werden ignoriert. Weitere Informationen finden Sie unter der [ \<FederationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) Element.  
  
 Diese Element legt die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration für die Autorisierung von Ansprüchen-Manager, besteht aus Paaren ressourcenaktion Richtlinie implementiert, von denen jedes booleschen Kombinationen der Ansprüche angibt, die ein anforderer zum Ausführen der Aktion für die Ressource besitzen muss. Der Code, der die Ansprüche Autorisierungs-Manager kann mit dieser Richtlinie implementiert finden Sie der `ClaimsBasedAuthorization` Beispiel.  
  
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
