---
title: 'Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: d45f18b0b8fe4e0cc9667091e166c80691faa2d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773294"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung

Wenn Sie einen sicheren Dienst oder Client mit Windows Communication Foundation (WCF) zu entwickeln, ist es oft notwendig, geben Sie ein x. 509-Zertifikat als Anmeldeinformationen verwendet werden soll. Das Zertifikat ist normalerweise Teil einer Zertifikatskette mit einer Stammstelle, die im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen des Computers enthalten ist. Wenn Sie über eine Zertifikatskette verfügen, können Sie einen Bereich mit Zertifikatsätzen angeben, wobei die Stammzertifizierungsstelle normalerweise von Ihrer Organisation bzw. Ihrem Geschäftsbereich stammt. Um dies zur Entwicklungszeit zu emulieren, können Sie zwei Zertifikate erstellen, um die Sicherheitsanforderungen zu erfüllen. Beim ersten Zertifikat handelt es sich um ein selbstsigniertes Zertifikat, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird. Das zweite Zertifikat wird aus dem ersten Zertifikat erstellt und entweder in den persönlichen Speicher unter "Lokaler Computer" oder in den persönlichen Speicher unter "Aktueller Benutzer" eingefügt. Dieses Thema führt durch die Schritte zum Erstellen dieser beiden Zertifikate mithilfe von Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) Cmdlet.

