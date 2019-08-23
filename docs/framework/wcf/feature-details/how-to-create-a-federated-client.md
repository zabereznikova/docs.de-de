---
title: 'Vorgehensweise: Erstellen eines Verbundclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 56ece47e-98bf-4346-b92b-fda1fc3b4d9c
ms.openlocfilehash: 988fc79f71b670f5eaed1a305f54cc90374e4b17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69950625"
---
# <a name="how-to-create-a-federated-client"></a>Vorgehensweise: Erstellen eines Verbundclients
In Windows Communication Foundation (WCF) besteht das Erstellen eines Clients für einen *Verbund Dienst* aus drei Hauptschritten:  
  
1. Konfigurieren Sie eine [ \<WSFederationHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) oder eine ähnliche benutzerdefinierte Bindung. Weitere Informationen zum Erstellen einer entsprechenden Bindung finden [Sie unter Gewusst wie: Erstellen Sie eine WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md). Alternativ können Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) für den Metadatenendpunkt des Verbund Diensts ausführen, um eine Konfigurationsdatei für die Kommunikation mit dem Verbund Dienst und einem oder mehreren Sicherheitstokendiensten zu generieren.  
  
2. Legen Sie die Eigenschaften der <xref:System.ServiceModel.Security.IssuedTokenClientCredential>-Instanz fest, die verschiedene Aspekte der Interaktion des Clients mit einem Sicherheitstokendienst steuert.  
  
3. Legen Sie die Eigenschaften der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>-Instanz fest, die Zertifikate zulässt, welche für die sichere Kommunikation mit gegebenen Endpunkten, z.&#160;B. Sicherheitstokendienste, erforderlich sind.  
  
> [!NOTE]
> Es kann eine <xref:System.Security.Cryptography.CryptographicException> ausgelöst werden, wenn ein Client die Anmeldeinformationen eines anderen Benutzers, dessen Identität er angenommen hat, die <xref:System.ServiceModel.WSFederationHttpBinding>-Bindung oder ein benutzerdefiniert ausgestelltes Token und asymmetrische Schlüssel verwendet. Asymmetrische Schlüssel werden in Verbindung mit der <xref:System.ServiceModel.WSFederationHttpBinding>-Bindung und benutzerdefiniert ausgestellten Token verwendet, wenn die <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuedKeyType%2A>-Eigenschaft bzw. die <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A>-Eigenschaft auf <xref:System.IdentityModel.Tokens.SecurityKeyType.AsymmetricKey> festgelegt ist. Die <xref:System.Security.Cryptography.CryptographicException>-Ausnahme wird ausgelöst, wenn der Client versucht, eine Nachricht zu senden, und kein Benutzerprofil für die Identität vorhanden ist, die der Client angenommen hat. Um dieses Problem zu minimieren, melden Sie sich am Clientcomputer an, oder rufen Sie `LoadUserProfile` vor dem Senden der Nachricht auf.  
  
 Dieses Thema enthält detaillierte Informationen zu diesen Verfahren. Weitere Informationen zum Erstellen einer entsprechenden Bindung finden [Sie unter Gewusst wie: Erstellen Sie eine WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md). Weitere Informationen über die Funktionsweise eines Verbund Dienstanbieter finden Sie unter [Federation](../../../../docs/framework/wcf/feature-details/federation.md).  
  
### <a name="to-generate-and-examine-the-configuration-for-a-federated-service"></a>So generieren und untersuchen Sie die Konfiguration für einen Verbunddienst  
  
1. Führen Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) mit der Adresse der Metadaten-URL des Dienstanbieter als Befehlszeilenparameter aus.  
  
2. Öffnen Sie die generierte Konfigurationsdatei in einem geeigneten Editor.  
  
3. Überprüfen Sie die Attribute und den Inhalt der generierten [ \<Aussteller >](../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md) und [ \<issuerMetadata >](../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md) Elemente. Diese befinden sich in den [ \<Sicherheits >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) Elementen für die [ \<WSFederationHttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) oder benutzerdefinierte Bindungs Elemente. Stellen Sie sicher, dass die Adressen die erwarteten Domänenamen oder andere Adressinformationen enthalten. Sie müssen diese Informationen unbedingt überprüfen, weil sich der Client gegenüber diesen Adressen authentifiziert und Informationen wie Benutzername-/Kennwort-Paare offen legt. Wenn es sich bei der Adresse nicht um die erwartete Adresse handelt, könnten Informationen für einen anderen als den vorgesehenen Empfänger zugänglich werden.  
  
