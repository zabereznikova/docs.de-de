---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 9505970c1fd7fcdfe62d3c6ef58f5d653fab4106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941995"
---
# <a name="add"></a>\<add>
Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
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
|Typ|Der CLR-Typname des tokenhandlers, der hinzugefügt werden soll. Weitere Informationen zum Angeben des `type` -Attributs finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|Stellt die Konfiguration für <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|Stellt eine optionale Konfiguration für <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<add>` -Element kann ein einzelnes untergeordnetes Element annehmen, das die Konfiguration für den Tokenhandler angibt. Dies hängt davon ab, ob die Handlerklasse, `type` auf die über `<add>` das-Attribut des-Elements verwiesen wird, Unterstützung für diese Funktion bietet Tokenhandlerklassen, die diese Funktion bereitstellen, müssen einen Konstruktor verfügbar machen, der ein <xref:System.Xml.XmlElement> Objekt annimmt.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Einige der integrierten sicherheitstokenhandlerklassen stellen diese Funktionalität bereit. Diese Klassen sind <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>und .<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
  
> [!IMPORTANT]
> Die tokenhandlerauflistung kann nur einen einzelnen Handler eines beliebigen Typs enthalten. Dies bedeutet beispielsweise Folgendes: Wenn Sie einen von der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> -Klasse abgeleiteten Handler zur-Auflistung hinzufügen möchten, müssen Sie zuerst den <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, der standardmäßig vorhanden ist, aus der-Auflistung entfernen. Sie können das [ \<remove >](remove.md) -Element verwenden, um einen einzelnen Handler aus der Auflistung zu entfernen, oder das [ \<Clear >](clear.md) -Element verwenden, um alle Handler aus der Auflistung zu entfernen.  
  
 Die Einstellungen, die für einen Handler angegeben werden, überschreiben die entsprechenden Einstellungen, die für die tokenhandlerauflistung unter dem [ \<securitytokenhandlerconfiguration->](securitytokenhandlerconfiguration.md) -Element angegeben sind, und die auf Dienst Ebene unter [ \< identityconfiguration >](identityconfiguration.md) Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML `<add>` -Code zeigt die Verwendung des `<remove>` -Elements und des-Elements, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler Der XML-Code stammt aus `ClaimsAwareWebFarm` dem Beispiel.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
