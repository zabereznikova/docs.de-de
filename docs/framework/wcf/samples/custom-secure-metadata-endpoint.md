---
title: Benutzerdefinierter sicherer Metadatenendpunkt
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
ms.openlocfilehash: 6e392f396b62ad2a3d3cda6e7d6ff31f186f0964
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592436"
---
# <a name="custom-secure-metadata-endpoint"></a><span data-ttu-id="49932-102">Benutzerdefinierter sicherer Metadatenendpunkt</span><span class="sxs-lookup"><span data-stu-id="49932-102">Custom Secure Metadata Endpoint</span></span>
<span data-ttu-id="49932-103">In diesem Beispiel wird veranschaulicht, wie ein Dienst mit einem sicheren Metadatenendpunkt, der eine der nicht-Metadatenaustausch-Bindungen verwendet, implementiert wird und wie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) oder Clients zum Abrufen der Metadaten von einem solchen Metadatenendpunkt konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="49932-103">This sample demonstrates how to implement a service with a secure metadata endpoint that uses one of the non-metadata exchange bindings, and how to configure [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) or clients to fetch the metadata from such a metadata endpoint.</span></span> <span data-ttu-id="49932-104">Es gibt zwei vom System bereitgestellte Bindungen, die für die Bereitstellung von Metadatenendpunkten verfügbar sind: mexHttpBinding und mexHttpsBinding.</span><span class="sxs-lookup"><span data-stu-id="49932-104">There are two system-provided bindings available for exposing metadata endpoints: mexHttpBinding and mexHttpsBinding.</span></span> <span data-ttu-id="49932-105">mexHttpBinding wird verwendet, um einen Metadatenendpunkt über eine nicht sichere Verbindung über HTTP bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="49932-105">mexHttpBinding is used to expose a metadata endpoint over HTTP in a non-secure manner.</span></span> <span data-ttu-id="49932-106">mexHttpsBinding wird verwendet, um einen Metadatenendpunkt über eine sichere Verbindung über HTTPS verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="49932-106">mexHttpsBinding is used to expose a metadata endpoint over HTTPS in a secure manner.</span></span> <span data-ttu-id="49932-107">In diesem Beispiel wird veranschaulicht, wie ein sicherer Metadatenendpunkt mithilfe der <xref:System.ServiceModel.WSHttpBinding> verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="49932-107">This sample illustrates how to expose a secure metadata endpoint using the <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="49932-108">Diese Vorgehensweise eignet sich, wenn Sie die Sicherheitseinstellungen der Bindung ändern, aber nicht HTTPS verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="49932-108">You would want to do this when you want to change the security settings on the binding, but you do not want to use HTTPS.</span></span> <span data-ttu-id="49932-109">Wenn Sie mexHttpsBinding verwenden, ist der Metadatenendpunkt sicher, die Bindungseinstellungen können jedoch nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="49932-109">If you use the mexHttpsBinding your metadata endpoint will be secure, but there is no way to modify the binding settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49932-110">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="49932-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="49932-111">Dienst</span><span class="sxs-lookup"><span data-stu-id="49932-111">Service</span></span>  
 <span data-ttu-id="49932-112">Der Dienst in diesem Beispiel hat zwei Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="49932-112">The service in this sample has two endpoints.</span></span> <span data-ttu-id="49932-113">Der Anwendungsendpunkt wird vom `ICalculator`-Vertrag auf einer `WSHttpBinding` mit aktivierter `ReliableSession` und einer `Message`-Sicherheit mit Zertifikaten genutzt.</span><span class="sxs-lookup"><span data-stu-id="49932-113">The application endpoint serves the `ICalculator` contract on a `WSHttpBinding` with `ReliableSession` enabled and `Message` security using certificates.</span></span> <span data-ttu-id="49932-114">Der Metadatenendpunkt verwendet ebenfalls `WSHttpBinding` mit denselben Sicherheitseinstellungen, jedoch ohne `ReliableSession`.</span><span class="sxs-lookup"><span data-stu-id="49932-114">The metadata endpoint also uses `WSHttpBinding`, with the same security settings but with no `ReliableSession`.</span></span> <span data-ttu-id="49932-115">Nachfolgend wird die relevante Konfiguration dargestellt:</span><span class="sxs-lookup"><span data-stu-id="49932-115">Here is the relevant configuration:</span></span>  
  