> [!IMPORTANT]
> Die Zertifikate, die das Cmdlet "New-SelfSignedCertificate" generiert werden nur für Testzwecke bereitgestellt. Beim Bereitstellen eines Diensts oder Clients sollten Sie ein geeignetes Zertifikat einer Zertifizierungsstelle verwenden. Dies kann entweder von einem Zertifikatserver für Windows Server in Ihrer Organisation werden oder einem Drittanbieter.
>
> In der Standardeinstellung die [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) -Cmdlet erstellt die Zertifikate, die Zertifikate selbstsigniert sind, und diese Zertifikate sind unsicher. Platzieren die selbstsignierten Zertifikate in der vertrauenswürdigen Stammzertifizierungsstellen ermöglicht Store Ihnen die Erstellung eine Entwicklungsumgebung, die Ihre bereitstellungsumgebung besser simuliert.

 Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [arbeiten mit Zertifikaten](working-with-certificates.md). Weitere Informationen zur Verwendung von einem Zertifikat als Anmeldeinformationen finden Sie unter [Sichern von Diensten und Clients](securing-services-and-clients.md). Ein Lernprogramm zur Verwendung der Microsoft Authenticode-Technologie finden Sie unter [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>So erstellen Sie ein selbstsigniertes Stammzertifizierungsstellen-Zertifikat und exportieren den privaten Schlüssel

Der folgende Befehl erstellt ein selbstsigniertes Zertifikat mit dem Antragstellernamen "Stammzertifizierungsstelle" im Aktueller Benutzer persönlich Speicher.

```powershell
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```

Wir müssen das Zertifikat in eine PFX-Datei exportieren, sodass es importiert werden kann, wo sie in einem späteren Schritt benötigt wird. Wenn Sie ein Zertifikat mit dem privaten Schlüssel exportieren, ist ein Kennwort erforderlich, für den Schutz aus. Wir speichern das Kennwort in einer `SecureString` und verwenden Sie die [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) Cmdlet, um das Zertifikat mit dem zugehörigen privaten Schlüssel in eine PFX-Datei zu exportieren. Wir speichern auch nur das öffentliche Zertifikat in einer CRT-Datei mithilfe der [Export-Certificate](/powershell/module/pkiclient/export-certificate) Cmdlet.

```powershell
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>So erstellen Sie ein neues von einem Stammzertifizierungsstellen-Zertifikat signiertes Zertifikat

Der folgende Befehl erstellt ein Testzertifikat signiertes Zertifikat der `RootCA` mit dem Antragstellernamen "SignedByRootCA" mit dem privaten Schlüssel des Ausstellers.

```powershell
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

Auf ähnliche Weise speichern wir das Zertifikat mit privatem Schlüssel in eine PFX-Datei und nur den öffentlichen Schlüssel in einer CRT-Datei ein.

```powershell
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Installieren eines Zertifikats im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen

Nachdem ein selbstsigniertes Zertifikat erstellt wurde, können Sie es im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installieren. Alle Zertifikate, die zu diesem Zeitpunkt mit dem Zertifikat signiert sind, werden vom Computer als vertrauenswürdig eingestuft. Aus diesem Grund sollten Sie das Zertifikat aus dem Speicher löschen, sobald Sie es nicht mehr benötigen. Wenn Sie dieses Stammzertifizierungsstellen-Zertifikat löschen, verlieren auch alle anderen Zertifikate, die zusammen damit signiert wurden, ihre Zertifizierung. Bei Stammzertifizierungsstellen-Zertifikaten handelt es sich einfach um einen Mechanismus, bei dem der Gültigkeitsbereich einer Gruppe von Zertifikaten festgelegt werden kann. Bei der Verwendung von Peer-to-Peer-Anwendungen ist eine Stammzertifizierungsstelle zum Beispiel normalerweise nicht erforderlich, weil Sie der Identität einer Person einfach aufgrund ihres bereitgestellten Zertifikats vertrauen.

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>So installieren Sie ein selbstsigniertes Zertifikat im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen

1. Öffnen Sie das Zertifikat-Snap-In. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).

2. Öffnen Sie den Ordner, um das Zertifikat zu speichern, also entweder **Lokaler Computer** oder **Aktueller Benutzer**.

3. Öffnen Sie den Ordner **Vertrauenswürdige Stammzertifizierungsstellen** .

4. Klicken Sie mit der rechten Maustaste auf den Ordner **Zertifikate** , und klicken Sie auf **Alle Aufgaben**und anschließend auf **Importieren**.

5. Führen Sie den Assistenten auf dem Bildschirm Anweisungen, um die RootCA.pfx in den Speicher zu importieren.

## <a name="using-certificates-with-wcf"></a>Verwenden von Zertifikaten mit WCF

Nach dem Einrichten der temporären Zertifikate können diese verwendet werden, um WCF-Lösungen zu entwickeln, mit denen Zertifikate als Clientanmeldeinformationstyp angegeben werden. So gibt beispielsweise die folgende XML-Konfiguration Nachrichtensicherheit und ein Zertifikat als Clientanmeldeinformationstyp an.

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a>So geben Sie ein Zertifikat als Clientanmeldeinformationstyp an

1. Verwenden Sie in der Konfigurationsdatei für einen Dienst die folgende XML, um den Sicherheitsmodus auf die Nachrichtenebene und den Clientanmeldeinformationstyp auf Zertifikate festzulegen:

    ```xml
    <bindings>
      <wsHttpBinding>
        <binding name="CertificateForClient">
          <security>
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    ```

2. Verwenden Sie in der Konfigurationsdatei für einen Client das folgende XML, um anzugeben, dass das Zertifikat im Speicher des Benutzers gefunden wird, und kann durch Durchsuchen des SubjectName-Felds für den Wert "CohoWinery" gefunden werden

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="CertForClient">
          <clientCredentials>
            <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

Weitere Informationen zum Verwenden von Zertifikaten in WCF finden Sie unter [Working with Certificates](working-with-certificates.md).

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Achten Sie darauf, alle temporären Stammzertifizierungsstellen-Zertifikate aus den Ordnern **Vertrauenswürdige Stammzertifizierungsstellen** und **Persönlich** zu löschen, indem Sie mit der rechten Maustaste auf das Zertifikat klicken und anschließend auf **Löschen**klicken.

## <a name="see-also"></a>Siehe auch

- [Arbeiten mit Zertifikaten](working-with-certificates.md)
- [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md)
- [Sichern von Diensten und Clients](securing-services-and-clients.md)
