---
title: Nachrichtensicherheit – Benutzername
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
ms.openlocfilehash: c6b742cbb438b10b443aa8d1cfca21a80acd2afe
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558614"
---
# <a name="message-security-user-name"></a><span data-ttu-id="e5ea5-102">Nachrichtensicherheit – Benutzername</span><span class="sxs-lookup"><span data-stu-id="e5ea5-102">Message Security User Name</span></span>
<span data-ttu-id="e5ea5-103">Dieses Beispiel zeigt, wie eine Anwendung implementiert wird, die WS-Sicherheit mit Benutzernamenauthentifizierung für den Client verwendet und eine Serverauthentifizierung über das X.509v3-Zertifikat des Servers erfordert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-103">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span> <span data-ttu-id="e5ea5-104">Alle Anwendungsnachrichten zwischen dem Client und dem Server werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="e5ea5-105">Standardmäßig werden ein vom Client angegebener Benutzername und ein Kennwort zum Anmelden bei einem gültigen Windows-Konto verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-105">By default, the username and password supplied by the client are used to logon to a valid Windows account.</span></span> <span data-ttu-id="e5ea5-106">Dieses Beispiel basiert auf [WSHttpBinding](wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e5ea5-106">This sample is based on the [WSHttpBinding](wshttpbinding.md).</span></span> <span data-ttu-id="e5ea5-107">Das Beispiel besteht aus einem Clientkonsolenprogramm (Client.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (Service.dll).</span><span class="sxs-lookup"><span data-stu-id="e5ea5-107">This sample consists of a client console program (Client.exe) and a service library (Service.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="e5ea5-108">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-108">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5ea5-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e5ea5-110">Dieses Beispiel veranschaulicht darüber hinaus:</span><span class="sxs-lookup"><span data-stu-id="e5ea5-110">This sample also demonstrates:</span></span>  
  
- <span data-ttu-id="e5ea5-111">Die Standardzuordnung zu Windows-Konten, sodass zusätzliche Autorisierung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-111">The default mapping to Windows accounts so that additional authorization can be performed.</span></span>  
  
- <span data-ttu-id="e5ea5-112">Wie auf die Identitätsinformationen der Aufrufer vom Dienstcode aus zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-112">How to access the caller's identity information from the service code.</span></span>  
  
 <span data-ttu-id="e5ea5-113">Der Dienst macht einen einzelnen Endpunkt für die Kommunikation mit dem Dienst verfügbar, der mithilfe der Konfigurationsdatei Web.config definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-113">The service exposes a single endpoint for communicating with the service, which is defined using the configuration file Web.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="e5ea5-114">Die Bindung wird mit einem Standard konfiguriert [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , der standardmäßig die Nachrichten Sicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-114">The binding is configured with a standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), which defaults to using message security.</span></span> <span data-ttu-id="e5ea5-115">In diesem Beispiel wird der Standard für die Verwendung der Authentifizierung mit dem [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) Client Benutzernamen</span><span class="sxs-lookup"><span data-stu-id="e5ea5-115">This sample sets the standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to use client username authentication.</span></span> <span data-ttu-id="e5ea5-116">Das Verhalten gibt an, dass zur Dienstauthentifizierung die Benutzeranmeldeinformationen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-116">The behavior specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="e5ea5-117">Das Serverzertifikat muss den gleichen Wert für den Antragsteller Namen wie das- `findValue` Attribut im enthalten [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="e5ea5-117">The server certificate must contain the same value for the subject name as the `findValue` attribute in the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
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
</system.serviceModel>  
```  
  
 <span data-ttu-id="e5ea5-118">Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-118">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="e5ea5-119">Die Clientbindung wird mit dem entsprechenden `securityMode` und `authenticationMode` konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-119">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span> <span data-ttu-id="e5ea5-120">Bei Ausführung in einem computerübergreifenden Szenario muss die Endpunktadresse entsprechend geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-120">When running in a cross-computer scenario, the service endpoint address must be changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e5ea5-121">Die Clientimplementierung legt den zu verwendenden Benutzernamen und das Kennwort fest.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-121">The client implementation sets the user name and password to use.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```

 <span data-ttu-id="e5ea5-122">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e5ea5-123">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="e5ea5-124">Mit der in den MessageSecurity-Beispielen enthaltenen Batchdatei "Setup.bat" können Sie den Server mit einem relevanten Zertifikat zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-124">The Setup.bat batch file included with the MessageSecurity samples enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="e5ea5-125">Die Batchdatei kann in zwei Modi ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-125">The batch file can be run in two modes.</span></span> <span data-ttu-id="e5ea5-126">Um die Batchdatei im Einzelcomputermodus auszuführen, geben Sie in der Befehlszeile `setup.bat` ein.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-126">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="e5ea5-127">Um sie im Dienstmodus auszuführen, geben Sie `setup.bat service` ein.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-127">To run it in service mode type `setup.bat service`.</span></span> <span data-ttu-id="e5ea5-128">Verwenden Sie diesen Modus, wenn Sie das Beispiel computerübergreifend ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-128">You use this mode when running the sample across computers.</span></span> <span data-ttu-id="e5ea5-129">Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-129">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="e5ea5-130">Im Folgenden wird eine kurze Übersicht über die verschiedenen Abschnitte der Batchdateien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-130">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="e5ea5-131">Erstellen des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="e5ea5-131">Creating the server certificate</span></span>  
  
     <span data-ttu-id="e5ea5-132">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-132">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="e5ea5-133">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-133">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="e5ea5-134">Das Zertifikat wird im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-134">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="e5ea5-135">Wird die Batchdatei Setup.bat mit einem service-Argument ausgeführt (z. B. `setup.bat service`), enthält %SERVER_NAME% den vollqualifizierten Domänennamen des Computers.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-135">If the Setup.bat batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span>  <span data-ttu-id="e5ea5-136">Andernfalls wird standardmäßig localhost verwendet.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-136">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="e5ea5-137">Installieren des Serverzertifikats im Speicher für vertrauenswürdige Zertifikate des Clients</span><span class="sxs-lookup"><span data-stu-id="e5ea5-137">Installing the server certificate into the client's trusted certificate store</span></span>  
  
     <span data-ttu-id="e5ea5-138">Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-138">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="e5ea5-139">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-139">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="e5ea5-140">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-140">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="e5ea5-141">Gewähren von Berechtigungen auf dem privaten Schlüssel des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="e5ea5-141">Granting permissions on the certificate's private key</span></span>  
  
     <span data-ttu-id="e5ea5-142">Mit den folgenden Zeilen in der Setup.bat Batch-Datei wird das Serverzertifikat, das im LocalMachine-Speicher gespeichert ist, für das ASP.NET Worker Process-Konto zugänglich.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-142">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
    ```bat
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i  
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="e5ea5-143">Wenn Sie ein nicht-U. S verwenden. Englische Edition von Windows Sie müssen die Setup.bat Datei bearbeiten und den `NT AUTHORITY\NETWORK SERVICE` Kontonamen durch Ihr regionales Äquivalent ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-143">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e5ea5-144">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="e5ea5-144">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e5ea5-145">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-145">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e5ea5-146">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-146">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="e5ea5-147">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="e5ea5-147">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="e5ea5-148">Vergewissern Sie sich, dass der Pfad den Ordner enthält, in dem sich die Dateien Makecert.exe und FindPrivateKey.exe befinden.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-148">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2. <span data-ttu-id="e5ea5-149">Führen Sie Setup.bat aus dem Beispiel Installationsordner in einer Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-149">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e5ea5-150">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-150">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e5ea5-151">Die Setup.bat Batchdatei ist für die Ausführung über eine Developer-Eingabeaufforderung für Visual Studio konzipiert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-151">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="e5ea5-152">Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-152">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="e5ea5-153">Diese Umgebungsvariable wird automatisch innerhalb einer Developer-Eingabeaufforderung für Visual Studio festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-153">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="e5ea5-154">Überprüfen Sie den Zugriff auf den Dienst mithilfe eines Browsers, indem Sie die Adresse eingeben `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="e5ea5-154">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>
  
