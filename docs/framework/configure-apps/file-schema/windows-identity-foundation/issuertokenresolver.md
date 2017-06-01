---
title: "&lt;issuerTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;issuerTokenResolver&gt;
Registriert den token Aussteller\-Konfliktlöser, der vom Handler in der Tokenhandler\-Auflistung verwendet wird.  Der token Aussteller\-Resolver wird verwendet, um Signaturtoken auf eingehende Tokens und Nachrichten zu beheben.  
  
## Syntax  
  
```  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|type|Gibt den Typ des Emittenten token Konfliktlösers.  Werden die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse oder ein Type, die von der <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.  Weitere Informationen zum Angeben der `type` \-Attribut, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  Erforderlich.|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheit Tokenhandler.|  
  
## Hinweise  
 Der token Aussteller\-Resolver wird verwendet, um Signaturtoken auf eingehende Tokens und Nachrichten zu beheben.  Es wird verwendet, um kryptografische Material abzurufen, das für die Überprüfung der Signatur verwendet wird.  Sie müssen angeben, die `type` Attribut.  Der angegebene Typ kann eine <xref:System.IdentityModel.Tokens.IssuerTokenResolver> oder einen benutzerdefinierten Typ, der von abgeleitet wird die <xref:System.IdentityModel.Tokens.IssuerTokenResolver> Klasse.  
  
 Einige Tokenhandler können Sie Aussteller token resolvereinstellungen in der Konfiguration angeben.  Einstellungen für einzelne Tokenhandler überschreiben auf der Security\-token Handler\-Auflistung angegeben.  
  
> [!NOTE]
>  Angabe der `<issuerTokenResolver>` Element als untergeordnetes Element von der [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber wird aus Kompatibilitätsgründen weiterhin unterstützt.  Einstellungen auf die `<securityTokenHandlerConfiguration>` Element überschreiben die auf die `<identityConfiguration>` Element.  
  
## Beispiel  
 Das folgende XML zeigt die Konfiguration für einen Emittenten token Konfliktlöser, die auf einer benutzerdefinierten Klasse, die abgeleitet <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  Der token Resolver verwaltet ein Dictionary Publikum\-Schlüsselpaare, die über ein benutzerdefiniertes Konfigurationselement initialisiert wird \(`<AddAudienceKeyPair>`\) für die Klasse definiert.  Die Klasse überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> \-Methode, um dieses Element zu verarbeiten.  Im folgenden Beispiel wird die Überschreibung angezeigt; Allerdings werden die aufgerufenen Methoden aus Platzgründen nicht angezeigt.  Das vollständige Beispiel finden Sie unter der `CustomToken` Beispiel.  
  
```  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## Beispiel  
  
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
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>