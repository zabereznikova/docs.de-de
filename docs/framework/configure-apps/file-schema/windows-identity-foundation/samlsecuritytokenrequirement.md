---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152631"
---
# <a name="samlsecuritytokenrequirement"></a>\<samlSecurityTokenRequirement>
Stellt die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> Konfiguration für <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> die Klasse, die Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit. Vertreten durch <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> die Klasse.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|mapToWindows|Gibt an, ob der Tokenhandler das Validierungstoken mithilfe des eingehenden UPN-Anspruchs einem Windows-Konto zuordnen soll. Der Standardwert lautet "false".|  
|AusstellerCertificateRevocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X.509-Zertifikat verwendet werden soll. Der Standardwert ist "Online".|  
|AusstellerCertificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungsmodus angibt, der für das X.509-Zertifikat verwendet werden soll. Der Standardwert ist "PeerOrChainTrust".|  
|AusstellerCertificateTrustedStoreLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X.509-Zertifikatspeicher angibt. Der Standardwert ist "LocalMachine".|  
|AusstellerCertificateValidator|Ein benutzerdefinierter Typ, <xref:System.IdentityModel.Selectors.X509CertificateValidator>der von ableitet. Wenn `issuerCertificateValidationMode` das Attribut "Custom" lautet, wird eine Instanz dieses Typs für die Validierung von Ausstellerzertifikaten verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<NameClaimType>](nameclaimtype.md)|Legt den Anspruchstyp <xref:System.Security.Principal.IIdentity.Name%2A> fest, der die Eigenschaft angibt.|  
|[\<roleClaimType>](roleclaimtype.md)|Gibt den Anspruchstyp an, der die Rollentypansprüche in der Auflistung von <xref:System.Security.Claims.ClaimsIdentity> Objekten definiert, die von der <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode des Tokenhandlers zurückgegeben werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<hinzufügen>](add.md)|Fügt der Tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `<samlSecurityTokenRequirement>` Element wird <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> durch die Klasse im Objektmodell `SamlSecurityTokenRequirement` dargestellt und <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> zum <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>Konfigurieren der Eigenschaft auf einer oder einer verwendet.  
  
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
