---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152670"
---
# \<issuerTokenResolver>
Registriert den Aussteller-tokenresolver, der von Handlern in der tokenhandlerauflistung verwendet wird. Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|type|Gibt den Typ des Aussteller-tokenresolvers an. Muss entweder die- <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ sein, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerTokenResolver> . Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Aussteller-tokenresolver wird verwendet, um das Signatur Token für eingehende Token und Nachrichten aufzulösen. Sie wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird. Sie müssen das- `type` Attribut angeben. Der angegebene Typ kann entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder ein benutzerdefinierter Typ sein, der von der-Klasse abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerTokenResolver> .  
  
 Einige Tokenhandler ermöglichen es Ihnen, Einstellungen für Aussteller-tokenresolver in der Konfiguration anzugeben. Einstellungen in einzelnen tokenhandlern überschreiben die in der Auflistung der Sicherheitstokenhandler angegebenen.  
  
> [!NOTE]
> Die Angabe des- `<issuerTokenResolver>` Elements als untergeordnetes Element des-Elements wurde als [\<identityConfiguration>](identityconfiguration.md) veraltet markiert, wird jedoch aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Die Einstellungen für das- `<securityTokenHandlerConfiguration>` Element überschreiben die für das- `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt die Konfiguration für einen Aussteller-tokenresolver, der auf einer benutzerdefinierten Klasse basiert, die von abgeleitet wird <xref:System.IdentityModel.Tokens.IssuerTokenResolver> . Der tokenresolver verwaltet ein Wörterbuch von Audience-Key-Paaren, die von einem benutzerdefinierten Konfigurationselement () initialisiert werden, das `<AddAudienceKeyPair>` für die Klasse definiert ist. Die-Klasse überschreibt die- <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten. Die außer Kraft setzung wird im folgenden Beispiel gezeigt. die Methoden, die Sie aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt. Das gesamte Beispiel finden Sie im Beispiel `CustomToken` .  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
