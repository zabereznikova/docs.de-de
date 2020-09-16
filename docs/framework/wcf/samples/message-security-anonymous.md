---
title: Nachrichtensicherheit – anonym
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
ms.openlocfilehash: 7ba64f28d621dad51957438025de22827405dd87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558666"
---
# <a name="message-security-anonymous"></a><span data-ttu-id="82e31-102">Nachrichtensicherheit – anonym</span><span class="sxs-lookup"><span data-stu-id="82e31-102">Message Security Anonymous</span></span>
<span data-ttu-id="82e31-103">Das Beispiel für die anonyme Nachrichten Sicherheit veranschaulicht, wie eine Windows Communication Foundation (WCF)-Anwendung implementiert wird, die Sicherheit auf Nachrichten Ebene ohne Client Authentifizierung verwendet, aber eine Server Authentifizierung mit dem X. 509-Zertifikat des Servers erfordert.</span><span class="sxs-lookup"><span data-stu-id="82e31-103">The Message Security Anonymous sample demonstrates how to implement a Windows Communication Foundation (WCF) application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span> <span data-ttu-id="82e31-104">Alle Anwendungsnachrichten zwischen dem Client und dem Server werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="82e31-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="82e31-105">Dieses Beispiel basiert auf dem Beispiel [WSHttpBinding](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="82e31-105">This sample is based on the [WSHttpBinding](wshttpbinding.md) sample.</span></span> <span data-ttu-id="82e31-106">Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="82e31-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="82e31-107">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="82e31-107">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
> <span data-ttu-id="82e31-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="82e31-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="82e31-109">Dieses Beispiel fügt einen neuen Vorgang zur Rechnerschnittstelle hinzu, der `True` zurückgibt, wenn der Client nicht authentifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="82e31-109">This sample adds a new operation to the calculator interface that returns `True` if the client was not authenticated.</span></span>

```csharp
public class CalculatorService : ICalculator
{
    public bool IsCallerAnonymous()
    {
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.
        return ServiceSecurityContext.Current.IsAnonymous;
    }
    ...
}
```

 <span data-ttu-id="82e31-110">Der Dienst macht einen einzigen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit einer Konfigurationsdatei (Web.conf) definiert wird.</span><span class="sxs-lookup"><span data-stu-id="82e31-110">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="82e31-111">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="82e31-111">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="82e31-112">Die Bindung wird mit einer `wsHttpBinding`-Bindung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="82e31-112">The binding is configured with a `wsHttpBinding` binding.</span></span> <span data-ttu-id="82e31-113">Der Standardsicherheitsmodus für die `wsHttpBinding`-Bindung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="82e31-113">The default security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="82e31-114">Das `clientCredentialType`-Attribut ist auf `None` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82e31-114">The `clientCredentialType` attribute is set to `None`.</span></span>

