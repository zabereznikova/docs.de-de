---
title: Verwenden von Zertifikaten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF]
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
ms.openlocfilehash: e61437efd87c30758c36d642bb9269ad2966c951
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600113"
---
# <a name="working-with-certificates"></a>Verwenden von Zertifikaten

Zum Programmieren der WCF-Sicherheit (Windows Communication Foundation) werden häufig digitale X.509-Zertifikate zum Authentifizieren von Clients und Servern sowie zum Verschlüsseln und digitalen Signieren von Nachrichten verwendet. Dieser Artikel bietet einen Überblick über die Funktionen digitaler X.509-Zertifikate und ihre Verwendung in WCF und enthält Links zu Themen, in denen diese Konzepte näher beschrieben oder die Ausführung allgemeiner Aufgaben mit WCF und Zertifikaten erläutert werden.

Digitale Zertifikate sind Teil einer *Public Key-Infrastruktur* (PKI). Dabei handelt es sich um ein System aus digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen zur Überprüfung und Authentifizierung der Gültigkeit aller beteiligten Parteien in einer elektronischen Transaktion unter Verwendung der Public Key-Kryptografie. Die Zertifikate werden von einer Zertifizierungsstelle ausgestellt, und jedes Zertifikat enthält eine Reihe von Feldern mit Daten, z.B. *Antragsteller* (die Entität, für die das Zertifikat ausgestellt wird), Gültigkeitsdatum (das Datum, bis zu dem das Zertifikat gültig ist), Aussteller (die Entität, von der das Zertifikat ausgestellt wurde) und öffentlicher Schlüssel. In WCF werden diese Eigenschaften als <xref:System.IdentityModel.Claims.Claim> verarbeitet, und jeder Anspruch wird weiter in zwei Typen unterteilt: Identität und Recht. Weitere Informationen zu X.509-Zertifikaten finden Sie unter [X.509 Public Key Certificates (X.509-Zertifikate mit öffentlichem Schlüssel)](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates). Weitere Informationen über Ansprüche und Autorisierung in WCF finden Sie unter [Managing Claims and Authorization with the Identity Model (Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell)](managing-claims-and-authorization-with-the-identity-model.md). Weitere Informationen zum Implementieren einer PKI finden Sie [unter Unternehmens-PKI mit Windows Server 2012 R2 Active Directory Certificate Services](https://docs.microsoft.com/archive/blogs/yungchou/enterprise-pki-with-windows-server-2012-r2-active-directory-certificate-services-part-1-of-2).

Die zentrale Funktion eines Zertifikats ist die Authentifizierung der Identität des Besitzers des Zertifikats gegenüber anderen. Ein Zertifikat enthält den *öffentlichen Schlüssel* des Besitzers, während der Besitzer den privaten Schlüssel behält. Der öffentliche Schlüssel kann zum Verschlüsseln von Nachrichten verwendet werden, die an den Besitzer des Zertifikats gesendet werden. Nur der Besitzer hat Zugriff auf den privaten Schlüssel, sodass niemand anders diese Nachrichten entschlüsseln kann.

Zertifikate müssen von einer Zertifizierungsstelle ausgestellt werden, bei der es sich oft um einen Drittanbieter-Zertifikataussteller handelt. Windows-Domänen verfügen über eine Zertifizierungsstelle, von der Zertifikate für Computer in der Domäne ausgestellt werden können.

## <a name="viewing-certificates"></a>Anzeigen von Zertifikaten

Bei der Verwendung von Zertifikaten ist es oft erforderlich, die Zertifikate anzuzeigen und ihre Eigenschaften zu überprüfen. Die einfachste Methode dazu ist das MMC (Microsoft Management Console)-Snap-In-Tool. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](how-to-view-certificates-with-the-mmc-snap-in.md).

## <a name="certificate-stores"></a>Zertifikatspeicher

Zertifikate werden in Speichern abgelegt. Die zwei Hauptspeicherorte sind in weitere Unterspeicher unterteilt. Administratoren können beide Hauptspeicher mit dem MMC-Snap-In-Tool anzeigen. Alle anderen Benutzer können lediglich den Speicher des aktuellen Benutzers anzeigen.

