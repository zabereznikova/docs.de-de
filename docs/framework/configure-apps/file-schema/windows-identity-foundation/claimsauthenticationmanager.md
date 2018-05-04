---
title: '&lt;Komponente "ClaimsAuthenticationManager"&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;Komponente "ClaimsAuthenticationManager"&gt;
Registriert einen Ansprüche Authentifizierungs-Manager für die eingehenden Ansprüche.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<Komponente "ClaimsAuthenticationManager" >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Gibt einen benutzerdefinierten Typ abgeleitet, die die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse. Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Liegt keine `type` -Attribut, oder wenn die `type` attributverweise der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` akzeptiert Element untergeordneten Elementen nicht; allerdings von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthenticationManager> können untergeordnete Konfigurationselemente definieren.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt an, Service Level identitätseinstellungen.|  
  
## <a name="remarks"></a>Hinweise  
 Das Standardverhalten über die <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse wiederholt die eingehenden Ansprüche. Wenn kein `type` -Attribut angegeben ist oder, wenn die `type` Attribut gibt an, die <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse, die `<claimsAuthenticationManager>` Element akzeptiert keine untergeordneten Elemente. Können Sie angeben, die `type` Attribut, um einen Typ registrieren, abgeleitet aus der <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse, um benutzerdefiniertes Verhalten zu implementieren. Abgeleitete Klassen können die Konfiguration über untergeordnete Elemente des unterstützen die `<claimsAuthenticationManager>` Element durch Überschreiben der <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Methode, um diese Elemente zu behandeln. Das Schema definiert die untergeordneten Elemente ist bis zu der Designer der-Klasse.  
  
 Die `<claimsAuthenticationManager>` Element legt die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Eigenschaft.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
