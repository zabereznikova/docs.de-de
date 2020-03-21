---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152748"
---
# <a name="claimsauthenticationmanager"></a>\<claimsAuthenticationManager>
Registriert einen Anspruchsauthentifizierungs-Manager für die eingehenden Ansprüche.  
  
[**\<Konfiguration>**](../configuration-element.md)\
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|type|Gibt einen benutzerdefinierten Typ an, <xref:System.Security.Claims.ClaimsAuthenticationManager> der von der Klasse abstammt. Weitere Informationen zum Angeben `type` des Attributs finden Sie unter [Benutzerdefinierte Typreferenzen].|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Wenn `type` kein Attribut vorhanden ist `type` oder <xref:System.Security.Claims.ClaimsAuthenticationManager> das Attribut `<claimsAuthenticationManager>` auf die Klasse verweist, nimmt das Element keine untergeordneten Elemente an. Von Klassen abgeleitete Klassen <xref:System.Security.Claims.ClaimsAuthenticationManager> können jedoch untergeordnete Konfigurationselemente definieren.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitätseinstellungen auf Dienstebene an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das Standardverhalten, <xref:System.Security.Claims.ClaimsAuthenticationManager> das über die Klasse bereitgestellt wird, spiegelt die eingehenden Ansprüche wider. Wenn `type` kein Attribut angegeben `type` ist oder <xref:System.Security.Claims.ClaimsAuthenticationManager> wenn das `<claimsAuthenticationManager>` Attribut die Klasse angibt, nimmt das Element keine untergeordneten Elemente an. Sie können `type` das Attribut angeben, um <xref:System.Security.Claims.ClaimsAuthenticationManager> einen von der Klasse abgeleiteten Typ zu registrieren, um benutzerdefiniertes Verhalten zu implementieren. Abgeleitete Klassen können die Konfiguration `<claimsAuthenticationManager>` über untergeordnete <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> Elemente des Elements unterstützen, indem die Methode zum Behandeln dieser Elemente überschreibt wird. Das für die untergeordneten Elemente definierte Schema hängt vom Designer der Klasse ab.  
  
 Das `<claimsAuthenticationManager>` Element <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> legt die Eigenschaft fest.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
