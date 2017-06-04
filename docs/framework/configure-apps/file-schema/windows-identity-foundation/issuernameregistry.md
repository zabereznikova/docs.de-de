---
title: "&lt;issuerNameRegistry&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# &lt;issuerNameRegistry&gt;
Wird die Aussteller Namen Registrierung, mit der Handler in der Auflistung Tokenhandler konfiguriert.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
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
|type|Ein Type, die von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse.  Weitere Informationen zum Angeben eines benutzerdefiniertes `type`, finden Sie unter [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|Wenn die `type` \-Attribut gibt die konfigurationsbasierte Aussteller Namen Registrierung \(die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse\), die [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) \-Element muss angegeben werden.  Die [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) Element nehmen `<add>`, `<clear>`, oder `<remove>` Elemente als untergeordnete Elemente.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheit Tokenhandler.|  
  
## Hinweise  
 Alle Aussteller Token werden mithilfe einer Aussteller Namen Registrierungs überprüft.  Dies ist ein von abgeleitetes Objekt an die <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse.  Die Aussteller Namen Registrierung wird verwendet, um einen mnemonischen Namen kryptografische Material zuzuordnen, die zum Überprüfen der Signaturen von Token, die vom entsprechenden Aussteller produziert benötigt wird.  Die Aussteller Namen Registrierung verwaltet eine Liste der Emittenten, die von der relying Party \(RP\) Anwendung vertrauenswürdig sind.  Der Typ der Aussteller Namen Registrierung wird angegeben, mit der `type` Attribut.  Die `<issuerNameRegistry>` Element untergeordnete Elemente, die Konfiguration für den angegebenen Typ haben kann.  Sie die Logik bereitstellen, die durch Überschreiben dieser untergeordneten Elemente verarbeitet, die <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> Methode.  
  
 WIF bietet einem einzigen Emittenten Name Registrierungstyp out of the Box, die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse.  Diese Klasse verwendet eine Reihe von Zertifikaten vertrauenswürdiger Aussteller, die in der Konfiguration angegeben werden.  Es muss ein untergeordnetes Element der Konfiguration `<trustedIssuers>`, unter denen die Auflistung von Zertifikaten vertrauenswürdiger Aussteller konfiguriert ist.  Vertrauenswürdige Zertifikate werden angegeben, verwenden die ASN. 1 codiert Form der Fingerabdruck des Zertifikats und hinzugefügt oder entfernt aus der Auflistung mithilfe von `<add>`, `<clear>`, oder `<remove>` Elemente.  
  
 Die `<issuerNameRegistry>` Element dargestellt durch die <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> Klasse.  
  
> [!NOTE]
>  Angabe der `<issuerNameRegistry>` Element als untergeordnetes Element von der [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) Element wurde als veraltet markiert, aber wird aus Kompatibilitätsgründen weiterhin unterstützt.  Einstellungen auf die `<securityTokenHandlerConfiguration>` Element überschreiben die auf die `<identityConfiguration>` Element.  
  
## Beispiel  
 Das folgende XML veranschaulicht der Emittent Konfiguration angeben Namen Registrierung.  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>