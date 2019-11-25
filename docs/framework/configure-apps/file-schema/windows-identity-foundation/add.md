---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973803"
---
# <a name="add"></a>\<add>
Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<hinzufügen >**  
  
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
|Typ|Der CLR-Typname des tokenhandlers, der hinzugefügt werden soll. Weitere Informationen zum Angeben des `type` Attributs finden Sie unter [benutzerdefinierte Typverweise](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<samlsecuritytokenrequirements >](samlsecuritytokenrequirement.md)|Stellt die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>-Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.|  
|[\<sessiontokenrequirements >](sessiontokenrequirement.md)|Stellt die Konfiguration für die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>-Klasse oder abgeleitete Klassen bereit.|  
|[\<usernamesecuritytokenhandlerrequirements >](usernamesecuritytokenhandlerrequirement.md)|Stellt die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>-Klasse oder abgeleitete Klassen bereit.|  
|[\<x509SecurityTokenHandlerRequirement >](x509securitytokenhandlerrequirement.md)|Stellt eine optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>-Klasse oder abgeleitete Klassen bereit.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securitytokenhandlers >](securitytokenhandlers.md)|Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<add>`-Element kann ein einzelnes untergeordnetes Element annehmen, das die Konfiguration für den Tokenhandler angibt. Dies hängt davon ab, ob die Handlerklasse, auf die über das `type`-Attribut des `<add>`-Elements verwiesen wird, Unterstützung für diese Funktion bietet. Tokenhandlerklassen, die diese Funktion bereitstellen, müssen einen Konstruktor verfügbar machen, der ein <xref:System.Xml.XmlElement> Objekt annimmt.  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Einige der integrierten sicherheitstokenhandlerklassen stellen diese Funktionalität bereit. Diese Klassen sind <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>und <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
> Die tokenhandlerauflistung kann nur einen einzelnen Handler eines beliebigen Typs enthalten. Wenn Sie z. b. einen Handler hinzufügen möchten, der von der <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>-Klasse zur-Auflistung abgeleitet ist, müssen Sie zuerst das <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, das standardmäßig vorhanden ist, aus der-Auflistung entfernen. Sie können das [\<remove >](remove.md) -Element verwenden, um einen einzelnen Handler aus der Auflistung zu entfernen, oder das [\<Clear >](clear.md) -Element verwenden, um alle Handler aus der Auflistung zu entfernen.  
  
 Die Einstellungen, die für einen Handler angegeben werden, überschreiben die entsprechenden Einstellungen, die für die [tokenhandlerauflistung unter dem\<securitytokenhandlerconfiguration->](securitytokenhandlerconfiguration.md) Element angegeben wurden, und die auf Dienst Ebene unter dem [\<identityconfiguration->](identityconfiguration.md) Element angegebenen  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt die Verwendung der `<add>`-und `<remove>`-Elemente, um den standardsitzungstokenhandler durch einen benutzerdefinierten Sitzungs Token-Handler zu ersetzen Der XML-Code stammt aus dem `ClaimsAwareWebFarm`-Beispiel.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
