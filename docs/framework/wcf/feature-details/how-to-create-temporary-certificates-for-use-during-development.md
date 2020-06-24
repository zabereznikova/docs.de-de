---
title: 'Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung'
description: Erfahren Sie, wie Sie mit einem PowerShell-Cmdlet zwei temporäre X. 509-Zertifikate erstellen, die für die Entwicklung eines sicheren WCF-Dienstanbieter oder-Clients verwendet werden.
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 0a21548386639a9f6a8c8572e5d7928ffdb270d6
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247038"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="f97ce-103">Vorgehensweise: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="f97ce-103">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="f97ce-104">Wenn Sie mit Windows Communication Foundation (WCF) einen sicheren Dienst oder Client entwickeln, müssen Sie häufig ein X. 509-Zertifikat angeben, das als Anmelde Informationen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f97ce-104">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="f97ce-105">Das Zertifikat ist normalerweise Teil einer Zertifikatskette mit einer Stammstelle, die im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen des Computers enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="f97ce-105">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="f97ce-106">Wenn Sie über eine Zertifikatskette verfügen, können Sie einen Bereich mit Zertifikatsätzen angeben, wobei die Stammzertifizierungsstelle normalerweise von Ihrer Organisation bzw. Ihrem Geschäftsbereich stammt.</span><span class="sxs-lookup"><span data-stu-id="f97ce-106">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="f97ce-107">Um dies zur Entwicklungszeit zu emulieren, können Sie zwei Zertifikate erstellen, um die Sicherheitsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f97ce-107">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="f97ce-108">Beim ersten Zertifikat handelt es sich um ein selbstsigniertes Zertifikat, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird. Das zweite Zertifikat wird aus dem ersten Zertifikat erstellt und entweder in den persönlichen Speicher unter "Lokaler Computer" oder in den persönlichen Speicher unter "Aktueller Benutzer" eingefügt.</span><span class="sxs-lookup"><span data-stu-id="f97ce-108">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="f97ce-109">In diesem Thema werden die Schritte zum Erstellen dieser beiden Zertifikate mit dem PowerShell-Cmdlet " [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) " erläutert.</span><span class="sxs-lookup"><span data-stu-id="f97ce-109">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f97ce-110">Die Zertifikate, die das New-selfsignedcertificate-Cmdlet generiert, werden nur zu Testzwecken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f97ce-110">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="f97ce-111">Beim Bereitstellen eines Diensts oder Clients sollten Sie ein geeignetes Zertifikat einer Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="f97ce-111">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="f97ce-112">Dies kann entweder von einem Windows Server-Zertifikat Server in Ihrer Organisation oder von einem Drittanbieter erfolgen.</span><span class="sxs-lookup"><span data-stu-id="f97ce-112">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="f97ce-113">Standardmäßig erstellt das Cmdlet " [New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) " Zertifikate, die selbst signiert sind, und diese Zertifikate sind unsicher.</span><span class="sxs-lookup"><span data-stu-id="f97ce-113">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="f97ce-114">Wenn Sie die selbst signierten Zertifikate in den Speicher für vertrauenswürdige Stamm Zertifizierungsstellen platzieren, können Sie eine Entwicklungsumgebung erstellen, die Ihre Bereitstellungs Umgebung genauer simuliert.</span><span class="sxs-lookup"><span data-stu-id="f97ce-114">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="f97ce-115">Weitere Informationen zum Erstellen und Verwenden von Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f97ce-115">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="f97ce-116">Weitere Informationen zur Verwendung eines Zertifikats als Anmelde Informationen finden Sie unter [Sichern von Diensten und Clients](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f97ce-116">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="f97ce-117">Ein Lernprogramm zur Verwendung der Microsoft Authenticode-Technologie finden Sie unter [Authenticode Overviews and Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="f97ce-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="f97ce-118">So erstellen Sie ein selbstsigniertes Stammzertifizierungsstellen-Zertifikat und exportieren den privaten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f97ce-118">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="f97ce-119">Der folgende Befehl erstellt ein selbst signiertes Zertifikat mit dem Antragsteller Namen "rootca" im persönlichen Speicher des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f97ce-119">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
$rootcert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

<span data-ttu-id="f97ce-120">Wir müssen das Zertifikat in eine PFX-Datei exportieren, damit es in einem späteren Schritt in importiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f97ce-120">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="f97ce-121">Beim Exportieren eines Zertifikats mit dem privaten Schlüssel ist ein Kennwort erforderlich, um es zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f97ce-121">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="f97ce-122">Wir speichern das Kennwort in einer `SecureString` und verwenden das [Export-pfxcertificate-](/powershell/module/pkiclient/export-pfxcertificate) Cmdlet, um das Zertifikat mit dem zugehörigen privaten Schlüssel in eine PFX-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="f97ce-122">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="f97ce-123">Mithilfe des Cmdlets " [Export-Certificate](/powershell/module/pkiclient/export-certificate) " wird auch nur das öffentliche Zertifikat in einer CRT-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f97ce-123">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
[System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="f97ce-124">So erstellen Sie ein neues von einem Stammzertifizierungsstellen-Zertifikat signiertes Zertifikat</span><span class="sxs-lookup"><span data-stu-id="f97ce-124">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="f97ce-125">Mit dem folgenden Befehl wird ein vom signiertes Zertifikat mit dem Antragsteller `RootCA` Namen "signedbyrootca" erstellt, wobei der private Schlüssel des Ausstellers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f97ce-125">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="f97ce-126">Ebenso speichern wir das signierte Zertifikat mit privatem Schlüssel in einer PFX-Datei und nur den öffentlichen Schlüssel in einer CRT-Datei.</span><span class="sxs-lookup"><span data-stu-id="f97ce-126">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="f97ce-127">Installieren eines Zertifikats im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen</span><span class="sxs-lookup"><span data-stu-id="f97ce-127">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="f97ce-128">Nachdem ein selbstsigniertes Zertifikat erstellt wurde, können Sie es im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installieren.</span><span class="sxs-lookup"><span data-stu-id="f97ce-128">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="f97ce-129">Alle Zertifikate, die zu diesem Zeitpunkt mit dem Zertifikat signiert sind, werden vom Computer als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="f97ce-129">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="f97ce-130">Aus diesem Grund sollten Sie das Zertifikat aus dem Speicher löschen, sobald Sie es nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="f97ce-130">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="f97ce-131">Wenn Sie dieses Stammzertifizierungsstellen-Zertifikat löschen, verlieren auch alle anderen Zertifikate, die zusammen damit signiert wurden, ihre Zertifizierung.</span><span class="sxs-lookup"><span data-stu-id="f97ce-131">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="f97ce-132">Bei Stammzertifizierungsstellen-Zertifikaten handelt es sich einfach um einen Mechanismus, bei dem der Gültigkeitsbereich einer Gruppe von Zertifikaten festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f97ce-132">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="f97ce-133">Bei der Verwendung von Peer-to-Peer-Anwendungen ist eine Stammzertifizierungsstelle zum Beispiel normalerweise nicht erforderlich, weil Sie der Identität einer Person einfach aufgrund ihres bereitgestellten Zertifikats vertrauen.</span><span class="sxs-lookup"><span data-stu-id="f97ce-133">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="f97ce-134">So installieren Sie ein selbstsigniertes Zertifikat im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen</span><span class="sxs-lookup"><span data-stu-id="f97ce-134">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="f97ce-135">Öffnen Sie das Zertifikat-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="f97ce-135">Open the certificate snap-in.</span></span> <span data-ttu-id="f97ce-136">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="f97ce-136">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="f97ce-137">Öffnen Sie den Ordner, um das Zertifikat zu speichern, also entweder **Lokaler Computer** oder **Aktueller Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f97ce-137">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="f97ce-138">Öffnen Sie den Ordner **Vertrauenswürdige Stammzertifizierungsstellen** .</span><span class="sxs-lookup"><span data-stu-id="f97ce-138">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="f97ce-139">Klicken Sie mit der rechten Maustaste auf den Ordner **Zertifikate** , und klicken Sie auf **Alle Aufgaben**und anschließend auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="f97ce-139">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="f97ce-140">Befolgen Sie die Anweisungen auf dem Bildschirm, um die Datei rootca. pfx in den Speicher zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f97ce-140">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="f97ce-141">Verwenden von Zertifikaten mit WCF</span><span class="sxs-lookup"><span data-stu-id="f97ce-141">Using certificates With WCF</span></span>

<span data-ttu-id="f97ce-142">Nach dem Einrichten der temporären Zertifikate können diese verwendet werden, um WCF-Lösungen zu entwickeln, mit denen Zertifikate als Clientanmeldeinformationstyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f97ce-142">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="f97ce-143">So gibt beispielsweise die folgende XML-Konfiguration Nachrichtensicherheit und ein Zertifikat als Clientanmeldeinformationstyp an.</span><span class="sxs-lookup"><span data-stu-id="f97ce-143">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="f97ce-144">So geben Sie ein Zertifikat als Clientanmeldeinformationstyp an</span><span class="sxs-lookup"><span data-stu-id="f97ce-144">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="f97ce-145">Verwenden Sie in der Konfigurationsdatei für einen Dienst die folgende XML, um den Sicherheitsmodus auf die Nachrichtenebene und den Clientanmeldeinformationstyp auf Zertifikate festzulegen:</span><span class="sxs-lookup"><span data-stu-id="f97ce-145">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

2. <span data-ttu-id="f97ce-146">Verwenden Sie in der Konfigurationsdatei für einen Client die folgende XML, um anzugeben, dass sich das Zertifikat im Speicher des Benutzers befindet, und suchen Sie, indem Sie im Feld "subjetname" nach dem Wert "cohuwinery" suchen.</span><span class="sxs-lookup"><span data-stu-id="f97ce-146">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="f97ce-147">Weitere Informationen zum Verwenden von Zertifikaten in WCF finden Sie unter [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="f97ce-147">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="f97ce-148">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f97ce-148">.NET Framework security</span></span>

<span data-ttu-id="f97ce-149">Achten Sie darauf, alle temporären Stammzertifizierungsstellen-Zertifikate aus den Ordnern **Vertrauenswürdige Stammzertifizierungsstellen** und **Persönlich** zu löschen, indem Sie mit der rechten Maustaste auf das Zertifikat klicken und anschließend auf **Löschen**klicken.</span><span class="sxs-lookup"><span data-stu-id="f97ce-149">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f97ce-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f97ce-150">See also</span></span>

- [<span data-ttu-id="f97ce-151">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="f97ce-151">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="f97ce-152">Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In</span><span class="sxs-lookup"><span data-stu-id="f97ce-152">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="f97ce-153">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="f97ce-153">Securing Services and Clients</span></span>](securing-services-and-clients.md)
