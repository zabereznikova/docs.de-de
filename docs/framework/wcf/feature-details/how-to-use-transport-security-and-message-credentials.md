---
title: 'Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen'
description: Erfahren Sie, wie Sie Transportsicherheit mit Nachrichten Anmelde Informationen implementieren, die das Beste aus Transport-und Nachrichten Sicherheitsmodi in WCF bieten.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
ms.openlocfilehash: f632a4389eafc155cedcae94707c9418b6696f2c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246648"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="1cddc-103">Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="1cddc-103">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="1cddc-104">Das Sichern eines Diensts mit Transport-und Nachrichten Anmelde Informationen verwendet das beste Transport-und Nachrichten Sicherheitsmodi in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1cddc-104">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="1cddc-105">Während die Transport Layer Security (TLS) Integrität und Vertraulichkeit bietet, stellt die Message Layer Security (MLS) verschiedene Anmeldeinformationen bereit, die bei reinen Transportsicherheitsmechanismen nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1cddc-105">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="1cddc-106">In diesem Thema werden die grundlegenden Schritte zur Implementierung des Transports mit Nachrichtenanmeldeinformationen mithilfe der Bindungen <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.NetTcpBinding> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1cddc-106">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="1cddc-107">Weitere Informationen zum Festlegen des Sicherheitsmodus finden Sie unter Gewusst [wie: Festlegen des Sicherheitsmodus](../how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1cddc-107">For more information about setting the security mode, see [How to: Set the Security Mode](../how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="1cddc-108">Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1cddc-108">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="1cddc-109">Der Secure Sockets Layer (SSL)-Mechanismus über HTTP (HTTPS) wird für HTTP verwendet, wohingegen SSL über TCP oder Windows für TCP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1cddc-109">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="1cddc-110">Wenn der Transport HTTP ist (unter Verwendung der <xref:System.ServiceModel.WSHttpBinding>), dann wird die Sicherheit auf Transportebene von SSL über HTTP bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1cddc-110">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="1cddc-111">In diesem Fall müssen Sie den Computer, der als Host für den Dienst fungiert, mit einem SSL-Zertifikat konfigurieren, das an einen Anschluss gebunden ist. Dies wird im weiteren Verlauf des Themas noch näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="1cddc-111">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="1cddc-112">Wenn der Transport TCP ist (unter Verwendung der <xref:System.ServiceModel.NetTcpBinding>), wird für die Sicherheit auf Transportebene standardmäßig die Windows-Sicherheit bereitgestellt oder SSL über TCP wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cddc-112">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="1cddc-113">Wenn Sie SSL über TCP verwenden, müssen Sie das Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode angeben. Dies wird im weiteren Verlauf des Themas noch näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="1cddc-113">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="1cddc-114">So verwenden Sie die WSHttpBinding mit einem Zertifikat für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="1cddc-114">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="1cddc-115">Binden Sie ein SSL-Zertifikat mit dem Tool HttpCfg.exe an einen Anschluss auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="1cddc-115">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="1cddc-116">Weitere Informationen finden Sie unter Vorgehens [Weise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="1cddc-116">For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2. <span data-ttu-id="1cddc-117">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-117">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3. <span data-ttu-id="1cddc-118">Legen Sie für die <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-118">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="1cddc-119">(Weitere Informationen finden Sie unter [Auswählen eines](selecting-a-credential-type.md)Anmelde Informations Typs.) Im folgenden Code wird der- <xref:System.ServiceModel.MessageCredentialType.Certificate> Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cddc-119">(For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="1cddc-120">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="1cddc-120">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="1cddc-121">Dabei muss das HTTPS-Schema verwendet werden, und die Adresse muss den tatsächlichen Namen des Computers sowie die Nummer des Anschlusses enthalten, an den das SSL-Zertifikat gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="1cddc-121">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="1cddc-122">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="1cddc-122">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="1cddc-123">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cddc-123">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6. <span data-ttu-id="1cddc-124">Erstellen Sie eine Instanz des <xref:System.ServiceModel.ServiceHost>, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1cddc-124">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="1cddc-125">So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="1cddc-125">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1. <span data-ttu-id="1cddc-126">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-126">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="1cddc-127">Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-127">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="1cddc-128">Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cddc-128">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3. <span data-ttu-id="1cddc-129">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="1cddc-129">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="1cddc-130">Die Adresse muss das NET.TCP-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cddc-130">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="1cddc-131">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="1cddc-131">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4. <span data-ttu-id="1cddc-132">Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1cddc-132">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5. <span data-ttu-id="1cddc-133">Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-133">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6. <span data-ttu-id="1cddc-134">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cddc-134">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7. <span data-ttu-id="1cddc-135">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1cddc-135">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="1cddc-136">So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="1cddc-136">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1. <span data-ttu-id="1cddc-137">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-137">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2. <span data-ttu-id="1cddc-138">Legen Sie die Transportsicherheit auf Windows fest, indem Sie den <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> auf <xref:System.ServiceModel.TcpClientCredentialType.Windows> festlegen.</span><span class="sxs-lookup"><span data-stu-id="1cddc-138">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="1cddc-139">(Dabei handelt es sich um die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="1cddc-139">(Note that this is the default.)</span></span>  
  
3. <span data-ttu-id="1cddc-140">Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-140">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="1cddc-141">Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="1cddc-141">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4. <span data-ttu-id="1cddc-142">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="1cddc-142">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="1cddc-143">Die Adresse muss das NET.TCP-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cddc-143">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="1cddc-144">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="1cddc-144">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5. <span data-ttu-id="1cddc-145">Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1cddc-145">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6. <span data-ttu-id="1cddc-146">Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-146">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7. <span data-ttu-id="1cddc-147">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cddc-147">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8. <span data-ttu-id="1cddc-148">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1cddc-148">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="1cddc-149">Verwenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1cddc-149">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="1cddc-150">So verwenden Sie die WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="1cddc-150">To use the WSHttpBinding</span></span>  
  
1. <span data-ttu-id="1cddc-151">Konfigurieren Sie den Computer mit einem SSL-Zertifikat, das an einen Anschluss gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="1cddc-151">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="1cddc-152">(Weitere Informationen finden Sie unter Vorgehens [Weise: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="1cddc-152">(For more information, see [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="1cddc-153">Sie müssen für `transport` Diese Konfiguration keine <> Elementwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="1cddc-153">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2. <span data-ttu-id="1cddc-154">Geben Sie den Typ der Anmeldeinformationen für den Client bezüglich der Sicherheit auf Nachrichtenebene an.</span><span class="sxs-lookup"><span data-stu-id="1cddc-154">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="1cddc-155">Im folgenden Beispiel wird das- `clientCredentialType` Attribut des <`message`>-Elements auf festgelegt `UserName` .</span><span class="sxs-lookup"><span data-stu-id="1cddc-155">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="1cddc-156">So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="1cddc-156">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1. <span data-ttu-id="1cddc-157">Bei SSL über TCP müssen Sie das Zertifikat explizit im `<behaviors>`-Element angeben.</span><span class="sxs-lookup"><span data-stu-id="1cddc-157">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="1cddc-158">Im folgenden Beispiel wird ein Zertifikat vom Aussteller am Standardspeicherort angegeben (lokaler Computer und persönlicher Speicher).</span><span class="sxs-lookup"><span data-stu-id="1cddc-158">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
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
  
2. <span data-ttu-id="1cddc-159">Fügen Sie [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) dem Bindungs Abschnitt ein hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cddc-159">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3. <span data-ttu-id="1cddc-160">Fügen Sie ein Bindungselement hinzu, und legen Sie das `name`-Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-160">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="1cddc-161">Fügen Sie ein <`security`>-Element hinzu, und legen Sie das- `mode` Attribut auf fest `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="1cddc-161">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5. <span data-ttu-id="1cddc-162">Fügen Sie ein <`message>` -Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-162">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
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
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="1cddc-163">So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="1cddc-163">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1. <span data-ttu-id="1cddc-164">Fügen Sie [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) dem Bindungs Abschnitt ein hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cddc-164">Add a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2. <span data-ttu-id="1cddc-165">Fügen Sie ein <`binding`> Element hinzu, und legen Sie das- `name` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-165">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="1cddc-166">Fügen Sie ein <`security`>-Element hinzu, und legen Sie das- `mode` Attribut auf fest `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="1cddc-166">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4. <span data-ttu-id="1cddc-167">Fügen Sie ein <`transport`> Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf fest `Windows`</span><span class="sxs-lookup"><span data-stu-id="1cddc-167">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5. <span data-ttu-id="1cddc-168">Fügen Sie ein <`message`> Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="1cddc-168">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="1cddc-169">Im folgenden Code wird der Wert auf ein Zertifikat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1cddc-169">The following code sets the value to a certificate.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1cddc-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cddc-170">See also</span></span>

- [<span data-ttu-id="1cddc-171">Vorgehensweise: Festlegen des Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="1cddc-171">How to: Set the Security Mode</span></span>](../how-to-set-the-security-mode.md)
- [<span data-ttu-id="1cddc-172">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="1cddc-172">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="1cddc-173">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1cddc-173">Securing Services and Clients</span></span>](securing-services-and-clients.md)
