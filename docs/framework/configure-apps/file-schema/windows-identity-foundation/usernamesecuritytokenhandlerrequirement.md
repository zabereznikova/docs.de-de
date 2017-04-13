---
title: "&lt;userNameSecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;userNameSecurityTokenHandlerRequirement&gt;
Stellt Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>\-Klasse oder \-abgeleiteten Klassen bereit.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
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
|membershipProviderName|Gibt <xref:System.Web.Security.MembershipProvider> an, das vom Sicherheitstokenhandler verwendet werden soll.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|Element|Description|  
|-------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Fügt den angegebenen Sicherheitstokenhandler der Tokenhandlerauflistung hinzu.|  
  
## Hinweise  
 Die `<userNameSecurityTokenHandlerRequirement>`\-Element legt die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>\-Eigenschaft, wenn ein <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>\-Objekt von der Konfiguration initialisiert wird.  
  
## Beispiel  
  
```  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```