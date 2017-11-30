---
title: 'Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen'
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
helpviewer_keywords: TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e29ae3a0374f6ee027180835629eacceaa928d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="eafa6-102">Vorgehensweise: Verwenden von Transportsicherheit und Nachrichtenanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="eafa6-102">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="eafa6-103">Das Absichern eines Diensts mit Transport- und Nachrichtenanmeldeinformationen vereint die Vorteile der Transport- und Nachrichtensicherheitsmodi in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eafa6-103">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="eafa6-104">Während die Transport Layer Security (TLS) Integrität und Vertraulichkeit bietet, stellt die Message Layer Security (MLS) verschiedene Anmeldeinformationen bereit, die bei reinen Transportsicherheitsmechanismen nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="eafa6-104">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="eafa6-105">In diesem Thema werden die grundlegenden Schritte zur Implementierung des Transports mit Nachrichtenanmeldeinformationen mithilfe der Bindungen <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.NetTcpBinding> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eafa6-105">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="eafa6-106">Festlegen des Sicherheitsmodus, finden Sie unter [Vorgehensweise: Festlegen des Sicherheitsmodus](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="eafa6-106"> setting the security mode, see [How to: Set the Security Mode](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="eafa6-107">Wenn Sie den Sicherheitsmodus auf `TransportWithMessageCredential` festlegen, wird der tatsächliche Mechanismus, der die Sicherheitseinstellungen auf Transportebene bereitstellt, vom Transport bestimmt.</span><span class="sxs-lookup"><span data-stu-id="eafa6-107">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="eafa6-108">Der Secure Sockets Layer (SSL)-Mechanismus über HTTP (HTTPS) wird für HTTP verwendet, wohingegen SSL über TCP oder Windows für TCP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eafa6-108">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="eafa6-109">Wenn der Transport HTTP ist (unter Verwendung der <xref:System.ServiceModel.WSHttpBinding>), dann wird die Sicherheit auf Transportebene von SSL über HTTP bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="eafa6-109">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="eafa6-110">In diesem Fall müssen Sie den Computer, der als Host für den Dienst fungiert, mit einem SSL-Zertifikat konfigurieren, das an einen Anschluss gebunden ist. Dies wird im weiteren Verlauf des Themas noch näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="eafa6-110">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="eafa6-111">Wenn der Transport TCP ist (unter Verwendung der <xref:System.ServiceModel.NetTcpBinding>), wird für die Sicherheit auf Transportebene standardmäßig die Windows-Sicherheit bereitgestellt oder SSL über TCP wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="eafa6-111">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="eafa6-112">Wenn Sie SSL über TCP verwenden, müssen Sie das Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode angeben. Dies wird im weiteren Verlauf des Themas noch näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="eafa6-112">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="eafa6-113">So verwenden Sie die WSHttpBinding mit einem Zertifikat für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="eafa6-113">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="eafa6-114">Binden Sie ein SSL-Zertifikat mit dem Tool HttpCfg.exe an einen Anschluss auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="eafa6-114">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="eafa6-115">[Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="eafa6-115"> [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2.  <span data-ttu-id="eafa6-116">Erstellen Sie eine Instanz der <xref:System.ServiceModel.WSHttpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-116">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3.  <span data-ttu-id="eafa6-117">Legen Sie für die <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-117">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="eafa6-118">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Auswählen eines Anmeldeinformationentyps](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="eafa6-118">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Selecting a Credential Type](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4.  <span data-ttu-id="eafa6-119">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="eafa6-119">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="eafa6-120">Dabei muss das HTTPS-Schema verwendet werden, und die Adresse muss den tatsächlichen Namen des Computers sowie die Nummer des Anschlusses enthalten, an den das SSL-Zertifikat gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="eafa6-120">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="eafa6-121">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="eafa6-121">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5.  <span data-ttu-id="eafa6-122">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="eafa6-122">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6.  <span data-ttu-id="eafa6-123">Erstellen Sie eine Instanz des <xref:System.ServiceModel.ServiceHost>, und rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eafa6-123">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="eafa6-124">So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="eafa6-124">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="eafa6-125">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-125">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2.  <span data-ttu-id="eafa6-126">Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-126">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="eafa6-127">Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="eafa6-127">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3.  <span data-ttu-id="eafa6-128">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="eafa6-128">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="eafa6-129">Die Adresse muss das NET.TCP-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="eafa6-129">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="eafa6-130">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="eafa6-130">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4.  <span data-ttu-id="eafa6-131">Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="eafa6-131">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5.  <span data-ttu-id="eafa6-132">Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-132">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6.  <span data-ttu-id="eafa6-133">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="eafa6-133">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7.  <span data-ttu-id="eafa6-134">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="eafa6-134">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="eafa6-135">So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit (im Code)</span><span class="sxs-lookup"><span data-stu-id="eafa6-135">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="eafa6-136">Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>-Klasse, und legen Sie die <xref:System.ServiceModel.NetTcpSecurity.Mode%2A>-Eigenschaft auf <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-136">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2.  <span data-ttu-id="eafa6-137">Legen Sie die Transportsicherheit auf Windows fest, indem Sie den <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> auf <xref:System.ServiceModel.TcpClientCredentialType.Windows> festlegen.</span><span class="sxs-lookup"><span data-stu-id="eafa6-137">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="eafa6-138">(Dabei handelt es sich um die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="eafa6-138">(Note that this is the default.)</span></span>  
  
3.  <span data-ttu-id="eafa6-139">Legen Sie den <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-139">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="eafa6-140">Im folgenden Code wird der <xref:System.ServiceModel.MessageCredentialType.Certificate>-Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="eafa6-140">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4.  <span data-ttu-id="eafa6-141">Erstellen Sie eine Instanz der <xref:System.Uri>-Klasse mit einer entsprechenden Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="eafa6-141">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="eafa6-142">Die Adresse muss das NET.TCP-Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="eafa6-142">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="eafa6-143">(Sie können die Basisadresse auch in der Konfiguration festlegen.)</span><span class="sxs-lookup"><span data-stu-id="eafa6-143">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5.  <span data-ttu-id="eafa6-144">Erstellen Sie die Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="eafa6-144">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6.  <span data-ttu-id="eafa6-145">Legen Sie das X.509-Zertifikat für den Dienst mit der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse explizit fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-145">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7.  <span data-ttu-id="eafa6-146">Fügen Sie mit der <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>-Methode einen Dienstendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="eafa6-146">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8.  <span data-ttu-id="eafa6-147">Rufen Sie die <xref:System.ServiceModel.ICommunicationObject.Open%2A>-Methode auf, wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="eafa6-147">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="eafa6-148">Verwenden der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="eafa6-148">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="eafa6-149">So verwenden Sie die WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="eafa6-149">To use the WSHttpBinding</span></span>  
  
1.  <span data-ttu-id="eafa6-150">Konfigurieren Sie den Computer mit einem SSL-Zertifikat, das an einen Anschluss gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="eafa6-150">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="eafa6-151">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="eafa6-151">([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="eafa6-152">Sie müssen nicht festlegen einer <`transport`> Elementwert mit dieser Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eafa6-152">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2.  <span data-ttu-id="eafa6-153">Geben Sie den Typ der Anmeldeinformationen für den Client bezüglich der Sicherheit auf Nachrichtenebene an.</span><span class="sxs-lookup"><span data-stu-id="eafa6-153">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="eafa6-154">Im folgenden Beispiel wird die `clientCredentialType` Attribut von der <`message`>-Element `UserName`.</span><span class="sxs-lookup"><span data-stu-id="eafa6-154">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="eafa6-155">So verwenden Sie die NetTcpBinding mit einem Zertifikat für die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="eafa6-155">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1.  <span data-ttu-id="eafa6-156">Bei SSL über TCP müssen Sie das Zertifikat explizit im `<behaviors>`-Element angeben.</span><span class="sxs-lookup"><span data-stu-id="eafa6-156">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="eafa6-157">Im folgenden Beispiel wird ein Zertifikat vom Aussteller am Standardspeicherort angegeben (lokaler Computer und persönlicher Speicher).</span><span class="sxs-lookup"><span data-stu-id="eafa6-157">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
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
  
2.  <span data-ttu-id="eafa6-158">Hinzufügen einer [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) , die im Abschnitt über Bindungen</span><span class="sxs-lookup"><span data-stu-id="eafa6-158">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3.  <span data-ttu-id="eafa6-159">Fügen Sie ein Bindungselement hinzu, und legen Sie das `name`-Attribut auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="eafa6-159">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="eafa6-160">Hinzufügen einer <`security`>-Element, und legen die `mode` -Attribut `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="eafa6-160">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5.  <span data-ttu-id="eafa6-161">Hinzufügen einer <`message>` -Element, und legen die `clientCredentialType` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="eafa6-161">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
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
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="eafa6-162">So verwenden Sie die NetTcpBinding mit Windows für die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="eafa6-162">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1.  <span data-ttu-id="eafa6-163">Hinzufügen einer [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) Abschnitt Bindungen</span><span class="sxs-lookup"><span data-stu-id="eafa6-163">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2.  <span data-ttu-id="eafa6-164">Hinzufügen einer <`binding`> Element, und legen die `name` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="eafa6-164">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="eafa6-165">Hinzufügen einer <`security`>-Element, und legen die `mode` -Attribut `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="eafa6-165">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="eafa6-166">Hinzufügen einer <`transport`> Element, und legen die `clientCredentialType` -Attribut `Windows`.</span><span class="sxs-lookup"><span data-stu-id="eafa6-166">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5.  <span data-ttu-id="eafa6-167">Hinzufügen einer <`message`> Element, und legen die `clientCredentialType` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="eafa6-167">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="eafa6-168">Im folgenden Code wird der Wert auf ein Zertifikat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="eafa6-168">The following code sets the value to a certificate.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eafa6-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eafa6-169">See Also</span></span>  
 [<span data-ttu-id="eafa6-170">Vorgehensweise: Festlegen des Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="eafa6-170">How to: Set the Security Mode</span></span>](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)  
 [<span data-ttu-id="eafa6-171">Sichern von Diensten</span><span class="sxs-lookup"><span data-stu-id="eafa6-171">Securing Services</span></span>](../../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="eafa6-172">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="eafa6-172">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