- **Lokaler Computerspeicher** Diese enthält die Zertifikate, auf die Computer Prozesse zugreifen, wie z. b. ASP.net. Speichern Sie die Zertifikate zur Authentifizierung des Servers gegenüber Clients im lokalen Computerspeicher.

- **Aktueller Benutzerspeicher** Interaktive Anwendungen legen Zertifikate für den aktuellen Benutzer des Computers normalerweise im aktuellen Benutzerspeicher ab. Beim Erstellen einer Clientanwendung werden die Zertifikate zur Authentifizierung eines Benutzers gegenüber einem Dienst normalerweise hier abgelegt.

Diese beiden Speicher teilen sich in weitere Unterspeicher auf. Die wichtigsten Unterspeicher für die Programmierung mit WCF sind folgende:

- **Vertrauenswürdige Stammzertifizierungsstellen** Mit den Zertifikaten in diesem Speicher können Sie eine Zertifikatkette erstellen, die zum Zertifikat einer Zertifizierungsstelle in diesem Speicher zurückverfolgt werden kann.

  > [!IMPORTANT]
  > Der lokale Computer stuft alle Zertifikate in diesem Speicher als implizit vertrauenswürdig ein; dies gilt auch, wenn das Zertifikat im Speicher nicht von einer vertrauenswürdigen Zertifizierungsstelle eines Drittanbieters stammt. Aus diesem Grund sollten Sie in diesem Speicher nur Zertifikate ablegen, wenn Sie dem Aussteller uneingeschränkt vertrauen und sich der möglichen Folgen bewusst sind.

- **Persönlich**. Dieser Speicher wird für Zertifikate verwendet, die dem Benutzer eines Computers zugeordnet sind. Dieser Speicher wird normalerweise für Zertifikate verwendet, die von einem der Zertifikate der Zertifizierungsstelle im Speicher vertrauenswürdiger Stammzertifizierungsstellen stammen. Darüber hinaus können in diesem Speicher auch selbst ausgestellte Zertifikate abgelegt werden, die von einer Anwendung als vertrauenswürdig eingestuft werden.

Weitere Informationen zu den Zertifikatformaten finden Sie unter [Certificate Stores (Zertifikatspeicher)](/windows/desktop/secauthn/certificate-stores).

### <a name="selecting-a-store"></a>Auswählen eines Speichers

Die Auswahl des Speichers für ein Zertifikat hängt davon ab, wie und wann der Dienst oder Client ausgeführt wird. Dabei gelten folgende allgemeine Regeln:

- Wenn der WCF-Dienst in einem Windows-Dienst gehostet wird, wird der Speicher des **lokalen Computers** verwendet. Sie benötigen Administratorrechte, wenn Sie Zertifikate im lokalen Computerspeicher installieren möchten.

- Wenn es sich beim Dienst oder Client um eine Anwendung handelt, die unter einem Benutzerkonto ausgeführt wird, wird der Speicher des **aktuellen Benutzers** verwendet.

### <a name="accessing-stores"></a>Zugreifen auf Speicher

Speicher werden analog zu Ordnern auf einem Computer durch Zugriffssteuerungslisten (ACLs) geschützt. Wenn Sie einen von Internetinformationsdienste (IIS) gehosteten Dienst erstellen, wird der ASP.NET-Prozess unter dem ASP.NET-Konto ausgeführt. Dieses Konto muss über Zugriff auf den Speicher mit den Zertifikaten verfügen, die von einem Dienst verwendet werden. Die zentralen Speicher werden durch eine Standardzugriffssteuerungsliste geschützt, eine Änderung der Listen ist jedoch möglich. Wenn Sie eine separate Rolle für den Speicherzugriff erstellen, muss diese über die entsprechende Zugriffsberechtigung verfügen. Unter [How to: Create Temporary Certificates for Use During Development (Vorgehensweise: Erstellen temporärer Zertifikate zur Verwendung während der Entwicklung)](how-to-create-temporary-certificates-for-use-during-development.md) erfahren Sie, wie Sie die Zugriffsliste mit dem Tool „WinHttpCertConfig.exe“ bearbeiten.