```xml
<system.serviceModel>

  <protocolMapping>
    <add scheme="http" binding="wsHttpBinding" />
  </protocolMapping>

  <bindings>
    <wsHttpBinding>
     <!-- This configuration defines the security mode as Message and -->
     <!-- the clientCredentialType as None. This mode provides -->
     <!-- server authentication only using the service certificate. -->

     <binding>
       <security mode="Message">
         <message clientCredentialType="None" />
       </security>
     </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 <span data-ttu-id="82e31-115">Die Anmelde Informationen, die für die Dienst Authentifizierung verwendet werden sollen, werden in der angegeben [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="82e31-115">The credentials to be used for service authentication are specified in the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span></span> <span data-ttu-id="82e31-116">Der Wert für `SubjectName` des Serverzertifikats muss dem Wert des `findValue`-Attributs entsprechen (wie in folgendem Beispielcode gezeigt).</span><span class="sxs-lookup"><span data-stu-id="82e31-116">The server certificate must contain the same value for the `SubjectName` as the value specified for the `findValue` attribute as shown in the following sample code.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior>
      <!--
    The serviceCredentials behavior allows you to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
      <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
      </serviceCredentials>
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

 <span data-ttu-id="82e31-117">Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="82e31-117">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="82e31-118">Der Clientsicherheitsmodus für die `wsHttpBinding`-Bindung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="82e31-118">The client security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="82e31-119">Das `clientCredentialType`-Attribut ist auf `None` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82e31-119">The `clientCredentialType` attribute is set to `None`.</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint name=""
             address="http://localhost/servicemodelsamples/service.svc"
             binding="wsHttpBinding"
             behaviorConfiguration="ClientCredentialsBehavior"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </client>

  <bindings>
    <wsHttpBinding>
      <!--This configuration defines the security mode as -->
      <!--Message and the clientCredentialType as None. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="None"/>
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 <span data-ttu-id="82e31-120">Das Beispiel setzt den <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> für die Authentifizierung des Dienstzertifikats auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust>.</span><span class="sxs-lookup"><span data-stu-id="82e31-120">The sample sets the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> to <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> for authenticating the service's certificate.</span></span> <span data-ttu-id="82e31-121">Dies erfolgt in der Datei "App.config" des Clients im Abschnitt `behaviors`.</span><span class="sxs-lookup"><span data-stu-id="82e31-121">This is done in the client's App.config file in the `behaviors` section.</span></span> <span data-ttu-id="82e31-122">Wenn sich das Zertifikat also im Speicher für vertrauenswürdige Personen des Benutzers befindet, wird es als vertrauenswürdig eingestuft wird, ohne dass eine Validierung der Ausstellerkette des Zertifikats erfolgt.</span><span class="sxs-lookup"><span data-stu-id="82e31-122">This means that if the certificate is in the user's Trusted People store, then it is trusted without performing a validation of the certificate's issuer chain.</span></span> <span data-ttu-id="82e31-123">Diese Einstellung wird hier der Einfachheit halber verwendet. So kann das Beispiel ausgeführt werden, ohne dass Zertifikate erforderlich sind, die von einer Zertifizierungsstelle ausgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="82e31-123">This setting is used here for convenience so that the sample can be run without requiring certificates issued by a certification authority (CA).</span></span> <span data-ttu-id="82e31-124">Diese Einstellung ist weniger sicher als die Standardeinstellung ChainTrust.</span><span class="sxs-lookup"><span data-stu-id="82e31-124">This setting is less secure than the default, ChainTrust.</span></span> <span data-ttu-id="82e31-125">Die aus dieser Einstellung resultierenden Sicherheitsauswirkungen sollten sorgfältig bedacht werden, bevor `PeerOrChainTrust` im Produktionscode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="82e31-125">The security implications of this setting should be carefully considered before using `PeerOrChainTrust` in production code.</span></span>

 <span data-ttu-id="82e31-126">Die Client Implementierung fügt einen Aufrufen der `IsCallerAnonymous` -Methode hinzu und unterscheidet sich andernfalls nicht vom [WSHttpBinding](wshttpbinding.md) -Beispiel.</span><span class="sxs-lookup"><span data-stu-id="82e31-126">The client implementation adds a call to the `IsCallerAnonymous` method and otherwise does not differ from the [WSHttpBinding](wshttpbinding.md) sample.</span></span>

```csharp
// Create a client with a client endpoint configuration.
CalculatorClient client = new CalculatorClient();

// Call the GetCallerIdentity operation.
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

...

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 <span data-ttu-id="82e31-127">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82e31-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="82e31-128">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="82e31-128">Press ENTER in the client window to shut down the client.</span></span>

```console
IsCallerAnonymous returned: True
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 <span data-ttu-id="82e31-129">Mit der im Beispiel "Nachrichtensicherheit – anonym" enthaltenen Batchdatei Setup.bat können Sie den Server mit einem relevanten Zertifikat zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="82e31-129">The Setup.bat batch file included with the Message Security Anonymous sample enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="82e31-130">Die Batchdatei kann in zwei Modi ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82e31-130">The batch file can be run in two modes.</span></span> <span data-ttu-id="82e31-131">Um die Batchdatei im Einzelcomputermodus auszuführen, geben Sie in der Befehlszeile `setup.bat` ein.</span><span class="sxs-lookup"><span data-stu-id="82e31-131">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="82e31-132">Um sie im Dienstmodus auszuführen, geben Sie `setup.bat service` ein.</span><span class="sxs-lookup"><span data-stu-id="82e31-132">To run it in service mode, type `setup.bat service`.</span></span> <span data-ttu-id="82e31-133">Verwenden Sie diesen Modus, wenn Sie das Beispiel computerübergreifend ausführen.</span><span class="sxs-lookup"><span data-stu-id="82e31-133">Use this mode when running the sample across computers.</span></span> <span data-ttu-id="82e31-134">Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="82e31-134">See the setup procedure at the end of this topic for details.</span></span>

 <span data-ttu-id="82e31-135">Im Folgenden wird eine kurze Übersicht über die verschiedenen Abschnitte der Batchdateien bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="82e31-135">The following provides a brief overview of the different sections of the batch files:</span></span>

- <span data-ttu-id="82e31-136">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="82e31-136">Creating the server certificate.</span></span>

     <span data-ttu-id="82e31-137">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="82e31-137">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="82e31-138">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="82e31-138">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="82e31-139">Das Zertifikat wird im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="82e31-139">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="82e31-140">Wenn die Setupbatchdatei mit dem service-Argument ausgeführt wird (z. B. `setup.bat service`), enthält %SERVER_NAME% den vollqualifizierten Domänennamen des Computers.</span><span class="sxs-lookup"><span data-stu-id="82e31-140">If the setup batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="82e31-141">Andernfalls wird standardmäßig localhost verwendet.</span><span class="sxs-lookup"><span data-stu-id="82e31-141">Otherwise it defaults to localhost.</span></span>

- <span data-ttu-id="82e31-142">Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.</span><span class="sxs-lookup"><span data-stu-id="82e31-142">Installing the server certificate into the client's trusted certificate store.</span></span>

     <span data-ttu-id="82e31-143">Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="82e31-143">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="82e31-144">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="82e31-144">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="82e31-145">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="82e31-145">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="82e31-146">Gewähren von Berechtigungen auf dem privaten Schlüssel des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="82e31-146">Granting permissions on the certificate's private key.</span></span>

     <span data-ttu-id="82e31-147">Mit den folgenden Zeilen in der Setup.bat Batch-Datei wird das Serverzertifikat, das im LocalMachine-Speicher gespeichert ist, für das ASP.NET Worker Process-Konto zugänglich.</span><span class="sxs-lookup"><span data-stu-id="82e31-147">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>

    ```bat
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
> <span data-ttu-id="82e31-148">Wenn Sie ein nicht-U. S verwenden. Englische Edition von Windows Sie müssen die Setup.bat Datei bearbeiten und den `NT AUTHORITY\NETWORK SERVICE` Kontonamen durch Ihr regionales Äquivalent ersetzen.</span><span class="sxs-lookup"><span data-stu-id="82e31-148">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="82e31-149">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="82e31-149">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="82e31-150">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="82e31-150">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="82e31-151">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="82e31-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="82e31-152">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="82e31-152">To run the sample on the same computer</span></span>

