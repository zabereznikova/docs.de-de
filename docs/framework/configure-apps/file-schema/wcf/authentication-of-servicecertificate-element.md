---
title: '&lt;authentication&gt; des &lt;serviceCertificate&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 967ab391c9a6dfe7da9b6ef0542b052872b21f52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661125"
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a>&lt;authentication&gt; des &lt;serviceCertificate&gt;-Elements
Gibt die vom Clientproxy zum Authentifizieren von Dienstzertifikaten verwendeten Einstellungen an, die mittels SSL/TLS-Verhandlung abgerufen werden.  
  
 \<system.ServiceModel>  
\<behaviors>  
EndpointBehaviors-Abschnitt  
\<behavior>  
\<clientCredentials>  
\<serviceCertificate>  
\<authentication>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<authentication customCertificateValidatorType="String"
                certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="LocalMachine/CurrentUser" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|customCertificateValidatorType|Zeichenfolge. Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.|  
|certificateValidationMode|Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an. Ist dies auf `Custom` festgelegt, muss außerdem ein customCertificateValidator zur Verfügung gestellt werden. Die Standardeinstellung ist `ChainTrust`.|  
|revocationMode|Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate. Die Standardeinstellung ist `Online`.|  
|trustedStoreLocation|Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`. Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird. Validierung wird ausgeführt, für die **vertrauenswürdige Personen** am angegebenen Speicherort zu speichern. Die Standardeinstellung ist `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>customCertificateValidator-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Zeichenfolge|Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>revocationMode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: NoCheck, Online, Offline.<br /><br /> Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: LocalMachine oder CurrentUser. Der Standardwert ist CurrentUser. Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in LocalMachine. Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in CurrentUser.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.|  
  
## <a name="remarks"></a>Hinweise  
 Mit dem `certificateValidationMode`-Attribut dieses Konfigurationselements wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden. Standardmäßig wird die Ebene `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet. Dies ist der sicherste Modus. Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`. Sie können den Wert auch auf `Custom` oder `None` festlegen. Wenn Sie den `Custom`-Wert verwenden möchten, müssen Sie auch das `customCertificateValidator`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden. Wenn Sie eine eigene benutzerdefinierte Validierung erstellen möchten, müssen Sie von der abstrakten X509CertificateValidator-Klasse erben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Das `revocationMode`-Attribut gibt an, wie Zertifikate auf eine Sperre hin überprüft werden. Der Standardwert ist `online`, wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden. Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel werden zwei Aufgaben ausgeführt. Es gibt zunächst ein Dienstzertifikat für den Client zu verwenden, wenn die Kommunikation mit Endpunkten, deren Domänenname `www.contoso.com` über das HTTP-Protokoll. Danach gibt es den Sperrmodus und den Speicherort für die Authentifizierung an.  
  
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
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes Zertifikatvalidierungssteuerelement verwendet](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)
- [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