## <a name="chain-trust-and-certificate-authorities"></a>Vertrauensketten und Zertifizierungsstellen

Zertifikate werden in einer Hierarchie erstellt, in der jedes einzelne Zertifikat mit der Zertifizierungsstelle verknüpft ist, von der es ausgestellt wurde. Dieser Link verweist auf das Zertifikat der Zertifizierungsstelle. Das Zertifikat der Zertifizierungsstelle wird dann mit der Zertifizierungsstelle verknüpft, von der das Zertifikat der ursprünglichen Zertifizierungsstelle ausgestellt wurde. Dieser Prozess wird wiederholt, bis das Zertifikat der Stammzertifizierungsstelle erreicht wird. Das Zertifikat der Stammzertifizierungsstelle ist grundsätzlich vertrauenswürdig.

Digitale Zertifikate werden verwendet, um eine Entität anhand dieser als *Zertifikatkette* bezeichneten Hierarchie zu authentifizieren. Mit dem MMC-Snap-in können Sie die Kette eines Zertifikats anzeigen, indem Sie auf ein beliebiges Zertifikat doppelklicken und dann auf die Registerkarte **Zertifikat Pfad** klicken. Weitere Informationen zum Importieren von Zertifikat Ketten für eine Zertifizierungsstelle finden Sie unter Gewusst [wie: Angeben der Zertifizierungsstellen Zertifikatskette, die zum Überprüfen von Signaturen verwendet wird](specify-the-certificate-authority-chain-verify-signatures-wcf.md).

> [!NOTE]
> Sie können jeden Aussteller zu einer vertrauenswürdigen Stammzertifizierungsstelle machen, indem Sie das Zertifikat des Ausstellers im Zertifikatspeicher der Stammzertifizierungsstelle ablegen.

### <a name="disabling-chain-trust"></a>Deaktivieren von Vertrauensketten

Wenn Sie einen neuen Dienst erstellen, verwenden Sie möglicherweise ein Zertifikat, das nicht von einer vertrauenswürdigen Stammzertifizierungsstelle ausgegeben wurde, oder das ausstellende Zertifikat befindet sich nicht im Speicher vertrauenswürdiger Stammzertifizierungsstellen. Sie können die Überprüfung der Kette von Vertrauensstellungen für ein Zertifikat in Entwicklungsumgebungen vorübergehend deaktivieren. Legen Sie dazu die `CertificateValidationMode`-Eigenschaft auf entweder `PeerTrust` oder `PeerOrChainTrust` fest. Durch den jeweiligen Modus wird angegeben, dass das Zertifikat entweder selbst ausgegeben (Peervertrauenszertifikat) oder Teil einer Kette von Vertrauensstellungen ist. Die Eigenschaft kann auf eine der folgenden Klassen festgelegt werden:

|Klasse|Eigenschaft|
|-----------|--------------|
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=nameWithType>|

Sie können die Eigenschaft auch in der Konfiguration festlegen. Folgende Elemente werden verwendet, um den Validierungsmodus anzugeben:

- [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)

- [\<peerAuthentication>](../../configure-apps/file-schema/wcf/peerauthentication-element.md)

- [\<messageSenderAuthentication>](../../configure-apps/file-schema/wcf/messagesenderauthentication-element.md)

## <a name="custom-authentication"></a>Benutzerdefinierte Authentifizierung

Die `CertificateValidationMode`-Eigenschaft ermöglicht es auch, die Authentifizierung von Zertifikaten anzupassen. Die Standardvertrauensebene ist `ChainTrust`. Wenn Sie den <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>-Wert verwenden möchten, müssen Sie auch das `CustomCertificateValidatorType`-Attribut auf eine Assembly und einen Typ festlegen, die zur Validierung des Zertifikats verwendet werden. Wenn Sie eine benutzerdefinierte Überprüfung erstellen möchten, müssen Sie die abstrakte <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse vererben.

