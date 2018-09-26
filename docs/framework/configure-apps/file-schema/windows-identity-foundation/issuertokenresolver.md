---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: eefd18c206b7f013c3a423df424c795583c0dde8
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216330"
---
# <a name="ltissuertokenresolvergt"></a>&lt;issuerTokenResolver&gt;
Registriert die Aussteller-tokenresolver, der von Handlern in die Auflistung der Tokenhandler verwendet wird. Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<SecurityTokenHandlers >  
\<SecurityTokenHandlerConfiguration >  
\<IssuerTokenResolver >  
  
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
|Typ|Gibt den Typ der Aussteller-tokenresolvers. Muss entweder die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Typ, der von abgeleitet ist die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse. Erforderlich.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<SecurityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung der Tokenhandler.|  
  
## <a name="remarks"></a>Hinweise  
 Die Aussteller-tokenresolver wird zum Auflösen des Signaturtokens auf eingehende Tokens und Nachrichten. Es wird verwendet, um das kryptografische Material abzurufen, das für die Überprüfung der Signatur verwendet wird. Sie müssen angeben, die `type` Attribut. Der angegebene Typ kann es sich entweder <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder einen benutzerdefinierten Typ abgeleitet, die die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.  
  
 Einige Tokenhandler können Sie Aussteller-tokenresolver Einstellungen in der Konfiguration anzugeben. Einstellungen für einzelne Tokenhandler außer Kraft setzen auf der Sicherheitstoken-Handlerauflistung angegeben.  
  
> [!NOTE]
>  Angeben der `<issuerTokenResolver>` -Element als untergeordnetes Element von der [ \<IdentityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element ist veraltet, jedoch wird für die Abwärtskompatibilität weiterhin unterstützt. Einstellungen für die `<securityTokenHandlerConfiguration>` Element überschreiben diejenigen auf dem `<identityConfiguration>` Element.  
  
## <a name="example"></a>Beispiel  
 Das folgende XML zeigt die Konfiguration für einen Aussteller-tokenresolver, der für eine benutzerdefinierte Klasse basiert, die von abgeleitet <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Der tokenresolver verwaltet ein Wörterbuch der Zielgruppe-Schlüssel-Paare, die über ein benutzerdefiniertes Konfigurationselement initialisiert wird (`<AddAudienceKeyPair>`) für die Klasse definiert. Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> Methode, um dieses Element zu verarbeiten. Die Außerkraftsetzung wurde im folgenden Beispiel dargestellt. Allerdings werden die Methoden, die er aufruft, aus Gründen der Übersichtlichkeit nicht angezeigt. Das vollständige Beispiel finden Sie unter den `CustomToken` Beispiel.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Beispiel  
  
```  
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
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
