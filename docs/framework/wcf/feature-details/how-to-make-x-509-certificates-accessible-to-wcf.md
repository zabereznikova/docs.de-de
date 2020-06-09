---
title: 'Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: e4f1aae021c4be49847b3b6dcd14b5a0a237c899
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597045"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="9a770-102">Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF</span><span class="sxs-lookup"><span data-stu-id="9a770-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="9a770-103">Um ein X. 509-Zertifikat für Windows Communication Foundation (WCF) zugänglich zu machen, muss der Anwendungscode den Namen und Speicherort des Zertifikat Speicher angeben.</span><span class="sxs-lookup"><span data-stu-id="9a770-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="9a770-104">In bestimmten Fällen benötigt die Prozessidentität Zugriff auf die Datei, die den zugeordneten privaten Schlüssel für das X.509-Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="9a770-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="9a770-105">Zum Abrufen des privaten Schlüssels, der einem X. 509-Zertifikat in einem Zertifikat Speicher zugeordnet ist, muss WCF über die entsprechende Berechtigung verfügen.</span><span class="sxs-lookup"><span data-stu-id="9a770-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="9a770-106">Standardmäßig können nur der Besitzer und das Systemkonto auf den privaten Schlüssel eines Zertifikats zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9a770-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="9a770-107">So machen Sie X.509-Zertifikate für WCF zugänglich</span><span class="sxs-lookup"><span data-stu-id="9a770-107">To make X.509 certificates accessible to WCF</span></span>  
  