1. <span data-ttu-id="82e31-153">Vergewissern Sie sich, dass der Pfad den Ordner enthält, in dem sich die Dateien Makecert.exe und FindPrivateKey.exe befinden.</span><span class="sxs-lookup"><span data-stu-id="82e31-153">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>

2. <span data-ttu-id="82e31-154">Führen Sie Setup.bat aus dem Beispiel Installationsordner in einer Developer-Eingabeaufforderung für Visual Studio aus, die mit Administratorrechten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="82e31-154">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="82e31-155">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="82e31-155">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="82e31-156">Die Setup Batchdatei ist so konzipiert, dass Sie von einem Developer-Eingabeaufforderung für Visual Studio ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="82e31-156">The setup batch file is designed to be run from a  Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="82e31-157">Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="82e31-157">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="82e31-158">Diese Umgebungsvariable wird automatisch innerhalb einer Developer-Eingabeaufforderung für Visual Studio festgelegt.</span><span class="sxs-lookup"><span data-stu-id="82e31-158">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="82e31-159">Überprüfen Sie den Zugriff auf den Dienst mithilfe eines Browsers, indem Sie die Adresse eingeben `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="82e31-159">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
4. <span data-ttu-id="82e31-160">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="82e31-160">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="82e31-161">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82e31-161">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="82e31-162">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="82e31-162">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="82e31-163">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="82e31-163">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="82e31-164">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="82e31-164">Create a directory on the service computer.</span></span> <span data-ttu-id="82e31-165">Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="82e31-165">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="82e31-166">Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="82e31-166">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="82e31-167">Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.</span><span class="sxs-lookup"><span data-stu-id="82e31-167">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="82e31-168">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="82e31-168">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="82e31-169">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="82e31-169">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="82e31-170">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="82e31-170">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="82e31-171">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="82e31-171">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="82e31-172">Führen Sie auf dem-Server `setup.bat service` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="82e31-172">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="82e31-173">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="82e31-173">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="82e31-174">Bearbeiten Sie Web.config, um den neuen Zertifikat Namen (im-Attribut im) widerzuspiegeln, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist.</span><span class="sxs-lookup"><span data-stu-id="82e31-174">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="82e31-175">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="82e31-175">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="82e31-176">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="82e31-176">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="82e31-177">Führen Sie auf dem Client ImportServiceCert.bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="82e31-177">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="82e31-178">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="82e31-178">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="82e31-179">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="82e31-179">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="82e31-180">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="82e31-180">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="82e31-181">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="82e31-181">To clean up after the sample</span></span>  
  
- <span data-ttu-id="82e31-182">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="82e31-182">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="82e31-183">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="82e31-183">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="82e31-184">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="82e31-184">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="82e31-185">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`.</span><span class="sxs-lookup"><span data-stu-id="82e31-185">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span></span>