```xml  
<services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 <span data-ttu-id="49932-116">In vielen der anderen Beispiele verwendet der Metadatenendpunkt die standardmäßige `mexHttpBinding`, die nicht sicher ist.</span><span class="sxs-lookup"><span data-stu-id="49932-116">In many of the other samples, the metadata endpoint uses the default `mexHttpBinding`, which is not secure.</span></span> <span data-ttu-id="49932-117">Hier werden die Metadaten durch `WSHttpBinding` mit `Message`-Sicherheit gesichert.</span><span class="sxs-lookup"><span data-stu-id="49932-117">Here the metadata is secured using `WSHttpBinding` with `Message` security.</span></span> <span data-ttu-id="49932-118">Damit Metadaten-Clients diese Metadaten abrufen können, müssen sie mit einer übereinstimmenden Bindung konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="49932-118">In order for metadata clients to retrieve this metadata, they must be configured with a matching binding.</span></span> <span data-ttu-id="49932-119">In diesem Beispiel werden zwei dieser Clients dargestellt.</span><span class="sxs-lookup"><span data-stu-id="49932-119">This sample demonstrates two such clients.</span></span>  
  
 <span data-ttu-id="49932-120">Der erste Client verwendet zum Abrufen der Metadaten und Generieren von Clientcode sowie der Konfiguration zur Entwurfszeit die Datei „Svcutil.exe“.</span><span class="sxs-lookup"><span data-stu-id="49932-120">The first client uses Svcutil.exe to fetch the metadata and generate client code and configuration at design time.</span></span> <span data-ttu-id="49932-121">Da der Dienst eine nicht standardmäßige Bindung für die Metadaten verwendet, muss das Tool „Svcutil.exe“ entsprechend konfiguriert werden, sodass es die Metadaten vom Dienst mithilfe dieser Bindung abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="49932-121">Because the service uses a non-default binding for the metadata, the Svcutil.exe tool must be specifically configured so that it can get the metadata from the service using that binding.</span></span>  
  
 <span data-ttu-id="49932-122">Der zweite Client nutzt `MetadataResolver`, um die Metadaten für einen bekannten Vertrag dynamisch abzurufen und dann Vorgänge auf dem dynamisch generierten Client auszulösen.</span><span class="sxs-lookup"><span data-stu-id="49932-122">The second client uses the `MetadataResolver` to dynamically fetch the metadata for a known contract and then invoke operations on the dynamically generated client.</span></span>  
  
## <a name="svcutil-client"></a><span data-ttu-id="49932-123">Svcutil-Client</span><span class="sxs-lookup"><span data-stu-id="49932-123">Svcutil client</span></span>  
 <span data-ttu-id="49932-124">Wenn Sie die Standardbindung zum Hosten des `IMetadataExchange`-Endpunkts verwenden, können Sie „Svcutil.exe“ mit der Adresse dieses Endpunkts ausführen:</span><span class="sxs-lookup"><span data-stu-id="49932-124">When using the default binding to host your `IMetadataExchange` endpoint, you can run Svcutil.exe with the address of that endpoint:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="49932-125">Und es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="49932-125">and it works.</span></span> <span data-ttu-id="49932-126">In diesem Beispiel verwendet der Server jedoch einen nicht standardmäßigen Endpunkt, um die Metadaten zu hosten.</span><span class="sxs-lookup"><span data-stu-id="49932-126">But in this sample, the server uses a non-default endpoint to host the metadata.</span></span> <span data-ttu-id="49932-127">Deshalb muss „Svcutil.exe“ angewiesen werden, die richtige Bindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="49932-127">So Svcutil.exe must be instructed to use the correct binding.</span></span> <span data-ttu-id="49932-128">Dazu können Sie eine Datei "Svcutil.exe.config" verwenden.</span><span class="sxs-lookup"><span data-stu-id="49932-128">This can be done using a Svcutil.exe.config file.</span></span>  
  
 <span data-ttu-id="49932-129">Die Datei "Svcutil.exe.config" sieht wie eine normale Clientkonfigurationsdatei aus.</span><span class="sxs-lookup"><span data-stu-id="49932-129">The Svcutil.exe.config file looks like a normal client configuration file.</span></span> <span data-ttu-id="49932-130">Die einzigen ungewöhnlichen Aspekte sind der Clientendpunktname und -vertrag:</span><span class="sxs-lookup"><span data-stu-id="49932-130">The only unusual aspects are the client endpoint name and contract:</span></span>  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="49932-131">Der Endpunktname muss mit dem Namen des Schemas der Adresse übereinstimmen, auf der die Metadaten gehostet sind, und der Endpunktvertrag muss `IMetadataExchange` lauten.</span><span class="sxs-lookup"><span data-stu-id="49932-131">The endpoint name must be the name of the scheme of the address where the metadata is hosted and the endpoint contract must be `IMetadataExchange`.</span></span> <span data-ttu-id="49932-132">Wenn also "Svcutil.exe" mit einer Befehlszeile wie der folgenden ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="49932-132">Thus, when Svcutil.exe is run with a command-line such as the following:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="49932-133">sucht es nach dem Endpunkt namens „http“ und dem Vertrag `IMetadataExchange`, um die Bindung und das Verhalten des Kommunikationsaustauschs mit dem Metadatenendpunkt zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="49932-133">it looks for the endpoint named "http" and contract `IMetadataExchange` to configure the binding and behavior of the communication exchange with the metadata endpoint.</span></span> <span data-ttu-id="49932-134">Der übrige Teil der Datei „Svcutil.exe.config“ im Beispiel legt die Bindungskonfiguration und Verhaltensanmeldeinformationen fest, um mit der Konfiguration des Servers für den Metadatenendpunkt übereinzustimmen.</span><span class="sxs-lookup"><span data-stu-id="49932-134">The rest of the Svcutil.exe.config file in the sample specifies the binding configuration and behavior credentials to match the server's configuration of the metadata endpoint.</span></span>  
  
 <span data-ttu-id="49932-135">Damit "Svcutil.exe" die Konfiguration in "Svcutil.exe.config" übernehmen kann, muss sich "Svcutil.exe" im selben Verzeichnis wie die Konfigurationsdatei befinden.</span><span class="sxs-lookup"><span data-stu-id="49932-135">In order for Svcutil.exe to pick up the configuration in Svcutil.exe.config, Svcutil.exe must be in the same directory as the configuration file.</span></span> <span data-ttu-id="49932-136">Demzufolge müssen Sie "Svcutil.exe" aus seinem Installationsort in das Verzeichnis kopieren, in dem die Datei "Svcutil.exe.config" gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="49932-136">As a result, you must copy Svcutil.exe from its install location to the directory that contains the Svcutil.exe.config file.</span></span> <span data-ttu-id="49932-137">Führen Sie dann in diesem Verzeichnis den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="49932-137">Then from that directory, run the following command:</span></span>  
  
```console  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="49932-138">Die führende ". \\ " stellt sicher, dass die Kopie von "Svcutil. exe" in diesem Verzeichnis (das mit der entsprechenden Datei "Svcutil. exe. config") ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49932-138">The leading ".\\" ensures that the copy of Svcutil.exe in this directory (the one which has a corresponding Svcutil.exe.config) is run.</span></span>  
  
