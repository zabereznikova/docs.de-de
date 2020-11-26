---
title: Programmieren der WCF-Sicherheit
description: Erfahren Sie, wie Sie eine sichere WCF-Anwendung erstellen, einschließlich Authentifizierung, Vertraulichkeit und Integrität.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message security [WCF], programming overview
ms.assetid: 739ec222-4eda-4cc9-a470-67e64a7a3f10
ms.openlocfilehash: 4ffbf6a05abd3ed9ebcea4b2e85f0dc305a4f2db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244768"
---
# <a name="programming-wcf-security"></a><span data-ttu-id="42f96-103">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="42f96-103">Programming WCF Security</span></span>

<span data-ttu-id="42f96-104">In diesem Thema werden die grundlegenden Programmieraufgaben beschrieben, die zum Erstellen einer Secure Windows Communication Foundation (WCF)-Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42f96-104">This topic describes the fundamental programming tasks used to create a secure Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="42f96-105">In diesem Thema werden nur Authentifizierung, Vertraulichkeit und Integrität behandelt, die zusammen als *Übertragungssicherheit* bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="42f96-105">This topic covers only authentication, confidentiality, and integrity, collectively known as *transfer security*.</span></span> <span data-ttu-id="42f96-106">In diesem Thema wird die Autorisierung (Kontrolle des Zugriffs auf Ressourcen oder Dienste) nicht behandelt. Informationen zur Autorisierung finden Sie unter [Autorisierung](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="42f96-106">This topic does not cover authorization (the control of access to resources or services); for information on authorization, see [Authorization](authorization-in-wcf.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42f96-107">Eine wertvolle Einführung in Sicherheitskonzepte, insbesondere im Hinblick auf WCF, finden Sie in den Tutorials zu Mustern und Vorgehensweisen auf MSDN unter [Szenarien, Muster und Implementierungs Leit Faden für Web Services-Erweiterungen (WSE) 3,0](/previous-versions/msp-n-p/ff648183(v=pandp.10)).</span><span class="sxs-lookup"><span data-stu-id="42f96-107">For a valuable introduction to security concepts, especially in regard to WCF, see the set of patterns and practices tutorials on MSDN at [Scenarios, Patterns, and Implementation Guidance for Web Services Enhancements (WSE) 3.0](/previous-versions/msp-n-p/ff648183(v=pandp.10)).</span></span>  
  
 <span data-ttu-id="42f96-108">Das Programmieren der WCF-Sicherheit basiert auf drei Schritten, die Folgendes festlegen: der Sicherheitsmodus, ein Client Anmelde Informationstyp und die Anmelde Informationswerte.</span><span class="sxs-lookup"><span data-stu-id="42f96-108">Programming WCF security is based on three steps setting the following: the security mode, a client credential type, and the credential values.</span></span> <span data-ttu-id="42f96-109">Sie können diese Schritte durch Code oder die Konfiguration durchführen.</span><span class="sxs-lookup"><span data-stu-id="42f96-109">You can perform these steps either through code or configuration.</span></span>  
  
## <a name="setting-the-security-mode"></a><span data-ttu-id="42f96-110">Festlegen des Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="42f96-110">Setting the Security Mode</span></span>  

 <span data-ttu-id="42f96-111">Im folgenden werden die allgemeinen Schritte zum Programmieren mit dem Sicherheitsmodus in WCF erläutert:</span><span class="sxs-lookup"><span data-stu-id="42f96-111">The following explains the general steps for programming with the security mode in WCF:</span></span>  
  
