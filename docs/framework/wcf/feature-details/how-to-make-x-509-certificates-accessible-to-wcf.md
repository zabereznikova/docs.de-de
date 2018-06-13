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
ms.openlocfilehash: cd13eae0a72ceaf5abfb93dfe84a53cfc3c8dec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493705"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="f44b0-102">Vorgehensweise: Zugänglichmachen von X.509-Zertifikaten für WCF</span><span class="sxs-lookup"><span data-stu-id="f44b0-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="f44b0-103">Um ein x. 509-Zertifikat auf der Windows Communication Foundation (WCF) zugreifen können, muss Anwendungscode Certificate Store Name und Speicherort angeben.</span><span class="sxs-lookup"><span data-stu-id="f44b0-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="f44b0-104">In bestimmten Fällen benötigt die Prozessidentität Zugriff auf die Datei, die den zugeordneten privaten Schlüssel für das X.509-Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="f44b0-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="f44b0-105">Um den zugeordneten privaten Schlüssel für ein x. 509-Zertifikat in keinem Zertifikatspeicher zu erhalten, muss WCF dazu berechtigt.</span><span class="sxs-lookup"><span data-stu-id="f44b0-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="f44b0-106">Standardmäßig können nur der Besitzer und das Systemkonto auf den privaten Schlüssel eines Zertifikats zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f44b0-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="f44b0-107">So machen Sie X.509-Zertifikate für WCF zugänglich</span><span class="sxs-lookup"><span data-stu-id="f44b0-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="f44b0-108">Gewähren Sie dem Konto, das unter den WCF Lesezugriff auf die Datei ausgeführt wird, die den mit dem x. 509-Zertifikat zugeordneten privaten Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="f44b0-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="f44b0-109">Bestimmen Sie, ob WCF Lesezugriff auf den privaten Schlüssel für das x. 509-Zertifikat erfordert.</span><span class="sxs-lookup"><span data-stu-id="f44b0-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="f44b0-110">Die folgende Tabelle beschreibt, ob ein privater Schlüssel bei der Verwendung eines X.509-Zertifikats verfügbar sein muss.</span><span class="sxs-lookup"><span data-stu-id="f44b0-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="f44b0-111">Verwendung des X.509-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="f44b0-111">X.509 certificate use</span></span>|<span data-ttu-id="f44b0-112">Privater Schlüssel</span><span class="sxs-lookup"><span data-stu-id="f44b0-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="f44b0-113">Digitales Signieren einer ausgehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f44b0-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="f44b0-114">Ja</span><span class="sxs-lookup"><span data-stu-id="f44b0-114">Yes</span></span>|  
        |<span data-ttu-id="f44b0-115">Überprüfen der Signatur einer eingehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f44b0-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="f44b0-116">Nein</span><span class="sxs-lookup"><span data-stu-id="f44b0-116">No</span></span>|  
        |<span data-ttu-id="f44b0-117">Verschlüsseln einer ausgehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f44b0-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="f44b0-118">Nein</span><span class="sxs-lookup"><span data-stu-id="f44b0-118">No</span></span>|  
        |<span data-ttu-id="f44b0-119">Verschlüsseln einer eingehenden SOAP-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f44b0-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="f44b0-120">Ja</span><span class="sxs-lookup"><span data-stu-id="f44b0-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="f44b0-121">Ermitteln Sie den Ort und Namen des Zertifikatspeicherspeichers, in dem sich das Zertifikat befindet.</span><span class="sxs-lookup"><span data-stu-id="f44b0-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="f44b0-122">Der Zertifikatspeicher, in dem das Zertifikat gespeichert ist, wird entweder im Anwendungscode oder in einer Konfiguration angegeben.</span><span class="sxs-lookup"><span data-stu-id="f44b0-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="f44b0-123">Im folgenden Beispiel wird angegeben, dass sich das Zertifikat im `CurrentUser`-Zertifikatsspeicher mit dem Namen `My` befindet.</span><span class="sxs-lookup"><span data-stu-id="f44b0-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="f44b0-124">Bestimmen, in dem der private Schlüssel für das Zertifikat auf dem Computer gefunden wurde die [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) Tool.</span><span class="sxs-lookup"><span data-stu-id="f44b0-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="f44b0-125">Die [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) Tool erfordert, dass der Zertifikatspeichername, zertifikatspeicherort und etwas, das das Zertifikat eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f44b0-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="f44b0-126">Als eindeutiger Bezeichner werden der Antragstellername oder der Fingerabdruck des Zertifikats von dem Tool akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="f44b0-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="f44b0-127">Weitere Informationen dazu, wie Sie den Fingerabdruck eines Zertifikats zu bestimmen, finden Sie unter [wie: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="f44b0-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="f44b0-128">Im folgenden Codebeispiel wird mit der [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) Tool, um zu bestimmen, den Speicherort des privaten Schlüssels eines Zertifikats in die `My` speichern in `CurrentUser` mit dem Fingerabdruck `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="f44b0-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="f44b0-129">Bestimmen Sie das Konto, unter dem WCF ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f44b0-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="f44b0-130">In der folgenden Tabelle werden die Konten beschrieben unter der WCF für ein bestimmtes Szenario ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f44b0-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="f44b0-131">Szenario</span><span class="sxs-lookup"><span data-stu-id="f44b0-131">Scenario</span></span>|<span data-ttu-id="f44b0-132">Prozessidentität</span><span class="sxs-lookup"><span data-stu-id="f44b0-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="f44b0-133">Client (Konsole oder WinForms-Anwendung)</span><span class="sxs-lookup"><span data-stu-id="f44b0-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="f44b0-134">Aktuell angemeldeter Benutzer</span><span class="sxs-lookup"><span data-stu-id="f44b0-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="f44b0-135">Selbst gehosteter Dienst</span><span class="sxs-lookup"><span data-stu-id="f44b0-135">Service that is self-hosted.</span></span>|<span data-ttu-id="f44b0-136">Aktuell angemeldeter Benutzer</span><span class="sxs-lookup"><span data-stu-id="f44b0-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="f44b0-137">Dienst, der in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) oder IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f44b0-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="f44b0-138">NETZWERKDIENST</span><span class="sxs-lookup"><span data-stu-id="f44b0-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="f44b0-139">Dienst, der in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f44b0-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="f44b0-140">Wird durch das `<processModel>`-Element in der Datei Machine.config gesteuert.</span><span class="sxs-lookup"><span data-stu-id="f44b0-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="f44b0-141">ASPNET ist das Standardkonto.</span><span class="sxs-lookup"><span data-stu-id="f44b0-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="f44b0-142">Gewähren Sie Lesezugriff auf die Datei, die den privaten Schlüssel für das Konto, die mithilfe eines Tools wie cacls.exe WCF enthält unter läuft.</span><span class="sxs-lookup"><span data-stu-id="f44b0-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as cacls.exe.</span></span>  
  
         <span data-ttu-id="f44b0-143">Im folgenden Codebeispiel wird die Zugriffssteuerungsliste (/E) für die angegebene Datei bearbeitet, um (/G), dem NETZWERKDIENST-Konto, Lesezugriff (:R) auf die Datei zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="f44b0-143">The following code example edits (/E) the access control list (ACL) for the specified file to grant (/G) the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="f44b0-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f44b0-144">See Also</span></span>  
 [<span data-ttu-id="f44b0-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="f44b0-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)  
 [<span data-ttu-id="f44b0-146">Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats</span><span class="sxs-lookup"><span data-stu-id="f44b0-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
 [<span data-ttu-id="f44b0-147">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="f44b0-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