Wenn Sie eine benutzerdefinierte Authentifizierung erstellen, müssen Sie auf jeden Fall die <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>-Methode überschreiben. Ein Beispiel zur benutzerdefinierten Authentifizierung finden Sie im Beispiel zum [Validierungssteuerelement des X.509-Zertifikats](../samples/x-509-certificate-validator.md). Weitere Informationen finden Sie unter [Custom Credential and Credential Validation (Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen)](../extending/custom-credential-and-credential-validation.md).

## <a name="using-the-powershell-new-selfsignedcertificate-cmdlet-to-build-a-certificate-chain"></a>Verwenden des PowerShell-Cmdlets "New-selfsignedcertificate" zum Erstellen einer Zertifikat Kette

Mit dem PowerShell-Cmdlet "New-selfsignedcertificate" werden X. 509-Zertifikate und private Schlüssel/öffentliche Schlüsselpaare erstellt. Sie können den privaten Schlüssel speichern und zum Ausstellen und Signieren neuer Zertifikate verwenden, um eine Hierarchie von Zertifikaten in einer Kette zu simulieren. Das-Cmdlet ist nur für die Verwendung als Hilfe beim Entwickeln von Diensten vorgesehen und sollte nie zum Erstellen von Zertifikaten für die tatsächliche Bereitstellung verwendet werden. Wenn Sie einen WCF-Dienst entwickeln, führen Sie die folgenden Schritte aus, um mit dem New-selfsignedcertificate-Cmdlet eine Vertrauenskette zu erstellen.

#### <a name="to-build-a-chain-of-trust-with-the-new-selfsignedcertificate-cmdlet"></a>So erstellen Sie eine Vertrauenskette mit dem Cmdlet "New-selfsignedcertificate"

1. Erstellen Sie mit dem Cmdlet "New-selfsignedcertificate" ein temporäres Stamm Zertifizierungsstellen-Zertifikat (selbst signiert). Speichern Sie den privaten Schlüssel.

2. Verwenden Sie das neue Zertifikat, um ein anderes Zertifikat auszustellen, das den öffentlichen Schlüssel enthält.

3. Importieren Sie das Zertifikat der Stammzertifizierungsstelle in den Speicher vertrauenswürdiger Stammzertifizierungsstellen.

4. Anweisungen finden Sie unter [How to: Create Temporary Certificates for Use During Development (Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung)](how-to-create-temporary-certificates-for-use-during-development.md).

## <a name="which-certificate-to-use"></a>Welches Zertifikat soll verwendet werden?

Im Zusammenhang mit Zertifikaten wird häufig danach gefragt, welches Zertifikat und warum dieses verwendet werden soll. Die Antwort hängt davon ab, ob Sie einen Client oder einen Dienst programmieren. Die folgenden Informationen bieten eine allgemeine Orientierung und stellen keine erschöpfende Antwort auf diese Fragen dar.

### <a name="service-certificates"></a>Dienstzertifikate

Dienstzertifikate werden in erster Linie zur Authentifizierung von Servern gegenüber Clients verwendet. Bei der Authentifizierung eines Servers durch einen Client wird u.a. zunächst überprüft, ob der Wert im Feld **Antragsteller** mit dem Uniform Resource Identifier (URI) übereinstimmt, der zum Herstellen der Verbindung mit dem Dienst verwendet wird: das DNS von Client und Server muss übereinstimmen. Wenn beispielsweise der URI des Dienstes ist, `http://www.contoso.com/endpoint/` muss das **Betrefffeld** auch den Wert enthalten `www.contoso.com` .

Das Feld kann mehrere Werte enthalten, denen jeweils eine Initialisierung zur Angabe des Werts vorangeht. In den meisten Fällen ist die Initialisierung "CN" (allgemeiner Name), z `CN = www.contoso.com` . b.. Das Feld **Antragsteller** kann auch leer sein. In diesem Fall kann das Feld **Alternativer Antragstellername** den Wert **DNS-Name** enthalten.

