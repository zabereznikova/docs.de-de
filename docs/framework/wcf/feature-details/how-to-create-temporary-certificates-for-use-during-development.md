---
title: 'Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ccbc8c6fa638c674dea28c312b2dedbc9d41968a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="7ee63-102">Gewusst wie: Erstellen von temporären Zertifikaten für die Verwendung während der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="7ee63-102">How to: Create Temporary Certificates for Use During Development</span></span>
<span data-ttu-id="7ee63-103">Wenn Sie mithilfe von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]einen sicheren Dienst oder Client entwickeln, müssen Sie häufig ein X.509-Zertifikat angeben, das für die Anmeldeinformationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ee63-103">When developing a secure service or client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="7ee63-104">Das Zertifikat ist normalerweise Teil einer Zertifikatskette mit einer Stammstelle, die im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen des Computers enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7ee63-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="7ee63-105">Wenn Sie über eine Zertifikatskette verfügen, können Sie einen Bereich mit Zertifikatsätzen angeben, wobei die Stammzertifizierungsstelle normalerweise von Ihrer Organisation bzw. Ihrem Geschäftsbereich stammt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="7ee63-106">Um dies zur Entwicklungszeit zu emulieren, können Sie zwei Zertifikate erstellen, um die Sicherheitsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="7ee63-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="7ee63-107">Beim ersten Zertifikat handelt es sich um ein selbstsigniertes Zertifikat, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird. Das zweite Zertifikat wird aus dem ersten Zertifikat erstellt und entweder in den persönlichen Speicher unter "Lokaler Computer" oder in den persönlichen Speicher unter "Aktueller Benutzer" eingefügt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="7ee63-108">In diesem Thema sind die Schritte zur Erstellung dieser beiden Zertifikate beschrieben. Dabei wird das [Certificate Creation-Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185)verwendet, das im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -SDK enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7ee63-108">This topic walks through the steps to create these two certificates using the [Certificate Creation Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), which is provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7ee63-109">Die Zertifikate, die das Certificate Creation-Tool generiert, werden nur zu Testzwecken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-109">The certificates the Certification Creation tool generates are provided for testing purposes only.</span></span> <span data-ttu-id="7ee63-110">Beim Bereitstellen eines Diensts oder Clients sollten Sie ein geeignetes Zertifikat einer Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="7ee63-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="7ee63-111">Dies kann entweder von einem [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] -Zertifikatsserver Ihrer Organisation oder von einem Drittanbieter stammen.</span><span class="sxs-lookup"><span data-stu-id="7ee63-111">This could either be from a [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] certificate server in your organization or a third party.</span></span>  
>   
>  <span data-ttu-id="7ee63-112">Wird standardmäßig die [Makecert.exe (Certificate Creation-Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) erstellt Zertifikate, deren Stammzertifizierungsstelle heißt "Root Agency **."**</span><span class="sxs-lookup"><span data-stu-id="7ee63-112">By default, the [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) creates certificates whose root authority is called "Root Agency **."**</span></span> <span data-ttu-id="7ee63-113">Da sich die Stammzertifizierungsstelle ("Root Agency") nicht im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen befindet, sind diese Zertifikate nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="7ee63-113">Because the "Root Agency" is not in the Trusted Root Certification Authorities store, this makes these certificates insecure.</span></span> <span data-ttu-id="7ee63-114">Indem Sie ein selbstsigniertes Zertifikat erstellen, das in den Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen eingefügt wird, können sie eine Entwicklungsumgebung anlegen, die eine bessere Simulation Ihrer Bereitstellungsumgebung darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-114">Creating a self-signed certificate that is placed in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7ee63-115"> zum Erstellen und Verwenden von Zertifikaten finden Sie unter [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="7ee63-115"> creating and using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7ee63-116"> zum Verwenden eines Zertifikats für die Anmeldeinformationen finden Sie unter [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="7ee63-116"> using a certificate as a credential, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="7ee63-117">Ein Lernprogramm zur Verwendung der Microsoft Authenticode-Technologie finden Sie unter [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="7ee63-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).</span></span>  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="7ee63-118">So erstellen Sie ein selbstsigniertes Stammzertifizierungsstellen-Zertifikat und exportieren den privaten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="7ee63-118">To create a self-signed root authority certificate and export the private key</span></span>  
  
1.  <span data-ttu-id="7ee63-119">Verwenden Sie das Tool MakeCert.exe mit den folgenden Schaltern:</span><span class="sxs-lookup"><span data-stu-id="7ee63-119">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="7ee63-120">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-120">`-n` `subjectName`.</span></span> <span data-ttu-id="7ee63-121">Gibt den Namen des Antragstellers an.</span><span class="sxs-lookup"><span data-stu-id="7ee63-121">Specifies the subject name.</span></span> <span data-ttu-id="7ee63-122">Normalerweise wird dem Namen des Antragstellers als Präfix "CN = " ("Common Name", gemeinsamer Name) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-122">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    2.  <span data-ttu-id="7ee63-123">`-r`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-123">`-r`.</span></span> <span data-ttu-id="7ee63-124">Gibt an, dass das Zertifikat selbstsigniert ist.</span><span class="sxs-lookup"><span data-stu-id="7ee63-124">Specifies that the certificate will be self-signed.</span></span>  
  
    3.  <span data-ttu-id="7ee63-125">`-sv` `privateKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-125">`-sv` `privateKeyFile`.</span></span> <span data-ttu-id="7ee63-126">Gibt die Datei an, die den Container für den privaten Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="7ee63-126">Specifies the file that contains the private key container.</span></span>  
  
     <span data-ttu-id="7ee63-127">Der folgende Befehl erstellt zum Beispiel ein selbstsigniertes Zertifikat mit dem Antragstellernamen "CN=TempCA".</span><span class="sxs-lookup"><span data-stu-id="7ee63-127">For example, the following command creates a self-signed certificate with a subject name of "CN=TempCA."</span></span>  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     <span data-ttu-id="7ee63-128">Sie werden aufgefordert, ein Kennwort anzugeben, um den privaten Schlüssel zu schützen.</span><span class="sxs-lookup"><span data-stu-id="7ee63-128">You will be prompted to provide a password to protect the private key.</span></span> <span data-ttu-id="7ee63-129">Dieses Kennwort ist erforderlich, wenn sie ein von diesem Stammzertifikat signiertes Zertifikat erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ee63-129">This password is required when creating a certificate signed by this root certificate.</span></span>  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="7ee63-130">So erstellen Sie ein neues von einem Stammzertifizierungsstellen-Zertifikat signiertes Zertifikat</span><span class="sxs-lookup"><span data-stu-id="7ee63-130">To create a new certificate signed by a root authority certificate</span></span>  
  
1.  <span data-ttu-id="7ee63-131">Verwenden Sie das Tool MakeCert.exe mit den folgenden Schaltern:</span><span class="sxs-lookup"><span data-stu-id="7ee63-131">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="7ee63-132">`-sk` `subjectKey`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-132">`-sk` `subjectKey`.</span></span> <span data-ttu-id="7ee63-133">Der Speicherort des Schlüsselcontainers des Antragstellers, in dem der private Schlüssel gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="7ee63-133">The location of the subject's key container that holds the private key.</span></span> <span data-ttu-id="7ee63-134">Wenn kein Schlüsselcontainer vorhanden ist, wird ein Schlüsselcontainer erstellt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-134">If a key container does not exist, one is created.</span></span> <span data-ttu-id="7ee63-135">Wenn weder die Option "-sk" noch die Option "-sv" verwendet wird, wird standardmäßig ein Schlüsselcontainer mit dem Namen "JoeSoft" erstellt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-135">If neither of the -sk or -sv options is used, a key container called JoeSoft is created by default.</span></span>  
  
    2.  <span data-ttu-id="7ee63-136">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-136">`-n` `subjectName`.</span></span> <span data-ttu-id="7ee63-137">Gibt den Namen des Antragstellers an.</span><span class="sxs-lookup"><span data-stu-id="7ee63-137">Specifies the subject name.</span></span> <span data-ttu-id="7ee63-138">Normalerweise wird dem Namen des Antragstellers als Präfix "CN = " ("Common Name", gemeinsamer Name) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7ee63-138">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    3.  <span data-ttu-id="7ee63-139">`-iv` `issuerKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-139">`-iv` `issuerKeyFile`.</span></span> <span data-ttu-id="7ee63-140">Gibt die Datei für den privaten Schlüssel des Herausgebers an.</span><span class="sxs-lookup"><span data-stu-id="7ee63-140">Specifies the issuer's private key file.</span></span>  
  
    4.  <span data-ttu-id="7ee63-141">`-ic` `issuerCertFile`.</span><span class="sxs-lookup"><span data-stu-id="7ee63-141">`-ic` `issuerCertFile`.</span></span> <span data-ttu-id="7ee63-142">Gibt den Speicherort für das Zertifikat des Herausgebers an.</span><span class="sxs-lookup"><span data-stu-id="7ee63-142">Specifies the location of the issuer's certificate.</span></span>  
  
     <span data-ttu-id="7ee63-143">Der folgende Befehl erstellt zum Beispiel ein Zertifikat, das von der Stammzertifizierungsstelle `TempCA` mit dem Antragstellernamen `"CN=SignedByCA"` signiert wird, indem der private Schlüssel des Herausgebers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ee63-143">For example, the following command creates a certificate signed by the `TempCA` root authority certificate with a subject name of `"CN=SignedByCA"` using the private key of the issuer.</span></span>  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="7ee63-144">Installieren eines Zertifikats im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen</span><span class="sxs-lookup"><span data-stu-id="7ee63-144">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>  
 <span data-ttu-id="7ee63-145">Nachdem ein selbstsigniertes Zertifikat erstellt wurde, können Sie es im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installieren.</span><span class="sxs-lookup"><span data-stu-id="7ee63-145">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="7ee63-146">Alle Zertifikate, die zu diesem Zeitpunkt mit dem Zertifikat signiert sind, werden vom Computer als vertrauenswürdig eingestuft.</span><span class="sxs-lookup"><span data-stu-id="7ee63-146">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="7ee63-147">Aus diesem Grund sollten Sie das Zertifikat aus dem Speicher löschen, sobald Sie es nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="7ee63-147">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="7ee63-148">Wenn Sie dieses Stammzertifizierungsstellen-Zertifikat löschen, verlieren auch alle anderen Zertifikate, die zusammen damit signiert wurden, ihre Zertifizierung.</span><span class="sxs-lookup"><span data-stu-id="7ee63-148">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="7ee63-149">Bei Stammzertifizierungsstellen-Zertifikaten handelt es sich einfach um einen Mechanismus, bei dem der Gültigkeitsbereich einer Gruppe von Zertifikaten festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7ee63-149">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="7ee63-150">Bei der Verwendung von Peer-to-Peer-Anwendungen ist eine Stammzertifizierungsstelle zum Beispiel normalerweise nicht erforderlich, weil Sie der Identität einer Person einfach aufgrund ihres bereitgestellten Zertifikats vertrauen.</span><span class="sxs-lookup"><span data-stu-id="7ee63-150">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="7ee63-151">So installieren Sie ein selbstsigniertes Zertifikat im Speicher mit den vertrauenswürdigen Stammzertifizierungsstellen</span><span class="sxs-lookup"><span data-stu-id="7ee63-151">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>  
  
1.  <span data-ttu-id="7ee63-152">Öffnen Sie das Zertifikat-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="7ee63-152">Open the certificate snap-in.</span></span> <span data-ttu-id="7ee63-153">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="7ee63-153">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="7ee63-154">Öffnen Sie den Ordner, um das Zertifikat zu speichern, also entweder **Lokaler Computer** oder **Aktueller Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7ee63-154">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>  
  
3.  <span data-ttu-id="7ee63-155">Öffnen Sie den Ordner **Vertrauenswürdige Stammzertifizierungsstellen** .</span><span class="sxs-lookup"><span data-stu-id="7ee63-155">Open the **Trusted Root Certification Authorities** folder.</span></span>  
  
4.  <span data-ttu-id="7ee63-156">Klicken Sie mit der rechten Maustaste auf den Ordner **Zertifikate** , und klicken Sie auf **Alle Aufgaben**und anschließend auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="7ee63-156">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>  
  
5.  <span data-ttu-id="7ee63-157">Folgen Sie den Anweisungen des Assistenten auf dem Bildschirm, um die Datei TempCa.cer in den Speicher zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7ee63-157">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>  
  
## <a name="using-certificates-with-wcf"></a><span data-ttu-id="7ee63-158">Verwenden von Zertifikaten mit WCF</span><span class="sxs-lookup"><span data-stu-id="7ee63-158">Using Certificates With WCF</span></span>  
 <span data-ttu-id="7ee63-159">Nach dem Einrichten der temporären Zertifikate können diese verwendet werden, um WCF-Lösungen zu entwickeln, mit denen Zertifikate als Clientanmeldeinformationstyp angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7ee63-159">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="7ee63-160">So gibt beispielsweise die folgende XML-Konfiguration Nachrichtensicherheit und ein Zertifikat als Clientanmeldeinformationstyp an.</span><span class="sxs-lookup"><span data-stu-id="7ee63-160">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="7ee63-161">So geben Sie ein Zertifikat als Clientanmeldeinformationstyp an</span><span class="sxs-lookup"><span data-stu-id="7ee63-161">To specify a certificate as the client credential type</span></span>  
  
-   <span data-ttu-id="7ee63-162">Verwenden Sie in der Konfigurationsdatei für einen Dienst die folgende XML, um den Sicherheitsmodus auf die Nachrichtenebene und den Clientanmeldeinformationstyp auf Zertifikate festzulegen:</span><span class="sxs-lookup"><span data-stu-id="7ee63-162">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>  
  
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
  
 <span data-ttu-id="7ee63-163">Verwenden Sie die folgende XML in der Konfigurationsdatei für einen Client um anzugeben, dass das Zertifikat im Speicher des Benutzers befindet und durch Durchsuchen des SubjectName-Felds für den Wert "CohoWinery" gefunden werden können</span><span class="sxs-lookup"><span data-stu-id="7ee63-163">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>  
  
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
  
 <span data-ttu-id="7ee63-164">Weitere Informationen zum Verwenden von Zertifikaten in WCF finden Sie unter [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="7ee63-164">For more information about using certificates in WCF, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7ee63-165">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7ee63-165">.NET Framework Security</span></span>  
 <span data-ttu-id="7ee63-166">Achten Sie darauf, alle temporären Stammzertifizierungsstellen-Zertifikate aus den Ordnern **Vertrauenswürdige Stammzertifizierungsstellen** und **Persönlich** zu löschen, indem Sie mit der rechten Maustaste auf das Zertifikat klicken und anschließend auf **Löschen**klicken.</span><span class="sxs-lookup"><span data-stu-id="7ee63-166">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee63-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ee63-167">See Also</span></span>  
 [<span data-ttu-id="7ee63-168">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="7ee63-168">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="7ee63-169">Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In</span><span class="sxs-lookup"><span data-stu-id="7ee63-169">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="7ee63-170">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7ee63-170">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
