---
title: <authentication>of- <serviceCertificate> Element
ms.date: 03/30/2017
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
ms.openlocfilehash: 29170f032469b4d55b50f57ca06ce403a5aeaf2c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398230"
---
# <a name="authentication-of-servicecertificate-element"></a>\<authentication>of- \<serviceCertificate> Element
Gibt die vom Clientproxy zum Authentifizieren von Dienstzertifikaten verwendeten Einstellungen an, die mittels SSL/TLS-Verhandlung abgerufen werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<authentication>**  
  
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
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|customCertificateValidatorType|Eine Zeichenfolge. Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden.|  
|certificateValidationMode|Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an. Ist dies auf `Custom` festgelegt, muss außerdem ein customCertificateValidator zur Verfügung gestellt werden. Der Standardwert lautet `ChainTrust`.|  
|revocationMode|Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate. Der Standardwert lautet `Online`.|  
|trustedStoreLocation|Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`. Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird. Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt. Der Standardwert lautet `CurrentUser`.|  
  
## <a name="customcertificatevalidator-attribute"></a>customCertificateValidator-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|String|Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>revocationMode-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: NoCheck, Online, Offline.<br /><br /> Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: LocalMachine oder CurrentUser. Der Standardwert lautet „CurrentUser“. Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in LocalMachine. Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in CurrentUser.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|Gibt ein Zertifikat an, das Sie zum Authentifizieren eines Diensts für den Client verwenden können.|  
  
## <a name="remarks"></a>Bemerkungen  
 Mit dem `certificateValidationMode`-Attribut dieses Konfigurationselements wird die Ebene der Vertrauenswürdigkeit angegeben, mit der Zertifikate authentifiziert werden. Standardmäßig wird die Ebene `ChainTrust` verwendet, die angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie zu finden sein muss, die in eine vertrauenswürdige Zertifizierungsstelle am Anfang der Kette mündet. Dies ist der sicherste Modus. Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`. Sie können den Wert auch auf `Custom` oder `None` festlegen. Wenn Sie den `Custom`-Wert verwenden möchten, müssen Sie auch das `customCertificateValidator`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden. Wenn Sie eine eigene benutzerdefinierte Validierung erstellen möchten, müssen Sie von der abstrakten X509CertificateValidator-Klasse erben. Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Dienstanbieter, der ein benutzerdefiniertes zertifikatvalidator verwendet](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
 Das `revocationMode`-Attribut gibt an, wie Zertifikate auf eine Sperre hin überprüft werden. Der Standardwert ist `online`, wodurch angegeben wird, dass Zertifikate automatisch auf eine Sperre hin überprüft werden. Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel werden zwei Aufgaben ausgeführt. Zuerst wird ein Dienst Zertifikat angegeben, das der Client bei der Kommunikation mit Endpunkten, deren Domänen Name sich über dem HTTP-Protokoll befindet, verwendet werden soll `www.contoso.com` . Danach gibt es den Sperrmodus und den Speicherort für die Authentifizierung an.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>
- <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>
- [Sicherheitsverhalten](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Verwenden von Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [Sichern von Clients](../../../wcf/securing-clients.md)
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
