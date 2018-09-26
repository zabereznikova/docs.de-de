---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: bd4033b2edea7450b66c25f446669b3ded65e9af
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112217"
---
# <a name="ltnameclaimtypegt"></a>&lt;nameClaimType&gt;
Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft. Der Anspruchstyp wird verwendet, um für die Suche eine <xref:System.Security.Claims.Claim> in der Auflistung der <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> -Methode der diesem Tokenhandler. Der Wert, der den übereinstimmenden Anspruch wird als Name des festgelegt die <xref:System.Security.Principal.IIdentity> aus dieser Handler token generiert.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<SecurityTokenHandlers >  
\<add>  
\<SamlSecurityTokenRequirement >  
\<NameClaimType >  
  
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
|Wert|Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs für die Verwendung der <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<nameClaimType>` Elementgruppen die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
