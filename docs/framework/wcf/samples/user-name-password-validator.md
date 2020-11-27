---
title: Benutzernamen- und Kennwort-Validierungssteuerelement
ms.date: 03/30/2017
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
ms.openlocfilehash: bf20c9baaec44ebdfed351b35c54ab14448c7644
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294923"
---
# <a name="user-name-password-validator"></a><span data-ttu-id="20817-102">Benutzernamen- und Kennwort-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="20817-102">User Name Password Validator</span></span>

<span data-ttu-id="20817-103">Dieses Beispiel veranschaulicht, wie ein benutzerdefiniertes UserNamePassword-Validierungssteuerelement implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="20817-103">This sample demonstrates how to implement a custom UserNamePassword Validator.</span></span> <span data-ttu-id="20817-104">Dies ist nützlich, wenn keines der integrierten UserNamePassword-Validierungsmodi den Anforderungen der Anwendung entspricht (z. B. wenn Benutzername/Kennwort-Paare in externen Speichern wie einer Datenbank gespeichert werden).</span><span class="sxs-lookup"><span data-stu-id="20817-104">This is useful in cases where none of the built-in UserNamePassword Validation modes is appropriate for the requirements of the application; for example, when username/password pairs are stored in some external store, such as a database.</span></span> <span data-ttu-id="20817-105">In diesem Beispiel wird ein Dienst gezeigt, der ein benutzerdefiniertes Validierungssteuerelement enthält, das auf zwei bestimmte Benutzername/Kennwort-Paare überprüft.</span><span class="sxs-lookup"><span data-stu-id="20817-105">This sample shows a service that has a custom validator that checks for two particular username/password pairs.</span></span> <span data-ttu-id="20817-106">Der Client verwendet solch ein Benutzername/Kennwort-Paar, um sich beim Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="20817-106">The client uses such a username/password pair to authenticate to the service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20817-107">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="20817-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="20817-108">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="20817-108">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="20817-109">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20817-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20817-110">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="20817-110">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
> <span data-ttu-id="20817-111">Da jeder eine Benutzername-Anmeldeinformation mit den Benutzername/Kennwort-Paaren erstellen kann, die das benutzerdefinierte Steuerelement akzeptiert, ist der Dienst weniger sicher als das Standardverhalten des normalen UserNamePassword-Validierungssteuerelements.</span><span class="sxs-lookup"><span data-stu-id="20817-111">Because anyone can construct a Username credential that uses the username/password pairs that the custom validator accepts, the service is less secure than the default behavior provided by the standard UserNamePassword Validator.</span></span> <span data-ttu-id="20817-112">Das normale UserNamePassword-Validierungssteuerelement versucht, das angegebene Benutzername/Kennwort-Paar einem Windows-Konto zuzuordnen. Schlägt diese Zuordnung fehl, wird die Authentifizierung mit einem Fehler abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="20817-112">The standard UserNamePassword Validator attempts to map the provided username/password pair to a Windows account and fails authentication if this mapping fails.</span></span> <span data-ttu-id="20817-113">Das benutzerdefinierte UserNamePassword-Validierungssteuerelement aus diesem Beispiel DARF NICHT in Produktionscode verwendet werden, es dient nur zur Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="20817-113">The custom UserNamePassword Validator in this sample MUST NOT be used in production code, it is for illustration purposes only.</span></span>

 <span data-ttu-id="20817-114">Insgesamt zeigt dieses Beispiel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20817-114">In summary this sample demonstrates how:</span></span>

- <span data-ttu-id="20817-115">Der Client kann mit einem Benutzernamentoken authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="20817-115">The client can be authenticated using a Username Token.</span></span>

- <span data-ttu-id="20817-116">Der Server überprüft die Clientanmeldeinformationen anhand eines benutzerdefinierten UserNamePasswordValidator und wie benutzerdefinierte Fehler aus der Logik zur Validierung von Benutzername und Kennwort an den Client weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="20817-116">The server validates the client credentials against a custom UserNamePasswordValidator and how to propagate custom faults from the username and password validation logic to the client.</span></span>

