---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152670"
---
# <a name="issuertokenresolver"></a>\<IssuerTokenResolver>
Registriert den Ausstellertokenlöser, der von Handlern in der Tokenhandlerauflistung verwendet wird. Der Ausstellertokenlöser wird verwendet, um das Signaturtoken für eingehende Token und Nachrichten zu beheben.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<IssuerTokenResolver>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|type|Gibt den Typ des Ausstellertokenlösers an. Es muss <xref:System.IdentityModel.Tokens.IssuerTokenResolver> entweder die Klasse oder ein <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Typ sein, der von der Klasse stammt. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
 Der Ausstellertokenlöser wird verwendet, um das Signaturtoken für eingehende Token und Nachrichten zu beheben. Es wird verwendet, um das kryptografische Material abzurufen, das zum Überprüfen der Signatur verwendet wird. Sie müssen `type` das Attribut angeben. Der angegebene Typ <xref:System.IdentityModel.Tokens.IssuerTokenResolver> kann entweder oder ein benutzerdefinierter Typ sein, der von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse abstammt.  
  
 Einige Tokenhandler ermöglichen es Ihnen, Ausstellertoken-Resolvereinstellungen in der Konfiguration anzugeben. Einstellungen für einzelne Tokenhandler überschreiben die in der Sicherheitstokenhandlerauflistung angegebenen.  
  
> [!NOTE]
> Die Angabe `<issuerTokenResolver>` des Elements als untergeordnetes Element der [ \<identityConfiguration>-Element](identityconfiguration.md) sprägiert, wird aber aus Gründen der Abwärtskompatibilität weiterhin unterstützt. Einstellungen für `<securityTokenHandlerConfiguration>` das Element überschreiben die Einstellungen für das `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt die Konfiguration für einen Ausstellertokenlöser, <xref:System.IdentityModel.Tokens.IssuerTokenResolver>der auf einer benutzerdefinierten Klasse basiert, die von ableitet. Der Token-Resolver verwaltet ein Wörterbuch von Zielgruppen-Schlüsselpaaren,`<AddAudienceKeyPair>`das aus einem benutzerdefinierten Konfigurationselement ( ) initialisiert wird, das für die Klasse definiert ist. Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode zum Verarbeiten dieses Elements. Die Außerkraftsetzung wird im folgenden Beispiel gezeigt. Die Methoden, die es aufruft, werden jedoch nicht aus Gründen der Kürze angezeigt. Das vollständige Beispiel finden `CustomToken` Sie im Beispiel.  
  
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
