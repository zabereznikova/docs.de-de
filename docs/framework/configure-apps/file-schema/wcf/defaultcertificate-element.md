---
title: <defaultCertificate>-Element
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: 93410e815a156f91db1962f05fb1aa6baca7f955
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919252"
---
# <a name="defaultcertificate-element"></a>\<defaultCertificate-> Element
Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.  
  
 \<system.ServiceModel>  
\<behaviors>  
endpointverhaltenbereich  
\<behavior>  
\<clientCredentials>  
\<serviceCertificate>  
\<defaultCertificate>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|findValue|Zeichenfolge. Der zu suchende Wert.|  
|x509FindType|Enumeration. Eines der zu durchsuchenden Zertifikatfelder.|  
|storeLocation|Enumeration. Einer der zwei zu durchsuchenden Systemspeicherorte.|  
|storeName|Enumeration. Einer der zu durchsuchenden Systemspeicher.|  
  
## <a name="findvalue-attribute"></a>findValue-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Zeichenfolge|Der Wert ist vom zu durchsuchenden Feld (das durch das X509FindType-Attribut angegeben wird) abhängig. Wenn Sie beispielsweise nach einem Fingerabdruck suchen, muss der Wert eine Zeichenfolge aus hexadezimalen Zahlen sein.|  
  
## <a name="x509findtype-attribute"></a>x509FindType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Mögliche Werte: FindByThumbprint, findbysubjetname, findbysubjetissushedname, FindByIssuerName, findbyissuererkennbar shedname, findbyserialnumber, FindByTimeValid, FindByTimeNotYetValid, findbyserialnumber, findbytimeabgelauf, findbytemplatename , Findbyapplicationpolicy, findbycertificatepolicy, findbyextension, findbykeyusage, findbysubjetkeyidentifier.|  
  
## <a name="storelocation-attribute"></a>storeLocation-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|CurrentUser oder LocalMachine.|  
  
## <a name="storename-attribute"></a>storeName-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Mögliche Werte: Addressbook, AuthRoot, CertificateAuthority, unallowed, my, root, treuhändpeople und Treuhänder Publisher.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.|  
  
## <a name="remarks"></a>Hinweise  
 Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird das durch dieses Konfigurationselement angegebene Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet. Es speichert ein einzelnes Zertifikat, das verwendent werden soll, wenn kein Zertifikat von einem Dienst angegeben wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel gibt ein Zertifikat an, das für Endpunkte verwendet wird, `http://www.contoso.com` deren URI mit beginnt, und ein Zertifikat, das für alle anderen Endpunkte verwendet werden soll, die keine Zertifikats Aushandlung ausführen.  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Sichern von Clients](../../../wcf/securing-clients.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
