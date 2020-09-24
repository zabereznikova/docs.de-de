---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 9e099b8de486631702548b8a035a46a7e0f4eb30
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158473"
---
# \<claimsAuthenticationManager>

Registriert einen anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|type|Gibt einen benutzerdefinierten Typ an, der von der-Klasse abgeleitet wird <xref:System.Security.Claims.ClaimsAuthenticationManager> . Weitere Informationen zum Angeben des- `type` Attributs finden Sie unter [Custom Type References].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Wenn kein-Attribut vorhanden ist `type` , oder wenn das- `type` Attribut auf die- <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse verweist, nimmt das- `<claimsAuthenticationManager>` Element keine untergeordneten Elemente an. von abgeleitete Klassen können jedoch untergeordnete <xref:System.Security.Claims.ClaimsAuthenticationManager> Konfigurationselemente definieren.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
  
## <a name="remarks"></a>Bemerkungen  

 Das von der-Klasse bereitgestellte Standardverhalten gibt <xref:System.Security.Claims.ClaimsAuthenticationManager> die eingehenden Ansprüche wieder. Wenn kein- `type` Attribut angegeben wird oder wenn das- `type` Attribut die- <xref:System.Security.Claims.ClaimsAuthenticationManager> Klasse angibt, nimmt das- `<claimsAuthenticationManager>` Element keine untergeordneten Elemente an. Sie können das `type` Attribut angeben, um einen von der-Klasse abgeleiteten Typ <xref:System.Security.Claims.ClaimsAuthenticationManager> zu registrieren, um benutzerdefiniertes Verhalten zu implementieren Abgeleitete Klassen können die Konfiguration durch untergeordnete Elemente des-Elements unterstützen `<claimsAuthenticationManager>` , indem Sie die- <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Methode zum Verarbeiten dieser Elemente überschreiben. Das Schema, das für die untergeordneten Elemente definiert ist, ist der Designer der-Klasse.  
  
 Das- `<claimsAuthenticationManager>` Element legt die- <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> Eigenschaft fest.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
