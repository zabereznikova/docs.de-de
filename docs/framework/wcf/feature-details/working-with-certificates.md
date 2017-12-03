---
title: Verwenden von Zertifikaten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: certificates [WCF]
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63f9d22c571a007653fc794dc7638c8221a676aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="working-with-certificates"></a>Verwenden von Zertifikaten
Bei der Programmierung der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Sicherheit werden digitale X.509-Zertifikate häufig zum Authentifizieren von Clients und Servern sowie zum Verschlüsseln und digitalen Signieren von Nachrichten verwendet. Dieses Thema bietet einen Überblick über die Funktionen digitaler X.509-Zertifikate und ihre Verwendung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und enthält Links zu Themen, in denen diese Konzepte näher beschrieben oder die Ausführung allgemeiner Aufgaben mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und Zertifikaten erläutert werden.  
  
 Kurz gesagt, ein digitales Zertifikat ist ein Teil einer *public Key-Infrastruktur* (PKI), dabei handelt es sich um ein System aus digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen, die Überprüfung und Authentifizierung die Gültigkeit beteiligten Parteien in einer elektronischen Transaktion unter Verwendung der Kryptografie mit öffentlichem Schlüssel. Eine Zertifizierungsstelle Zertifikate ausstellt, und jedes Zertifikat enthält einen Satz von Feldern, die Daten, z. B. enthalten *Betreff* (die Entität für die das Zertifikat ausgestellt wird), Gültigkeitsdatum (wenn das Zertifikat gültig ist), Aussteller (die Entität, die das Zertifikat ausgestellt wurde), und einem öffentlichen Schlüssel. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden diese Eigenschaften als <xref:System.IdentityModel.Claims.Claim> verarbeitet, und jeder Anspruch wird weiter in zwei Typen unterteilt: Identität und Recht. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]X. 509-Zertifikaten finden Sie unter [x. 509-Zertifikate für öffentliche Schlüssel](http://go.microsoft.com/fwlink/?LinkId=209952) [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Ansprüchen und Autorisierung in WCF finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]implementieren eine PKI, finden Sie unter [Windows Server 2008 R2 - Zertifikatdienste](http://go.microsoft.com/fwlink/?LinkId=209949).  
  
 Eine zentrale Funktion des Zertifikats ist die Authentifizierung der Identität des Besitzers des Zertifikats gegenüber anderen. Ein Zertifikat enthält die *öffentlichen Schlüssel* des Besitzers, während der Besitzer den privaten Schlüssel behält. Der öffentliche Schlüssel kann zum Verschlüsseln von Nachrichten verwendet werden, die an den Besitzer des Zertifikats gesendet werden. Nur der Besitzer hat Zugriff auf den privaten Schlüssel, sodass niemand anders diese Nachrichten entschlüsseln kann.  
  
 Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter-Zertifikataussteller handelt. Windows-Domänen verfügen über eine Zertifizierungsstelle, von der Zertifikate für Computer in der Domäne ausgestellt werden können.  
  
## <a name="viewing-certificates"></a>Anzeigen von Zertifikaten  
 Bei der Verwendung von Zertifikaten ist es oft erforderlich, die Zertifikate anzuzeigen und ihre Eigenschaften zu überprüfen. Die einfachste Methode dazu ist das MMC (Microsoft Management Console)-Snap-In-Tool. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## <a name="certificate-stores"></a>Zertifikatspeicher  
 Zertifikate werden in Speichern abgelegt. Die zwei Hauptspeicherorte sind in weitere Unterspeicher unterteilt. Administratoren können beide Hauptspeicher mit dem MMC-Snap-In-Tool anzeigen. Alle anderen Benutzer können lediglich den Speicher des aktuellen Benutzers anzeigen.  
  
-   **Im lokalen Computerspeicher**. Dieser enthält die Zertifikate, die von den Prozessen des Computers verwendet werden, z. B. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Speichern Sie die Zertifikate zur Authentifizierung des Servers gegenüber Clients im lokalen Computerspeicher.  
  
-   **Speicher des aktuellen Benutzers**. Interaktive Anwendungen legen Zertifikate für den aktuellen Benutzer des Computers normalerweise im aktuellen Benutzerspeicher ab. Beim Erstellen einer Clientanwendung werden die Zertifikate zur Authentifizierung eines Benutzers gegenüber einem Dienst normalerweise hier abgelegt.  
  
 Diese beiden Speicher teilen sich in weitere Unterspeicher auf. Die wichtigsten Unterspeicher für die Programmierung mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sind folgende:  
  
-   **Vertrauenswürdige Stammzertifizierungsstellen**. Mit den Zertifikaten in diesem Speicher können Sie eine Zertifikatkette erstellen, die zum Zertifikat einer Zertifizierungsstelle in diesem Speicher zurückverfolgt werden kann.  
  
    > [!IMPORTANT]
    >  Der lokale Computer stuft alle Zertifikate in diesem Speicher als implizit vertrauenswürdig ein; dies gilt auch, wenn das Zertifikat im Speicher nicht von einer vertrauenswürdigen Zertifizierungsstelle eines Drittanbieters stammt. Aus diesem Grund sollten Sie in diesem Speicher nur Zertifikate ablegen, wenn Sie dem Aussteller uneingeschränkt vertrauen und sich der möglichen Folgen bewusst sind.  
  
-   **Persönliche**. Dieser Speicher wird für Zertifikate verwendet, die dem Benutzer eines Computers zugeordnet sind. Dieser Speicher wird normalerweise für Zertifikate verwendet, die von einem der Zertifikate der Zertifizierungsstelle im Speicher vertrauenswürdiger Stammzertifizierungsstellen stammen. Darüber hinaus können in diesem Speicher auch selbst ausgestellte Zertifikate abgelegt werden, die von einer Anwendung als vertrauenswürdig eingestuft werden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Zertifikatspeichern, finden Sie unter [Zertifikatspeichern](http://go.microsoft.com/fwlink/?LinkId=88912).  
  
### <a name="selecting-a-store"></a>Auswählen eines Speichers  
 Die Auswahl des Speichers für ein Zertifikat hängt davon ab, wie und wann der Dienst oder Client ausgeführt wird. Dabei gelten folgende allgemeine Regeln:  
  
-   Wenn der WCF-Dienst, in einem Windows-Dienst verwenden gehostet wird das **lokalen** speichern. Sie benötigen Administratorrechte, wenn Sie Zertifikate im lokalen Computerspeicher installieren möchten.  
  
-   Wenn Sie den Dienst oder Client eine Anwendung, die unter einem Benutzerkonto ausgeführt wird ist, verwenden Sie die **Aktueller Benutzer** zu speichern.  
  
### <a name="accessing-stores"></a>Zugreifen auf Speicher  
 Speicher werden analog zu Ordnern auf einem Computer durch Zugriffssteuerungslisten (ACLs) geschützt. Beim Erstellen eines Diensts, der von Internet Information Services (IIS) gehostet wird, wird der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Prozess unter dem [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Konto ausgeführt. Dieses Konto muss über Zugriff auf den Speicher mit den Zertifikaten verfügen, die von einem Dienst verwendet werden. Die zentralen Speicher werden durch eine Standardzugriffssteuerungsliste geschützt, eine Änderung der Listen ist jedoch möglich. Wenn Sie eine separate Rolle für den Speicherzugriff erstellen, muss diese über die entsprechende Zugriffsberechtigung verfügen. Informationen zum Ändern der mit dem Tool WinHttpCertConfig.exe Publication Access List, finden Sie unter [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Clientzertifikate mit IIS verwenden, finden Sie unter [wie einen Webdienst aufgerufen wird, werden mithilfe von Clientzertifikaten für die Authentifizierung in einer ASP.NET-Webanwendung](http://go.microsoft.com/fwlink/?LinkId=88914).  
  
## <a name="chain-trust-and-certificate-authorities"></a>Vertrauensketten und Zertifizierungsstellen  
 Zertifikate werden in einer Hierarchie erstellt, in der jedes einzelne Zertifikat mit der Zertifizierungsstelle verknüpft ist, von der es ausgestellt wurde. Dieser Link verweist auf das Zertifikat der Zertifizierungsstelle. Das Zertifikat der Zertifizierungsstelle wird dann mit der Zertifizierungsstelle verknüpft, von der das ursprüngliche Zertifikat der Zertifizierungsstelle ausgestellt wurde. Dieser Prozess wird wiederholt, bis das Zertifikat der Stammzertifizierungsstelle erreicht wird. Das Zertifikat der Stammzertifizierungsstelle ist grundsätzlich vertrauenswürdig.  
  
 Digitale Zertifikate werden verwendet, um eine Entität zu authentifizieren, durch die Verwendung dieser Hierarchie, die so genannte eine *Vertrauenskette*. Sie können die Kette eines beliebigen Zertifikats, die über das MMC-Snap-in, indem auf das Zertifikat doppelklicken und anschließend auf Anzeigen der **Zertifikatpfad** Registerkarte [!INCLUDE[crabout](../../../../includes/crabout-md.md)] Zertifikatketten für eine Zertifizierungsstelle importiert werden, finden Sie unter [Wie: Angeben der Zertifizierungsstellenzertifikatskette, der zum Überprüfen von Signaturen verwendet](../../../../docs/framework/wcf/feature-details/specify-the-certificate-authority-chain-verify-signatures-wcf.md).  
  
> [!NOTE]
>  Sie können jeden Aussteller zu einer vertrauenswürdigen Stammzertifizierungsstelle machen, indem Sie das Zertifikat des Ausstellers im Zertifikatspeicher der Stammzertifizierungsstelle ablegen.  
  
### <a name="disabling-chain-trust"></a>Deaktivieren von Vertrauensketten  
 Wenn Sie einen neuen Dienst erstellen, verwenden Sie möglicherweise ein Zertifikat, das nicht von einer vertrauenswürdigen Stammzertifizierungsstelle ausgegeben wurde, oder das ausstellende Zertifikat befindet sich nicht im Speicher vertrauenswürdiger Stammzertifizierungsstellen. Sie können die Überprüfung der Kette von Vertrauensstellungen für ein Zertifikat in Entwicklungsumgebungen vorübergehend deaktivieren. Legen Sie dazu die `CertificateValidationMode`-Eigenschaft auf entweder `PeerTrust` oder `PeerOrChainTrust` fest. Durch den jeweiligen Modus wird angegeben, dass das Zertifikat entweder selbst ausgegeben (Peervertrauenszertifikat) oder Teil einer Kette von Vertrauensstellungen ist. Die Eigenschaft kann auf eine der folgenden Klassen festgelegt werden:  
  
|Klasse|Eigenschaft|  
|-----------|--------------|  
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=nameWithType>|  
  
 Sie können die Eigenschaft auch in der Konfiguration festlegen. Folgende Elemente werden verwendet, um den Validierungsmodus anzugeben:  
  
-   [\<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)  
  
-   [\<PeerAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)  
  
-   [\<MessageSenderAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)  
  
## <a name="custom-authentication"></a>Benutzerdefinierte Authentifizierung  
 Die `CertificateValidationMode`-Eigenschaft ermöglicht es auch, die Authentifizierung von Zertifikaten anzupassen. Die Standardvertrauensebene ist `ChainTrust`. Wenn Sie den <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>-Wert verwenden möchten, müssen Sie auch das `CustomCertificateValidatorType`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden. Wenn Sie eine benutzerdefinierte Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben.  
  
 Wenn Sie eine benutzerdefinierte Authentifizierung erstellen, müssen Sie auf jeden Fall die <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>-Methode überschreiben. Ein Beispiel der benutzerdefinierten Authentifizierung finden Sie unter der [x. 509-Zertifikats-Validierungssteuerelement](../../../../docs/framework/wcf/samples/x-509-certificate-validator.md) Beispiel. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md).  
  
## <a name="using-makecertexe-to-build-a-certificate-chain"></a>Verwenden von Makecert.exe zum Erstellen einer Zertifikatkette  
 Mit dem Certificate Creation-Tool (Makecert.exe) werden X.509-Zertifikate sowie Paare aus privaten und öffentlichen Schlüsseln erstellt. Sie können den privaten Schlüssel speichern und zum Ausstellen und Signieren neuer Zertifikate verwenden, um eine Hierarchie von Zertifikaten in einer Kette zu simulieren. Dieses Tool ist lediglich als Unterstützung bei der Entwicklung von Diensten gedacht und sollte niemals zur Erstellung von Zertifikaten für tatsächliche Bereitstellungen verwendet werden. Wenn Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst entwickeln, können Sie mit Makecert.exe anhand der folgenden Schritte eine Kette von Vertrauensstellungen erstellen.  
  
#### <a name="to-build-a-chain-of-trust-with-makecertexe"></a>So erstellen Sie eine Kette von Vertrauensstellungen mit Makecert.exe  
  
1.  Erstellen Sie ein (selbst signiertes) temporäres Zertifikat für eine Stammzertifizierungsstelle mit MakeCert.exe. Speichern Sie den privaten Schlüssel.  
  
2.  Verwenden Sie das neue Zertifikat, um ein anderes Zertifikat auszustellen, das den öffentlichen Schlüssel enthält.  
  
3.  Importieren Sie das Zertifikat der Stammzertifizierungsstelle in den Speicher vertrauenswürdiger Stammzertifizierungsstellen.  
  
4.  Schrittweise Anweisungen finden Sie unter [Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).  
  
## <a name="which-certificate-to-use"></a>Welches Zertifikat soll verwendet werden?  
 Im Zusammenhang mit Zertifikaten wird häufig danach gefragt, welches Zertifikat und warum dieses verwendet werden soll. Die Antwort hängt davon ab, ob Sie einen Client oder einen Dienst programmieren. Die folgenden Informationen bieten eine allgemeine Orientierung und stellen keine erschöpfende Antwort auf diese Fragen dar.  
  
### <a name="service-certificates"></a>Dienstzertifikate  
 Dienstzertifikate werden in erster Linie zur Authentifizierung von Servern gegenüber Clients verwendet. Eine zunächst überprüft, ob bei der Authentifizierung eines Clients eines Servers ist beim Vergleichen des Werts, der die **Betreff** Feld auf den Uniform Resource Identifier (URI) Verbindung mit dem Dienst verwendet: das DNS von übereinstimmen. Angenommen, wenn der URI des Diensts "http://www.contoso.com/endpoint/" ist die **Betreff** Feld muss auch den Wert "www.contoso.com" enthalten.  
  
 Das Feld kann mehrere Werte enthalten, denen jeweils eine Initialisierung zur Angabe des Werts vorangeht. Die am häufigsten verwendete Initialisierung lautet "CN" (Common Name), z. B. "CN = www.contoso.com". Es ist auch möglich, für die **Betreff** Feld leer ist, in diesem Fall werden die **Alternativer Antragstellername** Feld darf die **DNS-Namen** Wert.  
  
 Beachten Sie außerdem den Wert der **Beabsichtigte Zwecke** Feld des Zertifikats sollte einen entsprechenden Wert ein, z. B. "Serverauthentifizierung" oder "Clientauthentifizierung" enthalten.  
  
### <a name="client-certificates"></a>Clientzertifikate  
 Clientzertifikate werden normalerweise nicht von der Zertifizierungsstelle eines Drittanbieters ausgegeben. Stattdessen enthält der persönliche Speicher des aktuellen Benutzers für gewöhnlich Zertifikate, die von einer Stammzertifizierungsstelle dort abgelegt wurden und deren beabsichtigter Zweck die "Clientauthentifizierung" ist. Diese Zertifikate können vom Client verwendet werden, wenn eine wechselseitige Authentifizierung erforderlich ist.  
  
## <a name="online-revocation-and-offline-revocation"></a>Online-Sperrüberprüfung und Offline-Sperrüberprüfung  
  
### <a name="certificate-validity"></a>Zertifikatsgültigkeit  
 Jedes Zertifikat gilt nur für einen bestimmten Zeitraum, bezeichnet der *Gültigkeitsdauer*. Die Gültigkeitsdauer wird definiert, indem die **gültig von** und **gültig bis** Felder eines x. 509-Zertifikats. Während der Authentifizierung wird überprüft, ob das Zertifikat eine entsprechende Gültigkeitsdauer aufweist.  
  
### <a name="certificate-revocation-list"></a>Zertifikatsperrliste  
 Zertifikate können innerhalb der Gültigkeitsdauer jederzeit von der Zertifizierungsstelle widerrufen werden. Dafür kann es viele Gründe geben, beispielsweise kann die Sicherheit des privaten Schlüssels eines Zertifikats gefährdet sein.  
  
 In diesem Fall werden auch alle untergeordneten Zertifikate des widerrufenen Zertifikats ungültig und im Rahmen des Authentifizierungsprozesses als nicht vertrauenswürdig eingestuft. Um herauszufinden, welche Zertifikate gesperrt werden, jeder Aussteller veröffentlicht ein und Date-Zeitstempel *Zertifikatsperrliste* (CRL). Diese Liste kann mit einer Online-Sperrüberprüfung oder mit einer Offline-Sperrüberprüfung überprüft werden, indem die `RevocationMode`-Eigenschaft oder die `DefaultRevocationMode`-Eigenschaft der folgenden Klassen einschließlich der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Klassen auf einen der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Enumerationswerte festgelegt wird: <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>, <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>, <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>. Der Standardwert aller Eigenschaften lautet `Online`.  
  
 Sie können den Modus auch festlegen, in der Konfiguration mit der `revocationMode` Attribut beider der [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (von der [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)) und die [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (von der [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)).  
  
## <a name="the-setcertificate-method"></a>SetCertificate-Methode  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] müssen häufig Zertifikate oder Gruppen von Zertifikaten angegeben werden, die von einem Dienst oder von einem Client zum Authentifizieren, Verschlüsseln oder digitalen Signieren von Nachrichten verwendet werden. Dies kann programmgesteuert mit der `SetCertificate`-Methode verschiedener Klassen geschehen, die X.509-Zertifikate darstellen. Folgende Klassen geben mit der `SetCertificate`-Methode ein Zertifikat an.  
  
|Klasse|Methode|  
|-----------|------------|  
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|  
  
 Bei der `SetCertificate`-Methode werden ein Speicherort und ein Speicher angegeben sowie ein Suchtyp (`x509FindType`-Parameter), der ein Feld des Zertifikats bestimmt, und ein Wert, der im Feld gefunden werden soll. Der folgende Code erstellt z. B. eine <xref:System.ServiceModel.ServiceHost> Instanz, und legt das Dienstzertifikat zum Authentifizieren des Dienstes für Clients mit der `SetCertificate` Methode.  
  
 [!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
 [!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]  
  
### <a name="multiple-certificates-with-the-same-value"></a>Mehrere Zertifikate mit dem gleichen Wert  
 Ein Speicher kann mehrere Zertifikate mit dem gleichen Antragstellernamen enthalten. Dies bedeutet, dass, wenn Sie, dass angeben die `x509FindType` ist <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> oder <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectDistinguishedName>, und mehr als ein Zertifikat hat den gleichen Wert, wird eine Ausnahme ausgelöst Becausethereisno Möglichkeit zur Unterscheidung welches Zertifikat erforderlich ist. Legen Sie den `x509FindType` auf <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> fest, um dem entgegenzuwirken. Das Fingerabdruckfeld enthält einen eindeutigen Wert, mit dem ein bestimmtes Zertifikat in einem Speicher gefunden werden kann. Dies hat jedoch einen Nachteil: Wenn das Zertifikat widerrufen oder erneuert wird, schlägt die `SetCertificate`-Methode fehl, da der Fingerabdruck ebenfalls nicht mehr verfügbar ist. Ist das Zertifikat nicht mehr gültig ist, schlägt die Authentifizierung fehl. Legen Sie den `x590FindType`-Parameter auf <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByIssuerName> fest, und geben Sie den Namen des Ausstellers an, um dem entgegenzuwirken. Wenn kein bestimmter Aussteller angegeben werden muss, können Sie auch einen der anderen <xref:System.Security.Cryptography.X509Certificates.X509FindType>-Enumerationswerte wie <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByTimeValid> festlegen.  
  
## <a name="certificates-in-configuration"></a>Zertifikate in der Konfiguration  
 Sie können Zertifikate auch in der Konfiguration festlegen. Wenn Sie einen Dienst erstellen, werden Anmeldeinformationen, Zertifikate, einschließlich angegeben, unter der [ \<ServiceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md). Wenn Sie einen Client programmieren, werden Zertifikate angegeben, unter der [ \<EndpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md).  
  
## <a name="mapping-a-certificate-to-a-user-account"></a>Zuordnen eines Zertifikats zu einem Benutzerkonto  
 IIS und Active Directory bieten u. a. die Möglichkeit, ein Zertifikat einem Windows-Benutzerkonto zuzuordnen. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Das Feature "" finden Sie unter [Zuordnen von Zertifikaten zu Benutzerkonten](http://go.microsoft.com/fwlink/?LinkId=88917).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Mithilfe von Active Directory-Zuordnung finden Sie [Zuordnung von Clientzertifikaten mithilfe der Zuordnung von Directory Service](http://go.microsoft.com/fwlink/?LinkId=88918).  
  
 Wenn diese Funktion aktiviert ist, können Sie die <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A>-Eigenschaft der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse auf `true` festlegen. In der Konfiguration können Sie festlegen der `mapClientCertificateToWindowsAccount` Attribut von der [ \<Authentifizierung >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) Element `true`, wie im folgenden Code gezeigt.  
  
```xml  
<serviceBehaviors>  
 <behavior name="MappingBehavior">  
  <serviceCredentials>  
   <clientCertificate>  
    <authentication certificateValidationMode="None" mapClientCertificateToWindowsAccount="true" />  
   </clientCertificate>  
  </serviceCredentials>  
 </behavior>  
</serviceBehaviors>  
```  
  
 Die Zuordnung eines X.509-Zertifikats zu einem Token, das ein Windows-Benutzerkonto darstellt, wird als Erweiterung der Berechtigungen angesehen, da das Windows-Token nach der Zuordnung Zugriff auf geschützte Ressourcen ermöglicht. Das X.509-Zertifikat muss daher vor der Zuordnung die entsprechenden Anforderungen der Domänenrichtlinie erfüllen. Die *SChannel* Sicherheitspaket erzwingt diese Anforderung.  
  
 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] stellt bei Verwendung von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] oder höher sicher, dass das Zertifikat der Domänenrichtlinie entspricht, bevor es dem Windows-Konto zugeordnet wird.  
  
 In der ersten Version von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfolgt die Zuordnung ohne auf die Domänenrichtlinie zurückzugreifen. Möglicherweise tritt daher bei älteren Anwendungen, die mit dem ersten Release ausgeführt werden konnten, ein Fehler auf, wenn die Zuordnung aktiviert ist und die Anforderungen der Domänenrichtlinie vom X.509-Zertifikat nicht erfüllt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Channels>  
 <xref:System.ServiceModel.Security>  
 <xref:System.ServiceModel>  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType>  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