Der Wert des Felds **Beabsichtigte Zwecke** des Zertifikats sollte einen entsprechenden Wert enthalten, z.B. „Serverauthentifizierung“ oder „Clientauthentifizierung“.

### <a name="client-certificates"></a>Clientzertifikate

Clientzertifikate werden normalerweise nicht von der Zertifizierungsstelle eines Drittanbieters ausgegeben. Stattdessen enthält der persönliche Speicher des aktuellen Benutzers für gewöhnlich Zertifikate, die von einer Stammzertifizierungsstelle dort abgelegt wurden und deren beabsichtigter Zweck die "Clientauthentifizierung" ist. Der Client kann ein solches Zertifikat verwenden, wenn eine gegenseitige Authentifizierung erforderlich ist.

## <a name="online-revocation-and-offline-revocation"></a>Online-Sperrüberprüfung und Offline-Sperrüberprüfung

### <a name="certificate-validity"></a>Zertifikatsgültigkeit

Jedes Zertifikat ist nur für einen angegebenen Zeitraum gültig, der auch als *Gültigkeitsdauer* bezeichnet wird. Die Gültigkeitsdauer wird durch die Felder **Gültig ab** und **Gültig bis** eines X.509-Zertifikats bestimmt. Während der Authentifizierung wird überprüft, ob das Zertifikat eine entsprechende Gültigkeitsdauer aufweist.

### <a name="certificate-revocation-list"></a>Zertifikatsperrliste

Zertifikate können innerhalb der Gültigkeitsdauer jederzeit von der Zertifizierungsstelle widerrufen werden. Dafür kann es viele Gründe geben, beispielsweise kann die Sicherheit des privaten Schlüssels eines Zertifikats gefährdet sein.

In diesem Fall werden auch alle untergeordneten Zertifikate des widerrufenen Zertifikats ungültig und im Rahmen des Authentifizierungsprozesses als nicht vertrauenswürdig eingestuft. Mithilfe einer *Zertifikatsperrliste* (CRL), die über Datums- und Zeitstempel verfügt, können Sie herausfinden, welche Zertifikate widerrufen wurden. Diese Liste kann mit einer Online-Sperrüberprüfung oder mit einer Offline-Sperrüberprüfung überprüft werden, indem die `RevocationMode`-Eigenschaft oder die `DefaultRevocationMode`-Eigenschaft der folgenden Klassen einschließlich der <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>-Klassen auf einen der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Enumerationswerte festgelegt wird: <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>, <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>, <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>. Der Standardwert aller Eigenschaften lautet `Online`.

