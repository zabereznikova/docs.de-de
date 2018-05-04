---
title: '&lt;scopedCertificates&gt;-Element'
ms.date: 03/30/2017
ms.assetid: c7b6fc35-d4b2-4c18-98bd-83e09591f1d3
ms.openlocfilehash: d95e608fa9b94086dac72341eb599f258dae6097
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltscopedcertificatesgt-element"></a>&lt;scopedCertificates&gt;-Element
Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden. Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.  
  
 \<system.ServiceModel>  
\<behaviors>  
EndpointBehaviors-Abschnitt  
\<Verhalten >  
\<clientCredentials>  
\<ServiceCertificate >  
\<ScopedCertificates >-Element  
\<Hinzufügen >-Element für \<ScopedCertificates >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<scopedCertificates>  
      <add findValue="String"  
                storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                targetUri="string"  
            x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />   
</scopedCertificates>   
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)|Fügt ein X.509-Zertifikat zur Auflistung der Zertifikate mit Gültigkeitsbereich hinzu.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ServiceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)|Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Auflistung ermöglicht dem Client, die zu verwendenden Dienstzertifikate basierend auf der URL des Diensts, mit dem er kommuniziert, zu konfigurieren. Dies ist vor allem hilfreich bei Szenarien mit ausgestellten Token, in denen ein Client mit verschiedenen Diensten kommuniziert (dem Endservice und den zwischengeschalteten Sicherheitstokendiensten). Bei Bindungen mit Zertifikat-basierter Nachrichtensicherheit wird dieses Zertifikat zum Verschlüsseln von Nachrichten für den Dienst sowie für die Signierung von Antworten an den Client verwendet.  
  
 Wenn eine Bindung ein Zertifikat für den Dienst erfordert und kein bestimmtes Zertifikat für die Dienst-URL in ScopedCertificates gefunden wird, wird das Standardzertifikat verwendet.  
  
 Weitere Informationen finden Sie im Abschnitt "Zertifikate im Bereich" [Vorgehensweise: Erstellen eines Clients Federated](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Dienstzertifikat für den Client zu verwenden, wenn bei der Kommunikation mit Endpunkten, deren Domänenname http://www.contoso.com über das HTTP-Protokoll.  
  
```xml  
<serviceCertificate>  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
</serviceCertificate>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopedcertificates-element.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