4. <span data-ttu-id="e5ea5-155">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-155">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="e5ea5-156">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-156">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="e5ea5-157">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-157">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e5ea5-158">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="e5ea5-158">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="e5ea5-159">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-159">Create a directory on the service computer.</span></span> <span data-ttu-id="e5ea5-160">Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-160">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services management tool.</span></span>  
  
2. <span data-ttu-id="e5ea5-161">Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-161">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="e5ea5-162">Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-162">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="e5ea5-163">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-163">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="e5ea5-164">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-164">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="e5ea5-165">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-165">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="e5ea5-166">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-166">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="e5ea5-167">Führen Sie auf dem-Server `setup.bat service` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-167">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e5ea5-168">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-168">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="e5ea5-169">Bearbeiten Sie die Datei Web.config so, dass sie den neuen Zertifikatnamen (im findValue-Attribut im serviceCertificate-Element) enthält, der dem vollqualifizierten Domänennamen des Computers entspricht`.`</span><span class="sxs-lookup"><span data-stu-id="e5ea5-169">Edit Web.config to reflect the new certificate name (in the findValue attribute in the serviceCertificate element) which is the same as the fully-qualified domain name of the computer`.`</span></span>  
  
7. <span data-ttu-id="e5ea5-170">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-170">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="e5ea5-171">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-171">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="e5ea5-172">Führen Sie auf dem Client ImportServiceCert.bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-172">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e5ea5-173">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-173">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="e5ea5-174">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-174">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="e5ea5-175">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-175">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="e5ea5-176">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="e5ea5-176">To clean up after the sample</span></span>  
  
- <span data-ttu-id="e5ea5-177">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-177">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e5ea5-178">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-178">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="e5ea5-179">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-179">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="e5ea5-180">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="e5ea5-180">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