Sie können den Modus auch mit dem `revocationMode` -Attribut der [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (von [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) ) und der [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (von [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) ) in der Konfiguration festlegen.

## <a name="the-setcertificate-method"></a>SetCertificate-Methode

In WCF müssen häufig Zertifikate oder Gruppen von Zertifikaten angegeben werden, die von einem Dienst oder von einem Client zum Authentifizieren, Verschlüsseln oder digitalen Signieren von Nachrichten verwendet werden. Dies kann programmgesteuert mit der `SetCertificate`-Methode verschiedener Klassen geschehen, die X.509-Zertifikate darstellen. Folgende Klassen geben mit der `SetCertificate`-Methode ein Zertifikat an.

|Klasse|Methode|
|-----------|------------|
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|

Bei der `SetCertificate`-Methode werden ein Speicherort und ein Speicher angegeben sowie ein Suchtyp (`x509FindType`-Parameter), der ein Feld des Zertifikats bestimmt, und ein Wert, der im Feld gefunden werden soll. So wird beispielsweise mit dem folgenden Code eine <xref:System.ServiceModel.ServiceHost>-Instanz erstellt, und das Dienstzertifikat, mit dem der Dienst gegenüber Clients mit der `SetCertificate`-Methode authentifiziert wird, wird festgelegt.

[!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
[!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]

### <a name="multiple-certificates-with-the-same-value"></a>Mehrere Zertifikate mit dem gleichen Wert

Ein Speicher kann mehrere Zertifikate mit dem gleichen Antragstellernamen enthalten. Wenn Sie also `x509FindType` auf <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName> oder <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectDistinguishedName> festlegen und mehrere Zertifikate den gleichen Wert aufweisen, wird eine Ausnahme ausgelöst, da nicht ermittelt werden kann, welches Zertifikat benötigt wird. Legen Sie den `x509FindType` auf <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> fest, um dem entgegenzuwirken. Das Fingerabdruckfeld enthält einen eindeutigen Wert, mit dem ein bestimmtes Zertifikat in einem Speicher gefunden werden kann. Dies hat jedoch einen Nachteil: Wenn das Zertifikat widerrufen oder erneuert wird, schlägt die `SetCertificate`-Methode fehl, da der Fingerabdruck ebenfalls nicht mehr verfügbar ist. Ist das Zertifikat nicht mehr gültig ist, schlägt die Authentifizierung fehl. Legen Sie den `x590FindType`-Parameter auf <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByIssuerName> fest, und geben Sie den Namen des Ausstellers an, um dem entgegenzuwirken. Wenn kein bestimmter Aussteller angegeben werden muss, können Sie auch einen der anderen <xref:System.Security.Cryptography.X509Certificates.X509FindType>-Enumerationswerte wie <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByTimeValid> festlegen.

## <a name="certificates-in-configuration"></a>Zertifikate in der Konfiguration

Sie können Zertifikate auch in der Konfiguration festlegen. Wenn Sie einen Dienst erstellen, werden die Anmelde Informationen, einschließlich der Zertifikate, unter der angegeben [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) . Wenn Sie einen Client programmieren, werden die Zertifikate unter der angegeben [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) .

## <a name="mapping-a-certificate-to-a-user-account"></a>Zuordnen eines Zertifikats zu einem Benutzerkonto

IIS und Active Directory bieten u. a. die Möglichkeit, ein Zertifikat einem Windows-Benutzerkonto zuzuordnen. Weitere Informationen über das Feature finden Sie unter [Map certificates to user accounts (Zuordnen von Zertifikaten zu Benutzerkonten)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc736706(v=ws.10)).

Informationen zur Verwendung der Azure Directory-Zuweisung finden Sie unter [Mapping Client Certificates with Directory Service Mapping (Zuordnen von Clientzertifikaten mit der Verzeichnisdienstzuordnung)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc758484(v=ws.10)).

Wenn diese Funktion aktiviert ist, können Sie die <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A>-Eigenschaft der <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>-Klasse auf `true` festlegen. In der Konfiguration können Sie das- `mapClientCertificateToWindowsAccount` Attribut des- [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) Elements auf festlegen `true` , wie im folgenden Code gezeigt.

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

Die Zuordnung eines X.509-Zertifikats zu einem Token, das ein Windows-Benutzerkonto darstellt, wird als Erweiterung der Berechtigungen angesehen, da das Windows-Token nach der Zuordnung Zugriff auf geschützte Ressourcen ermöglicht. Das X.509-Zertifikat muss daher vor der Zuordnung die entsprechenden Anforderungen der Domänenrichtlinie erfüllen. Dies wird durch das *SChannel*-Sicherheitspaket sichergestellt.

Wenn Sie .NET Framework 3,5 oder höhere Versionen verwenden, stellt WCF sicher, dass das Zertifikat der Domänen Richtlinie entspricht, bevor es einem Windows-Konto zugeordnet wird.

Im ersten Release von WCF erfolgt die Zuordnung ohne auf die Domänenrichtlinie zurückzugreifen. Möglicherweise tritt daher bei älteren Anwendungen, die mit dem ersten Release ausgeführt werden konnten, ein Fehler auf, wenn die Zuordnung aktiviert ist und die Anforderungen der Domänenrichtlinie vom X.509-Zertifikat nicht erfüllt werden.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Security>
- <xref:System.ServiceModel>
- <xref:System.Security.Cryptography.X509Certificates.X509FindType>
- [Sichern von Diensten und Clients](securing-services-and-clients.md)