## <a name="metadataresolver-client"></a><span data-ttu-id="49932-139">MetadataResolver-Client</span><span class="sxs-lookup"><span data-stu-id="49932-139">MetadataResolver client</span></span>  
 <span data-ttu-id="49932-140">Wenn der Client zur Entwurfszeit den Vertrag kennt und weiß, wie er mit den Metadaten kommuniziert, kann er mithilfe von `MetadataResolver` die Bindung und Adresse der Anwendungsendpunkte dynamisch herausfinden.</span><span class="sxs-lookup"><span data-stu-id="49932-140">If the client knows the contract and how to talk to the metadata at design time, the client can dynamically find out the binding and address of application endpoints using the `MetadataResolver`.</span></span> <span data-ttu-id="49932-141">Dies wird in diesem Beispielclient dargestellt. Es wird gezeigt, wie die vom `MetadataResolver` verwendete Bindung und die Anmeldeinformationen konfiguriert werden, indem ein `MetadataExchangeClient` erstellt und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="49932-141">This sample client demonstrates this, showing how to configure the binding and credentials used by `MetadataResolver` by creating and configuring a `MetadataExchangeClient`.</span></span>  
  
 <span data-ttu-id="49932-142">Die Bindungs- und Zertifikatsinformationen, die in „Svcutil.exe.config“ angezeigt wurden, können auf dem `MetadataExchangeClient` zwingend angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="49932-142">The same binding and certificate information that appeared in Svcutil.exe.config can be specified imperatively on the `MetadataExchangeClient`:</span></span>  
  
