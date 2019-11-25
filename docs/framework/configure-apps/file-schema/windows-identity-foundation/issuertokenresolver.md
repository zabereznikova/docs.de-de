---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968514"
---
# <a name="issuertokenresolver"></a>\<issuertokenresolver >
Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird. Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlerconfiguration >** ](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuertokenresolver >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Gibt den Typ des Aussteller-tokenresolvers an. Muss entweder die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse abgeleitet ist. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securitytokenhandlerconfiguration >](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Hinweise  
 Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen. Sie wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird. Sie müssen das `type`-Attribut angeben. Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver>-Klasse abgeleitet wird.  
  
 Einige Tokenhandler ermöglichen es Ihnen, Einstellungen für Aussteller-tokenresolver in der Konfiguration anzugeben. Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.  
  
> [!NOTE]
> Das Angeben des `<issuerTokenResolver>`-Elements als untergeordnetes Element des [\<identityconfiguration->](identityconfiguration.md) Elements ist veraltet, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für das `<securityTokenHandlerConfiguration>` Element überschreiben die für das `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt die Konfiguration für einen Aussteller-tokenresolver, der auf einer benutzerdefinierten Klasse basiert, die von <xref:System.IdentityModel.Tokens.IssuerTokenResolver>abgeleitet ist. Der tokenresolver verwaltet ein Wörterbuch von Audience-Key-Paaren, die von einem benutzerdefinierten Konfigurationselement (`<AddAudienceKeyPair>`) initialisiert werden, das für die Klasse definiert ist. Die-Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A>-Methode, um dieses Element zu verarbeiten. Die außer Kraft setzung wird im folgenden Beispiel gezeigt. die Methoden, die Sie aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt. Das gesamte Beispiel finden Sie im `CustomToken` Beispiel.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Beispiel
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
``` 
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
