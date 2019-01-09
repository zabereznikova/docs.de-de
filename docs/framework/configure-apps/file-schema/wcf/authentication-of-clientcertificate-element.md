---
title: '&lt;authentication&gt;-Element des &lt;clientCertificate&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
ms.openlocfilehash: 97c742cbcaeba10bc7fcf88a461360b96beebc22
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147108"
---
# <a name="ltauthenticationgt-of-ltclientcertificategt-element"></a>&lt;authentication&gt;-Element des &lt;clientCertificate&gt;-Elements
Gibt die Authentifizierungsverhalten für Clientzertifikate an, die von einem Dienst verwendet werden.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<Verhalten >  
\<serviceCredentials>  
\<ClientCertificate >  
\<Authentifizierung >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<authentication customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                includeWindowsGroups="Boolean"
                mapClientCertificateToWindowsAccount="Boolean"
                revocationMode="NoCheck/Online/Offline"
                trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|customCertificateValidatorType|Optionale Zeichenfolge. Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden. Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.|  
|certificateValidationMode|Optionale Enumeration. Gibt einen der für die Prüfung von Anmeldeinformationen verwendeten Modi an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.X509CertificateValidationMode>. Wenn dies auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType> festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden. Die Standardeinstellung ist <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.|  
|includeWindowsGroups|Optionaler boolescher Wert. Gibt an, ob Windows-Gruppen im Sicherheitskontext enthalten sind. Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird. Legen Sie dieses Attribut auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht angeben müssen.|  
|mapClientCertificateToWindowsAcccount|Boolesch. Gibt an, ob der Client mithilfe des Zertifikats einer Windows-Identität zugeordnet werden kann. Active Directory muss dafür aktiviert sein.|  
|revocationMode|Optionale Enumeration. Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate. Die Standardeinstellung ist `Online`. Dieser Wert wird ignoriert, wenn HTTP-Transportsicherheit verwendet wird.|  
|trustedStoreLocation|Optionale Enumeration. Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`. Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird. Validierung wird ausgeführt, für die **vertrauenswürdige Personen** am angegebenen Speicherort zu speichern. Die Standardeinstellung ist `CurrentUser`.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>customCertificateValidatorType-Attribut  
  
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
|Enumeration|Einer der folgenden Werte: NoCheck, Online, Offline. Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`. Die Standardeinstellung ist `CurrentUser`. Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`. Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|Definiert ein X.509-Zertifikat, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<authentication>`-Element entspricht der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse. Mit dem Element können Sie die Art der Clientauthentifizierung anpassen. Sie können als Wert für das `certificateValidationMode`-Attribut `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` oder `Custom` festlegen. In der Standardeinstellung die standardvertrauensebene ist `ChainTrust`, der angibt, dass jedes Zertifikat in einer Zertifizierungshierarchie befinden muss eine *Stammzertifizierungsstelle* am Anfang der Kette. Dies ist der sicherste Modus. Sie können auch den Wert `PeerOrChainTrust` verwenden, der vorgibt, dass neben den Zertifikaten in einer Vertrauenskette auch selbst ausgestellte Zertifikate (Peervertrauen) akzeptiert werden. Sie können diesen Wert beim Entwickeln und Debuggen von Clients und Diensten verwenden, da selbst ausgestellte Zertifikate nicht von einer vertrauenswürdigen Zertifizierungsstelle bezogen werden müssen. Verwenden Sie beim Bereitstellen eines Clients jedoch den Wert `ChainTrust`.  
  
 Sie können den Wert auch auf `Custom` setzen. Wenn Sie den Wert `Custom` verwenden, müssen Sie für das `customCertificateValidatorType`-Attribut zudem ein Assembly und einen Typ, mit dem das Zertifikat überprüft wird, festlegen. Wenn Sie Ihre eigene Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Code gibt ein X.509-Zertifikat und einen benutzerdefinierten Validierungstyp im `<authentication>`-Element an.  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>  
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>  
 [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Vorgehensweise: Erstellen Sie einen Dienst, der ein benutzerdefiniertes Zertifikatvalidierungssteuerelement verwendet](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [Arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
