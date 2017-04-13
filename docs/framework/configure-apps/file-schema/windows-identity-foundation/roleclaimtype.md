---
title: "&lt;roleClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;roleClaimType&gt;
Gibt den Anspruchstyp an, der die Rolle Typanspruch in der Auflistung von Objekten <xref:System.Security.Claims.ClaimsIdentity> definiert, die von der <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>\-Methode des Tokenhandlers zurückgegeben werden.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Description|  
|--------------|-----------------|  
|value|Eine Zeichenfolge, die den URI angibt, das den Anspruchstyp des Anspruchs, für den Rollenanspruchstyp verwenden darstellt.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|Element|Description|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Stellt Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>\-Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>\-Klasse oder eine abgeleitete Klasse von einer dieser Klassen bereit.|  
  
## Hinweise  
 Die `<roleClaimType>`\-Element legt die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>\-Eigenschaft, wenn ein <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>\-Objekt von der Konfiguration initialisiert wird.  
  
## Beispiel  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>