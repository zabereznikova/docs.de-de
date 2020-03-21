---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152813"
---
# <a name="certificatereference"></a>\<certificateReferenz>
Gibt Einstellungen an, die zum Suchen und Überprüfen eines X.509-Zertifikats in einem Zertifikatspeicher verwendet werden.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<FederationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReferenz>**  
  
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
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|storeName|Der Namen des X.509-Zertifikatsspeichers. Der Standardwert ist "Mein". Optional.|  
|storeLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den Speicherort des X.509-Zertifikatspeichers angibt. Der Standardwert ist "LocalMachine". Optional.|  
|x509FindType|Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> Wert, der den Suchtyp angibt, der ausgeführt werden soll. Der Standardwert ist "FindBySubjectDistinguishedName". Optional.|  
|findValue|Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Optional.|  
|isChainIncluded|Gibt an, ob die Validierung mithilfe der Zertifikatkette durchgeführt werden soll. Der Standardwert ist "true"; Die Validierung wird mithilfe der Zertifikatkette durchgeführt. Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|Konfiguriert das Zertifikat, das zum Ver- und Entschlüsseln von Token verwendet wird.|  
  
## <a name="remarks"></a>Bemerkungen  
 Das `<certificateReference>` Element gibt Einstellungen an, die zum Suchen und Überprüfen eines X.509-Zertifikats in einem Zertifikatspeicher verwendet werden. Wenn es als untergeordnetes Element `<serviceCertificate>` des Elements angegeben wird, gibt es den Speicherort und die Überprüfungseinstellungen des X.509-Zertifikats an, das zum Ver- und Entschlüsseln von Token verwendet wird. Das `<certificateReference>` Element wird <xref:System.ServiceModel.Configuration.CertificateReferenceElement> durch die Klasse dargestellt.
