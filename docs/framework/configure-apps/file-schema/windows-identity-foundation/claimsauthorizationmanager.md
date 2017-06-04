---
title: "&lt;claimsAuthorizationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;claimsAuthorizationManager&gt;
Registriert einen Ansprüche Autorisierungs\-Manager für die eingehenden Ansprüche.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Eine benutzerdefinierte Type, die von der <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse.  Weitere Informationen zum Angeben der `type` \-Attribut, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Untergeordnete Elemente  
 Liegt keine `type` \-Attribut, oder, wenn die `type` References\-Attribut der <xref:System.Security.Claims.ClaimsAuthenticationManager> \-Klasse, die `<claimsAuthorizationManager>` Element nimmt keine untergeordneten Elemente; jedoch von abgeleiteten Klassen <xref:System.Security.Claims.ClaimsAuthorizationManager> können die untergeordneten Konfigurationselemente definieren.  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Gibt die von Service\-Level\-Identitätseinstellungen.|  
  
## Hinweise  
 Das Standardverhalten durch die <xref:System.Security.Claims.ClaimsAuthorizationManager> Klasse immer die eingehenden Ansprüche autorisiert.  Wenn keine `type` \-Attribut angegeben ist oder, wenn die `type` \-Attribut gibt die <xref:System.Security.Claims.ClaimsAuthorizationManager> \-Klasse, die `<claimsAuthorizationManager>` Element nimmt keine untergeordneten Elemente.  Können Sie die `type` \-Attribut auf einen Typ registrieren abgeleitet die <xref:System.Security.Claims.ClaimsAuthorizationManager> \-Klasse, um benutzerdefiniertes Verhalten implementieren.  Abgeleitete Klassen unterstützen die Konfiguration über untergeordnete Elemente von der `<claimsAuthorizationManager>` Element durch Überschreiben der <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> \-Methode, um diese Elemente zu behandeln.  Das Schema definiert, die für die untergeordneten Elemente ist der Designer die Klasse.  
  
> [!IMPORTANT]
>  Bei Verwendung der <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> oder die <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> Klasse, um anspruchsbasierte Zugriffssteuerung in Ihrem Code die Identität\-Konfiguration die verwiesen wird die `<federationConfiguration>` \-Element konfiguriert die Ansprüche Autorisierungs\-Manager und die Richtlinie, die verwendet wird, um Autorisierungsentscheidungen treffen zu können.  Dies gilt, auch in Szenarien, die nicht passive Web\-Szenarien, z. B. Windows Communication Foundation \(WCF\)\-Anwendungen oder eine Anwendung, die nicht Web\-basiert ist.  Wenn die Anwendung nicht über eine passive Webanwendung ist die `<claimsAuthorizationManager>` Element \(und seine untergeordneten Richtlinienelemente, sofern vorhanden\) die referenzierte Identität\-Konfiguration sind die einzigen Einstellungen angewendet.  Alle anderen Einstellungen werden ignoriert.  Weitere Informationen finden Sie unter dem [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)\-Element.  
  
 Dieses Element setzt die <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=fullName> Eigenschaft.  
  
## Beispiel  
 Das folgende XML zeigt die Konfiguration für eine Anspruchsautorisierung\-Manager, Politik, bestehend aus Resource\-Aktion\-Paar implementiert jeweils boolesche Kombinationen der Ansprüche angeben, die ein Anforderer Ausführen der Aktion für die Ressource besitzen muss.  Der Code, der den Ansprüche Autorisierungs\-Manager kann mit dieser Richtlinie implementiert finden Sie der `ClaimsBasedAuthorization` Beispiel.  
  
```  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```