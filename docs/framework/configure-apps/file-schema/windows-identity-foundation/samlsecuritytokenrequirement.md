---
title: "&lt;samlSecurityTokenRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;samlSecurityTokenRequirement&gt;
Stellt Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>\-Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>\-Klasse oder eine abgeleitete Klasse von einer dieser Klassen bereit.  Wird von der <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>\-Klasse dargestellt.  
  
## Syntax  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
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
|mapToWindows|Gibt an, ob der Tokenhandler durch das Token zu einem Windows\-Konto zuordnen soll, indem er den eingehenden UPN\-Anspruch verwendet.  Der Standardwert ist "false".|  
|issuerCertificateRevocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>\-Wert, der den Sperrungsmodus angibt, das für das X.509\-Zertifikat zu verwenden.  Der Standardwert ist "Online".|  
|issuerCertificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode>\-Wert, der den Validierungsmodus angibt, das für das X.509\-Zertifikat zu verwenden.  Der Standardwert ist "PeerOrChainTrust".|  
|issuerCertificateTrustedStoreLocation|Ein Wert, der den <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509\-Zertifikatspeicher angibt.  Der Standardwert ist "LocalMachine".|  
|issuerCertificateValidator|Ein benutzerdefinierter Typ, der von <xref:System.IdentityModel.Selectors.X509CertificateValidator> abgeleitet.  Wenn das `issuerCertificateValidationMode`\-Attribut "Custom" ist, wird eine Instanz dieses Typs für Ausstellerzertifikatsvalidierung verwendet.|  
  
### Untergeordnete Elemente  
  
|Element|Description|  
|-------------|-----------------|  
|[\<nameClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|Legt den Anspruchstyp fest, der die <xref:System.Security.Principal.IIdentity.Name%2A>\-Eigenschaft angibt.|  
|[\<roleClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|Gibt den Anspruchstyp an, der die Rolle Typanspruch in der Auflistung von Objekten <xref:System.Security.Claims.ClaimsIdentity> definiert, die von der <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>\-Methode des Tokenhandlers zurückgegeben werden.|  
  
### Übergeordnete Elemente  
  
|Element|Description|  
|-------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Fügt den angegebenen Sicherheitstokenhandler der Tokenhandlerauflistung hinzu.|  
  
## Hinweise  
 Das Element `<samlSecurityTokenRequirement>` wird durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>\-Klasse im Objektmodell dargestellt und wird verwendet, um die `SamlSecurityTokenRequirement`\-Eigenschaft auf <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> zu konfigurieren.  
  
## Beispiel  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```