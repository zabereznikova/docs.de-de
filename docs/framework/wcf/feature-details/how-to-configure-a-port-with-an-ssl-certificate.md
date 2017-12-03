---
title: 'Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat'
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
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc4d6e3bb20cbe005ad7ce21ed37fe57c5d3466b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="ca564-102">Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ca564-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="ca564-103">Beim Erstellen eines selbst gehosteten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienstes mit der <xref:System.ServiceModel.WSHttpBinding>-Klasse, die die Transportsicherheit verwendet, müssen Sie auch einen Anschluss mit einem X.509-Zertifikat konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ca564-103">When creating a self-hosted [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="ca564-104">Wenn Sie keinen selbst gehosteten Dienst erstellen, können Sie Ihren Dienst auch über Internetinformationsdienste (IIS) hosten.</span><span class="sxs-lookup"><span data-stu-id="ca564-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ca564-105">[HTTP-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="ca564-105"> [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="ca564-106">Welches Tool zum Konfigurieren eines Anschlusses verwendet wird, hängt vom Betriebssystem des Computers ab.</span><span class="sxs-lookup"><span data-stu-id="ca564-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="ca564-107">Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das HttpCfg.exe-Tool.</span><span class="sxs-lookup"><span data-stu-id="ca564-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="ca564-108">Unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] ist dieses Tool bereits installiert.</span><span class="sxs-lookup"><span data-stu-id="ca564-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="ca564-109">Mit [!INCLUDE[wxp](../../../../includes/wxp-md.md)], Sie können das Tool herunterladen [Windows XP Service Pack 2-Supporttools](http://go.microsoft.com/fwlink/?LinkId=88606).</span><span class="sxs-lookup"><span data-stu-id="ca564-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](http://go.microsoft.com/fwlink/?LinkId=88606).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ca564-110">[Httpcfg-Übersicht](http://go.microsoft.com/fwlink/?LinkId=88605).</span><span class="sxs-lookup"><span data-stu-id="ca564-110"> [Httpcfg Overview](http://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="ca564-111">Die [Dokumentation der Windows-Supporttools](http://go.microsoft.com/fwlink/?LinkId=94840) erklärt die Syntax der Tools "Httpcfg.exe".</span><span class="sxs-lookup"><span data-stu-id="ca564-111">The [Windows Support Tools documentation](http://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="ca564-112">Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das bereits installierte Tool Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="ca564-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="ca564-113">In diesem Thema wird die Ausführung einer Reihe von Prozeduren beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ca564-113">This topic describes how to accomplish several procedures:</span></span>  
  
-   <span data-ttu-id="ca564-114">Bestimmen der aktuellen Anschlusskonfiguration eines Computers</span><span class="sxs-lookup"><span data-stu-id="ca564-114">Determining a computer's current port configuration.</span></span>  
  
-   <span data-ttu-id="ca564-115">Abrufen des Fingerabdrucks eines Zertifikats (notwendig für die beiden anschließenden Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="ca564-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
-   <span data-ttu-id="ca564-116">Binden eines SSL-Zertifikats an eine Anschlusskonfiguration</span><span class="sxs-lookup"><span data-stu-id="ca564-116">Binding an SSL certificate to a port configuration.</span></span>  
  
-   <span data-ttu-id="ca564-117">Binden eines SSL-Zertifikats an eine Anschlusskonfiguration und Unterstützen von Clientzertifikaten</span><span class="sxs-lookup"><span data-stu-id="ca564-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
-   <span data-ttu-id="ca564-118">Löschen eines SSL-Zertifikats aus einer Anschlussnummer</span><span class="sxs-lookup"><span data-stu-id="ca564-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="ca564-119">Zum Ändern der auf dem Computer gespeicherten Zertifikate sind Administratorrechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca564-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="ca564-120">So ermitteln Sie, wie Anschlüsse konfiguriert sind</span><span class="sxs-lookup"><span data-stu-id="ca564-120">To determine how ports are configured</span></span>  
  
1.  <span data-ttu-id="ca564-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)], verwenden Sie die Tools "HttpCfg.exe" zum Anzeigen der aktuellen Portkonfiguration mithilfe der **Abfrage** und **Ssl** gewechselt wird, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca564-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  <span data-ttu-id="ca564-122">Verwenden Sie zum Anzeigen der aktuellen Anschlusskonfiguration unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe-Tool, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca564-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="ca564-123">So rufen Sie den Fingerabdruck eines Zertifikats ab</span><span class="sxs-lookup"><span data-stu-id="ca564-123">To get a certificate's thumbprint</span></span>  
  
1.  <span data-ttu-id="ca564-124">Verwenden Sie das Zertifikats-MMC-Snap-In, um nach einem X.509-Zertifikat zu suchen, das eine bestimmte Clientauthentifizierungsfunktion aufweist.</span><span class="sxs-lookup"><span data-stu-id="ca564-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ca564-125">[Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="ca564-125"> [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="ca564-126">Greifen Sie auf den Fingerabdruck des Zertifikats zu.</span><span class="sxs-lookup"><span data-stu-id="ca564-126">Access the certificate's thumbprint.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="ca564-127">[Wie: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="ca564-127"> [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3.  <span data-ttu-id="ca564-128">Kopieren Sie den Fingerabdruck des Zertifikats in einen Texteditor, beispielsweise den Windows-Editor.</span><span class="sxs-lookup"><span data-stu-id="ca564-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4.  <span data-ttu-id="ca564-129">Entfernen Sie alle Leerstellen zwischen den Hexadezimalzeichen.</span><span class="sxs-lookup"><span data-stu-id="ca564-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="ca564-130">Eine Möglichkeit besteht darin, die Suchen/Ersetzen-Funktion des Editors zu nutzen, um jede Leerstelle durch ein NULL-Zeichen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ca564-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="ca564-131">So binden Sie ein SSL-Zertifikat an eine Anschlussnummer</span><span class="sxs-lookup"><span data-stu-id="ca564-131">To bind an SSL certificate to a port number</span></span>  
  
1.  <span data-ttu-id="ca564-132">Verwenden Sie unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] das Tool-HttpCfg.exe im Secure Sockets Layer (SSL)-Speicher im Modus "Set", um das Zertifikat an eine Anschlussnummer zu binden.</span><span class="sxs-lookup"><span data-stu-id="ca564-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="ca564-133">Das Tool verwendet den Fingerabdruck, um das Zertifikat zu identifizieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca564-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   <span data-ttu-id="ca564-134">Die **-i** Switch verfügt über die Syntax der `IP`:`port` und weist das Tool, um das Zertifikat auf den Anschluss 8012 des Computers festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ca564-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="ca564-135">Optional können Sie die vier Nullen vor der Nummer auch durch die tatsächliche IP-Adresse des Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ca564-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    -   <span data-ttu-id="ca564-136">Die **-h** Switch gibt den Fingerabdruck des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="ca564-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2.  <span data-ttu-id="ca564-137">Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe-Tool, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca564-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   <span data-ttu-id="ca564-138">Die **"CertHash"** Parameter gibt den Fingerabdruck des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="ca564-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    -   <span data-ttu-id="ca564-139">Die **IP-Port lautet** Parameter gibt die IP-Adresse und den Port an, und wie funktioniert die **-i** -Schalter des Tools "Httpcfg.exe" beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca564-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    -   <span data-ttu-id="ca564-140">Die **Appid** Parameter ist eine GUID, die mit die besitzende Anwendung identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca564-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="ca564-141">So binden Sie ein SSL-Zertifikat an eine Anschlussnummer und unterstützen Clientzertifikate</span><span class="sxs-lookup"><span data-stu-id="ca564-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1.  <span data-ttu-id="ca564-142">Führen Sie zum Unterstützen von Clients, die die Authentifizierung mithilfe von X.509-Zertifikaten auf der Transportebene durchführen, unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)] die obige Prozedur aus, übergeben Sie jedoch einen zusätzlichen Befehlszeilenparameter an HttpCfg.exe, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca564-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="ca564-143">Die **-f** Switch verfügt über die Syntax der `n` wobei n eine Zahl zwischen 1 und 7 ist.</span><span class="sxs-lookup"><span data-stu-id="ca564-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="ca564-144">Bei dem Wert "2" (wie im vorherigen Beispiel gezeigt) sind Clientzertifikate auf der Transportebene aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ca564-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="ca564-145">Der Wert&#160;"3" aktiviert Clientzertifikate und ordnet die Zertifikate einem Windows-Konto zu.</span><span class="sxs-lookup"><span data-stu-id="ca564-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="ca564-146">Das Verhalten bei anderen Werten finden Sie in der Hilfe zu HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="ca564-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2.  <span data-ttu-id="ca564-147">Führen Sie zum Unterstützen von Clients, die die Authentifizierung mithilfe von X.509-Zertifikaten auf der Transportebene durchführen, unter [!INCLUDE[wv](../../../../includes/wv-md.md)] die obige Prozedur aus, verwenden Sie jedoch einen zusätzlichen Parameter, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca564-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="ca564-148">So löschen Sie ein SSL-Zertifikat aus einer Anschlussnummer</span><span class="sxs-lookup"><span data-stu-id="ca564-148">To delete an SSL certificate from a port number</span></span>  
  
1.  <span data-ttu-id="ca564-149">Verwenden Sie das HttpCfg.exe- oder das Netsh.exe-Tool, um die Anschlüsse und Fingerabdrücke aller Bindungen auf dem Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca564-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="ca564-150">Verwenden Sie das Umleitungszeichen ">", um die Informationen auf den Datenträger auszugeben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca564-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  <span data-ttu-id="ca564-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder [!INCLUDE[wxp](../../../../includes/wxp-md.md)], verwenden Sie die Tools "HttpCfg.exe" mit der **löschen** und **Ssl** Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="ca564-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="ca564-152">Verwenden der **-i** Switch an, die `IP`:`port` Anzahl, und die **-h** Switch den Fingerabdruck angegeben.</span><span class="sxs-lookup"><span data-stu-id="ca564-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  <span data-ttu-id="ca564-153">Verwenden Sie unter [!INCLUDE[wv](../../../../includes/wv-md.md)] das Netsh.exe-Tool, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca564-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="ca564-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca564-154">Example</span></span>  
 <span data-ttu-id="ca564-155">Der folgende Code zeigt, wie Sie einen selbst gehosteten Dienst erstellen, indem Sie die auf die Transportsicherheit festgelegte <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca564-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="ca564-156">Geben Sie beim Erstellen einer Anwendung die Anschlussnummer in der Adresse an.</span><span class="sxs-lookup"><span data-stu-id="ca564-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="ca564-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca564-157">See Also</span></span>  
 [<span data-ttu-id="ca564-158">HTTP-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="ca564-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
