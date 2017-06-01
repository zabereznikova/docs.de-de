---
title: "Verwenden von Zertifikaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Zertifikate [WCF]"
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Verwenden von Zertifikaten
Bei der Programmierung der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Sicherheit werden digitale X.509\-Zertifikate häufig zum Authentifizieren von Clients und Servern sowie zum Verschlüsseln und digitalen Signieren von Nachrichten verwendet.Dieses Thema bietet einen Überblick über die Funktionen digitaler X.509\-Zertifikate und ihre Verwendung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und enthält Links zu Themen, in denen diese Konzepte näher beschrieben oder die Ausführung allgemeiner Aufgaben mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und Zertifikaten erläutert werden.  
  
 Digitale Zertifikate sind Teil einer *Public Key\-Infrastruktur* \(PKI\). Dabei handelt es sich um ein System aus digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen zur Überprüfung und Authentifizierung der Gültigkeit aller beteiligten Parteien in einer elektronischen Transaktion unter Verwendung der Public Key\-Kryptologie.Die Zertifikate werden von einer Zertifizierungsstelle ausgestellt, und jedes Zertifikat enthält eine Reihe von Feldern mit Daten wie *Antragsteller* \(die Entität, für die das Zertifikat ausgestellt wird\), Gültigkeitsdatum \(das Datum, bis zu dem das Zertifikat gültig ist\), Aussteller \(die Entität, von der das Zertifikat ausgestellt wurde\) und öffentlichem Schlüssel.In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden diese Eigenschaften als <xref:System.IdentityModel.Claims.Claim> verarbeitet, und jeder Anspruch wird weiter in zwei Typen unterteilt: Identität und Recht.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur X.509\-Zertifikaten finden Sie unter [X.509\-Zertifikate mit öffentlichem Schlüssel](http://go.microsoft.com/fwlink/?LinkId=209952)[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Ansprüchen und zur Autorisierung in WCF finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Implementieren einer PKI finden Sie unter [Windows Server 2008 R2 \- Zertifikatdienste](http://go.microsoft.com/fwlink/?LinkId=209949).  
  
 Eine zentrale Funktion des Zertifikats ist die Authentifizierung der Identität des Besitzers des Zertifikats gegenüber anderen.Ein Zertifikat enthält den *öffentlichen Schlüssel* des Besitzers, während der Besitzer den privaten Schlüssel behält.Der öffentliche Schlüssel kann zum Verschlüsseln von Nachrichten verwendet werden, die an den Besitzer des Zertifikats gesendet werden.Nur der Besitzer hat Zugriff auf den privaten Schlüssel, sodass niemand anders diese Nachrichten entschlüsseln kann.  
  
 Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter\-Zertifikataussteller handelt.Windows\-Domänen verfügen über eine Zertifizierungsstelle, von der Zertifikate für Computer in der Domäne ausgestellt werden können.  
  
## Anzeigen von Zertifikaten  
 Bei der Verwendung von Zertifikaten ist es oft erforderlich, die Zertifikate anzuzeigen und ihre Eigenschaften zu überprüfen.Die einfachste Methode dazu ist das MMC \(Microsoft Management Console\)\-Snap\-In\-Tool.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC\-Snap\-In](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
## Zertifikatspeicher  
 Zertifikate werden in Speichern abgelegt.Die zwei Hauptspeicherorte sind in weitere Unterspeicher unterteilt.Administratoren können beide Hauptspeicher mit dem MMC\-Snap\-In\-Tool anzeigen.Alle anderen Benutzer können lediglich den Speicher des aktuellen Benutzers anzeigen.  
  
-   **Lokaler Computerspeicher**Dieser enthält die Zertifikate, die von den Prozessen des Computers verwendet werden, z. B. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].Speichern Sie die Zertifikate zur Authentifizierung des Servers gegenüber Clients im lokalen Computerspeicher.  
  
-   **Aktueller Benutzerspeicher**.Interaktive Anwendungen legen Zertifikate für den aktuellen Benutzer des Computers normalerweise im aktuellen Benutzerspeicher ab.Beim Erstellen einer Clientanwendung werden die Zertifikate zur Authentifizierung eines Benutzers gegenüber einem Dienst normalerweise hier abgelegt.  
  
 Diese beiden Speicher teilen sich in weitere Unterspeicher auf.Die wichtigsten Unterspeicher für die Programmierung mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sind folgende:  
  
