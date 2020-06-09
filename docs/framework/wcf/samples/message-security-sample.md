---
title: Beispiel für Nachrichtensicherheit
ms.date: 03/30/2017
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
ms.openlocfilehash: 935695a46e907bf1deeb2e5cb24917ba92b81fe0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584850"
---
# <a name="message-security-sample"></a><span data-ttu-id="000a8-102">Beispiel für Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="000a8-102">Message Security Sample</span></span>
<span data-ttu-id="000a8-103">In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die `basicHttpBinding` und Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="000a8-103">This sample demonstrates how to implement an application that uses the `basicHttpBinding` and message security.</span></span> <span data-ttu-id="000a8-104">Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="000a8-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="000a8-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="000a8-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="000a8-106">Der Sicherheitsmodus von `basicHttpBinding` kann auf die folgenden Werte festgelegt werden: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` und `None`.</span><span class="sxs-lookup"><span data-stu-id="000a8-106">The security mode of `basicHttpBinding` can be set to the following values: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` and `None`.</span></span> <span data-ttu-id="000a8-107">In der folgenden Datei "App.config" des Beispieldiensts gibt die Endpunktdefinition die `basicHttpBinding` an und verweist auf die Bindungskonfiguration `Binding1` (wie in folgender Beispielkonfiguration gezeigt).</span><span class="sxs-lookup"><span data-stu-id="000a8-107">In the following sample service App.config file, the endpoint definition specifies the `basicHttpBinding` and references a binding configuration named `Binding1`, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="000a8-108">Die Bindungs Konfiguration legt das `mode` -Attribut des [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) auf fest `Message` und legt das- `clientCredentialType` Attribut von [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) auf fest, `Certificate` wie in der folgenden Beispielkonfiguration gezeigt:</span><span class="sxs-lookup"><span data-stu-id="000a8-108">The binding configuration sets the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message` and sets the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) to `Certificate` as shown in the following sample configuration:</span></span>  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="000a8-109">Das vom Dienst zum Authentifizieren beim Client verwendete Zertifikat wird im Verhaltensabschnitt der Konfigurationsdatei im Element `serviceCredentials` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="000a8-109">The certificate that the service uses to authenticate itself to the client is set in the behaviors section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="000a8-110">Der Validierungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im Verhaltensabschnitt im `clientCertificate`-Element festgelegt.</span><span class="sxs-lookup"><span data-stu-id="000a8-110">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the behaviors section under the `clientCertificate` element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="000a8-111">Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="000a8-111">The same binding and security details are specified in the client configuration file.</span></span>  
  
 <span data-ttu-id="000a8-112">Die Identität des Aufrufers wird im Dienstkonsolenfenster angezeigt, indem folgender Code verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="000a8-112">The identity of the caller is displayed in the service console window by using the following code:</span></span>  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 <span data-ttu-id="000a8-113">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="000a8-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="000a8-114">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="000a8-114">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="000a8-115">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="000a8-115">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="000a8-116">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="000a8-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="000a8-117">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="000a8-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="000a8-118">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="000a8-118">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="000a8-119">Führen Sie "Setup.bat" im Beispielinstallationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-119">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="000a8-120">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="000a8-120">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="000a8-121">Die Batchdatei "Setup.bat" ist dafür ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="000a8-121">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="000a8-122">Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="000a8-122">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="000a8-123">Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="000a8-123">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
2. <span data-ttu-id="000a8-124">Führen Sie die Dienstanwendung in "\service\bin" aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-124">Run the service application from \service\bin.</span></span>  
  
3. <span data-ttu-id="000a8-125">Führen Sie die Clientanwendung in "\client\bin" aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-125">Run the client application from \client\bin.</span></span> <span data-ttu-id="000a8-126">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="000a8-126">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="000a8-127">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="000a8-127">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
5. <span data-ttu-id="000a8-128">Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="000a8-128">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="000a8-129">In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="000a8-129">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="000a8-130">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="000a8-130">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="000a8-131">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="000a8-131">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="000a8-132">Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="000a8-132">Copy the service program files to the service directory on the server.</span></span> <span data-ttu-id="000a8-133">Kopieren Sie auch die Dateien "Setup.bat", "Cleanup.bat" und "ImportClientCert.bat" auf den Server.</span><span class="sxs-lookup"><span data-stu-id="000a8-133">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the server.</span></span>  
  
3. <span data-ttu-id="000a8-134">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="000a8-134">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="000a8-135">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="000a8-135">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="000a8-136">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="000a8-136">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="000a8-137">Führen Sie auf dem Server `setup.bat service` aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-137">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="000a8-138">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="000a8-138">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="000a8-139">Bearbeiten Sie die Datei "Service. exe. config" so, dass Sie den neuen Zertifikat Namen (im- `findValue` Attribut im-Element) widerspiegelt, der mit [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) dem voll qualifizierten Domänen Namen des Computers identisch ist.</span><span class="sxs-lookup"><span data-stu-id="000a8-139">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) element) which is the same as the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="000a8-140">Ändern Sie auch den Wert der Basisadresse, um anstelle von "localhost" einen vollqualifizierten Computernamen anzugeben`.`</span><span class="sxs-lookup"><span data-stu-id="000a8-140">Also change the value of the base address to specify a fully-qualified machine name instead of localhost`.`</span></span>  
  
7. <span data-ttu-id="000a8-141">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="000a8-141">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="000a8-142">Führen Sie auf dem Client `setup.bat client` aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-142">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="000a8-143">Durch Ausführen von  mit dem Argument  wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.</span><span class="sxs-lookup"><span data-stu-id="000a8-143">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="000a8-144">Ändern Sie in der Datei "Client.exe.config" auf dem Clientcomputer den Wert für die Adresse des Endpunkts so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="000a8-144">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="000a8-145">Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.</span><span class="sxs-lookup"><span data-stu-id="000a8-145">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="000a8-146">Ändern Sie auch das- `findValue` Attribut von [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) in den neuen Dienst Zertifikat Namen, der den voll qualifizierten Domänen Namen des Servers ist.</span><span class="sxs-lookup"><span data-stu-id="000a8-146">Also change the `findValue` attribute of the [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) to the new service certificate name which is the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="000a8-147">Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="000a8-147">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="000a8-148">Führen Sie auf dem Client "ImportServiceCert.bat" aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-148">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="000a8-149">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="000a8-149">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="000a8-150">Führen Sie auf dem Server "ImportClientCert.bat" aus. Dadurch wird das Clientzertifikat von der Datei "Client.cer" in den LocalMachine &#8211; TrustedPeople-Speicher importiert.</span><span class="sxs-lookup"><span data-stu-id="000a8-150">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="000a8-151">Führen Sie auf dem Dienstcomputer die Datei "Service.exe" über eine Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="000a8-151">On the service machine, run Service.exe from a command prompt.</span></span>  
  
14. <span data-ttu-id="000a8-152">Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="000a8-152">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
    1. <span data-ttu-id="000a8-153">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="000a8-153">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="000a8-154">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="000a8-154">To clean up after the sample</span></span>  
  
- <span data-ttu-id="000a8-155">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="000a8-155">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="000a8-156">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="000a8-156">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="000a8-157">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, stellen Sie sicher, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="000a8-157">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="000a8-158">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="000a8-158">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="000a8-159">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="000a8-159">The samples may already be installed on your machine.</span></span> <span data-ttu-id="000a8-160">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="000a8-160">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="000a8-161">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="000a8-161">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="000a8-162">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="000a8-162">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`  
