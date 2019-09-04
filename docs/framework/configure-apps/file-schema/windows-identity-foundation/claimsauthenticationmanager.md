---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252089"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ClaimsAuthenticationManager->**  
  
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
|Typ|Gibt einen benutzerdefinierten Typ an, der <xref:System.Security.Claims.ClaimsAuthenticationManager> von der-Klasse abgeleitet wird. Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [Custom Type References].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Wenn kein `type` -Attribut vorhanden ist, oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> auf die- `<claimsAuthenticationManager>` Klasse verweist, nimmt das-Element keine untergeordneten Elemente an <xref:System.Security.Claims.ClaimsAuthenticationManager> . von abgeleitete Klassen können jedoch untergeordnete Konfigurationselemente definieren.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
  
## <a name="remarks"></a>Hinweise  
 Das von der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse bereitgestellte Standardverhalten gibt die eingehenden Ansprüche wieder. Wenn kein `type` -Attribut angegeben wird oder wenn `type` das-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager> die-Klasse `<claimsAuthenticationManager>` angibt, nimmt das-Element keine untergeordneten Elemente an. Sie können das `type` Attribut angeben, um einen von der <xref:System.Security.Claims.ClaimsAuthenticationManager> -Klasse abgeleiteten Typ zu registrieren, um benutzerdefiniertes Verhalten zu implementieren Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente `<claimsAuthenticationManager>` des-Elements unter <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> stützen, indem Sie die-Methode zum Verarbeiten dieser Elemente überschreiben. Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.  
  
 Das `<claimsAuthenticationManager>` -Element legt <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> die-Eigenschaft fest.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