-   **Vertrauenswürdige Stammzertifizierungsstellen**.Mit den Zertifikaten in diesem Speicher können Sie eine Zertifikatskette erstellen, die zum Zertifikat einer Zertifizierungsstelle in diesem Speicher zurückverfolgt werden kann.  
  
    > [!IMPORTANT]
    >  Der lokale Computer stuft alle Zertifikate in diesem Speicher als implizit vertrauenswürdig ein; dies gilt auch, wenn das Zertifikat im Speicher nicht von einer vertrauenswürdigen Zertifizierungsstelle eines Drittanbieters stammt.Aus diesem Grund sollten Sie in diesem Speicher nur Zertifikate ablegen, wenn Sie dem Aussteller uneingeschränkt vertrauen und sich der möglichen Folgen bewusst sind.  
  
-   **Persönlich**.Dieser Speicher wird für Zertifikate verwendet, die dem Benutzer eines Computers zugeordnet sind.Dieser Speicher wird normalerweise für Zertifikate verwendet, die von einem der Zertifikate der Zertifizierungsstelle im Speicher vertrauenswürdiger Stammzertifizierungsstellen stammen.Darüber hinaus können in diesem Speicher auch selbst ausgestellte Zertifikate abgelegt werden, die von einer Anwendung als vertrauenswürdig eingestuft werden.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Zertifikatspeichern finden Sie unter [Zertifikatspeicher](http://go.microsoft.com/fwlink/?LinkId=88912).  
  
### Auswählen eines Speichers  
 Die Auswahl des Speichers für ein Zertifikat hängt davon ab, wie und wann der Dienst oder Client ausgeführt wird.Dabei gelten folgende allgemeine Regeln:  
  
-   Wenn der WCF\-Dienst in einem Windows\-Dienst gehostet wird, wird der Speicher des **lokalen Computers** verwendet.Sie benötigen Administratorrechte, wenn Sie Zertifikate im lokalen Computerspeicher installieren möchten.  
  
-   Wenn es sich beim Dienst oder Client um eine Anwendung handelt, die unter einem Benutzerkonto ausgeführt wird, wird der Speicher des **aktuellen Benutzers** verwendet.  
  
### Zugreifen auf Speicher  
 Speicher werden analog zu Ordnern auf einem Computer durch Zugriffssteuerungslisten \(ACLs\) geschützt.Beim Erstellen eines Diensts, der von Internet Information Services \(IIS\) gehostet wird, wird der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Prozess unter dem [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Konto ausgeführt.Dieses Konto muss über Zugriff auf den Speicher mit den Zertifikaten verfügen, die von einem Dienst verwendet werden.Die zentralen Speicher werden durch eine Standardzugriffssteuerungsliste geschützt, eine Änderung der Listen ist jedoch möglich.Wenn Sie eine separate Rolle für den Speicherzugriff erstellen, muss diese über die entsprechende Zugriffsberechtigung verfügen.Informationen zum Bearbeiten der Zugriffssteuerungsliste mit dem Tool "WinHttpCertConfig.exe" finden Sie unter [Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Verwendung von Clientzertifikaten mit IIS finden Sie unter [Aufrufen eines Webdiensts mit einem Clientzertifikat zur Authentifizierung in einer ASP.NET\-Webanwendung](http://go.microsoft.com/fwlink/?LinkId=88914)  
  
## Vertrauensketten und Zertifizierungsstellen  
 Zertifikate werden in einer Hierarchie erstellt, in der jedes einzelne Zertifikat mit der Zertifizierungsstelle verknüpft ist, von der es ausgestellt wurde.Dieser Link verweist auf das Zertifikat der Zertifizierungsstelle.Das Zertifikat der Zertifizierungsstelle wird dann mit der Zertifizierungsstelle verknüpft, von der das ursprüngliche Zertifikat der Zertifizierungsstelle ausgestellt wurde.Dieser Prozess wird wiederholt, bis das Zertifikat der Stammzertifizierungsstelle erreicht wird.Das Zertifikat der Stammzertifizierungsstelle ist grundsätzlich vertrauenswürdig.  
  
 Digitale Zertifikate werden verwendet, um eine Entität anhand dieser als *Zertifikatskette* bezeichneten Hierarchie zu authentifizieren.Sie können die Kette eines beliebigen Zertifikats mit dem MMC\-Snap\-In anzeigen, indem Sie auf das Zertifikat doppelklicken und anschließend auf die Registerkarte **Zertifikatpfad** klicken.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Importieren von Zertifikatketten für Zertifizierungsstellen finden Sie unter [Vorgehensweise: Angeben der Zertifizierungsstellenzertifikatskette, die verwendet wird, um Signaturen zu überprüfen](../../../../docs/framework/wcf/feature-details/specify-the-certificate-authority-chain-verify-signatures-wcf.md).  
  
> [!NOTE]
>  Sie können jeden Aussteller zu einer vertrauenswürdigen Stammzertifizierungsstelle machen, indem Sie das Zertifikat des Ausstellers im Zertifikatspeicher der Stammzertifizierungsstelle ablegen.  
  
### Deaktivieren von Vertrauensketten  
 Wenn Sie einen neuen Dienst erstellen, verwenden Sie möglicherweise ein Zertifikat, das nicht von einer vertrauenswürdigen Stammzertifizierungsstelle ausgegeben wurde, oder das ausstellende Zertifikat befindet sich nicht im Speicher vertrauenswürdiger Stammzertifizierungsstellen.Sie können die Überprüfung der Kette von Vertrauensstellungen für ein Zertifikat in Entwicklungsumgebungen vorübergehend deaktivieren.Legen Sie dazu die `CertificateValidationMode`\-Eigenschaft auf entweder `PeerTrust` oder `PeerOrChainTrust` fest.Durch den jeweiligen Modus wird angegeben, dass das Zertifikat entweder selbst ausgegeben \(Peervertrauenszertifikat\) oder Teil einer Kette von Vertrauensstellungen ist.Die Eigenschaft kann auf eine der folgenden Klassen festgelegt werden:  
  
|Klasse|Eigenschaft|  
|------------|-----------------|  
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=fullName>|  
  
 Sie können die Eigenschaft auch in der Konfiguration festlegen.Folgende Elemente werden verwendet, um den Validierungsmodus anzugeben:  
  
-   [\<Authentifizierung\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)  
  
-   [\<peerAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)  
  
-   [\<messageSenderAuthentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)  
  
## Benutzerdefinierte Authentifizierung  
 Die `CertificateValidationMode`\-Eigenschaft ermöglicht es auch, die Authentifizierung von Zertifikaten anzupassen.Die Standardvertrauensebene ist `ChainTrust`.Wenn Sie den <xref:System.ServiceModel.Security.X509CertificateValidationMode>\-Wert verwenden möchten, müssen Sie auch das `CustomCertificateValidatorType`\-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden.Wenn Sie eine benutzerdefinierte Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>\-Klasse vererben.  
  
 Wenn Sie eine benutzerdefinierte Authentifizierung erstellen, müssen Sie auf jeden Fall die <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>\-Methode überschreiben.Ein Beispiel für eine benutzerdefinierte Authentifizierung finden Sie unter [X.509\-Zertifikats\-Validierungssteuerelement](../../../../docs/framework/wcf/samples/x-509-certificate-validator.md).[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md).  
  
## Verwenden von Makecert.exe zum Erstellen einer Zertifikatkette  
 Mit dem Certificate Creation\-Tool \(Makecert.exe\) werden X.509\-Zertifikate sowie Paare aus privaten und öffentlichen Schlüsseln erstellt.Sie können den privaten Schlüssel speichern und zum Ausstellen und Signieren neuer Zertifikate verwenden, um eine Hierarchie von Zertifikaten in einer Kette zu simulieren.Dieses Tool ist lediglich als Unterstützung bei der Entwicklung von Diensten gedacht und sollte niemals zur Erstellung von Zertifikaten für tatsächliche Bereitstellungen verwendet werden.Wenn Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst entwickeln, können Sie mit Makecert.exe anhand der folgenden Schritte eine Kette von Vertrauensstellungen erstellen.  
  
#### So erstellen Sie eine Kette von Vertrauensstellungen mit Makecert.exe  
  
1.  Erstellen Sie ein \(selbst signiertes\) temporäres Zertifikat für eine Stammzertifizierungsstelle mit MakeCert.exe.Speichern Sie den privaten Schlüssel.  
  
2.  Verwenden Sie das neue Zertifikat, um ein anderes Zertifikat auszustellen, das den öffentlichen Schlüssel enthält.  
  
3.  Importieren Sie das Zertifikat der Stammzertifizierungsstelle in den Speicher vertrauenswürdiger Stammzertifizierungsstellen.  
  
4.  Schritt\-für\-Schritt\-Anweisungen finden Sie unter [Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md).  
  
## Welches Zertifikat soll verwendet werden?  
 Im Zusammenhang mit Zertifikaten wird häufig danach gefragt, welches Zertifikat und warum dieses verwendet werden soll.Die Antwort hängt davon ab, ob Sie einen Client oder einen Dienst programmieren.Die folgenden Informationen bieten eine allgemeine Orientierung und stellen keine erschöpfende Antwort auf diese Fragen dar.  
  
### Dienstzertifikate  
 Dienstzertifikate werden in erster Linie zur Authentifizierung von Servern gegenüber Clients verwendet.Bei der Authentifizierung eines Servers durch einen Client wird u. a. zunächst überprüft, ob der Wert im Feld **Antragsteller** mit dem Uniform Resource Identifier \(URI\) übereinstimmt, der zum Herstellen der Verbindung mit dem Dienst verwendet wird: das DNS von Client und Server muss übereinstimmen.Angenommen, der URI des Diensts lautet "http:\/\/www.contoso.com\/endpoint\/". In diesem Fall muss das Feld **Antragsteller** ebenfalls den Wert "http:\/\/www.contoso.com\/endpoint\/" enthalten.  
  
 Das Feld kann mehrere Werte enthalten, denen jeweils eine Initialisierung zur Angabe des Werts vorangeht.Die am häufigsten verwendete Initialisierung lautet "CN" \(Common Name\), z. B. "CN \= www.contoso.com".Das Feld **Antragsteller** kann auch leer sein. In diesem Fall kann das Feld **Alternativer Antragstellername** den Wert **DNS\-Name** enthalten.  
  
 Der Wert des Felds **Beabsichtigte Zwecke** des Zertifikats sollte einen entsprechenden Wert enthalten, z. B. "Serverauthentifizierung" oder "Clientauthentifizierung".  
  
### Clientzertifikate  
 Clientzertifikate werden normalerweise nicht von der Zertifizierungsstelle eines Drittanbieters ausgegeben.Stattdessen enthält der persönliche Speicher des aktuellen Benutzers für gewöhnlich Zertifikate, die von einer Stammzertifizierungsstelle dort abgelegt wurden und deren beabsichtigter Zweck die "Clientauthentifizierung" ist.Diese Zertifikate können vom Client verwendet werden, wenn eine wechselseitige Authentifizierung erforderlich ist.  
  
## Online\-Sperrüberprüfung und Offline\-Sperrüberprüfung  
  
### Zertifikatsgültigkeit  
 Jedes Zertifikat ist nur für einen angegebenen Zeitraum gültig, der auch als *Gültigkeitsdauer* bezeichnet wird.Die Gültigkeitsdauer wird durch die Felder **Gültig ab** und **Gültig bis** eines X.509\-Zertifikats bestimmt.Während der Authentifizierung wird überprüft, ob das Zertifikat eine entsprechende Gültigkeitsdauer aufweist.  
  
### Zertifikatsperrliste  
 Zertifikate können innerhalb der Gültigkeitsdauer jederzeit von der Zertifizierungsstelle widerrufen werden.Dafür kann es viele Gründe geben, beispielsweise kann die Sicherheit des privaten Schlüssels eines Zertifikats gefährdet sein.  
  
 In diesem Fall werden auch alle untergeordneten Zertifikate des widerrufenen Zertifikats ungültig und im Rahmen des Authentifizierungsprozesses als nicht vertrauenswürdig eingestuft.Mithilfe einer *Zertifikatsperrliste* \(CRL\), die über Datums\- und Zeitstempel verfügt, können Sie herausfinden, welche Zertifikate widerrufen wurden.Diese Liste kann mit einer Online\-Sperrüberprüfung oder mit einer Offline\-Sperrüberprüfung überprüft werden, indem die `RevocationMode`\-Eigenschaft oder die `DefaultRevocationMode`\-Eigenschaft der folgenden Klassen einschließlich der <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>\-Klassen auf einen der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>\-Enumerationswerte festgelegt wird: <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>, <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>, <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>.Der Standardwert aller Eigenschaften lautet `Online`.  
  
 Sie können den Modus auch mit dem `revocationMode`\-Attribut von [\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)[\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)[\<authentication\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)[\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)\) und von  \(für \) in der Konfiguration festlegen.  
  
## SetCertificate\-Methode  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] müssen häufig Zertifikate oder Gruppen von Zertifikaten angegeben werden, die von einem Dienst oder von einem Client zum Authentifizieren, Verschlüsseln oder digitalen Signieren von Nachrichten verwendet werden.Dies kann programmgesteuert mit der `SetCertificate`\-Methode verschiedener Klassen geschehen, die X.509\-Zertifikate darstellen.Folgende Klassen geben mit der `SetCertificate`\-Methode ein Zertifikat an.  
  
|Klasse|Methode|  
|------------|-------------|  
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|  
  
 Bei der `SetCertificate`\-Methode werden ein Speicherort und ein Speicher angegeben sowie ein Suchtyp \(`x509FindType`\-Parameter\), der ein Feld des Zertifikats bestimmt, und ein Wert, der im Feld gefunden werden soll.So wird beispielsweise mit dem folgenden Code eine <xref:System.ServiceModel.ServiceHost>\-Instanz erstellt, und das Dienstzertifikat, mit dem der Dienst gegenüber Clients mit der `SetCertificate` \-Methode authentifiziert wird, wird festgelegt.  
  
 [!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
 [!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]  
  
### Mehrere Zertifikate mit dem gleichen Wert  
 Ein Speicher kann mehrere Zertifikate mit dem gleichen Antragstellernamen enthalten.Wenn Sie also `x509FindType` auf <xref:System.Security.Cryptography.X509Certificates.X509FindType> oder <xref:System.Security.Cryptography.X509Certificates.X509FindType> festlegen und mehrere Zertifikate den gleichen Wert aufweisen, wird eine Ausnahme ausgelöst, da nicht ermitteltwerdenkann, welches Zertifikat benötigt wird.Legen Sie den `x509FindType` auf <xref:System.Security.Cryptography.X509Certificates.X509FindType> fest, um dem entgegenzuwirken.Das Fingerabdruckfeld enthält einen eindeutigen Wert, mit dem ein bestimmtes Zertifikat in einem Speicher gefunden werden kann.Dies hat jedoch einen Nachteil: Wenn das Zertifikat widerrufen oder erneuert wird, schlägt die `SetCertificate`\-Methode fehl, da der Fingerabdruck ebenfalls nicht mehr verfügbar ist.Ist das Zertifikat nicht mehr gültig ist, schlägt die Authentifizierung fehl.Legen Sie den `x590FindType`\-Parameter auf <xref:System.Security.Cryptography.X509Certificates.X509FindType> fest, und geben Sie den Namen des Ausstellers an, um dem entgegenzuwirken.Wenn kein bestimmter Aussteller angegeben werden muss, können Sie auch einen der anderen <xref:System.Security.Cryptography.X509Certificates.X509FindType>\-Enumerationswerte wie <xref:System.Security.Cryptography.X509Certificates.X509FindType> festlegen.  
  
## Zertifikate in der Konfiguration  
 Sie können Zertifikate auch in der Konfiguration festlegen.Wenn Sie einen Dienst erstellen, werden die Anmeldeinformationen, einschließlich der Zertifikate unter [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) angegeben.Wenn Sie einen Client programmieren, werden die Zertifikate unter [\<endpointBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) angegeben.  
  
## Zuordnen eines Zertifikats zu einem Benutzerkonto  
 IIS und Active Directory bieten u. a. die Möglichkeit, ein Zertifikat einem Windows\-Benutzerkonto zuzuordnen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Funktion finden Sie unter [Zuordnen von Zertifikaten zu Benutzerkonten](http://go.microsoft.com/fwlink/?LinkId=88917)  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Active Directory\-Zuordnung finden Sie unter [Zuordnen von Clientzertifikaten mit der Verzeichnisdienstzuordnung](http://go.microsoft.com/fwlink/?LinkId=88918) \(möglicherweise in englischer Sprache\).  
  
 Wenn diese Funktion aktiviert ist, können Sie die <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A>\-Eigenschaft der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>\-Klasse auf `true` festlegen.In der Konfiguration können Sie das `mapClientCertificateToWindowsAccount`\-Attribut des [\<Authentifizierung\>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)`true-Elements wie im folgenden Codebeispiel auf`  festlegen.  
  
```  
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
  
 Die Zuordnung eines X.509\-Zertifikats zu einem Token, das ein Windows\-Benutzerkonto darstellt, wird als Erweiterung der Berechtigungen angesehen, da das Windows\-Token nach der Zuordnung Zugriff auf geschützte Ressourcen ermöglicht.Das X.509\-Zertifikat muss daher vor der Zuordnung die entsprechenden Anforderungen der Domänenrichtlinie erfüllen.Dies wird durch das *SChannel*\-Sicherheitspaket sichergestellt.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt bei Verwendung von [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] oder höher sicher, dass das Zertifikat der Domänenrichtlinie entspricht, bevor es dem Windows\-Konto zugeordnet wird.  
  
 In der ersten Version von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfolgt die Zuordnung ohne auf die Domänenrichtlinie zurückzugreifen.Möglicherweise tritt daher bei älteren Anwendungen, die mit der ersten Version ausgeführt werden konnten, ein Fehler auf, wenn die Zuordnung aktiviert ist und die Anforderungen der Domänenrichtlinie vom X.509\-Zertifikat nicht erfüllt werden.  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels>   
 <xref:System.ServiceModel.Security>   
 <xref:System.ServiceModel>   
 <xref:System.Security.Cryptography.X509Certificates.X509FindType>   
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)