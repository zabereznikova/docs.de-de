---
title: "&lt;nameClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;nameClaimType&gt;
Legt den Anspruchstyp fest, der die <xref:System.Security.Principal.IIdentity.Name%2A>\-Eigenschaft angibt.  Der Anspruchstyp wird verwendet, um für <xref:System.Security.Claims.Claim> in der Auflistung von Objekten <xref:System.Security.Claims.ClaimsIdentity> zu suchen, die durch die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>\-Methode dieses Tokenhandlers zurückgegeben werden.  Der Wert des entsprechenden Anspruchs wird dann wie Name <xref:System.Security.Principal.IIdentity> festgelegt, das von diesem Tokenhandler generiert wird.  
  
## Syntax  
  
```  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Description|  
|--------------|-----------------|  
|value|Eine Zeichenfolge, die den URI angibt, das den Anspruchstyp des Anspruchs, für die <xref:System.Security.Principal.IIdentity.Name%2A>\-Eigenschaft verwenden darstellt.  Erforderlich.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|Element|Description|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Stellt Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>\-Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>\-Klasse oder eine abgeleitete Klasse von einer dieser Klassen bereit.|  
  
## Hinweise  
 Die `<nameClaimType>`\-Element legt die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>\-Eigenschaft, wenn ein <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>\-Objekt von der Konfiguration initialisiert wird.  
  
## Beispiel  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>