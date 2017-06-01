---
title: "&lt;claimsAuthenticationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;claimsAuthenticationManager&gt;
Registriert einen Anspruchsauthentifizierungs\-Manager für die eingehenden Eine.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Gibt einen benutzerdefinierten Typ an, der von der <xref:System.Security.Claims.ClaimsAuthenticationManager>\-Klasse abgeleitet ist.  Weitere Informationen zur Verwendung des `type`\-Attribut finden Sie unter angibt [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferencess).|  
  
### Untergeordnete Elemente  
 Wenn kein `type`\-Attribut vorhanden ist oder wenn die `type`\-Attribut <xref:System.Security.Claims.ClaimsAuthenticationManager>\-Klasse die verwiesen wird, hat das Element `<claimsAuthenticationManager>` keine untergeordneten Elemente. Allerdings können die Klassen, die von <xref:System.Security.Claims.ClaimsAuthenticationManager> abgeleitet sind, untergeordnete Konfigurationselemente definieren.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die Identität von Einstellungen auf Dienstebene auf.|  
  
## Hinweise  
 Das Standardverhalten, das von der <xref:System.Security.Claims.ClaimsAuthenticationManager>\-Klasse bereitgestellt wird, gibt die eingehenden Eine als Echo aus.  Wenn kein `type`\-Attribut angegeben ist oder wenn das Attribut `type` die <xref:System.Security.Claims.ClaimsAuthenticationManager>\-Klasse angibt, akzeptiert das `<claimsAuthenticationManager>`\-Element nicht über untergeordnete Elemente.  Sie können das `type`\-Attribut angeben, um einen Typ zu registrieren, der von der <xref:System.Security.Claims.ClaimsAuthenticationManager>\-Klasse, um ein benutzerdefiniertes Verhalten zu implementieren.  Abgeleitete Klassen können Konfiguration von untergeordneten Elementen des `<claimsAuthenticationManager>`\-Elements unterstützen, indem sie die <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>\-Methode überschreiben, um diese Elemente zu behandeln.  Das Schema, das für die untergeordneten Elemente definiert wird, hängt in den Designer der Klasse.  
  
 Die `<claimsAuthenticationManager>`\-Element die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=fullName>\-Eigenschaft.  
  
## Beispiel  
  
```  
<system.identityModel>  
    <identityConfiguration name=”MyIdentity”>  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```