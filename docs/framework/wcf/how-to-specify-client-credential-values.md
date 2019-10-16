---
title: 'Gewusst wie: Angeben der Clientanmeldeinformationswerte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 2417c2dd16224d6cbf00d3f1f4a8958420830b6c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319860"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="e12ac-102">Gewusst wie: Angeben der Clientanmeldeinformationswerte</span><span class="sxs-lookup"><span data-stu-id="e12ac-102">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="e12ac-103">Mithilfe von Windows Communication Foundation (WCF) kann der Dienst angeben, wie ein Client für den Dienst authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="e12ac-103">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="e12ac-104">Ein Dienst kann beispielsweise festlegen, dass der Client mit einem Zertifikat authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="e12ac-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="e12ac-105">So bestimmen Sie den Typ der Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="e12ac-105">To determine the client credential type</span></span>

1. <span data-ttu-id="e12ac-106">Rufen Sie die Metadaten aus dem Metadatenendpunkt des Diensts ab.</span><span class="sxs-lookup"><span data-stu-id="e12ac-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="e12ac-107">Die Metadaten umfassen in der Regel zwei Dateien: den Clientcode in der Programmiersprache Ihrer Wahl (die Standardeinstellung ist Visual C#) und eine XML-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e12ac-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="e12ac-108">Eine Möglichkeit zum Abrufen der Metadaten ist, das Tool "Svcutil.exe" zu verwenden, um den Clientcode und die Clientkonfiguration zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e12ac-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="e12ac-109">Weitere Informationen finden Sie unter [Abrufen von Metadaten](./feature-details/retrieving-metadata.md) und [Service Model Metadata Utility Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e12ac-109">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="e12ac-110">Öffnen Sie die XML-Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e12ac-110">Open the XML configuration file.</span></span> <span data-ttu-id="e12ac-111">Wenn Sie das Tool "Svcutil.exe" verwenden, lautet der Standardname der Datei "Output.config".</span><span class="sxs-lookup"><span data-stu-id="e12ac-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="e12ac-112">Suchen Sie das **\<Security->** Element mit dem **Mode** -Attribut ( **\<Security Mode =** `MessageOrTransport` **>** , wobei `MessageOrTransport` auf einen der Sicherheitsmodi festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e12ac-112">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="e12ac-113">Suchen Sie nach dem untergeordneten Element, das dem Moduswert entspricht.</span><span class="sxs-lookup"><span data-stu-id="e12ac-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="e12ac-114">Wenn der Modus z. b. auf **Message**festgelegt ist, suchen Sie das >-Element **\<message** , das im **\<Security->** Element enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e12ac-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="e12ac-115">Beachten Sie den Wert, der dem **clientkredentialtype** -Attribut zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e12ac-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="e12ac-116">Der tatsächliche Wert hängt davon ab, welcher Modus verwendet wird: Transport oder Nachricht.</span><span class="sxs-lookup"><span data-stu-id="e12ac-116">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="e12ac-117">Der folgende XML-Code veranschaulicht die Konfiguration für einen Client, der die Nachrichtensicherheit verwendet und ein Zertifikat zum Authentifizieren des Clients erfordert.</span><span class="sxs-lookup"><span data-stu-id="e12ac-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="e12ac-118">Beispiel: TCP-Transportmodus mit einem Zertifikat als Clientanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="e12ac-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="e12ac-119">In diesem Beispiel wird der Sicherheitsmodus auf "Transport" und der Clientanmeldeinformationswert auf ein X.509-Zertifikat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e12ac-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="e12ac-120">Die folgenden Vorgänge zeigen, wie Sie den Clientanmeldeinformationswert für den Client im Code und in der Konfiguration festlegen können.</span><span class="sxs-lookup"><span data-stu-id="e12ac-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="e12ac-121">Dabei wird davon ausgegangen, dass Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet haben, um die Metadaten (Code und Konfiguration) vom Dienst zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e12ac-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="e12ac-122">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen eines Clients](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="e12ac-122">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="e12ac-123">So legen Sie den Clientanmeldeinformationswert für den Client im Code fest</span><span class="sxs-lookup"><span data-stu-id="e12ac-123">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="e12ac-124">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) , um Code und Konfiguration aus dem Dienst zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e12ac-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="e12ac-125">Erstellen Sie eine Instanz des WCF-Clients mithilfe des generierten Codes.</span><span class="sxs-lookup"><span data-stu-id="e12ac-125">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="e12ac-126">Legen Sie für die Clientklasse die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der <xref:System.ServiceModel.ClientBase%601>-Klasse auf einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="e12ac-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="e12ac-127">In diesem Beispiel wird die Eigenschaft auf ein X.509-Zertifikat mit der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>-Klasse festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e12ac-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="e12ac-128">Sie können jede beliebige Enumeration der <xref:System.Security.Cryptography.X509Certificates.X509FindType>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="e12ac-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="e12ac-129">Der Betreffname wird hier verwendet, für den Fall, dass das Zertifikat (aufgrund des Ablaufdatums) geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e12ac-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="e12ac-130">Anhand des Betreffnamens kann die Infrastruktur das Zertifikat wieder suchen.</span><span class="sxs-lookup"><span data-stu-id="e12ac-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="e12ac-131">So legen Sie den Clientanmeldeinformationswert für den Client in der Konfiguration fest</span><span class="sxs-lookup"><span data-stu-id="e12ac-131">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="e12ac-132">Fügen Sie dem [\<behavior->](../configure-apps/file-schema/wcf/behaviors.md) Element ein >-Element vom Typ " [\<behavior](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) " hinzu.</span><span class="sxs-lookup"><span data-stu-id="e12ac-132">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="e12ac-133">Fügen Sie dem [\<verhalten>](../configure-apps/file-schema/wcf/behaviors.md) Element ein [>-Element \<clientanmelde](../configure-apps/file-schema/wcf/clientcredentials.md) Informationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="e12ac-133">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="e12ac-134">Achten Sie darauf, für das erforderliche `name`-Attribut einen geeigneten Wert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e12ac-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="e12ac-135">Fügen Sie dem [> Element \<clientanmelde](../configure-apps/file-schema/wcf/clientcredentials.md) Informationen ein [>-Element \<clientcertificate](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) hinzu.</span><span class="sxs-lookup"><span data-stu-id="e12ac-135">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="e12ac-136">Legen Sie für die folgenden Attribute geeignete Werte fest: `storeLocation`, `storeName`, `x509FindType` und `findValue`, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e12ac-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="e12ac-137">Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](./feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="e12ac-137">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

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

5. <span data-ttu-id="e12ac-138">Wenn Sie den Client konfigurieren, legen Sie das Verhalten fest, indem Sie das `behaviorConfiguration`-Attribut des `<endpoint>`-Elements festlegen, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e12ac-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="e12ac-139">Das Endpunkt Element ist ein untergeordnetes Element des [>-Elements \<client](../configure-apps/file-schema/wcf/client.md) .</span><span class="sxs-lookup"><span data-stu-id="e12ac-139">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="e12ac-140">Geben Sie auch den Namen der Bindungskonfiguration an, indem Sie das `bindingConfiguration`-Attribut auf die Bindung für den Client festlegen.</span><span class="sxs-lookup"><span data-stu-id="e12ac-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="e12ac-141">Wenn Sie eine generierte Konfigurationsdatei verwenden, wird der Name der Bindung automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="e12ac-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="e12ac-142">In diesem Beispiel lautet der Name `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="e12ac-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="e12ac-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e12ac-143">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="e12ac-144">Programmieren der WCF-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e12ac-144">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="e12ac-145">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="e12ac-145">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e12ac-146">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e12ac-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="e12ac-147">Arbeiten mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="e12ac-147">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="e12ac-148">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="e12ac-148">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="e12ac-149">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="e12ac-149">\<netTcpBinding></span></span>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [<span data-ttu-id="e12ac-150">\<Security ></span><span class="sxs-lookup"><span data-stu-id="e12ac-150">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [<span data-ttu-id="e12ac-151">\<message ></span><span class="sxs-lookup"><span data-stu-id="e12ac-151">\<message></span></span>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [<span data-ttu-id="e12ac-152">\<-Verhalten ></span><span class="sxs-lookup"><span data-stu-id="e12ac-152">\<behavior></span></span>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [<span data-ttu-id="e12ac-153">\<-Verhalten ></span><span class="sxs-lookup"><span data-stu-id="e12ac-153">\<behaviors></span></span>](../configure-apps/file-schema/wcf/behaviors.md)
- [<span data-ttu-id="e12ac-154">\<clientcertificate ></span><span class="sxs-lookup"><span data-stu-id="e12ac-154">\<clientCertificate></span></span>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [<span data-ttu-id="e12ac-155">\<clientanmelde Informationen ></span><span class="sxs-lookup"><span data-stu-id="e12ac-155">\<clientCredentials></span></span>](../configure-apps/file-schema/wcf/clientcredentials.md)
