---
title: "&lt;trustedIssuers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;trustedIssuers&gt;
Konfiguriert die Liste der vertrauenswürdigen Aussteller\-Zertifikate, die der Aussteller konfigurationsbasierte Namen Registrierung verwendet \(<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>\).  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 None  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`<add thumbprint=xs:string name=xs:string>`|Fügt ein Zertifikat zur Auflistung der vertrauenswürdiger Aussteller.  Das Zertifikat wird angegeben, mit der `thumbprint` Attribut.  Dieses Attribut ist erforderlich und sollte die ASN. 1 codiert Form der Fingerabdruck des Zertifikats enthalten.  Die `name` \-Attribut ist optional und kann verwendet werden, um einen Anzeigenamen für das Zertifikat anzugeben.|  
|`<clear>`|Löscht alle Zertifikate aus der Auflistung der vertrauenswürdiger Aussteller.|  
|`<remove thumbprint=xs:string>`|Entfernt ein Zertifikat aus der Auflistung der vertrauenswürdiger Aussteller.  Das Zertifikat wird angegeben, mit der `thumbprint` Attribut.  Dieses Attribut ist erforderlich.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|Konfiguriert die Registrierung des Emittenten Name. **Important:**  Die `type` \-Attribut des der `<issuerNameRegistry>` Element verweisen muss die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse für die `<trustedIssuers>` Element gültig ist.|  
  
## Hinweise  
 Windows\-Identität\-Foundation \(WIF\) stellt eine einzelne Implementierung von der <xref:System.IdentityModel.Tokens.IssuerNameRegistry> Klasse aus dem Feld der <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse.  Der Name die Konfigurationsregistrierung\-Aussteller verwaltet eine Liste vertrauenswürdiger Aussteller, die aus der Konfiguration geladen wird.  Jede Ausstellername verknüpft mit x. 509\-Zertifikat, das zum Überprüfen der Signatur von Token, die vom Emittenten produziert benötigt wird.  Die Liste der Zertifikate vertrauenswürdiger Aussteller wird angegeben, unter der `<trustedIssuers>` Element.  Jedes Element in der Liste ordnet eine mnemonische Ausstellername der x. 509\-Zertifikat, das zum Überprüfen der Signatur von Token, die von diesem Aussteller produziert benötigt wird.  Vertrauenswürdige Zertifikate mithilfe der ASN. 1 codiert Form der Fingerabdruck des Zertifikats angegeben sind, und werden unter Verwendung die Auflistung hinzugefügt `<add>` Element.  Sie können löschen oder Entfernen von Emittenten \(Zertifikate\) aus der Liste mithilfe der `<clear>` und `<remove>` Elemente.  
  
 Die `type` \-Attribut des der `<issuerNameRegistry>` Element verweisen muss die <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> Klasse für die `<trustedIssuers>` Element gültig ist.  
  
## Beispiel  
 Das folgende XML veranschaulicht der Emittent Konfiguration angeben Namen Registrierung.  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>