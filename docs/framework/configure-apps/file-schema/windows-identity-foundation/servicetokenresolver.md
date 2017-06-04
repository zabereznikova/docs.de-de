---
title: "&lt;serviceTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;serviceTokenResolver&gt;
Registriert den token Service\-Konfliktlöser, der vom Handler in der Tokenhandler\-Auflistung verwendet wird.  Der Service\-token\-Resolver wird verwendet, zum Auflösen des Tokens Verschlüsselung auf eingehende Tokens und Nachrichten.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
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
|type|Gibt den Typ des Resolvers token Service.  Entweder die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Typ oder ein Typ, der von abgeleitet wird die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.  Weitere Informationen zum Angeben der `type` \-Attribut, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  Erforderlich.|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheit Tokenhandler.|  
  
## Hinweise  
 Der Service\-token\-Resolver kann zum Auflösen des Tokens Verschlüsselung auf eingehende Tokens und Nachrichten verwendet werden.  Es wird verwendet, um den Schlüssel abzurufen, der zum Entschlüsseln von eingehender Tokens verwendet werden soll.  Sie müssen angeben, die `type` Attribut.  Der angegebene Typ kann eine <xref:System.IdentityModel.Selectors.SecurityTokenResolver> oder einen benutzerdefinierten Typ, der von abgeleitet wird die <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Klasse.  
  
 Einige Tokenhandler können Sie token Resolver Diensteinstellungen in der Konfiguration angeben.  Einstellungen für einzelne Tokenhandler überschreiben auf der Security\-token Handler\-Auflistung angegeben.  
  
> [!NOTE]
>  Angabe der `<serviceTokenResolver>` Element als untergeordnetes Element von der [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber wird aus Kompatibilitätsgründen weiterhin unterstützt.  Einstellungen auf die `<securityTokenHandlerConfiguration>` Element überschreiben die auf die `<identityConfiguration>` Element.  
  
## Beispiel  
  
```  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```