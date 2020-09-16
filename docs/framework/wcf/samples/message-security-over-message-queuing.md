---
title: Nachrichtensicherheit über Message Queuing
ms.date: 03/30/2017
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
ms.openlocfilehash: 1733cea17c82f85751b810f4a6033caefd828e29
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558640"
---
# <a name="message-security-over-message-queuing"></a><span data-ttu-id="fda4b-102">Nachrichtensicherheit über Message Queuing</span><span class="sxs-lookup"><span data-stu-id="fda4b-102">Message Security over Message Queuing</span></span>
<span data-ttu-id="fda4b-103">Dieses Beispiel zeigt, wie eine Anwendung implementiert wird, in der WS-Sicherheit mit X.509v3-Zertifikatauthentifizierung für den Client verwendet wird, und die eine Serverauthentifizierung mit dem X.509v3-Zertifikat des Servers über MSMQ erfordert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-103">This sample demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span> <span data-ttu-id="fda4b-104">Nachrichtensicherheit wird manchmal vorgezogen, um sicherzustellen, dass die Nachrichten im MSMQ-Speicher verschlüsselt bleiben und die Anwendung ihre eigene Authentifizierung der Nachricht ausführt.</span><span class="sxs-lookup"><span data-stu-id="fda4b-104">Message security is sometimes more desirable to ensure that the messages in the MSMQ store stay encrypted and the application can perform its own authentication of the message.</span></span>

 <span data-ttu-id="fda4b-105">Dieses Beispiel basiert auf dem [transaktiven MSMQ-Bindungs](transacted-msmq-binding.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fda4b-105">This sample is based on the [Transacted MSMQ Binding](transacted-msmq-binding.md) sample.</span></span> <span data-ttu-id="fda4b-106">Die Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-106">The messages are encrypted and signed.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fda4b-107">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="fda4b-107">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="fda4b-108">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="fda4b-108">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="fda4b-109">Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fda4b-109">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="fda4b-110">Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="fda4b-110">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="fda4b-111">Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ-Warteschlangen-Manager erstellen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-111">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="fda4b-112">Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="fda4b-112">Follow these steps to create a queue in Windows 2008.</span></span>

    1. <span data-ttu-id="fda4b-113">Öffnen Sie Server-Manager in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="fda4b-113">Open Server Manager in Visual Studio 2012.</span></span>

    2. <span data-ttu-id="fda4b-114">Erweitern Sie die Registerkarte **Features** .</span><span class="sxs-lookup"><span data-stu-id="fda4b-114">Expand the **Features** tab.</span></span>

    3. <span data-ttu-id="fda4b-115">Klicken Sie mit der rechten Maustaste auf private Meldungs **Warteschlangen**, und wählen Sie **neu**, **private**</span><span class="sxs-lookup"><span data-stu-id="fda4b-115">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>

    4. <span data-ttu-id="fda4b-116">Aktivieren Sie das Kontrollkästchen **transaktional** .</span><span class="sxs-lookup"><span data-stu-id="fda4b-116">Check the **Transactional** box.</span></span>

    5. <span data-ttu-id="fda4b-117">Geben Sie `ServiceModelSamplesTransacted` als Namen für die neue Warteschlange ein.</span><span class="sxs-lookup"><span data-stu-id="fda4b-117">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>

3. <span data-ttu-id="fda4b-118">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="fda4b-119">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="fda4b-119">To run the sample on the same computer</span></span>

1. <span data-ttu-id="fda4b-120">Vergewissern Sie sich, dass der Pfad den Ordner enthält, in dem sich die Dateien Makecert.exe und FindPrivateKey.exe befinden.</span><span class="sxs-lookup"><span data-stu-id="fda4b-120">Ensure that the path includes the folder that contains Makecert.exe and FindPrivateKey.exe.</span></span>

2. <span data-ttu-id="fda4b-121">Führen Sie "Setup.bat" im Beispielinstallationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="fda4b-121">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="fda4b-122">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="fda4b-122">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fda4b-123">Wenn Sie mit dem Beispiel fertig sind, müssen Sie die Datei Cleanup.bat ausführen, um die Zertifikate zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-123">Ensure that you remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="fda4b-124">In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="fda4b-124">Other security samples use the same certificates.</span></span>  
  
3. <span data-ttu-id="fda4b-125">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="fda4b-125">Launch Service.exe from \service\bin.</span></span>  
  
4. <span data-ttu-id="fda4b-126">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="fda4b-126">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="fda4b-127">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fda4b-127">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="fda4b-128">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-128">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="fda4b-129">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="fda4b-129">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="fda4b-130">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportClientCert.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="fda4b-130">Copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service computer.</span></span>  
  
2. <span data-ttu-id="fda4b-131">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="fda4b-131">Create a directory on the client computer for the client binaries.</span></span>  
  
3. <span data-ttu-id="fda4b-132">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="fda4b-132">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="fda4b-133">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="fda4b-133">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
4. <span data-ttu-id="fda4b-134">Führen Sie auf dem Server `setup.bat service` aus.</span><span class="sxs-lookup"><span data-stu-id="fda4b-134">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="fda4b-135">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-135">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
5. <span data-ttu-id="fda4b-136">Bearbeiten Sie die service.exe.config des dienstanders, um den neuen Zertifikat Namen (im-Attribut im) widerzuspiegeln, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist.</span><span class="sxs-lookup"><span data-stu-id="fda4b-136">Edit service's service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span>  
  
6. <span data-ttu-id="fda4b-137">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="fda4b-137">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
7. <span data-ttu-id="fda4b-138">Führen Sie auf dem Client `setup.bat client` aus.</span><span class="sxs-lookup"><span data-stu-id="fda4b-138">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="fda4b-139">Durch Ausführen von  mit dem Argument  wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-139">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
8. <span data-ttu-id="fda4b-140">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fda4b-140">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="fda4b-141">Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.</span><span class="sxs-lookup"><span data-stu-id="fda4b-141">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  <span data-ttu-id="fda4b-142">Sie müssen auch den Zertifikatnamen des Diensts so ändern, dass er mit dem vollqualifizierten Domänennamen des Dienstcomputers übereinstimmt (im `findValue`-Attribut im `defaultCertificate`-Element von `serviceCertificate` unter `clientCredentials`).</span><span class="sxs-lookup"><span data-stu-id="fda4b-142">You must also change the certificate name of the service to be the same as the fully-qualified domain name of the service computer (in the `findValue` attribute in the `defaultCertificate` element of `serviceCertificate` under `clientCredentials`).</span></span>  
  
9. <span data-ttu-id="fda4b-143">Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="fda4b-143">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
10. <span data-ttu-id="fda4b-144">Führen Sie auf dem Client `ImportServiceCert.bat` aus.</span><span class="sxs-lookup"><span data-stu-id="fda4b-144">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="fda4b-145">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-145">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
11. <span data-ttu-id="fda4b-146">Führen Sie auf dem Server `ImportClientCert.bat` aus. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-146">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="fda4b-147">Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fda4b-147">On the service computer, launch Service.exe from the command prompt.</span></span>  
  
13. <span data-ttu-id="fda4b-148">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="fda4b-148">On the client computer, launch Client.exe from the command prompt.</span></span> <span data-ttu-id="fda4b-149">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-149">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="fda4b-150">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="fda4b-150">To clean up after the sample</span></span>  
  
- <span data-ttu-id="fda4b-151">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="fda4b-151">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="fda4b-152">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="fda4b-152">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="fda4b-153">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="fda4b-153">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="fda4b-154">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="fda4b-154">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>

## <a name="requirements"></a><span data-ttu-id="fda4b-155">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fda4b-155">Requirements</span></span>
 <span data-ttu-id="fda4b-156">Für dieses Beispiel ist es erforderlich, dass MSMQ installiert ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fda4b-156">This sample requires that MSMQ is installed and running.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="fda4b-157">Zeigt</span><span class="sxs-lookup"><span data-stu-id="fda4b-157">Demonstrates</span></span>
 <span data-ttu-id="fda4b-158">Der Client verschlüsselt die Nachricht mit dem öffentlichen Schlüssel des Diensts und signiert sie mit seinem eigenen Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="fda4b-158">The client encrypts the message using the public key of the service and signs the message using its own certificate.</span></span> <span data-ttu-id="fda4b-159">Der Dienst, der die Nachricht aus der Warteschlange liest, authentifiziert das Clientzertifikat mit dem Zertifikat in seinem Speicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-159">The service reading the message from the queue authenticates the client certificate with the certificate in its trusted people store.</span></span> <span data-ttu-id="fda4b-160">Anschließend entschlüsselt er die Nachricht und leitet sie an den Dienstvorgang weiter.</span><span class="sxs-lookup"><span data-stu-id="fda4b-160">It then decrypts the message and dispatches the message to the service operation.</span></span>

 <span data-ttu-id="fda4b-161">Da die Windows Communication Foundation (WCF)-Nachricht als Nutzlast im Text der MSMQ-Nachricht übertragen wird, bleibt der Text im MSMQ-Speicher verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="fda4b-161">Because the Windows Communication Foundation (WCF) message is carried as a payload in the body of the MSMQ message, the body remains encrypted in the MSMQ store.</span></span> <span data-ttu-id="fda4b-162">Dadurch wird sichergestellt, dass die Nachricht von unerwünschter Seite aus eingesehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fda4b-162">This secures the message from unwanted disclosure of the message.</span></span> <span data-ttu-id="fda4b-163">Beachten Sie, dass es für MSMQ selbst keine Rolle spielt, ob die enthaltene Nachricht verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="fda4b-163">Note that MSMQ itself is not aware whether the message it is carrying is encrypted.</span></span>

 <span data-ttu-id="fda4b-164">Im Beispiel wird veranschaulicht, wie gegenseitige Authentifizierung auf Nachrichtenebene mit MSMQ verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fda4b-164">The sample demonstrates how mutual authentication at the message level can be used with MSMQ.</span></span> <span data-ttu-id="fda4b-165">Die Zertifikate werden "Out-of-Band" ausgetauscht.</span><span class="sxs-lookup"><span data-stu-id="fda4b-165">The certificates are exchanged out-of-band.</span></span> <span data-ttu-id="fda4b-166">Dies ist bei Anwendungen in einer Warteschlange stets der Fall, da der Dienst und der Client nicht zum selben Zeitpunkt aktiv sein müssen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-166">This is always the case with queued application because the service and the client do not have to be up and running at the same time.</span></span>

## <a name="description"></a><span data-ttu-id="fda4b-167">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fda4b-167">Description</span></span>
 <span data-ttu-id="fda4b-168">Der Beispiel Client und der Dienst Code sind identisch mit dem [transaktiven MSMQ-Bindungs](transacted-msmq-binding.md) Beispiel mit einem Unterschied.</span><span class="sxs-lookup"><span data-stu-id="fda4b-168">The sample client and service code are the same as the [Transacted MSMQ Binding](transacted-msmq-binding.md) sample with one difference.</span></span> <span data-ttu-id="fda4b-169">Der Vorgangsvertrag ist mit einer Schutzebene versehen, die anzeigt, dass die Nachricht signiert und verschlüsselt werden muss.</span><span class="sxs-lookup"><span data-stu-id="fda4b-169">The operation contract is annotated with protection level, which suggests that the message must be signed and encrypted.</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 <span data-ttu-id="fda4b-170">Um sicherzustellen, dass die Nachricht mit dem erforderlichen Token zum Identifizieren des Diensts und des Clients gesichert wird, enthält die "App.config" Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-170">To ensure that the message is secured using the required token to identify the service and client, the App.config contains credential information.</span></span>

 <span data-ttu-id="fda4b-171">Die Clientkonfiguration gibt das Dienstzertifikat zum Authentifizieren des Diensts an.</span><span class="sxs-lookup"><span data-stu-id="fda4b-171">The client configuration specifies the service certificate to authenticate the service.</span></span> <span data-ttu-id="fda4b-172">Dabei wird der eigene LocalMachine-Speicher als vertrauenswürdiger Speicher verwendet, damit die Gültigkeit des Diensts sichergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="fda4b-172">It uses its LocalMachine store as the trusted store to rely on the validity of the service.</span></span> <span data-ttu-id="fda4b-173">Außerdem wird das Clientzertifikat angegeben, das zur Dienstauthentifizierung des Clients an die Nachricht angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="fda4b-173">It also specifies the client certificate that is attached with the message for service authentication of the client.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <system.serviceModel>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                binding="netMsmqBinding"
                bindingConfiguration="messageSecurityBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"
                behaviorConfiguration="ClientCertificateBehavior" />
    </client>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate"/>
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <!--
        The clientCredentials behavior allows one to define a certificate to present to a service.
        A certificate is used by a client to authenticate itself to the service and provide message integrity.
        This configuration references the "client.com" certificate installed during the setup instructions.
        -->
          <clientCredentials>
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />
            <serviceCertificate>
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
</configuration>
```

 <span data-ttu-id="fda4b-174">Beachten Sie, dass der Sicherheitsmodus auf "Nachricht" und der ClientCredentialType auf "Zertifikat" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fda4b-174">Note that the security mode is set to Message and the ClientCredentialType is set to Certificate.</span></span>

 <span data-ttu-id="fda4b-175">Die Dienstkonfiguration enthält ein Dienstverhalten, das die Anmeldeinformationen des Diensts angibt, die beim Authentifizieren des Diensts durch den Client verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fda4b-175">The service configuration includes a service behavior that specifies the service's credentials that are used when the client authenticates the service.</span></span> <span data-ttu-id="fda4b-176">Der Serverzertifikat-Antragsteller Name wird im- `findValue` Attribut in der angegeben [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="fda4b-176">The server certificate subject name is specified in the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>

  <appSettings>
    <!-- Use appSetting to configure MSMQ queue name. -->
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />
  </appSettings>

  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"
          behaviorConfiguration="PurchaseOrderServiceBehavior">
        <host>
          <baseAddresses>
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
          </baseAddresses>
        </host>
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"
                  binding="netMsmqBinding"
                  bindingConfiguration="messageSecurityBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <bindings>
        <netMsmqBinding>
            <binding name="messageSecurityBinding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
                </security>
            </binding>
        </netMsmqBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="PurchaseOrderServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <!--
               The serviceCredentials behavior allows one to define a service certificate.
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.
               This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
            <clientCertificate>
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it is trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </clientCertificate>
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

 <span data-ttu-id="fda4b-177">Das Beispiel zeigt, wie die Authentifizierung mithilfe der Konfiguration gesteuert und wie die Identität des Aufrufers aus dem Sicherheitskontext ermittelt wird:</span><span class="sxs-lookup"><span data-stu-id="fda4b-177">The sample demonstrates controlling authentication using configuration, and how to obtain the caller’s identity from the security context, as shown in the following sample code:</span></span>

```csharp
// Service class which implements the service contract.
// Added code to write output to the console window.
public class OrderProcessorService : IOrderProcessor
{
    private string GetCallerIdentity()
    {
        // The client certificate is not mapped to a Windows identity by default.
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information
        // in the certificate that the client used to authenticate itself to the service.
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
    }
  //…
}
```

 <span data-ttu-id="fda4b-178">Beim Ausführen zeigt der Dienstcode die Clientidentifikation an.</span><span class="sxs-lookup"><span data-stu-id="fda4b-178">When run, the service code displays the client identification.</span></span> <span data-ttu-id="fda4b-179">Nachfolgend sehen Sie eine Beispielausgabe vom Dienstcode:</span><span class="sxs-lookup"><span data-stu-id="fda4b-179">The following is a sample output from the service code:</span></span>

```console
The service is ready.
Press <ENTER> to terminate service.

Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

## <a name="comments"></a><span data-ttu-id="fda4b-180">Kommentare</span><span class="sxs-lookup"><span data-stu-id="fda4b-180">Comments</span></span>

- <span data-ttu-id="fda4b-181">Erstellen des Clientzertifikats.</span><span class="sxs-lookup"><span data-stu-id="fda4b-181">Creating the client certificate.</span></span>

     <span data-ttu-id="fda4b-182">Die folgende Zeile in der Batchdatei erstellt das Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="fda4b-182">The following line in the batch file creates the client certificate.</span></span> <span data-ttu-id="fda4b-183">Der angegebene Clientname wird im Antragstellernamen des erstellten Zertifikats verwendet.</span><span class="sxs-lookup"><span data-stu-id="fda4b-183">The client name specified is used in the subject name of the certificate created.</span></span> <span data-ttu-id="fda4b-184">Das Zertifikat wird im `My`-Speicher am Speicherort `CurrentUser` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-184">The certificate is stored in `My` store at the `CurrentUser` store location.</span></span>

    ```bat
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="fda4b-185">Installieren des Clientzertifikats in den Serverspeicher für vertrauenswürdige Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="fda4b-185">Installing the client certificate into server’s trusted certificate store.</span></span>

     <span data-ttu-id="fda4b-186">Die folgende Zeile in der Batchdatei kopiert das Clientzertifikat in den Speicher TrustedPeople des Servers, damit der Server selbst entscheiden kann, was vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="fda4b-186">The following line in the batch file copies the client certificate into the server's TrustedPeople store so that the server can make the relevant trust or no-trust decisions.</span></span> <span data-ttu-id="fda4b-187">Damit ein im Trust dpeople-Speicher installiertes Zertifikat von einem Windows Communication Foundation (WCF)-Dienst als vertrauenswürdig eingestuft wird, muss der Überprüfungs Modus des Client Zertifikats auf den Wert oder festgelegt werden `PeerOrChainTrust` `PeerTrust` .</span><span class="sxs-lookup"><span data-stu-id="fda4b-187">For a certificate installed in the TrustedPeople store to be trusted by a Windows Communication Foundation (WCF) service, the client certificate validation mode must be set to `PeerOrChainTrust` or `PeerTrust` value.</span></span> <span data-ttu-id="fda4b-188">Wie dies mithilfe einer Konfigurationsdatei durchgeführt werden kann, wurde im vorherigen Dienstkonfigurationsbeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="fda4b-188">See the previous service configuration sample to learn how this can be done using a configuration file.</span></span>

    ```bat
    echo ************
    echo copying client cert to server's LocalMachine store
    echo ************
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="fda4b-189">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="fda4b-189">Creating the server certificate.</span></span>

     <span data-ttu-id="fda4b-190">Die folgenden Zeilen aus der Batchdatei "Setup.bat" erstellen das zu verwendende Serverzertifikat:</span><span class="sxs-lookup"><span data-stu-id="fda4b-190">The following lines from the Setup.bat batch file create the server certificate to be used:</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="fda4b-191">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="fda4b-191">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="fda4b-192">Das Zertifikat wird im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-192">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="fda4b-193">Wenn die Setup Batchdatei mit einem Dienst Argument (z. b.) ausgeführt wird, `setup.bat service` enthält der% SERVER_NAME% den voll qualifizierten Domänen Namen des Computers. Andernfalls wird standardmäßig "localhost" verwendet.</span><span class="sxs-lookup"><span data-stu-id="fda4b-193">If the setup batch file is run with an argument of service (such as, `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.Otherwise it defaults to localhost</span></span>

- <span data-ttu-id="fda4b-194">Installieren des Serverzertifikats im Clientspeicher für vertrauenswürdige Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="fda4b-194">Installing server certificate into the client’s trusted certificate store.</span></span>

     <span data-ttu-id="fda4b-195">Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-195">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="fda4b-196">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="fda4b-196">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="fda4b-197">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fda4b-197">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="fda4b-198">Wenn Sie ein nicht-U. S verwenden. Englische Edition von Microsoft Windows Sie müssen die Setup.bat Datei bearbeiten und den Kontonamen "NT-Autorität \ Netzwerkdienst" durch Ihr regionales Äquivalent ersetzen.</span><span class="sxs-lookup"><span data-stu-id="fda4b-198">If you are using a non-U.S. English edition of Microsoft Windows you must edit the Setup.bat file and replace the "NT AUTHORITY\NETWORK SERVICE" account name with your regional equivalent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fda4b-199">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="fda4b-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fda4b-200">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="fda4b-200">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="fda4b-201">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fda4b-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fda4b-202">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fda4b-202">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`
