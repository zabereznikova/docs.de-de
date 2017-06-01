---
title: "&lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;add&gt;
Fügt der angegebenen Sicherheits\-Tokenhandler der Tokenhandler Auflistung hinzu.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Der CLR\-Typname der Tokenhandler hinzugefügt werden.  Weitere Informationen zum Angeben der `type` \-Attribut, finden Sie unter [Custom Type References](http://msdn.microsoft.com/de-de/7286d2e3-c63d-49fd-abdc-ce2705f22c24).|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> \-Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.|  
|[\<sessionTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse oder abgeleiteter Klassen.|  
|[\<userNameSecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Klasse oder abgeleiteter Klassen.|  
|[\<x509SecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|Bietet optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> Klasse oder abgeleiteter Klassen.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandler, die mit dem Endpunkt registriert sind.|  
  
## Hinweise  
 Die `<add>` Element kann ein einzelnes untergeordnetes Element, der angibt, die Konfiguration der Tokenhandler in Anspruch nehmen.  Dies ist abhängig davon, ob die Handlerklasse, durch verwiesen die `type` \-Attribut des der `<add>` Element bietet Unterstützung für dieses Feature.  Tokenhandler\-Klassen, die diese Funktion bereitstellen müssen einen Konstruktor, der nimmt setzen ein <xref:System.Xml.XmlElement> Objekt.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Einige der integrierten Sicherheit Tokenhandler Klassen stellen diese Funktionalität bereit.  These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  Die Tokenhandler\-Auflistung kann nur einen einzelnen Handler eines beliebigen angegebenen Typs enthalten.  Also, z. B. Wenn Sie einen Handler hinzufügen, die von abgeleitet ist die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse Sie müssen zuerst entfernen, um die Auflistung der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, die standardmäßig aus der Auflistung vorhanden ist.  Können Sie die [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) Element aus der Auflistung oder der Verwendung einen einzelnen Handler Entfernen der [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) alle Handler aus der Auflistung zu entfernende Element.  
  
 Auf einen Handler angegebene Einstellungen Vorrang vor entsprechende Einstellungen auf der Tokenhandler Sammlung unter der [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) \-Element, und die auf der Service\-Ebene unter der [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.  
  
## Beispiel  
 Die folgende XML veranschaulicht die Verwendung der `<add>` und `<remove>` Elemente den Standardhandler für Session token durch eine benutzerdefinierte Sitzungs\-Tokenhandler ersetzen.  Der XML\-Code stammt aus der `ClaimsAwareWebFarm` Beispiel.  
  
```  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```