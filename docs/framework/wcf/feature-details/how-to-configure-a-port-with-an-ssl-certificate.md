---
title: 'Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat'
description: Erfahren Sie, wie Sie einen Port mit einem X. 509-Zertifikat konfigurieren, das für einen selbst gehosteten WCF-Dienst mit der WSHttpBinding-Klasse unter Verwendung der Transportsicherheit erforderlich ist.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 0eccdf916dae7b886cbc4e6563e6dfe17039c321
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247181"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="88d5c-103">Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="88d5c-103">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="88d5c-104">Beim Erstellen eines selbst gehosteten Windows Communication Foundation (WCF)-Diensts mit der- <xref:System.ServiceModel.WSHttpBinding> Klasse, die Transportsicherheit verwendet, müssen Sie auch einen Port mit einem X. 509-Zertifikat konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="88d5c-104">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="88d5c-105">Wenn Sie keinen selbst gehosteten Dienst erstellen, können Sie Ihren Dienst auch über Internetinformationsdienste (IIS) hosten.</span><span class="sxs-lookup"><span data-stu-id="88d5c-105">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="88d5c-106">Weitere Informationen finden Sie unter [http-Transport Sicherheit](http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="88d5c-106">For more information, see [HTTP Transport Security](http-transport-security.md).</span></span>  
  
 <span data-ttu-id="88d5c-107">Welches Tool zum Konfigurieren eines Anschlusses verwendet wird, hängt vom Betriebssystem des Computers ab.</span><span class="sxs-lookup"><span data-stu-id="88d5c-107">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="88d5c-108">Wenn Sie Windows Server 2003 ausführen, verwenden Sie das HttpCfg.exe Tool.</span><span class="sxs-lookup"><span data-stu-id="88d5c-108">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="88d5c-109">Unter Windows Server 2003 ist dieses Tool installiert.</span><span class="sxs-lookup"><span data-stu-id="88d5c-109">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="88d5c-110">Weitere Informationen finden Sie unter [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="88d5c-110">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="88d5c-111">In der [Dokumentation zur Windows-Support Tools](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) wird die Syntax für das Httpcfg.exe Tool erläutert.</span><span class="sxs-lookup"><span data-stu-id="88d5c-111">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="88d5c-112">Wenn Sie Windows Vista ausführen, verwenden Sie das Netsh.exe Tool, das bereits installiert ist.</span><span class="sxs-lookup"><span data-stu-id="88d5c-112">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="88d5c-113">Zum Ändern der auf dem Computer gespeicherten Zertifikate sind Administratorrechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="88d5c-113">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="88d5c-114">Bestimmen, wie Ports konfiguriert werden</span><span class="sxs-lookup"><span data-stu-id="88d5c-114">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="88d5c-115">Verwenden Sie unter Windows Server 2003 oder Windows XP das HttpCfg.exe Tool, um die aktuelle Port Konfiguration mithilfe der **Abfrage** -und **SSL** -Switches anzuzeigen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-115">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="88d5c-116">Verwenden Sie in Windows Vista das Netsh.exe Tool zum Anzeigen der aktuellen Port Konfiguration, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-116">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="88d5c-117">Fingerabdruck eines Zertifikats erhalten</span><span class="sxs-lookup"><span data-stu-id="88d5c-117">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="88d5c-118">Verwenden Sie das Zertifikats-MMC-Snap-In, um nach einem X.509-Zertifikat zu suchen, das eine bestimmte Clientauthentifizierungsfunktion aufweist.</span><span class="sxs-lookup"><span data-stu-id="88d5c-118">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="88d5c-119">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Zertifikaten mit dem MMC-Snap-In](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="88d5c-119">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="88d5c-120">Greifen Sie auf den Fingerabdruck des Zertifikats zu.</span><span class="sxs-lookup"><span data-stu-id="88d5c-120">Access the certificate's thumbprint.</span></span> <span data-ttu-id="88d5c-121">Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="88d5c-121">For more information, see [How to: Retrieve the Thumbprint of a Certificate](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="88d5c-122">Kopieren Sie den Fingerabdruck des Zertifikats in einen Texteditor, beispielsweise den Windows-Editor.</span><span class="sxs-lookup"><span data-stu-id="88d5c-122">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="88d5c-123">Entfernen Sie alle Leerstellen zwischen den Hexadezimalzeichen.</span><span class="sxs-lookup"><span data-stu-id="88d5c-123">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="88d5c-124">Eine Möglichkeit besteht darin, die Suchen/Ersetzen-Funktion des Editors zu nutzen, um jede Leerstelle durch ein NULL-Zeichen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="88d5c-124">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="88d5c-125">Binden eines SSL-Zertifikats an eine Portnummer</span><span class="sxs-lookup"><span data-stu-id="88d5c-125">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="88d5c-126">Verwenden Sie in Windows Server 2003 oder Windows XP das HttpCfg.exe Tool im Modus "festlegen" im Secure Sockets Layer (SSL), um das Zertifikat an eine Portnummer zu binden.</span><span class="sxs-lookup"><span data-stu-id="88d5c-126">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="88d5c-127">Das Tool verwendet den Fingerabdruck, um das Zertifikat zu identifizieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-127">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="88d5c-128">Der Schalter **-i** hat die Syntax von `IP` : `port` und weist das Tool an, das Zertifikat auf Port 8012 des Computers festzulegen.</span><span class="sxs-lookup"><span data-stu-id="88d5c-128">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="88d5c-129">Optional können Sie die vier Nullen vor der Nummer auch durch die tatsächliche IP-Adresse des Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="88d5c-129">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="88d5c-130">Der Schalter **-h** gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="88d5c-130">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="88d5c-131">Verwenden Sie in Windows Vista das Netsh.exe Tool, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-131">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - <span data-ttu-id="88d5c-132">Der **CertHash** -Parameter gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="88d5c-132">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="88d5c-133">Der **IPPort** -Parameter gibt die IP-Adresse und den Port sowie die Funktionen an, die wie der **-i-** Schalter des Httpcfg.exe Tools beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="88d5c-133">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="88d5c-134">Der **AppID** -Parameter ist eine GUID, die zum Identifizieren der besitzenden Anwendung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="88d5c-134">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="88d5c-135">Binden eines SSL-Zertifikats an eine Portnummer und unterstützen von Client Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="88d5c-135">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="88d5c-136">In Windows Server 2003 oder Windows XP befolgen Sie zur Unterstützung von Clients, die sich bei X. 509-Zertifikaten auf der Transport Ebene authentifizieren, das vorangehende Verfahren, übergeben aber einen zusätzlichen Befehlszeilenparameter an HttpCfg.exe, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-136">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="88d5c-137">Der Schalter **-f** hat die Syntax, `n` wobei n eine Zahl zwischen 1 und 7 ist.</span><span class="sxs-lookup"><span data-stu-id="88d5c-137">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="88d5c-138"> Bei dem Wert "2" (wie im vorherigen Beispiel gezeigt) sind Clientzertifikate auf der Transportebene aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88d5c-138">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="88d5c-139">Der Wert&#160;"3" aktiviert Clientzertifikate und ordnet die Zertifikate einem Windows-Konto zu.</span><span class="sxs-lookup"><span data-stu-id="88d5c-139">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="88d5c-140">Das Verhalten bei anderen Werten finden Sie in der Hilfe zu HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="88d5c-140">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="88d5c-141">Zur Unterstützung von Clients, die sich bei X. 509-Zertifikaten auf der Transport Ebene authentifizieren, führen Sie in Windows Vista das vorherige Verfahren aus, aber mit einem zusätzlichen Parameter, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-141">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="88d5c-142">Löschen eines SSL-Zertifikats aus einer Portnummer</span><span class="sxs-lookup"><span data-stu-id="88d5c-142">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="88d5c-143">Verwenden Sie das HttpCfg.exe- oder das Netsh.exe-Tool, um die Anschlüsse und Fingerabdrücke aller Bindungen auf dem Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="88d5c-143">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="88d5c-144">Um die Informationen auf dem Datenträger zu drucken, verwenden Sie das Umleitungs Zeichen ">", wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-144">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="88d5c-145">Verwenden Sie in Windows Server 2003 oder Windows XP das HttpCfg.exe Tool mit den Schlüsselwörtern " **Delete** " und " **SSL** ".</span><span class="sxs-lookup"><span data-stu-id="88d5c-145">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="88d5c-146">Verwenden Sie den Schalter **-i** , um den Wert " `IP` : Number" anzugeben `port` , und den Schalter **-h** , um den Fingerabdruck anzugeben.</span><span class="sxs-lookup"><span data-stu-id="88d5c-146">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="88d5c-147">Verwenden Sie in Windows Vista das Netsh.exe Tool, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="88d5c-147">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="88d5c-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="88d5c-148">Example</span></span>  

 <span data-ttu-id="88d5c-149">Der folgende Code zeigt, wie Sie einen selbst gehosteten Dienst erstellen, indem Sie die auf die Transportsicherheit festgelegte <xref:System.ServiceModel.WSHttpBinding>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="88d5c-149">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="88d5c-150">Geben Sie beim Erstellen einer Anwendung die Anschlussnummer in der Adresse an.</span><span class="sxs-lookup"><span data-stu-id="88d5c-150">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="88d5c-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88d5c-151">See also</span></span>

- [<span data-ttu-id="88d5c-152">HTTP-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="88d5c-152">HTTP Transport Security</span></span>](http-transport-security.md)
