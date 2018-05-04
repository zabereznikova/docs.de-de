---
title: '&lt;CertificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e0f9a826a4c8d292346d9efee7970a82b88fb612
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltcertificatereferencegt"></a>&lt;CertificateReference&gt;
Gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden.  
  
 \<system.identityModel.services >  
\<FederationConfiguration >  
\<ServiceCertificate >  
\<CertificateReference >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|storeName|Der Name des x. 509-Zertifikatspeichers. Die Standardeinstellung ist "My". Dies ist optional.|  
|storeLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt. Der Standardwert ist "LocalMachine". Dies ist optional.|  
|x509FindType|Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll. Der Standardwert ist "FindBySubjectDistinguishedName". Dies ist optional.|  
|findValue|Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Dies ist optional.|  
|isChainIncluded|Gibt an, ob die Überprüfung der Zertifikatkette mit ausgeführt werden soll. Der Standardwert ist "true" Überprüfung erfolgt über die Zertifikatkette. Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<certificateReference>` -Element gibt die Einstellungen, die zum finden und überprüfen ein x. 509-Zertifikat in keinem Zertifikatspeicher verwendet werden. Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird. Die `<certificateReference>` Element dargestellt ist, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.