4. Überprüfen Sie alle zusätzlichen [ \<issuedTokenParameters](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md) -Elemente > Elemente innerhalb`alternativeIssuedTokenParameters`des auskommentierten < > Elements. Wenn mit dem Tool Svcutil.exe eine Konfiguration für einen Verbunddienst generiert wird und der Verbunddienst oder einer der zwischengeschalteten Sicherheitstokendienste keine Ausstelleradresse, sondern eine Metadatenadresse für einen Sicherheitstokendienst angeben, der mehrere Endpunkte verfügbar macht, dann verweist die resultierende Konfigurationsdatei auf den ersten Endpunkt. Weitere Endpunkte sind in der Konfigurationsdatei als auskommentiertes <`alternativeIssuedTokenParameters`> Elemente in der Konfigurationsdatei.  
  
     Bestimmen Sie, ob einer dieser`issuedTokenParameters`< > dem bereits in der Konfiguration vorhandenen Wert vorzuziehen ist. Beispielsweise kann es sein, dass der Client die Authentifizierung bei einem Sicherheitstokendienst mithilfe eines Windows CardSpace-Tokens anstelle eines Benutzernamen-/Kennwort-Paars bevorzugt.  
  
    > [!NOTE]
    > Wenn mehrere Sicherheitstokendienste durchlaufen werden müssen, bevor mit dem Dienst kommuniziert wird, ist es möglich, dass ein zwischengelagerter Sicherheitstokendienst den Client an einen falschen Sicherheitstokendienst weiterleitet. Stellen Sie daher sicher, dass der Endpunkt für den Sicherheitstokendienst im [ \<issuedTokenParameters->](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md) der erwartete Sicherheitstokendienst und kein Unbekannter Sicherheitstokendienst ist.  
  
### <a name="to-configure-an-issuedtokenclientcredential-in-code"></a>So konfigurieren Sie IssuedTokenClientCredential im Code  
  
1. Greifen Sie auf die <xref:System.ServiceModel.Security.IssuedTokenClientCredential> zu und zwar über die <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>-Eigenschaft der <xref:System.ServiceModel.Description.ClientCredentials>-Klasse (die von der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse oder über die <xref:System.ServiceModel.ChannelFactory>-Klasse zurückgegeben wird), wie im folgenden Beispielcode gezeigt.  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
2. Falls die Token nicht zwischengespeichert werden müssen, legen Sie die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A>-Eigenschaft auf `false` fest. Die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.CacheIssuedTokens%2A>-Eigenschaft steuert, ob solche Token von einem Sicherheitstokendienst zwischengespeichert werden. Wenn diese Eigenschaft auf `false` festgelegt wird, fordert der Client, sobald er sich gegenüber dem Verbunddienst authentifizieren muss, auch dann ein neues Token vom Sicherheitstokendienst an, wenn ein vorheriges Token noch gültig ist. Wenn diese Eigenschaft auf `true` festgelegt wird, verwendet der Client ein vorhandenes Token erneut, sobald er sich gegenüber dem Verbunddienst authentifizieren muss (solange das Token nicht ungültig geworden ist). Die Standardeinstellung ist `true`.  
  
