---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a1b3f5f7e8eea555be10870bc00f9b975c57a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientcredentialsgt"></a>&lt;clientCredentials&gt;
Gibt die zum Authentifizieren des Clients an einem Dienst verwendeten Anmeldeinformationen an.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<ClientCredentials >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<clientCredentials type="String"  
      supportInteractive="Boolean" >  
   <clientCertificate>  
   </clientCertificate>  
   <digest>  
   </digest>  
   <isuedToken>  
   </isuedToken>  
   <peer>  
   </peer>  
   <serviceCertificate>  
   </serviceCertificate>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</clientCredentials>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`supportInteractive`|Ein boolescher Wert, der angibt, ob ein interaktiver Benutzer in die Auswahl von Clientanmeldeinformationen zur Laufzeit einbezogen werden kann. Der Standardwert ist `true`.|  
|`type`|Eine Zeichenfolge, die den Typ dieses Konfigurationselements angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|Gibt das zum Authentifizieren des Clients am Dienst verwendete Zertifikat an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.|  
|[\<HttpDigest >](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|Gibt einen zum Authentifizieren des Clients am Dienst verwendeten Hashwert an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.|  
|[\<IssuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Gibt einen zum Authentifizieren des Clients an einem Secure Token Service (STS) verwendeten benutzerdefinierten Tokentyp an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.|  
|[\<Peer >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Gibt die aktuellen Peeranmeldeinformationen an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<ServiceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Gibt das zum Authentifizieren des Diensts am Client verwendete Zertifikat an und liefert eine Struktur zum Festlegen der Zertifikatsoptionen. Dieses Zertifikat muss dem Client out-of-band vom Dienst zur Verfügung gestellt werden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.|  
|[\<Windows >](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|Gibt Windows-Anmeldeinformationen an. Der Standardwert sind die Anmeldeinformationen des aktuellen Threads. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.WindowsClientElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="remarks"></a>Hinweise  
 Durch die Clientanmeldeinformationen wird der Client bei den Diensten authentifiziert, wenn eine gegenseitige Authentifizierung erforderlich ist. Dieser Konfigurationsabschnitt kann auch zur Angabe von Dienstzertifikaten in Szenarien verwendet werden, bei denen der Client seine Nachrichten an einen Dienst mithilfe des Dienstzertifikats schützen muss.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)
