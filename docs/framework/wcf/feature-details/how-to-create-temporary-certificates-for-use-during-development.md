---
title: 'Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung'
description: Erfahren Sie, wie Sie mit einem PowerShell-Cmdlet zwei temporäre X. 509-Zertifikate erstellen, die für die Entwicklung eines sicheren WCF-Dienstanbieter oder-Clients verwendet werden.
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: a249f0de00c45b1588762ffa0f826e890f961334
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91607771"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a>Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung

Wenn Sie mit Windows Communication Foundation (WCF) einen sicheren Dienst oder Client entwickeln, müssen Sie häufig ein X. 509-Zertifikat angeben, das als Anmelde Informationen verwendet werden soll. Das Zertifikat ist normalerweise Teil einer Zertifikatskette mit einer Stammstelle, die im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen des Computers enthalten ist. Wenn Sie über eine Zertifikatskette verfügen, können Sie einen Bereich mit Zertifikatsätzen angeben, wobei die Stammzertifizierungsstelle normalerweise von Ihrer Organisation bzw. Ihrem Geschäftsbereich stammt. Um dies zur Entwicklungszeit zu emulieren, können Sie zwei Zertifikate erstellen, um die Sicherheitsanforderungen zu erfüllen. Beim ersten Zertifikat handelt es sich um ein selbstsigniertes Zertifikat, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird. Das zweite Zertifikat wird aus dem ersten Zertifikat erstellt und entweder in den persönlichen Speicher unter "Lokaler Computer" oder in den persönlichen Speicher unter "Aktueller Benutzer" eingefügt. In diesem Thema werden die Schritte zum Erstellen dieser beiden Zertifikate mit dem PowerShell-Cmdlet " [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) " erläutert.

> [!IMPORTANT]
> Die Zertifikate, die das New-selfsignedcertificate-Cmdlet generiert, werden nur zu Testzwecken bereitgestellt. Beim Bereitstellen eines Diensts oder Clients sollten Sie ein geeignetes Zertifikat einer Zertifizierungsstelle verwenden. Dies kann entweder von einem Windows Server-Zertifikat Server in Ihrer Organisation oder von einem Drittanbieter erfolgen.
>
> Standardmäßig erstellt das Cmdlet " [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) " Zertifikate, die selbst signiert sind, und diese Zertifikate sind unsicher. Wenn Sie die selbst signierten Zertifikate in den Speicher für vertrauenswürdige Stamm Zertifizierungsstellen platzieren, können Sie eine Entwicklungsumgebung erstellen, die Ihre Bereitstellungs Umgebung genauer simuliert.

 Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md). Weitere Informationen zur Verwendung eines Zertifikats als Anmelde Informationen finden Sie unter [Sichern von Diensten und Clients](securing-services-and-clients.md). Ein Lernprogramm zur Verwendung der Microsoft Authenticode-Technologie finden Sie unter [Authenticode Overviews and Tutorials](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a>So erstellen Sie ein selbstsigniertes Stammzertifizierungsstellen-Zertifikat und exportieren den privaten Schlüssel

Der folgende Befehl erstellt ein selbst signiertes Zertifikat mit dem Antragsteller Namen "rootca" im persönlichen Speicher des aktuellen Benutzers.

```powershell
$rootcert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

Wir müssen das Zertifikat in eine PFX-Datei exportieren, damit es in einem späteren Schritt in importiert werden kann. Beim Exportieren eines Zertifikats mit dem privaten Schlüssel ist ein Kennwort erforderlich, um es zu schützen. Wir speichern das Kennwort in einer `SecureString` und verwenden das [Export-pfxcertificate-](/powershell/module/pkiclient/export-pfxcertificate) Cmdlet, um das Zertifikat mit dem zugehörigen privaten Schlüssel in eine PFX-Datei zu exportieren. Mithilfe des Cmdlets " [Export-Certificate](/powershell/module/pkiclient/export-certificate) " wird auch nur das öffentliche Zertifikat in einer CRT-Datei gespeichert.

```powershell
[System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a>So erstellen Sie ein neues von einem Stammzertifizierungsstellen-Zertifikat signiertes Zertifikat

Mit dem folgenden Befehl wird ein vom signiertes Zertifikat mit dem Antragsteller `RootCA` Namen "signedbyrootca" erstellt, wobei der private Schlüssel des Ausstellers verwendet wird.

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

Ebenso speichern wir das signierte Zertifikat mit privatem Schlüssel in einer PFX-Datei und nur den öffentlichen Schlüssel in einer CRT-Datei.

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a>Installieren eines Zertifikats im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen

Nachdem ein selbstsigniertes Zertifikat erstellt wurde, können Sie es im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installieren. Alle Zertifikate, die zu diesem Zeitpunkt mit dem Zertifikat signiert sind, werden vom Computer als vertrauenswürdig eingestuft. Aus diesem Grund sollten Sie das Zertifikat aus dem Speicher löschen, sobald Sie es nicht mehr benötigen. Wenn Sie dieses Stammzertifizierungsstellen-Zertifikat löschen, verlieren auch alle anderen Zertifikate, die zusammen damit signiert wurden, ihre Zertifizierung. Bei Stammzertifizierungsstellen-Zertifikaten handelt es sich einfach um einen Mechanismus, bei dem der Gültigkeitsbereich einer Gruppe von Zertifikaten festgelegt werden kann. Bei der Verwendung von Peer-to-Peer-Anwendungen ist eine Stammzertifizierungsstelle zum Beispiel normalerweise nicht erforderlich, weil Sie der Identität einer Person einfach aufgrund ihres bereitgestellten Zertifikats vertrauen.

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a>So installieren Sie ein selbstsigniertes Zertifikat im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen

1. Öffnen Sie das Zertifikat-Snap-In. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](how-to-view-certificates-with-the-mmc-snap-in.md).

2. Öffnen Sie den Ordner, um das Zertifikat zu speichern, also entweder **Lokaler Computer** oder **Aktueller Benutzer**.

3. Öffnen Sie den Ordner **Vertrauenswürdige Stammzertifizierungsstellen** .

4. Klicken Sie mit der rechten Maustaste auf den Ordner **Zertifikate** , und klicken Sie auf **Alle Aufgaben**und anschließend auf **Importieren**.

5. Befolgen Sie die Anweisungen auf dem Bildschirm, um die Datei rootca. pfx in den Speicher zu importieren.

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

2. Verwenden Sie in der Konfigurationsdatei für einen Client die folgende XML, um anzugeben, dass sich das Zertifikat im Speicher des Benutzers befindet, und suchen Sie, indem Sie im Feld "subjetname" nach dem Wert "cohuwinery" suchen.

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

## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Zertifikaten](working-with-certificates.md)
- [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](how-to-view-certificates-with-the-mmc-snap-in.md)
- [Sichern von Diensten und Clients](securing-services-and-clients.md)