1. <span data-ttu-id="9a770-108">Vergeben Sie das Konto, unter dem WCF Lesezugriff auf die Datei mit dem privaten Schlüssel enthält, der dem X. 509-Zertifikat zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9a770-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1. <span data-ttu-id="9a770-109">Stellen Sie fest, ob WCF Lesezugriff auf den privaten Schlüssel für das X. 509-Zertifikat erfordert.</span><span class="sxs-lookup"><span data-stu-id="9a770-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="9a770-110">Die folgende Tabelle beschreibt, ob ein privater Schlüssel bei der Verwendung eines X.509-Zertifikats verfügbar sein muss.</span><span class="sxs-lookup"><span data-stu-id="9a770-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="9a770-111">Verwendung des X.509-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="9a770-111">X.509 certificate use</span></span>|<span data-ttu-id="9a770-112">Privater Schlüssel</span><span class="sxs-lookup"><span data-stu-id="9a770-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="9a770-113">Digitales Signieren einer ausgehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9a770-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="9a770-114">Ja</span><span class="sxs-lookup"><span data-stu-id="9a770-114">Yes</span></span>|  
        |<span data-ttu-id="9a770-115">Überprüfen der Signatur einer eingehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9a770-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="9a770-116">Nein</span><span class="sxs-lookup"><span data-stu-id="9a770-116">No</span></span>|  
        |<span data-ttu-id="9a770-117">Verschlüsseln einer ausgehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9a770-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="9a770-118">Nein</span><span class="sxs-lookup"><span data-stu-id="9a770-118">No</span></span>|  
        |<span data-ttu-id="9a770-119">Verschlüsseln einer eingehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9a770-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="9a770-120">Ja</span><span class="sxs-lookup"><span data-stu-id="9a770-120">Yes</span></span>|  
  
    2. <span data-ttu-id="9a770-121">Ermitteln Sie den Ort und Namen des Zertifikatspeicherspeichers, in dem sich das Zertifikat befindet.</span><span class="sxs-lookup"><span data-stu-id="9a770-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="9a770-122">Der Zertifikatspeicher, in dem das Zertifikat gespeichert ist, wird entweder im Anwendungscode oder in einer Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="9a770-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="9a770-123">Im folgenden Beispiel wird angegeben, dass sich das Zertifikat im `CurrentUser`-Zertifikatsspeicher mit dem Namen `My` befindet.</span><span class="sxs-lookup"><span data-stu-id="9a770-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. <span data-ttu-id="9a770-124">Legen Sie mithilfe des Tools [FindPrivateKey](../samples/findprivatekey.md) fest, wo sich der private Schlüssel für das Zertifikat auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="9a770-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="9a770-125">Das Tool [FindPrivateKey](../samples/findprivatekey.md) erfordert den Zertifikat Speicher Namen, den Zertifikat Speicherort und etwas, das das Zertifikat eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9a770-125">The [FindPrivateKey](../samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="9a770-126">Als eindeutiger Bezeichner werden der Antragstellername oder der Fingerabdruck des Zertifikats von dem Tool akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9a770-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="9a770-127">Weitere Informationen zum Ermitteln des Fingerabdrucks für ein Zertifikat finden Sie unter Gewusst [wie: Abrufen des](how-to-retrieve-the-thumbprint-of-a-certificate.md)Fingerabdrucks eines Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="9a770-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="9a770-128">Im folgenden Codebeispiel wird das [FindPrivateKey](../samples/findprivatekey.md) -Tool verwendet, um den Speicherort des privaten Schlüssels für ein Zertifikat im `My` Speicher in `CurrentUser` mit einem Fingerabdruck von zu bestimmen `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d` .</span><span class="sxs-lookup"><span data-stu-id="9a770-128">The following code example uses the [FindPrivateKey](../samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. <span data-ttu-id="9a770-129">Bestimmen Sie das Konto, unter dem WCF ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a770-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="9a770-130">In der folgenden Tabelle wird das Konto erläutert, unter dem WCF für ein bestimmtes Szenario ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a770-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="9a770-131">Szenario</span><span class="sxs-lookup"><span data-stu-id="9a770-131">Scenario</span></span>|<span data-ttu-id="9a770-132">Prozessidentität</span><span class="sxs-lookup"><span data-stu-id="9a770-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="9a770-133">Client (Konsole oder WinForms-Anwendung)</span><span class="sxs-lookup"><span data-stu-id="9a770-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="9a770-134">Aktuell angemeldeter Benutzer</span><span class="sxs-lookup"><span data-stu-id="9a770-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="9a770-135">Selbst gehosteter Dienst</span><span class="sxs-lookup"><span data-stu-id="9a770-135">Service that is self-hosted.</span></span>|<span data-ttu-id="9a770-136">Aktuell angemeldeter Benutzer</span><span class="sxs-lookup"><span data-stu-id="9a770-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="9a770-137">Dienst, der in IIS 6,0 (Windows Server 2003) oder IIS 7,0 (Windows Vista) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9a770-137">Service that is hosted in IIS 6.0 (Windows Server 2003) or IIS 7.0 (Windows Vista).</span></span>|<span data-ttu-id="9a770-138">NETZWERKDIENST</span><span class="sxs-lookup"><span data-stu-id="9a770-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="9a770-139">Dienst, der in IIS 5. X (Windows XP) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="9a770-139">Service that is hosted in IIS 5.X (Windows XP).</span></span>|<span data-ttu-id="9a770-140">Wird durch das `<processModel>`-Element in der Datei Machine.config gesteuert.</span><span class="sxs-lookup"><span data-stu-id="9a770-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="9a770-141">ASPNET ist das Standardkonto.</span><span class="sxs-lookup"><span data-stu-id="9a770-141">The default account is ASPNET.</span></span>|  
  
    5. <span data-ttu-id="9a770-142">Erteilen Sie mithilfe eines Tools wie "icacls. exe" Lesezugriff auf die Datei, die den privaten Schlüssel für das Konto enthält, unter dem WCF ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9a770-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="9a770-143">Im folgenden Codebeispiel wird die freigegebene Zugriffs Steuerungs Liste (DACL) für die angegebene Datei bearbeitet, um dem Netzwerkdienst Konto Lesezugriff (: R) auf die Datei zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="9a770-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="9a770-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a770-144">See also</span></span>

- [<span data-ttu-id="9a770-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="9a770-145">FindPrivateKey</span></span>](../samples/findprivatekey.md)
- [<span data-ttu-id="9a770-146">Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="9a770-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="9a770-147">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="9a770-147">Working with Certificates</span></span>](working-with-certificates.md)
