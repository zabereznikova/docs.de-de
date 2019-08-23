---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942493"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityTokenRequirement>
Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit. Wird von der <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse dargestellt.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<samlSecurityTokenRequirement>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|mapToWindows|Gibt an, ob der Tokenhandler das Validierungs Token einem Windows-Konto zuordnen soll, indem der eingehende UPN-Anspruch verwendet wird. Der Standardwert ist "false".|  
|issuerCertificateRevocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll. Der Standardwert ist "Online".|  
|issuerCertificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll. Der Standardwert ist "Peer-ChainTrust".|  
|issuerCertificateTrustedStoreLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt. Der Standardwert ist "LocalMachine".|  
|issuerCertificateValidator|Ein benutzerdefinierter Typ, der <xref:System.IdentityModel.Selectors.X509CertificateValidator>von abgeleitet wird. Wenn das `issuerCertificateValidationMode` Attribut "Custom" ist, wird eine Instanz dieses Typs für die Überprüfung des Zertifikat Ausstellers verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|Legt den Anspruchstyp fest, der <xref:System.Security.Principal.IIdentity.Name%2A> die Eigenschaft angibt.|  
|[\<roleClaimType>](roleclaimtype.md)|Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung <xref:System.Security.Claims.ClaimsIdentity> von-Objekten definiert <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> , die von der-Methode des tokenhandlers zurückgegeben werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](add.md)|Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<samlSecurityTokenRequirement>` -Element wird durch die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Klasse im Objektmodell dargestellt und zum Konfigurieren der `SamlSecurityTokenRequirement` -Eigenschaft in einem <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> oder einem <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>verwendet.  
  
## <a name="example"></a>Beispiel  
  
```xml  
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