1. <span data-ttu-id="42f96-112">Wählen Sie eine der vordefinierten Bindungen, die den Anwendungsanforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="42f96-112">Select one of the predefined bindings appropriate to your application requirements.</span></span> <span data-ttu-id="42f96-113">Eine Liste der Bindungs Optionen finden Sie unter vom [System bereitgestellte Bindungen](../system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="42f96-113">For a list of the binding choices, see [System-Provided Bindings](../system-provided-bindings.md).</span></span> <span data-ttu-id="42f96-114">Standardmäßig ist beinahe jede Bindung sicherheitsaktiviert.</span><span class="sxs-lookup"><span data-stu-id="42f96-114">By default, nearly every binding has security enabled.</span></span> <span data-ttu-id="42f96-115">Die einzige Ausnahme ist die- <xref:System.ServiceModel.BasicHttpBinding> Klasse (mithilfe der-Konfiguration, der [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) ).</span><span class="sxs-lookup"><span data-stu-id="42f96-115">The one exception is the <xref:System.ServiceModel.BasicHttpBinding> class (using configuration, the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)).</span></span>  
  
     <span data-ttu-id="42f96-116">Durch die von Ihnen ausgewählte Bindung bestimmen Sie auch den Transport.</span><span class="sxs-lookup"><span data-stu-id="42f96-116">The binding you select determines the transport.</span></span> <span data-ttu-id="42f96-117"><xref:System.ServiceModel.WSHttpBinding> verwendet beispielsweise HTTP als Transportmethode, <xref:System.ServiceModel.NetTcpBinding> verwendet TCP.</span><span class="sxs-lookup"><span data-stu-id="42f96-117">For example, <xref:System.ServiceModel.WSHttpBinding> uses HTTP as the transport; <xref:System.ServiceModel.NetTcpBinding> uses TCP.</span></span>  
  
