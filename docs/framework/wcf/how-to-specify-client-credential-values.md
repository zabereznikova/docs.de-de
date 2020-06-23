---
title: 'Vorgehensweise: Angeben der Clientanmeldeinformationswerte'
description: Erfahren Sie, wie ein WCF-Dienst angeben kann, wie ein Client für den Dienst authentifiziert wird. In diesem Beispiel werden ein X. 509-Zertifikat und ein Transport Modus angegeben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 75a21a7dc083282f6b2fe839167ff1b2eddfb373
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244451"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="2e370-104">Vorgehensweise: Angeben der Clientanmeldeinformationswerte</span><span class="sxs-lookup"><span data-stu-id="2e370-104">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="2e370-105">Mithilfe von Windows Communication Foundation (WCF) kann der Dienst angeben, wie ein Client für den Dienst authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="2e370-105">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="2e370-106">Ein Dienst kann beispielsweise festlegen, dass der Client mit einem Zertifikat authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="2e370-106">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="2e370-107">So bestimmen Sie den Typ der Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2e370-107">To determine the client credential type</span></span>

1. <span data-ttu-id="2e370-108">Rufen Sie die Metadaten aus dem Metadatenendpunkt des Diensts ab.</span><span class="sxs-lookup"><span data-stu-id="2e370-108">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="2e370-109">Die Metadaten umfassen in der Regel zwei Dateien: den Clientcode in der Programmiersprache Ihrer Wahl (die Standardeinstellung ist Visual C#) und eine XML-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2e370-109">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="2e370-110">Eine Möglichkeit zum Abrufen der Metadaten ist, das Tool "Svcutil.exe" zu verwenden, um den Clientcode und die Clientkonfiguration zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e370-110">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="2e370-111">Weitere Informationen finden Sie unter [Abrufen von Metadaten](./feature-details/retrieving-metadata.md) und [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2e370-111">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="2e370-112">Öffnen Sie die XML-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2e370-112">Open the XML configuration file.</span></span> <span data-ttu-id="2e370-113">Wenn Sie das Tool "Svcutil.exe" verwenden, lautet der Standardname der Datei "Output.config".</span><span class="sxs-lookup"><span data-stu-id="2e370-113">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="2e370-114">Suchen Sie das- **\<security>** Element mit dem **Mode** -Attribut ( **\<security mode =**`MessageOrTransport`**>** wobei `MessageOrTransport` auf einen der Sicherheitsmodi festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2e370-114">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="2e370-115">Suchen Sie nach dem untergeordneten Element, das dem Moduswert entspricht.</span><span class="sxs-lookup"><span data-stu-id="2e370-115">Find the child element that matches the mode value.</span></span> <span data-ttu-id="2e370-116">Wenn der Modus z. b. auf **Message**festgelegt ist, suchen Sie das-Element, das **\<message>** im-Element enthalten ist **\<security>** .</span><span class="sxs-lookup"><span data-stu-id="2e370-116">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="2e370-117">Beachten Sie den Wert, der dem **clientkredentialtype** -Attribut zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2e370-117">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="2e370-118">Der tatsächliche Wert hängt davon ab, welcher Modus verwendet wird: Transport oder Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2e370-118">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="2e370-119">Der folgende XML-Code veranschaulicht die Konfiguration für einen Client, der die Nachrichtensicherheit verwendet und ein Zertifikat zum Authentifizieren des Clients erfordert.</span><span class="sxs-lookup"><span data-stu-id="2e370-119">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="2e370-120">Beispiel: TCP-Transportmodus mit einem Zertifikat als Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2e370-120">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="2e370-121">In diesem Beispiel wird der Sicherheitsmodus auf "Transport" und der Clientanmeldeinformationswert auf ein X.509-Zertifikat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2e370-121">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="2e370-122">Die folgenden Vorgänge zeigen, wie Sie den Clientanmeldeinformationswert für den Client im Code und in der Konfiguration festlegen können.</span><span class="sxs-lookup"><span data-stu-id="2e370-122">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="2e370-123">Dabei wird davon ausgegangen, dass Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet haben, um die Metadaten (Code und Konfiguration) vom Dienst zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e370-123">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="2e370-124">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="2e370-124">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="2e370-125">So legen Sie den Clientanmeldeinformationswert für den Client im Code fest</span><span class="sxs-lookup"><span data-stu-id="2e370-125">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="2e370-126">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) , um Code und Konfiguration aus dem Dienst zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2e370-126">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="2e370-127">Erstellen Sie eine Instanz des WCF-Clients mithilfe des generierten Codes.</span><span class="sxs-lookup"><span data-stu-id="2e370-127">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="2e370-128">Legen Sie für die Clientklasse die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="2e370-128">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="2e370-129">In diesem Beispiel wird die Eigenschaft auf ein X.509-Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>-Klasse festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2e370-129">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="2e370-130">Sie können jede beliebige Enumeration der <xref:System.Security.Cryptography.X509Certificates.X509FindType>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e370-130">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="2e370-131">Der Betreffname wird hier verwendet, für den Fall, dass das Zertifikat (aufgrund des Ablaufdatums) geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2e370-131">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="2e370-132">Anhand des Betreffnamens kann die Infrastruktur das Zertifikat wieder suchen.</span><span class="sxs-lookup"><span data-stu-id="2e370-132">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="2e370-133">So legen Sie den Clientanmeldeinformationswert für den Client in der Konfiguration fest</span><span class="sxs-lookup"><span data-stu-id="2e370-133">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="2e370-134">Fügen Sie [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) dem-Element ein-Element hinzu [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="2e370-134">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="2e370-135">Fügen Sie [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) dem-Element ein-Element hinzu [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="2e370-135">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="2e370-136">Achten Sie darauf, für das erforderliche `name`-Attribut einen geeigneten Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2e370-136">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="2e370-137">Fügen Sie [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) dem-Element ein-Element hinzu [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="2e370-137">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="2e370-138">Legen Sie für die folgenden Attribute geeignete Werte fest: `storeLocation`, `storeName`, `x509FindType` und `findValue`, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2e370-138">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="2e370-139">Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](./feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="2e370-139">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

    ```xml
    <behaviors>
       <endpointBehaviors>
          <behavior name="endpointCredentialBehavior">
            <clientCredentials>
              <clientCertificate findValue="Contoso.com"
                                 storeLocation="LocalMachine"
                                 storeName="TrustedPeople"
                                 x509FindType="FindBySubjectName" />
            </clientCredentials>
          </behavior>
       </endpointBehaviors>
    </behaviors>
    ```

5. <span data-ttu-id="2e370-140">Wenn Sie den Client konfigurieren, legen Sie das Verhalten fest, indem Sie das `behaviorConfiguration`-Attribut des `<endpoint>`-Elements festlegen, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2e370-140">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="2e370-141">Das Endpunkt Element ist ein untergeordnetes Element des- [\<client>](../configure-apps/file-schema/wcf/client.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="2e370-141">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="2e370-142">Geben Sie auch den Namen der Bindungskonfiguration an, indem Sie das `bindingConfiguration`-Attribut auf die Bindung für den Client festlegen.</span><span class="sxs-lookup"><span data-stu-id="2e370-142">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="2e370-143">Wenn Sie eine generierte Konfigurationsdatei verwenden, wird der Name der Bindung automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="2e370-143">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="2e370-144">In diesem Beispiel lautet der Name `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="2e370-144">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="2e370-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e370-145">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="2e370-146">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2e370-146">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="2e370-147">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="2e370-147">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2e370-148">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="2e370-148">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="2e370-149">Verwenden von Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="2e370-149">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="2e370-150">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="2e370-150">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<message>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md)
