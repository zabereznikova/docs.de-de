---
title: 'Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f49c0eb46141081b91100a5ae1869cbcf556e353
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579383"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="89041-102">Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="89041-102">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="89041-103">Das Sichern eines Diensts mit Transport-und Nachrichten Anmelde Informationen verwendet das beste Transport-und Nachrichten Sicherheitsmodi in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="89041-103">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="89041-104">Während die Transport Layer Security (TLS) Integrität und Vertraulichkeit bietet, stellt die Message Layer Security (MLS) verschiedene Anmeldeinformationen bereit, die bei reinen Transportsicherheitsmechanismen nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="89041-104">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="89041-105">In diesem Thema werden die grundlegenden Schritte zur Implementierung des Transports mit Nachrichtenanmeldeinformationen mithilfe der Bindungen <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.NetTcpBinding> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="89041-105">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="89041-106">Weitere Informationen zum Festlegen des Sicherheitsmodus finden Sie unter Gewusst [wie: Festlegen des Sicherheitsmodus](../how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="89041-106">For more information about setting the security mode, see [How to: Set the Security Mode](../how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="89041-107">Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt.</span><span class="sxs-lookup"><span data-stu-id="89041-107">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="89041-108">Der Secure Sockets Layer (SSL)-Mechanismus über HTTP (HTTPS) wird für HTTP verwendet, wohingegen SSL über TCP oder Windows für TCP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="89041-108">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="89041-109">Wenn der Transport HTTP ist (unter Verwendung der <xref:System.ServiceModel.WSHttpBinding>), dann wird die Sicherheit auf Transportebene von SSL über HTTP bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="89041-109">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="89041-110">In diesem Fall müssen Sie den Computer, der als Host für den Dienst fungiert, mit einem SSL-Zertifikat konfigurieren, das an einen Anschluss gebunden ist. Dies wird im weiteren Verlauf des Themas noch näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="89041-110">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="89041-111">Wenn der Transport TCP ist (unter Verwendung der <xref:System.ServiceModel.NetTcpBinding>), wird für die Sicherheit auf Transportebene standardmäßig die Windows-Sicherheit bereitgestellt oder SSL über TCP wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="89041-111">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="89041-112">Wenn Sie SSL über TCP verwenden, müssen Sie das Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode angeben. Dies wird im weiteren Verlauf des Themas noch näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="89041-112">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="89041-113">So verwenden Sie die WSHttpBinding mit einem Zertifikat für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="89041-113">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="89041-114">Binden Sie ein SSL-Zertifikat mit dem Tool HttpCfg.exe an einen Anschluss auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="89041-114">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="89041-115">Weitere Informationen finden Sie unter Vorgehens [Weise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="89041-115">For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="89041-116">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="89041-116">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="89041-117">Legen Sie für die <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-117">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="89041-118">(Weitere Informationen finden Sie unter [Auswählen eines](selecting-a-credential-type.md)Anmelde Informations Typs.) Im folgenden Code wird der- <xref:System.ServiceModel.MessageCredentialType.Certificate> Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="89041-118">(For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="89041-119">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="89041-119">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="89041-120">Dabei muss das HTTPS-Schema verwendet werden, und die Adresse muss den tatsächlichen Namen des Computers sowie die Nummer des Anschlusses enthalten, an den das SSL-Zertifikat gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="89041-120">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="89041-121">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="89041-121">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="89041-122">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="89041-122">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="89041-123">Erstellen Sie eine Instanz des <xref:System.ServiceModel.ServiceHost>, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="89041-123">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="89041-124">So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="89041-124">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="89041-125">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="89041-125">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="89041-126">Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-126">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="89041-127">Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="89041-127">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="89041-128">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="89041-128">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="89041-129">Die Adresse muss das NET.TCP-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="89041-129">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="89041-130">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="89041-130">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="89041-131">Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="89041-131">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="89041-132">Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.</span><span class="sxs-lookup"><span data-stu-id="89041-132">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="89041-133">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="89041-133">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="89041-134">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="89041-134">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="89041-135">So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="89041-135">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="89041-136">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="89041-136">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="89041-137">Legen Sie die Transportsicherheit auf Windows fest, indem Sie den <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> auf <xref:System.ServiceModel.TcpClientCredentialType.Windows> festlegen.</span><span class="sxs-lookup"><span data-stu-id="89041-137">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="89041-138">(Dabei handelt es sich um die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="89041-138">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="89041-139">Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-139">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="89041-140">Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="89041-140">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="89041-141">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="89041-141">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="89041-142">Die Adresse muss das NET.TCP-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="89041-142">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="89041-143">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="89041-143">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="89041-144">Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="89041-144">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="89041-145">Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.</span><span class="sxs-lookup"><span data-stu-id="89041-145">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="89041-146">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="89041-146">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="89041-147">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="89041-147">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="89041-148">Verwenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="89041-148">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="89041-149">So verwenden Sie die WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="89041-149">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="89041-150">Konfigurieren Sie den Computer mit einem SSL-Zertifikat, das an einen Anschluss gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="89041-150">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="89041-151">(Weitere Informationen finden Sie unter Vorgehens [Weise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="89041-151">(For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="89041-152">Sie müssen für `transport` Diese Konfiguration keine <> Elementwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="89041-152">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="89041-153">Geben Sie den Typ der Anmeldeinformationen für den Client bezüglich der Sicherheit auf Nachrichtenebene an.</span><span class="sxs-lookup"><span data-stu-id="89041-153">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="89041-154">Im folgenden Beispiel wird das- `clientCredentialType` Attribut des <`message`>-Elements auf festgelegt `UserName` .</span><span class="sxs-lookup"><span data-stu-id="89041-154">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="89041-155">So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="89041-155">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="89041-156">Bei SSL über TCP müssen Sie das Zertifikat explizit im `<behaviors>`-Element angeben.</span><span class="sxs-lookup"><span data-stu-id="89041-156">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="89041-157">Im folgenden Beispiel wird ein Zertifikat vom Aussteller am Standardspeicherort angegeben (lokaler Computer und persönlicher Speicher).</span><span class="sxs-lookup"><span data-stu-id="89041-157">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="89041-158">Fügen Sie [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) dem Bindungs Abschnitt ein hinzu.</span><span class="sxs-lookup"><span data-stu-id="89041-158">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="89041-159">Fügen Sie ein Bindungselement hinzu, und legen Sie das `name`-Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-159">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="89041-160">Fügen Sie ein <`security`>-Element hinzu, und legen Sie das- `mode` Attribut auf fest `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="89041-160">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="89041-161">Fügen Sie ein <`message>` -Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-161">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="89041-162">So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="89041-162">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="89041-163">Fügen Sie [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) dem Bindungs Abschnitt ein hinzu.</span><span class="sxs-lookup"><span data-stu-id="89041-163">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="89041-164">Fügen Sie ein <`binding`> Element hinzu, und legen Sie das- `name` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-164">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="89041-165">Fügen Sie ein <`security`>-Element hinzu, und legen Sie das- `mode` Attribut auf fest `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="89041-165">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="89041-166">Fügen Sie ein <`transport`> Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf fest `Windows`</span><span class="sxs-lookup"><span data-stu-id="89041-166">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="89041-167">Fügen Sie ein <`message`> Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="89041-167">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="89041-168">Im folgenden Code wird der Wert auf ein Zertifikat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="89041-168">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="89041-169">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89041-169">See also</span></span>

- [<span data-ttu-id="89041-170">Vorgehensweise: Festlegen des Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="89041-170">How to: Set the Security Mode</span></span>](../how-to-set-the-security-mode.md)
- [<span data-ttu-id="89041-171">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="89041-171">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="89041-172">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="89041-172">Securing Services and Clients</span></span>](securing-services-and-clients.md)
