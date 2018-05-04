---
title: '&lt;serviceCertificate&gt; von &lt;clientCredentials&gt;-Element'
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 1d54c39fd681e0686e419b7b73243703e9184d1f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicecertificategt-of-ltclientcredentialsgt-element"></a>&lt;serviceCertificate&gt; von &lt;clientCredentials&gt;-Element
Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<Verhalten >  
\<clientCredentials>  
\<ServiceCertificate >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceCertificate />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DefaultCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|Gibt ein X.509-Zertifikat an, das verwendet wird, wenn ein Dienst oder STS kein Zertifikat über ein Aushandlungsprotokoll bereitstellt.|  
|[\<ScopedCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Stellt eine Auflistung von X.509-Zertifikaten dar, die von bestimmten Diensten (mit Gültigkeitsbereich) zur Authentifizierung bereitgestellt werden. Diese Auflistung wird normalerweise verwendet, um die Dienstzertifikate für Sicherheitstokendienste in einem Verbundsszenario anzugeben.|  
|[\<Authentifizierung >](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|Gibt die Authentifizierungsverhalten für Dienstzertifikate an, die von einem Client verwendet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement gibt die Einstellungen an, anhand derer der Client das während der SSL-Authentifizierung vom Dienst bereitgestellte Zertifikat überprüft. Enthält außerdem Zertifikate für den Dienst, die explizit auf dem Client für die Verschlüsselung von Nachrichten unter Verwendung der Nachrichtensicherheit konfiguriert sind.  
  
 Die Attribute der `serviceCertificate` Elements sind identisch zu den Attributen eines der [ \<ClientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