3. Wenn ein Zeitlimit für zwischengespeicherte Token erforderlich ist, legen Sie die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.MaxIssuedTokenCachingTime%2A>-Eigenschaft auf einen <xref:System.TimeSpan>-Wert fest. Die Eigenschaft gibt an, wie lange ein Token zwischengespeichert werden kann. Nachdem die angegebene Zeitspanne verstrichen ist, wird das Token aus dem Clientcache entfernt. Standardmäßig werden Token unendlich lange zwischengespeichert. Im folgenden Beispiel wird die Zeitspanne auf 10 Minuten eingestellt.  
  
     [!code-csharp[c_CreateSTS#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#15)]
     [!code-vb[c_CreateSTS#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#15)]  
  
4. Optional. Legen Sie die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A>-Eigenschaft auf einen Prozentwert fest. Der Standardwert lautet&#160;60 (Prozent). Die Eigenschaft gibt einen Prozentwert der Gültigkeitsdauer des Tokens an. Wenn das ausgestellte Token beispielsweise 10 Stunden lang gültig ist und <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuedTokenRenewalThresholdPercentage%2A> auf 80 festgelegt wird, dann wird das Token nach acht Stunden erneuert. Im folgenden Beispiel wird als Wert 80 Prozent festgelegt.  
  
     [!code-csharp[c_CreateSTS#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#16)]
     [!code-vb[c_CreateSTS#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#16)]  
  
     Das Erneuerungsintervall, das durch die Gültigkeitsdauer des Tokens und den `IssuedTokenRenewalThresholdPercentage`-Wert bestimmt wird, wird durch den `MaxIssuedTokenCachingTime`-Wert außer Kraft gesetzt, wenn die Zwischenspeicherungsdauer kürzer als die durch den Erneuerungsschwellenwert festgelegte Zeitspanne ist. Wenn beispielsweise das Produkt aus `IssuedTokenRenewalThresholdPercentage` und der Gültigkeitsdauer des Tokens acht Stunden beträgt und der `MaxIssuedTokenCachingTime`-Wert gleich 10 Minuten ist, dann fordert der Client alle 10 Minuten vom Sicherheitstokendienst ein aktualisiertes Token an.  
  
5. Wenn ein anderer Schlüsselentropiemodus als <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy> für eine Bindung erforderlich ist, bei der nicht Nachrichtensicherheit oder Transportsicherheit mit Nachrichtenanmeldeinformationen verwendet wird (beispielsweise eine Bindung, die über kein <xref:System.ServiceModel.Channels.SecurityBindingElement> verfügt), legen Sie die <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A>-Eigenschaft auf einen geeigneten Wert fest. Der *Entropie* Modus bestimmt, ob symmetrische Schlüssel mithilfe der <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> -Eigenschaft gesteuert werden können. Diese Standardeinstellung lautet <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.CombinedEntropy>, wobei sowohl der Client als auch der Tokenaussteller Daten bereitstellen, durch deren Kombination der tatsächliche Schlüssel erzeugt wird. Andere Werte lauten <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ClientEntropy> und <xref:System.ServiceModel.Security.SecurityKeyEntropyMode.ServerEntropy>, womit festgelegt wird, dass der gesamte Schlüssel vom Client bzw. vom Server angegeben wird. Im folgenden Beispiel wird die Eigenschaft so festgelegt, dass nur die Serverdaten für den Schlüssel verwendet werden.  
  
     [!code-csharp[c_CreateSTS#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#17)]
     [!code-vb[c_CreateSTS#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#17)]  
  
    > [!NOTE]
    > Wenn in einem Sicherheitstokendienst oder einer Dienstbindung ein <xref:System.ServiceModel.Channels.SecurityBindingElement> vorhanden ist, wird der auf <xref:System.ServiceModel.Security.IssuedTokenClientCredential.DefaultKeyEntropyMode%2A> festgelegte <xref:System.ServiceModel.Security.IssuedTokenClientCredential> durch die <xref:System.ServiceModel.Channels.SecurityBindingElement.KeyEntropyMode%2A>-Eigenschaft von `SecurityBindingElement` überschrieben.  
  
6. Konfigurieren Sie ausstellerspezifische Endpunktverhalten, indem Sie diese Verhalten der Auflistung hinzufügen, die von der <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>-Eigenschaft zurückgegeben wird.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-issuedtokenclientcredential-in-configuration"></a>So konfigurieren Sie IssuedTokenClientCredential in der Konfiguration  
  
1. Erstellen Sie ein [ \<IssuedToken->](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) -Element als unter [ \<geordnetes Element des IssuedToken->](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) -Elements in einem Endpunkt Verhalten.  
  
2. Wenn das Zwischenspeichern von Token nicht erforderlich ist `cacheIssuedTokens` , legen Sie das-`issuedToken`Attribut (des < `false`>-Element) auf fest.  
  
3. Wenn ein Zeitlimit für zwischengespeicherte Token erforderlich ist, legen `maxIssuedTokenCachingTime` Sie das-Attribut`issuedToken`für das < >-Element auf einen geeigneten Wert fest. Beispiel:  
    `<issuedToken maxIssuedTokenCachingTime='00:10:00' />`  
  
4. Wenn ein anderer Wert als der Standardwert bevorzugt wird, legen `issuedTokenRenewalThresholdPercentage` Sie das-Attribut`issuedToken`für das < >-Element auf einen geeigneten Wert fest, z. b.:  
  
    ```xml  
    <issuedToken issuedTokenRenewalThresholdPercentage = "80" />  
    ```  
  
5. Wenn ein anderer Schlüsselentropiemodus als `CombinedEntropy` für eine Bindung erforderlich ist, bei der nicht Nachrichtensicherheit oder Transportsicherheit mit Nachrichtenanmeldeinformationen verwendet wird (beispielsweise eine Bindung, die über kein `SecurityBindingElement` verfügt), dann legen Sie das `defaultKeyEntropyMode`-Attribut für das `<issuedToken>`ServerEntropy-Element je nach Bedarf auf`ServerEntropy`oder`ClientEntropy` fest.  
  
    ```xml  
    <issuedToken defaultKeyEntropyMode = "ServerEntropy" />  
    ```  
  
6. Optional. Konfigurieren Sie jedes Aussteller spezifische benutzerdefinierte Endpunkt Verhalten, indem Sie`issuerChannelBehaviors`ein < >-Element als untergeordnetes`issuedToken`Element des < > Elements erstellen. Erstellen Sie für jedes Verhalten ein <`add`>-Element als untergeordnetes Element des`issuerChannelBehaviors`< > Elements. Geben Sie die Aussteller Adresse des Verhaltens an, indem `issuerAddress` Sie das-Attribut`add`für das < >-Element festlegen. Geben Sie das Verhalten selbst an, `behaviorConfiguration` indem Sie das-`add`Attribut für das < >-Element festlegen.  
  
    ```xml  
    <issuerChannelBehaviors>  
    <add issuerAddress="http://fabrikam.org/sts" behaviorConfiguration="FabrikamSTS" />  
    </issuerChannelBehaviors>  
    ```  
  
### <a name="to-configure-an-x509certificaterecipientclientcredential-in-code"></a>So konfigurieren Sie X509CertificateRecipientClientCredential im Code  
  
1. Greifen Sie über die <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>-Eigenschaft der <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Klasse oder die <xref:System.ServiceModel.ClientBase%601>-Eigenschaft auf <xref:System.ServiceModel.ChannelFactory> zu.  
  
     [!code-csharp[c_CreateSTS#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#18)]
     [!code-vb[c_CreateSTS#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#18)]  
  
2. Wenn eine <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Instanz für das Zertifikat eines gegebenen Endpunkts verfügbar ist, verwenden Sie die <xref:System.Collections.Generic.ICollection%601.Add%2A>-Methode der Auflistung, die von der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>-Eigenschaft zurückgegeben wird.  
  
     [!code-csharp[c_CreateSTS#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#19)]
     [!code-vb[c_CreateSTS#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#19)]  
  
3. Wenn keine <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Instanz verfügbar ist, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>-Klasse, wie im folgenden Beispiel gezeigt.  
  
     [!code-csharp[c_CreateSTS#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#20)]
     [!code-vb[c_CreateSTS#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#20)]  
  
### <a name="to-configure-an-x509certificaterecipientclientcredential-in-configuration"></a>So konfigurieren Sie X509CertificateRecipientClientCredential in der Konfiguration  
  
1. Erstellen Sie ein [ \<scopedzertifikate >](../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md) -Element als unter [ \<geordnetes Element des serviceCertificate->](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) Elements, das selbst ein untergeordnetes Element des [ \<Clientanmelde->](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) -Elements in einem Endpunkt Verhalten ist.  
  
2. Erstellen Sie ein `<add>`-Element als untergeordnetes Element des `<scopedCertificates>`-Elements. Geben Sie Werte für die Attribute `storeLocation`, `storeName`, `x509FindType` und `findValue` an, um auf das geeignete Zertifikat zu verweisen. Legen Sie das `targetUri`-Attribut auf einen Wert fest, der die Adresse des Endpunkts angibt, für den das Zertifikat verwendet werden soll. Dies wird im folgenden Beispiel gezeigt.  
  
    ```xml  
    <scopedCertificates>  
     <add targetUri="http://fabrikam.com/sts"   
          storeLocation="CurrentUser"  
          storeName="TrustedPeople"  
          x509FindType="FindBySubjectName"  
          findValue="FabrikamSTS" />  
    </scopedCertificates>  
    ```  
  
## <a name="example"></a>Beispiel  
 Im nächsten Codebeispiel wird eine Instanz der <xref:System.ServiceModel.Security.IssuedTokenClientCredential>-Klasse im Code konfiguriert.  
  
 [!code-csharp[c_FederatedClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_federatedclient/cs/source.cs#2)]
 [!code-vb[c_FederatedClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_federatedclient/vb/source.vb#2)]  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Um einer möglichen Enthüllung von Informationen vorzubeugen, sollten Clients, die mit dem Tool Svcutil.exe Metadaten von Verbundendpunkten verarbeiten, sicherstellen, dass es sich bei den resultierenden Sicherheitstokendienst-Adressen auch tatsächlich um die erwarteten Adressen handelt. Dies ist insbesondere wichtig, wenn ein Sicherheitstokendienst mehrere Endpunkte verfügbar macht, weil das Tool Svcutil.exe die Konfigurationsdatei generiert, die mit einem solchen Endpunkt verwendet werden soll. Sie müssen überprüfen, ob die Konfigurationsdatei für den richtigen Endpunkt erzeugt wurde.  
  
## <a name="localissuer-required"></a>LocalIssuer erforderlich  
 Wenn erwartet wird, dass Clients immer einen lokalen Aussteller verwenden, ist Folgendes zu beachten: Die Standardausgabe von Svcutil.exe resultiert darin, dass der lokale Aussteller nicht verwendet wird, wenn der vorletzte Sicherheitstokendienst in der Kette eine Ausstelleradresse oder eine Ausstellermetaadresse angibt.  
  
 Weitere Informationen zum <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A>Festlegen der Eigenschaften, <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A>und der <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> <xref:System.ServiceModel.Security.IssuedTokenClientCredential> -Klasse finden [Sie unter Gewusst wie: Konfigurieren Sie einen lokalen](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)Aussteller.  
  
## <a name="scoped-certificates"></a>Zertifikate mit Gültigkeitsbereich  
 Wenn zur Kommunikation mit einem Sicherheitstokendienst Dienstzertifikate angegeben werden müssen, weil keine Zertifikatsaushandlung verwendet wird, können diese mit der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>-Eigenschaft der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>-Klasse angegeben werden. Die <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetDefaultCertificate%2A>-Methode akzeptiert die beiden Parameter <xref:System.Uri> und <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>. Das angegebene Zertifikat wird zur Kommunikation mit Endpunkten beim angegebenen URI verwendet. Stattdessen können Sie auch mit der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.SetScopedCertificate%2A>-Methode ein Zertifikat der Auflistung hinzufügen, die von der <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>-Eigenschaft zurückgegeben wird.  
  
> [!NOTE]
> Das Clientkonzept von Zertifikaten, deren Bereich durch einen gegebenen URI festgelegt wird, gilt nur für Anwendungen, die ausgehende Aufrufe an Dienste durchführen, die bei diesen URIs Endpunkte verfügbar machen. Es gilt nicht für Zertifikate, die zum Signieren von <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A> <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> ausgestellten Token verwendet werden, wie z. b. die auf dem Server in der vom-Klasse zurückgegebenen Auflistung konfigurierten. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren Sie die Anmelde Informationen](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)für einen Verbunddienst.  
  
## <a name="see-also"></a>Siehe auch

- [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md)
- [Vorgehensweise: Deaktivieren von sicheren Sitzungen für eine WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Vorgehensweise: Erstellen einer WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Vorgehensweise: Konfigurieren von Anmelde Informationen für eine Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Vorgehensweise: Konfigurieren eines lokalen Ausstellers](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [Sicherheitsüberlegungen für Metadaten](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)
- [Vorgehensweise: Sichere Metadatenendpunkte](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md)
