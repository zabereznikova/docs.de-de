---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667378"
---
# <a name="certificatereference"></a>\<certificateReference>
Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<serviceCertificate>  
\<certificateReference>  
  
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
|storeName|Der Name des x. 509-Zertifikatspeichers. Der Standardwert ist "My". Dies ist optional.|  
|storeLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des x. 509-Zertifikatspeichers angibt. Der Standardwert ist "LocalMachine". Dies ist optional.|  
|x509FindType|Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Typ der Suche angibt, die ausgeführt werden soll. Der Standardwert ist "FindBySubjectDistinguishedName". Dies ist optional.|  
|findValue|Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Dies ist optional.|  
|isChainIncluded|Gibt an, ob die Validierung mithilfe der Zertifikatskette ausgeführt werden soll. Der Standardwert ist "true"; Mithilfe der Zertifikatskette erfolgt die Validierung. Dies ist optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<certificateReference>` Element gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509-Zertifikat im Zertifikatspeicher verwendet werden. Wenn er angegeben wird als untergeordnetes Element von der `<serviceCertficate>` -Element, es gibt die Speicherort und die Überprüfung der Einstellungen des x. 509-Zertifikats, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird. Die `<certificateReference>` Element wird dargestellt, durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.
