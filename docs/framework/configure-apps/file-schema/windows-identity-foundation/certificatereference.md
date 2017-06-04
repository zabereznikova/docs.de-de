---
title: "&lt;certificateReference&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateReference&gt;
Gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509\-Zertifikat in einem Zertifikatspeicher.  
  
## Syntax  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName=”AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher”  
        storeLocation=”CurrentUser||LocalMachine”  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|storeName|Der Name des x. 509\-Zertifikatsspeicher.  Der Standardwert ist "My".  Optional.|  
|storeLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> \-Wert, der den Speicherort des x. 509\-Zertifikatsspeichers angibt.  Der Standardwert ist "LocalMachine".  Optional.|  
|x509FindType|Ein <xref:System.Security.Cryptography.X509Certificates.X509FindType> \-Wert, der den Typ der Suche angibt, die ausgeführt werden soll.  Der Standardwert ist "FindBySubjectDistinguishedName".  Optional.|  
|findValue|Der Wert, nach dem im X.509\-Zertifikatsspeicher gesucht werden soll.  Optional.|  
|isChainIncluded|Gibt an, ob die Validierung ausgeführt werden soll, mithilfe der Zertifikatkette.  Der Standardwert ist "true"; Validierung mithilfe der Zertifikatkette.  Optional.|  
  
### Untergeordnete Elemente  
 None  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Konfiguriert das Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token verwendet wird.|  
  
## Hinweise  
 Die `<certificateReference>` Element gibt die Einstellungen, die zum Suchen und überprüfen ein x. 509\-Zertifikat in einem Zertifikatspeicher.  Wenn es als untergeordnetes Element des angegebenen die `<serviceCertficate>` \-Element gibt die Einstellungen für Speicherort und Überprüfung von x. 509\-Zertifikat, das zum Verschlüsseln und Entschlüsseln von Token an.  Die `<certificateReference>` Element dargestellt durch die <xref:System.ServiceModel.Configuration.CertificateReferenceElement> Klasse.