---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941933"
---
# <a name="certificatereference"></a>\<certificateReference>
Gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen.  
  
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
|storeName|Der Name des X. 509-Zertifikats Speicher. Der Standardwert ist "My". Optional.|  
|storeLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den Speicherort des X. 509-Zertifikat Speicher angibt. Der Standardwert ist "LocalMachine". Optional.|  
|x509FindType|Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> -Wert, der den Typ der auszuführenden Suche angibt. Der Standardwert ist "findbysubjeterkennbare shedname". Optional.|  
|findValue|Der Wert, nach dem im X.509-Zertifikatspeicher gesucht werden soll. Optional.|  
|isChainIncluded|Gibt an, ob die Überprüfung mithilfe der Zertifikat Kette durchgeführt werden soll. Der Standardwert ist "true". die Überprüfung erfolgt mithilfe der Zertifikat Kette. Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<certificateReference>` -Element gibt Einstellungen an, die verwendet werden, um ein X. 509-Zertifikat in einem Zertifikat Speicher zu suchen und zu überprüfen. Wenn es als untergeordnetes Element des `<serviceCertificate>` -Elements angegeben ist, gibt es den Speicherort und die Überprüfungs Einstellungen des X. 509-Zertifikats an, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird. Das `<certificateReference>` -Element wird durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> -Klasse dargestellt.
