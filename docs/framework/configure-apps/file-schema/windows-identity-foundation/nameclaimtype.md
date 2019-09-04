---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251940"
---
# <a name="nameclaimtype"></a>\<nameClaimType>
Legt den Anspruchstyp fest, der <xref:System.Security.Principal.IIdentity.Name%2A> die Eigenschaft angibt. Der Anspruchstyp wird verwendet, um <xref:System.Security.Claims.Claim> in der Auflistung von <xref:System.Security.Claims.ClaimsIdentity> -Objekten zu suchen, die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> von der-Methode dieses tokenhandlers zurückgegeben werden. Der Wert des übereinstimmenden Anspruchs wird dann als Name <xref:System.Security.Principal.IIdentity> der von diesem Tokenhandler generierten festgelegt.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlsecuritytokenrequirements->** ](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameclaimtype->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Wert|Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der <xref:System.Security.Principal.IIdentity.Name%2A> für die Eigenschaft verwendet werden soll. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<nameClaimType>` -Element legt <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> die-Eigenschaft <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
