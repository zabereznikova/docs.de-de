---
title: "&lt;x509SecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# &lt;x509SecurityTokenHandlerRequirement&gt;
Stellt optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>\-Klasse oder \-abgeleiteten Klassen bereit.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Description|  
|--------------|-----------------|  
|certificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode>\-Wert, der den Validierungsmodus angibt, das für das X.509\-Zertifikat zu verwenden.  Der Standardwert ist "PeerOrChainTrust".|  
|mapToWindows|Gibt an, ob der Tokenhandler durch das Token zu einem Windows\-Konto zuordnen soll, indem er den eingehenden UPN\-Anspruch verwendet.  Der Standardwert ist "false".|  
|revocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>\-Wert, der den Sperrungsmodus angibt, das für das X.509\-Zertifikat zu verwenden.  Der Standardwert ist "Online".|  
|trustedStoreLocation|Ein Wert, der den <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509\-Zertifikatspeicher angibt.  Der Standardwert ist "LocalMachine".|  
|certificateValidator|Ein benutzerdefinierter Typ, der von <xref:System.IdentityModel.Selectors.X509CertificateValidator> abgeleitet.  Wenn das `certificateValidationMode`\-Attribut "Custom" ist, wird eine Instanz dieses Typs für Ausstellerzertifikatsvalidierung verwendet.|  
  
### Untergeordnete Elemente  
 Kein  
  
### Übergeordnete Elemente  
  
|Element|Description|  
|-------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Fügt den angegebenen Sicherheitstokenhandler der Tokenhandlerauflistung hinzu.|  
  
## Beispiel  
  
```  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```