- <span data-ttu-id="20817-117">Der Server wird mit dem X.509-Zertifikat des Servers authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="20817-117">The server is authenticated using the server's X.509 certificate.</span></span>

 <span data-ttu-id="20817-118">Der Dienst macht einen einzelnen Endpunkt für die Kommunikation mit dem Dienst verfügbar, der mithilfe der Konfigurationsdatei definiert wird, App.config. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="20817-118">The service exposes a single endpoint for communicating with the service, defined using the configuration file, App.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="20817-119">Die Bindung wird mit einem Standard konfiguriert, der standardmäßig `wsHttpBinding` WS-Security-und username-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="20817-119">The binding is configured with a standard `wsHttpBinding` that defaults to using WS-Security and username authentication.</span></span> <span data-ttu-id="20817-120">Das Dienstverhalten gibt den `Custom`-Modus zum Überprüfen von Benutzername/Kennwort-Paaren zusammen mit dem Typ der Validierungssteuerelementklasse an.</span><span class="sxs-lookup"><span data-stu-id="20817-120">The service behavior specifies the `Custom` mode for validating client username/password pairs along with the type of the validator class.</span></span> <span data-ttu-id="20817-121">Das Verhalten gibt auch das Serverzertifikat mit dem `serviceCertificate`-Element an.</span><span class="sxs-lookup"><span data-stu-id="20817-121">The behavior also specifies the server certificate using the `serviceCertificate` element.</span></span> <span data-ttu-id="20817-122">Das Serverzertifikat muss den gleichen Wert für den `SubjectName` `findValue` in der enthalten [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="20817-122">The server certificate has to contain the same value for the `SubjectName` as the `findValue` in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <!-- use host/baseAddresses to configure base address provided by host -->
      <host>
        <baseAddresses>
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />
        </baseAddresses>
      </host>
      <!-- use base address specified above, provide one endpoint -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- username binding -->
      <binding name="Binding">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceDebug includeExceptionDetailInFaults ="true"/>
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to
          specify a custom validator for username/password
          combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom"
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="20817-123">Die Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="20817-123">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="20817-124">Die Clientbindung wird mit dem entsprechenden Modus und der `clientCredentialType`-Nachricht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="20817-124">The client binding is configured with the appropriate mode and message `clientCredentialType`.</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
address="http://localhost:8001/servicemodelsamples/service/username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
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
```

 <span data-ttu-id="20817-125">Die Clientimplementierung fordert den Benutzer auf, einen Benutzernamen und ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="20817-125">The client implementation prompts the user to enter a username and password.</span></span>

```csharp
// Get the username and password
Console.WriteLine("Username authentication required.");
Console.WriteLine("Provide a username.");
Console.WriteLine("   Enter username: (test1)");
string username = Console.ReadLine();
Console.WriteLine("   Enter password:");
string password = "";
ConsoleKeyInfo info = Console.ReadKey(true);
while (info.Key != ConsoleKey.Enter)
{
    if (info.Key != ConsoleKey.Backspace)
    {
        if (info.KeyChar != '\0')
        {
            password += info.KeyChar;
        }
        info = Console.ReadKey(true);
    }
    else if (info.Key == ConsoleKey.Backspace)
    {
        if (password != "")
        {
            password = password.Substring(0, password.Length - 1);
        }
        info = Console.ReadKey(true);
    }
}
for (int i = 0; i < password.Length; i++)
{
    Console.Write("*");
}
Console.WriteLine();
// Create a proxy with Certificate endpoint configuration
CalculatorProxy proxy = new CalculatorProxy("Username")
try
{
  proxy.ClientCredentials.Username.Username = username;
  proxy.ClientCredentials.Username.Password = password;
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = proxy.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
  }
  catch (Exception e)
  {
      Console.WriteLine("Call failed:");
      while (e != null)
      {
          Console.WriteLine("\t{0}", e.Message);
          e = e.InnerException;
      }
      proxy.Abort();
  }
}
```

 <span data-ttu-id="20817-126">In diesem Beispiel wird ein benutzerdefinierter UserNamePasswordValidator verwendet, um Benutzername/Kennwort-Paare zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="20817-126">This sample uses a custom UserNamePasswordValidator to validate username/password pairs.</span></span> <span data-ttu-id="20817-127">Das Beispiel implementiert `CustomUserNamePasswordValidator`, das von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="20817-127">The sample implements `CustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="20817-128">Weitere Informationen finden Sie in der Dokumentation zu <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="20817-128">See the documentation for <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="20817-129">Dieses Beispiel zu einem benutzerdefinierten Validierungssteuerelement implementiert die `Validate`-Methode zum Akzeptieren zweier bestimmter Benutzername/Kennwort-Paare, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="20817-129">This particular custom validator sample implements the `Validate` method to accept two particular username/password pairs as shown in the following code.</span></span>

```csharp
public class CustomUserNameValidator : UserNamePasswordValidator
{
 // This method validates users. It allows in two users,
 // test1 and test2 with passwords 1tset and 2tset respectively.
 // This code is for illustration purposes only and
 // MUST NOT be used in a production environment because it
 // is NOT secure.
 public override void Validate(string userName, string password)
 {
  if (null == userName || null == password)
  {
   throw new ArgumentNullException();
  }

  if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
  {
   throw new FaultException("Unknown Username or Incorrect Password");
   }
  }
 }
```

 <span data-ttu-id="20817-130">Nachdem das Validierungssteuerelement im Dienstcode implementiert ist, muss der Diensthost über die zu verwendende Validierungssteuerelementinstanz informiert werden.</span><span class="sxs-lookup"><span data-stu-id="20817-130">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="20817-131">Dies wird mit dem folgenden Code durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="20817-131">This is done using the following code.</span></span>

