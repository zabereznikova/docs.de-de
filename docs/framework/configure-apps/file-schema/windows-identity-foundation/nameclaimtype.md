---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4ffc19366d91e4a14ee0f931d7009ede390cc097
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165025"
---
# \<nameClaimType>

Legt den Anspruchstyp fest, der die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft angibt. Der Anspruchstyp wird verwendet, um in der Auflistung von-Objekten zu suchen, die <xref:System.Security.Claims.Claim> <xref:System.Security.Claims.ClaimsIdentity> von der- <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode dieses tokenhandlers zurückgegeben werden. Der Wert des übereinstimmenden Anspruchs wird dann als Name der <xref:System.Security.Principal.IIdentity> von diesem Tokenhandler generierten festgelegt.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|value|Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der für die Eigenschaft verwendet werden soll <xref:System.Security.Principal.IIdentity.Name%2A> . Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Stellt die Konfiguration für die- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> Klasse, die- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.|  
  
## <a name="remarks"></a>Bemerkungen  

 Das- `<nameClaimType>` Element legt die-Eigenschaft fest, <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Wenn ein- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekt aus der Konfiguration initialisiert wird.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