```csharp  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 <span data-ttu-id="49932-143">Nachdem der `mexClient` konfiguriert ist, können Sie die für Sie interessanten Verträge auflisten und `MetadataResolver` verwenden, um eine Liste der Endpunkte mit diesen Verträgen abzurufen:</span><span class="sxs-lookup"><span data-stu-id="49932-143">With the `mexClient` configured, we can enumerate the contracts we are interested in, and use `MetadataResolver` to fetch a list of endpoints with those contracts:</span></span>  
  
```csharp  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts = new Collection<ContractDescription>();  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints = MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 <span data-ttu-id="49932-144">Abschließend können Sie die Informationen von diesen Endpunkten dazu verwenden, die Bindung und die Adresse einer `ChannelFactory` zu initialisieren, die zum Erstellen von Kanälen für die Kommunikation mit den Anwendungsendpunkten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="49932-144">Finally we can use the information from those endpoints to initialize the binding and address of a `ChannelFactory` used to create channels to communicate with the application endpoints.</span></span>  
  
```csharp  
ChannelFactory<ICalculator> cf = new ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 <span data-ttu-id="49932-145">Als wichtigster Punkt soll in diesem Beispielclient veranschaulicht werden, dass Sie einen `MetadataResolver` zum Festlegen dieser benutzerdefinierten Einstellungen verwenden können, wenn Sie `MetadataExchangeClient` verwenden und benutzerdefinierte Bindungen oder Verhalten für die Metadatenaustauschkommunikation festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="49932-145">The key point of this sample client is to demonstrate that, if you are using `MetadataResolver`, and you must specify custom bindings or behaviors for the metadata exchange communication, you can use a `MetadataExchangeClient` to specify those custom settings.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="49932-146">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="49932-146">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="49932-147">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="49932-147">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="49932-148">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49932-148">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="49932-149">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="49932-149">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="49932-150">Führen Sie "Setup.bat" im Beispielinstallationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="49932-150">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="49932-151">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="49932-151">This installs all the certificates required for running the sample.</span></span> <span data-ttu-id="49932-152">Beachten Sie, dass Setup. bat das Tool FindPrivateKey. exe verwendet, das durch Ausführen von Setupcerttool. bat aus [dem einmaligen Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)installiert wird.</span><span class="sxs-lookup"><span data-stu-id="49932-152">Note that Setup.bat uses the FindPrivateKey.exe tool, which is installed by running setupCertTool.bat from [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="49932-153">Führen Sie die Clientanwendung von "\MetadataResolverClient\bin" oder von ""\SvcutilClient\bin" aus.</span><span class="sxs-lookup"><span data-stu-id="49932-153">Run the client application from \MetadataResolverClient\bin or \SvcutilClient\bin.</span></span> <span data-ttu-id="49932-154">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49932-154">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="49932-155">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="49932-155">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
4. <span data-ttu-id="49932-156">Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="49932-156">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="49932-157">In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="49932-157">Other security samples use the same certificates.</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="49932-158">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="49932-158">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="49932-159">Führen Sie auf dem Server `setup.bat service` aus.</span><span class="sxs-lookup"><span data-stu-id="49932-159">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="49932-160">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="49932-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
2. <span data-ttu-id="49932-161">Bearbeiten Sie auf dem Server die Datei "Web.config", damit sie dem neuen Zertifikatnamen entspricht,</span><span class="sxs-lookup"><span data-stu-id="49932-161">On the server, edit Web.config to reflect the new certificate name.</span></span> <span data-ttu-id="49932-162">Das heißt, ändern Sie das- `findValue` Attribut im- [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) Element in den voll qualifizierten Domänen Namen des Computers.</span><span class="sxs-lookup"><span data-stu-id="49932-162">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the machine.</span></span>  
  
3. <span data-ttu-id="49932-163">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="49932-163">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
4. <span data-ttu-id="49932-164">Führen Sie auf dem Client `setup.bat client` aus.</span><span class="sxs-lookup"><span data-stu-id="49932-164">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="49932-165">Wenn `setup.bat` Sie mit dem- `client` Argument ausführen, wird ein Client Zertifikat mit dem Namen Client.com erstellt und das Client Zertifikat in eine Datei mit dem Namen Client. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="49932-165">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5. <span data-ttu-id="49932-166">Ändern Sie in der Datei "App.config" des `MetadataResolverClient` auf dem Clientcomputer den Wert für die Adresse des MEX-Endpunkts, sodass er mit der neuen Adresse des Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="49932-166">In the App.config file of the `MetadataResolverClient` on the client machine, change the address value of the mex endpoint to match the new address of your service.</span></span> <span data-ttu-id="49932-167">Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.</span><span class="sxs-lookup"><span data-stu-id="49932-167">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="49932-168">Ändern Sie auch das Vorkommen von localhost in der Datei "metadataResolverClient.cs" in den neuen Namen des Dienstzertifikats (den vollqualifizierten Domänennamen des Servers).</span><span class="sxs-lookup"><span data-stu-id="49932-168">Also change the occurrence of "localhost" in the metadataResolverClient.cs file to the new service certificate name (the fully-qualified domain name of the server).</span></span> <span data-ttu-id="49932-169">Führen Sie denselben Schritt für die Datei "App.config" des "SvcutilClient"-Projekts aus.</span><span class="sxs-lookup"><span data-stu-id="49932-169">Do the same thing for the App.config of the SvcutilClient project.</span></span>  
  
6. <span data-ttu-id="49932-170">Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="49932-170">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7. <span data-ttu-id="49932-171">Führen Sie auf dem Client `ImportServiceCert.bat` aus.</span><span class="sxs-lookup"><span data-stu-id="49932-171">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="49932-172">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="49932-172">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8. <span data-ttu-id="49932-173">Führen Sie auf dem Server `ImportClientCert.bat` aus. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="49932-173">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="49932-174">Erstellen Sie auf dem Dienstcomputer das Dienstprojekt in Visual Studio, und wählen Sie die Hilfeseite in einem Webbrowser aus, um zu überprüfen, ob sie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="49932-174">On the service machine, build the service project in Visual Studio and select the help page in a web browser to verify that it is running.</span></span>  
  
10. <span data-ttu-id="49932-175">Führen Sie auf dem Clientcomputer den MetadataResolverClient oder den SvcutilClient von Visual Studio aus.</span><span class="sxs-lookup"><span data-stu-id="49932-175">On the client machine, run the MetadataResolverClient or the SvcutilClient from VS.</span></span>  
  
    1. <span data-ttu-id="49932-176">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="49932-176">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="49932-177">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="49932-177">To clean up after the sample</span></span>  
  
- <span data-ttu-id="49932-178">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="49932-178">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="49932-179">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="49932-179">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="49932-180">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, stellen Sie sicher, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="49932-180">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="49932-181">Führen Sie dazu folgenden Befehl aus: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`</span><span class="sxs-lookup"><span data-stu-id="49932-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span></span> <span data-ttu-id="49932-182">Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="49932-182">For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="49932-183">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="49932-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="49932-184">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="49932-184">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="49932-185">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49932-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="49932-186">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="49932-186">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