```csharp
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();
```

 <span data-ttu-id="20817-132">Sie können dasselbe aber auch wie folgt in der Konfiguration vornehmen.</span><span class="sxs-lookup"><span data-stu-id="20817-132">Or you can do the same thing in configuration as follows.</span></span>

```xml
<behaviors>
 <serviceBehaviors>
  <behavior name="CalculatorServiceBehavior">
  ...
   <serviceCredentials>
    <!--
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.
    -->
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />
   ...
   </serviceCredentials>
  </behavior>
 </serviceBehaviors>
</behaviors>
```

 <span data-ttu-id="20817-133">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20817-133">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="20817-134">Der Client sollte alle Methoden erfolgreich aufrufen.</span><span class="sxs-lookup"><span data-stu-id="20817-134">The client should successfully call all the methods.</span></span> <span data-ttu-id="20817-135">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="20817-135">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="20817-136">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="20817-136">Setup Batch File</span></span>

 <span data-ttu-id="20817-137">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="20817-137">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="20817-138">Diese Batchdatei muss so geändert werden, dass sie computerübergreifend oder in einem nicht selbst gehosteten Fall funktioniert.</span><span class="sxs-lookup"><span data-stu-id="20817-138">This batch file must be modified to work across machines or to work in a non-self-hosted case.</span></span>

 <span data-ttu-id="20817-139">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="20817-139">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="20817-140">Erstellen des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="20817-140">Creating the server certificate:</span></span>

     <span data-ttu-id="20817-141">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="20817-141">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="20817-142">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="20817-142">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="20817-143">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="20817-143">Change this variable to specify your own server name.</span></span> <span data-ttu-id="20817-144">Der Standardwert ist localhost.</span><span class="sxs-lookup"><span data-stu-id="20817-144">The default value is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="20817-145">Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate:</span><span class="sxs-lookup"><span data-stu-id="20817-145">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="20817-146">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="20817-146">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="20817-147">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="20817-147">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="20817-148">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="20817-148">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="20817-149">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="20817-149">To set up and build the sample</span></span>

1. <span data-ttu-id="20817-150">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20817-150">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="20817-151">Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="20817-151">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>

#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="20817-152">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="20817-152">To run the sample on the same machine</span></span>

1. <span data-ttu-id="20817-153">Führen Sie Setup.bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="20817-153">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt.</span></span> <span data-ttu-id="20817-154">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="20817-154">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="20817-155">Die Batchdatei Setup.bat ist für die Ausführung über eine Visual Studio 2012-Eingabeaufforderung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="20817-155">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="20817-156">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Setup.bat Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="20817-156">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="20817-157">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="20817-157">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="20817-158">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="20817-158">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="20817-159">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20817-159">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="20817-160">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="20817-160">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="20817-161">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="20817-161">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="20817-162">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="20817-162">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="20817-163">Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="20817-163">Copy the service program files the service directory on the service machine.</span></span> <span data-ttu-id="20817-164">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="20817-164">Also copy the Setup.bat and Cleanup.bat files to the service machine.</span></span>  
  
3. <span data-ttu-id="20817-165">Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält.</span><span class="sxs-lookup"><span data-stu-id="20817-165">You need a server certificate with the subject name that contains the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="20817-166">Die Konfigurationsdatei für den Server muss entsprechend aktualisiert werden, dass sie diesen neuen Zertifikatsnamen wiedergibt.</span><span class="sxs-lookup"><span data-stu-id="20817-166">The configuration file for the server must be updated to reflect this new certificate name.</span></span>  
  
4. <span data-ttu-id="20817-167">Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients.</span><span class="sxs-lookup"><span data-stu-id="20817-167">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="20817-168">Dies ist nur dann erforderlich, wenn das Serverzertifikat nicht von einem vertrauenswürdigen Aussteller ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="20817-168">You need to do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5. <span data-ttu-id="20817-169">Ändern Sie in der Datei "App.config" auf dem Dienstcomputer den Wert der Basisadresse, um anstelle von "localhost" einen vollqualifizierten Computernamen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="20817-169">In the App.config file on the service machine, change the value of the base address to specify a fully-qualified machine name instead of localhost.</span></span>  
  
6. <span data-ttu-id="20817-170">Starten Sie auf dem Dienstcomputer Service.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="20817-170">On the service machine, launch Service.exe from a command prompt window.</span></span>  
  
7. <span data-ttu-id="20817-171">Kopieren Sie die Clientprogrammdateien aus dem Ordner "\client\bin\" (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="20817-171">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
8. <span data-ttu-id="20817-172">Ändern Sie in der Datei "Client.exe.config" auf dem Clientcomputer den Wert für die Adresse des Endpunkts so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="20817-172">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="20817-173">Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="20817-173">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="20817-174">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="20817-174">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="20817-175">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="20817-175">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="20817-176">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="20817-176">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="20817-177">Dadurch wird das Serverzertifikat aus dem Zertifikatspeicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="20817-177">This removes the server certificate from the certificate store.</span></span>