2. <span data-ttu-id="42f96-118">Wählen Sie einen der Sicherheitsmodi für die Bindung aus.</span><span class="sxs-lookup"><span data-stu-id="42f96-118">Select one of the security modes for the binding.</span></span> <span data-ttu-id="42f96-119">Beachten Sie, dass die von Ihnen ausgewählte Bindung auch die Verfügbarkeit der Modi beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="42f96-119">Note that the binding you select determines the available mode choices.</span></span> <span data-ttu-id="42f96-120">Die <xref:System.ServiceModel.WSDualHttpBinding> ermöglicht beispielsweise keine Transportsicherheit. (Sie steht nicht als Option zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="42f96-120">For example, the <xref:System.ServiceModel.WSDualHttpBinding> does not allow transport security (it is not an option).</span></span> <span data-ttu-id="42f96-121">Auf ähnliche Weise ermöglichen weder <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> noch <xref:System.ServiceModel.NetNamedPipeBinding> die Nachrichtensicherheit.</span><span class="sxs-lookup"><span data-stu-id="42f96-121">Similarly, neither the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> nor the <xref:System.ServiceModel.NetNamedPipeBinding> allows message security.</span></span>  
  
     <span data-ttu-id="42f96-122">Sie haben drei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="42f96-122">You have three choices:</span></span>  
  
    1. `Transport`  
  
         <span data-ttu-id="42f96-123">Die Transportsicherheit ist vom Mechanismus abhängig, den die ausgewählte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="42f96-123">Transport security depends on the mechanism that the binding you have selected uses.</span></span> <span data-ttu-id="42f96-124">Wenn Sie beispielsweise `WSHttpBinding` verwenden, wird als Sicherheitsmechanismus Secure Sockets Layer (SSL) verwendet, was auch der Mechanismus für das HTTPS-Protokoll ist.</span><span class="sxs-lookup"><span data-stu-id="42f96-124">For example, if you are using `WSHttpBinding` then the security mechanism is Secure Sockets Layer (SSL) (also the mechanism for the HTTPS protocol).</span></span> <span data-ttu-id="42f96-125">Der Hauptvorteil der Transportsicherheit besteht im Allgemeinen darin, dass sie unabhängig von der Transportmethode einen guten Durchsatz ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="42f96-125">Generally speaking, the main advantage of transport security is that it delivers good throughput no matter which transport you are using.</span></span> <span data-ttu-id="42f96-126">Es gibt jedoch zwei Einschränkungen: Der Transportmechanismus bestimmt den Anmeldeinformationstyp, der zum Authentifizieren eines Benutzers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="42f96-126">However, it does have two limitations: The first is that the transport mechanism dictates the credential type used to authenticate a user.</span></span> <span data-ttu-id="42f96-127">Dies ist jedoch nur dann von Nachteil, wenn ein Dienst mit anderen Diensten zusammenarbeiten muss, für die unterschiedliche Anmeldeinformationstypen notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="42f96-127">This is a drawback only if a service needs to interoperate with other services that demand different types of credentials.</span></span> <span data-ttu-id="42f96-128">Darüber hinaus wird die Sicherheit nicht auf Nachrichtenebene angewendet, vielmehr wird die Sicherheit per Hop-by-Hop-Methode anstelle einer End-to-End-Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="42f96-128">The second is that, because the security is not applied at the message level, security is implemented in a hop-by-hop manner rather than end-to-end.</span></span> <span data-ttu-id="42f96-129">Diese zweite Einschränkung ist nur dann ein Problem, wenn der Nachrichtenpfad zwischen Client und Dienst Vermittler umfasst.</span><span class="sxs-lookup"><span data-stu-id="42f96-129">This latter limitation is an issue only if the message path between client and service includes intermediaries.</span></span> <span data-ttu-id="42f96-130">Weitere Informationen zum zu verwendenden Transport finden Sie unter [Auswählen eines Transports](choosing-a-transport.md).</span><span class="sxs-lookup"><span data-stu-id="42f96-130">For more information about which transport to use, see [Choosing a Transport](choosing-a-transport.md).</span></span> <span data-ttu-id="42f96-131">Weitere Informationen zum Verwenden der Transportsicherheit finden Sie unter Übersicht über die [Transportsicherheit](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="42f96-131">For more information about using transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>  
  
    2. `Message`  
  
         <span data-ttu-id="42f96-132">Nachrichtensicherheit bedeutet, dass jede Nachricht die notwendigen Header und Daten enthält, um die Nachricht zu sichern.</span><span class="sxs-lookup"><span data-stu-id="42f96-132">Message security means that every message includes the necessary headers and data to keep the message secure.</span></span> <span data-ttu-id="42f96-133">Da die Struktur der Header unterschiedlich ist, können Sie beliebig viele Anmeldeinformationen umfassen.</span><span class="sxs-lookup"><span data-stu-id="42f96-133">Because the composition of the headers varies, you can include any number of credentials.</span></span> <span data-ttu-id="42f96-134">Dies spielt eine Rolle, wenn Sie mit anderen Diensten zusammenarbeiten, die einen bestimmten Anmeldeinformationstyp erfordern, den ein Transportmechanismus nicht bereitstellen kann, oder wenn die Nachricht mit mehr als einem Dienst verwendet werden muss, wobei jeder Dienst einen unterschiedlichen Anmeldeinformationstyp erfordert.</span><span class="sxs-lookup"><span data-stu-id="42f96-134">This becomes a factor if you are interoperating with other services that demand a specific credential type that a transport mechanism can't supply, or if the message must be used with more than one service, where each service demands a different credential type.</span></span>  
  
         <span data-ttu-id="42f96-135">Weitere Informationen finden Sie unter [Nachrichten Sicherheit](message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="42f96-135">For more information, see [Message Security](message-security-in-wcf.md).</span></span>  
  
    3. `TransportWithMessageCredential`  
  
         <span data-ttu-id="42f96-136">Diese Auswahl verwendet die Transportschicht, um die Nachrichtenübertragung zu sichern, während jede Nachricht die komplexen Anmeldeinformationen enthält, die andere Dienste benötigen.</span><span class="sxs-lookup"><span data-stu-id="42f96-136">This choice uses the transport layer to secure the message transfer, while every message includes the rich credentials other services need.</span></span> <span data-ttu-id="42f96-137">Dadurch wird der Leistungsvorteil der Transportsicherheit mit dem Vorteil komplexer Anmeldeinformationen der Nachrichtensicherheit kombiniert.</span><span class="sxs-lookup"><span data-stu-id="42f96-137">This combines the performance advantage of transport security with the rich credentials advantage of message security.</span></span> <span data-ttu-id="42f96-138">Dies ist mit den folgenden Bindungen verfügbar: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding> und <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="42f96-138">This is available with the following bindings: <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSFederationHttpBinding>, <xref:System.ServiceModel.NetPeerTcpBinding>, and <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
3. <span data-ttu-id="42f96-139">Wenn Sie für HTTP eine Transportsicherheit verwenden möchten (d. h. HTTPS), müssen Sie auch den Host mit einem SSL-Zertifikat konfigurieren und SSL auf einem Port aktivieren.</span><span class="sxs-lookup"><span data-stu-id="42f96-139">If you decide to use transport security for HTTP (in other words, HTTPS), you must also configure the host with an SSL certificate and enable SSL on a port.</span></span> <span data-ttu-id="42f96-140">Weitere Informationen finden Sie unter [http-Transport Sicherheit](http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="42f96-140">For more information, see [HTTP Transport Security](http-transport-security.md).</span></span>  
  
4. <span data-ttu-id="42f96-141">Wenn Sie <xref:System.ServiceModel.WSHttpBinding> verwenden und keine sichere Sitzung einrichten müssen, legen Sie für die <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>-Eigenschaft den Wert `false` fest.</span><span class="sxs-lookup"><span data-stu-id="42f96-141">If you are using the <xref:System.ServiceModel.WSHttpBinding> and do not need to establish a secure session, set the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="42f96-142">Eine sichere Sitzung entsteht, wenn ein Client und ein Dienst einen Kanal mithilfe eines symmetrischen Schlüssels erstellen (sowohl Client als auch Server verwenden den gleichen Schlüssel für die Dauer einer Konversation und bis der Dialog geschlossen wird).</span><span class="sxs-lookup"><span data-stu-id="42f96-142">A secure session occurs when a client and service create a channel using a symmetric key (both client and server use the same key for the length of a conversation, until the dialog is closed).</span></span>  
  
## <a name="setting-the-client-credential-type"></a><span data-ttu-id="42f96-143">Festlegen des Clientanmeldeinformationstyps</span><span class="sxs-lookup"><span data-stu-id="42f96-143">Setting the Client Credential Type</span></span>  

 <span data-ttu-id="42f96-144">Wählen Sie wie erforderlich einen Clientanmeldeinformationstyp aus.</span><span class="sxs-lookup"><span data-stu-id="42f96-144">Select a client credential type as appropriate.</span></span> <span data-ttu-id="42f96-145">Weitere Informationen finden Sie unter [Auswählen eines](selecting-a-credential-type.md)Anmelde Informations Typs.</span><span class="sxs-lookup"><span data-stu-id="42f96-145">For more information, see [Selecting a Credential Type](selecting-a-credential-type.md).</span></span> <span data-ttu-id="42f96-146">Die folgenden Clientanmeldeinformationstypen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="42f96-146">The following client credential types are available:</span></span>  
  
- `Windows`  
  
- `Certificate`  
  
- `Digest`  
  
- `Basic`  
  
- `UserName`  
  
- `NTLM`  
  
- `IssuedToken`  
  
 <span data-ttu-id="42f96-147">Die Art und Weise, wie Sie den Modus festlegen, bestimmt auch die Festlegung des Anmeldeinformationstyps.</span><span class="sxs-lookup"><span data-stu-id="42f96-147">Depending on how you set the mode, you must set the credential type.</span></span> <span data-ttu-id="42f96-148">Wenn Sie beispielsweise `wsHttpBinding` ausgewählt haben und als Modus "Message" festgelegt haben, können Sie auch das `clientCredentialType`-Attribut des Nachrichtenelements auf einen der folgenden Werte festlegen: `None`, `Windows`, `UserName`, `Certificate` und `IssuedToken`, wie im folgenden Konfigurationsbeispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="42f96-148">For example, if you have selected the `wsHttpBinding`, and have set the mode to "Message," then you can also set the `clientCredentialType` attribute of the Message element to one of the following values: `None`, `Windows`, `UserName`, `Certificate`, and `IssuedToken`, as shown in the following configuration example.</span></span>  
  
```xml  
<system.serviceModel>  
<bindings>  
  <wsHttpBinding>  
    <binding name="myBinding">  
      <security mode="Message"/>  
      <message clientCredentialType="Windows"/>  
    </binding>
  </wsHttpBinding>
</bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="42f96-149">Oder in Code:</span><span class="sxs-lookup"><span data-stu-id="42f96-149">Or in code:</span></span>  
  
 [!code-csharp[c_WsHttpService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#1)]
 [!code-vb[c_WsHttpService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#1)]  
  
## <a name="setting-service-credential-values"></a><span data-ttu-id="42f96-150">Festlegen von Dienstanmeldeinformationswerten</span><span class="sxs-lookup"><span data-stu-id="42f96-150">Setting Service Credential Values</span></span>  

 <span data-ttu-id="42f96-151">Nachdem Sie einen Dienstanmeldeinformationstyp ausgewählt haben, müssen Sie die tatsächlichen Anmeldeinformationen für den zu verwendenden Dienst und Client festlegen.</span><span class="sxs-lookup"><span data-stu-id="42f96-151">Once you select a client credential type, you must set the actual credentials for the service and client to use.</span></span> <span data-ttu-id="42f96-152">Für den Dienst werden die Anmeldeinformationen mit der <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse festgelegt und von der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft der <xref:System.ServiceModel.ServiceHostBase>-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42f96-152">On the service, credentials are set using the <xref:System.ServiceModel.Description.ServiceCredentials> class and returned by the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property of the <xref:System.ServiceModel.ServiceHostBase> class.</span></span> <span data-ttu-id="42f96-153">Die verwendete Bindung gibt den Dienstanmeldeinformationstyp, den ausgewählten Sicherheitsmodus und den Typ der Clientanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="42f96-153">The binding in use implies the service credential type, the security mode chosen, and the type of the client credential.</span></span> <span data-ttu-id="42f96-154">Mit dem folgenden Code wird ein Zertifikat für die Dienstanmeldeinformationen festgelegt:</span><span class="sxs-lookup"><span data-stu-id="42f96-154">The following code sets a certificate for a service credential.</span></span>  
  
 [!code-csharp[c_tcpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#3)]
 [!code-vb[c_tcpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#3)]  
  
## <a name="setting-client-credential-values"></a><span data-ttu-id="42f96-155">Festlegen der Werte der Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="42f96-155">Setting Client Credential Values</span></span>  

 <span data-ttu-id="42f96-156">Für den Client werden die Clientanmeldeinformationswerte mit der <xref:System.ServiceModel.Description.ClientCredentials>-Klasse festgelegt und von der <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="42f96-156">On the client, set client credential values using the <xref:System.ServiceModel.Description.ClientCredentials> class and returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class.</span></span> <span data-ttu-id="42f96-157">Mit dem folgenden Code wird ein Zertifikat als Anmeldeinformationen auf einem Client mit dem TCP-Protokoll festgelegt.</span><span class="sxs-lookup"><span data-stu-id="42f96-157">The following code sets a certificate as a credential on a client using the TCP protocol.</span></span>  
  
 [!code-csharp[c_TcpClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpclient/cs/source.cs#1)]
 [!code-vb[c_TcpClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpclient/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="42f96-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42f96-158">See also</span></span>

- [<span data-ttu-id="42f96-159">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="42f96-159">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- [<span data-ttu-id="42f96-160">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="42f96-160">Common Security Scenarios</span></span>](common-security-scenarios.md)
