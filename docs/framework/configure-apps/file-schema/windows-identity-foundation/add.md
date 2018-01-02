---
title: '&lt;add&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c0709159207cfd9f32aa9b6243bb53b7c1ed0e3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt"></a>&lt;add&gt;
Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.  
  
 \<system.identityModel >  
\<IdentityConfiguration >  
\<SecurityTokenHandlers >  
\<add>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Der CLR-Typname der der Tokenhandler hinzugefügt werden. Weitere Informationen zum Angeben der `type` -Attribut angegeben wird, finden Sie unter [benutzerdefinierte Typverweise](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SamlSecurityTokenRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.|  
|[\<auf "sessiontokenrequirement" >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> abgeleiteten Klassen.|  
|[\<UserNameSecurityTokenHandlerRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> abgeleiteten Klassen.|  
|[\<x509SecurityTokenHandlerRequirement >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|Bietet optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> abgeleiteten Klassen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SecurityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Gibt eine Auflistung von sicherheitstokenhandlern, die mit dem Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<add>` Element kann ein einzelnes untergeordnetes Element, der angibt, die Konfiguration der Tokenhandler in Anspruch nehmen. Dies ist abhängig davon, ob die Handlerklasse über verwiesen die `type` Attribut von der `<add>` -Element stellt Unterstützung für diese Funktion. Tokenhandler-Klassen, die diese Funktion bereitstellen, verfügbar machen einen Konstruktor, akzeptiert eine <xref:System.Xml.XmlElement> Objekt.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Einige der integrierten Sicherheit Tokenhandler Klassen stellen diese Funktionalität bereit. Diese Klassen sind <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, und <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  Die Tokenhandler Auflistung darf nur einen einzigen Handler eines angegebenen Typs. Dies bedeutet, z. B., dass wenn Sie möchten einen Handler hinzuzufügen, die abgeleitet ist die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse auf die Auflistung, müssen Sie zuerst Entfernen der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, die standardmäßig aus der Auflistung vorhanden ist. Können Sie die [ \<entfernen >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) Element So entfernen Sie einen einzigen Handler aus der Auflistung oder die Verwendung der [ \<deaktivieren >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) zu alle Handler aus der Auflistung zu entfernenden Elements.  
  
 Für einen Ereignishandler angegebene Einstellungen außer Kraft setzen entsprechende Einstellungen auf der Tokenhandler Sammlung im angegebenen der [ \<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) Element und den angegebenen auf Dienstebene unter die [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Verwendung der `<add>` und `<remove>` Elemente der Standardhandler für Sitzung token mit einer benutzerdefinierten-Sitzung Tokenhandler ersetzen. Der XML-Code stammt aus dem `ClaimsAwareWebFarm` Beispiel.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
