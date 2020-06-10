---
title: X.509-Zertifikats-Validierungssteuerelement
ms.date: 03/30/2017
ms.assetid: 3b042379-02c4-4395-b927-e57c842fd3e0
ms.openlocfilehash: 32d99b93ef014967aa04bc70f73fbd2ebcfe2c60
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594828"
---
# <a name="x509-certificate-validator"></a><span data-ttu-id="e69b6-102">X.509-Zertifikats-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="e69b6-102">X.509 Certificate Validator</span></span>

<span data-ttu-id="e69b6-103">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefiniertes X.509-Zertifikats-Validierungssteuerelement implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e69b6-103">This sample demonstrates how to implement a custom X.509 Certificate Validator.</span></span> <span data-ttu-id="e69b6-104">Dies ist nützlich, wenn keines der integrierten X.509-Zertifikats-Validierungsmodi den Anforderungen der Anwendung entspricht.</span><span class="sxs-lookup"><span data-stu-id="e69b6-104">This is useful in cases where none of the built-in X.509 Certificate Validation modes is appropriate for the requirements of the application.</span></span> <span data-ttu-id="e69b6-105">Dieses Beispiel zeigt einen Dienst, der über ein benutzerdefiniertes Validierungssteuerelement verfügt, das selbst herausgegebene Zertifikate akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-105">This sample shows a service that has a custom validator that accepts self-issued certificates.</span></span> <span data-ttu-id="e69b6-106">Der Client verwendet solch ein Zertifikat, um den Dienst zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="e69b6-106">The client uses such a certificate to authenticate to the service.</span></span>

<span data-ttu-id="e69b6-107">Hinweis: Da jeder ein selbst herausgegebenes Zertifikat erstellen kann, ist das vom Dienst verwendete benutzerdefinierte Validierungssteuerelement unsicherer als das Standardverhalten vom ChainTrust X509CertificateValidationMode.</span><span class="sxs-lookup"><span data-stu-id="e69b6-107">Note: As anyone can construct a self-issued certificate the custom validator used by the service is less secure than the default behavior provided by the ChainTrust X509CertificateValidationMode.</span></span> <span data-ttu-id="e69b6-108">Die daraus resultierenden Sicherheitsauswirkungen sollten sorgfältig bedacht werden, bevor diese Validierungslogik im Produktionscode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e69b6-108">The security implications of this should be carefully considered before using this validation logic in production code.</span></span>

<span data-ttu-id="e69b6-109">Insgesamt zeigt dieses Beispiel Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e69b6-109">In summary this sample demonstrates how:</span></span>

- <span data-ttu-id="e69b6-110">Der Client kann mit einem X.509-Zertifikat authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="e69b6-110">The client can be authenticated using an X.509 certificate.</span></span>

- <span data-ttu-id="e69b6-111">Der Server überprüft die Clientanmeldeinformationen mithilfe eines benutzerdefinierten X509CertificateValidator.</span><span class="sxs-lookup"><span data-stu-id="e69b6-111">The server validates the client credentials against a custom X509CertificateValidator.</span></span>

- <span data-ttu-id="e69b6-112">Der Server wird mit dem X.509-Zertifikat des Servers authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-112">The server is authenticated using the server's X.509 certificate.</span></span>

<span data-ttu-id="e69b6-113">Der Dienst macht einen einzelnen Endpunkt für die Kommunikation mit dem Dienst verfügbar, der mithilfe der Konfigurationsdatei "App. config" definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e69b6-113">The service exposes a single endpoint for communicating with the service, defined using the configuration file App.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="e69b6-114">Die Bindung wird mit einem Standard konfiguriert, der standardmäßig `wsHttpBinding` die `WSSecurity` Client Zertifikat Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e69b6-114">The binding is configured with a standard `wsHttpBinding` that defaults to using `WSSecurity` and client certificate authentication.</span></span> <span data-ttu-id="e69b6-115">Das Dienstverhalten gibt den benutzerdefinierten Modus zur Prüfung von X.509-Clientzertifikaten zusammen mit dem Typ der Validierungssteuerelementklasse an.</span><span class="sxs-lookup"><span data-stu-id="e69b6-115">The service behavior specifies the Custom mode for validating client X.509 certificates along with the type of the validator class.</span></span> <span data-ttu-id="e69b6-116">Das Verhalten gibt auch das Serverzertifikat mit dem serviceCertificate-Element an.</span><span class="sxs-lookup"><span data-stu-id="e69b6-116">The behavior also specifies the server certificate using the serviceCertificate element.</span></span> <span data-ttu-id="e69b6-117">Das Serverzertifikat muss den gleichen Wert für den `SubjectName` `findValue` in der enthalten [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="e69b6-117">The server certificate has to contain the same value for the `SubjectName` as the `findValue` in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- use host/baseAddresses to configure base address -->
        <!-- provided by host -->
        <host>
          <baseAddresses>
            <add baseAddress =
                "http://localhost:8001/servicemodelsamples/service" />
          </baseAddresses>
        </host>
        <!-- use base address specified above, provide one endpoint -->
        <endpoint address="certificate"
               binding="wsHttpBinding"
               bindingConfiguration="Binding"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <!-- X509 certificate binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults ="true"/>
          <serviceCredentials>
            <!-- The serviceCredentials behavior allows one -->
            <!-- to specify authentication constraints on -->
            <!-- client certificates. -->
            <clientCertificate>
              <!-- Setting the certificateValidationMode to -->
              <!-- Custom means that if the custom -->
              <!-- X509CertificateValidator does NOT throw -->
              <!-- an exception, then the provided certificate -->
              <!-- will be trusted without performing any -->
              <!-- validation beyond that performed by the custom -->
              <!-- validator. The security implications of this -->
              <!-- setting should be carefully considered before -->
              <!-- using Custom in production code. -->
              <authentication
                 certificateValidationMode="Custom"
                 customCertificateValidatorType =
"Microsoft.ServiceModel.Samples.CustomX509CertificateValidator, service" />
            </clientCertificate>
            <!-- The serviceCredentials behavior allows one to -->
            <!-- define a service certificate. -->
            <!-- A service certificate is used by a client to -->
            <!-- authenticate the service and provide message -->
            <!-- protection. This configuration references the -->
            <!-- "localhost" certificate installed during the setup -->
            <!-- instructions. -->
            <serviceCertificate findValue="localhost"
                 storeLocation="LocalMachine"
                 storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
      </system.serviceModel>
```

<span data-ttu-id="e69b6-118">Die Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e69b6-118">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="e69b6-119">Die Clientbindung wird mit dem entsprechenden Modus und der `clientCredentialType`-Nachricht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-119">The client binding is configured with the appropriate mode and message `clientCredentialType`.</span></span>

```xml
<system.serviceModel>
    <client>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
        address=
        "http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>
    <bindings>
        <wsHttpBinding>
            <!-- X509 certificate binding -->
            <binding name="Binding">
                <security mode="Message">
                    <message clientCredentialType="Certificate" />
               </security>
            </binding>
       </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!-- Setting the certificateValidationMode to -->
              <!-- PeerOrChainTrust means that if the certificate -->
              <!-- is in the user's Trusted People store, then it -->
              <!-- is trusted without performing a validation of -->
              <!-- the certificate's issuer chain. -->
              <!-- This setting is used here for convenience so -->
              <!-- that the sample can be run without having to -->
              <!-- have certificates issued by a certification -->
              <!-- authority (CA). This setting is less secure -->
              <!-- than the default, ChainTrust. The security -->
              <!-- implications of this setting should be -->
              <!-- carefully considered before using -->
              <!-- PeerOrChainTrust in production code.-->
              <authentication
                  certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>
```

<span data-ttu-id="e69b6-120">Die Clientimplementierung legt das zu verwendende Clientzertifikat fest.</span><span class="sxs-lookup"><span data-stu-id="e69b6-120">The client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client = new CalculatorClient("Certificate");
try
{
    client.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

    // Call the Subtract service operation.
    value1 = 145.00D;
    value2 = 76.54D;
    result = client.Subtract(value1, value2);
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

    // Call the Multiply service operation.
    value1 = 9.00D;
    value2 = 81.25D;
    result = client.Multiply(value1, value2);
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

    // Call the Divide service operation.
    value1 = 22.00D;
    value2 = 7.00D;
    result = client.Divide(value1, value2);
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
    client.Close();
}
catch (TimeoutException e)
{
    Console.WriteLine("Call timed out : {0}", e.Message);
    client.Abort();
}
catch (CommunicationException e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
    client.Abort();
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
    client.Abort();
}
```

<span data-ttu-id="e69b6-121">In diesem Beispiel wird ein benutzerdefinierter X509CertificateValidator verwendet, um Zertifikate zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-121">This sample uses a custom X509CertificateValidator to validate certificates.</span></span> <span data-ttu-id="e69b6-122">Das Beispiel implementiert CustomX509CertificateValidator, das von <xref:System.IdentityModel.Selectors.X509CertificateValidator> abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="e69b6-122">The sample implements CustomX509CertificateValidator, derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="e69b6-123">Weitere Informationen finden Sie in der Dokumentation zu <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="e69b6-123">See documentation about <xref:System.IdentityModel.Selectors.X509CertificateValidator> for more information.</span></span> <span data-ttu-id="e69b6-124">In diesem speziellen Beispiel zu einem benutzerdefinierten Validierungssteuerelement ist die Validate-Methode so implementiert, dass sie jedes selbst herausgegebene X.509-Zertifikat akzeptiert, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-124">This particular custom validator sample implements the Validate method to accept any X.509 certificate that is self-issued as shown in the following code.</span></span>

```csharp
public class CustomX509CertificateValidator : X509CertificateValidator
{
  public override void Validate ( X509Certificate2 certificate )
  {
   // Only accept self-issued certificates
   if (certificate.Subject != certificate.Issuer)
     throw new Exception("Certificate is not self-issued");
   }
}
```

 <span data-ttu-id="e69b6-125">Nachdem das Validierungssteuerelement im Dienstcode implementiert ist, muss der Diensthost über die zu verwendende Validierungssteuerelementinstanz informiert werden.</span><span class="sxs-lookup"><span data-stu-id="e69b6-125">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="e69b6-126">Dies wird mit dem folgenden Code durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-126">This is done using the following code.</span></span>

```csharp
serviceHost.Credentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.Custom;
serviceHost.Credentials.ClientCertificate.Authentication.CustomCertificateValidator = new CustomX509CertificateValidator();
```

 <span data-ttu-id="e69b6-127">Sie können dasselbe aber auch wie folgt in der Konfiguration vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-127">Or you can do the same thing in configuration as follows.</span></span>

```xml
<behaviors>
    <serviceBehaviors>
     <behavior name="CalculatorServiceBehavior">
       ...
   <serviceCredentials>
    <!--The serviceCredentials behavior allows one to specify -->
    <!--authentication constraints on client certificates.-->
    <clientCertificate>
    <!-- Setting the certificateValidationMode to Custom means -->
    <!--that if the custom X509CertificateValidator does NOT -->
    <!--throw an exception, then the provided certificate will -->
    <!--be trusted without performing any validation beyond that -->
    <!--performed by the custom validator. The security -->
    <!--implications of this setting should be carefully -->
    <!--considered before using Custom in production code. -->
    <authentication certificateValidationMode="Custom"
       customCertificateValidatorType =
"Microsoft.ServiceModel.Samples. CustomX509CertificateValidator, service" />
   </clientCertificate>
   </serviceCredentials>
   ...
  </behavior>
 </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="e69b6-128">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="e69b6-129">Der Client sollte alle Methoden erfolgreich aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-129">The client should successfully call all the methods.</span></span> <span data-ttu-id="e69b6-130">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-130">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="e69b6-131">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="e69b6-131">Setup Batch File</span></span>

<span data-ttu-id="e69b6-132">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-132">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="e69b6-133">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e69b6-133">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

<span data-ttu-id="e69b6-134">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e69b6-134">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="e69b6-135">Erstellen des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="e69b6-135">Creating the server certificate:</span></span>

     <span data-ttu-id="e69b6-136">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-136">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="e69b6-137">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="e69b6-137">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="e69b6-138">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="e69b6-138">Change this variable to specify your own server name.</span></span> <span data-ttu-id="e69b6-139">Der Standardwert ist localhost.</span><span class="sxs-lookup"><span data-stu-id="e69b6-139">The default value is localhost.</span></span>

    ```bash
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="e69b6-140">Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate:</span><span class="sxs-lookup"><span data-stu-id="e69b6-140">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="e69b6-141">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-141">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="e69b6-142">Dieser Schritt ist erforderlich, da von Makecert.exe generierten Zertifikaten nicht implizit vom Clientsystem vertraut wird.</span><span class="sxs-lookup"><span data-stu-id="e69b6-142">This step is required since certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="e69b6-143">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e69b6-143">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```bash
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="e69b6-144">Erstellen des Clientzertifikats</span><span class="sxs-lookup"><span data-stu-id="e69b6-144">Creating the client certificate:</span></span>

     <span data-ttu-id="e69b6-145">Die folgenden Zeilen aus der Batchdatei Setup.bat erstellen das zu verwendende Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="e69b6-145">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="e69b6-146">Die Variable % USER_NAME% gibt den Clientnamen an.</span><span class="sxs-lookup"><span data-stu-id="e69b6-146">The %USER_NAME% variable specifies the client name.</span></span> <span data-ttu-id="e69b6-147">Dieser Wert wird auf "test1" festgelegt, da dies der Name ist, nach dem der Clientcode sucht.</span><span class="sxs-lookup"><span data-stu-id="e69b6-147">This value is set to "test1" because this is the name the client code looks for.</span></span> <span data-ttu-id="e69b6-148">Wenn Sie den Wert von %USER_NAME% ändern, müssen Sie auch den zugehörigen Wert in der Client.cs-Quelldatei ändern und den Client neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-148">If you change the value of %USER_NAME% you must change the corresponding value in the Client.cs source file and rebuild the client.</span></span>

     <span data-ttu-id="e69b6-149">Das Zertifikat wird im persönlichen Speicher unterhalb von CurrentUser gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-149">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```bash
    echo ************
    echo Client cert setup starting
    echo %USER_NAME%
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="e69b6-150">Installieren des Clientzertifikats in den Serverspeicher für vertrauenswürdige Zertifikate:</span><span class="sxs-lookup"><span data-stu-id="e69b6-150">Installing the client certificate into server's trusted certificate store:</span></span>

     <span data-ttu-id="e69b6-151">Die folgenden Zeilen in der Batchdatei Setup.bat kopieren das Clientzertifikat in den Speicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-151">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="e69b6-152">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierten Zertifikaten nicht implizit vom Serversystem vertraut wird.</span><span class="sxs-lookup"><span data-stu-id="e69b6-152">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="e69b6-153">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Stammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Serverzertifikatspeichers mit dem Clientzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e69b6-153">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```bash
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="e69b6-154">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="e69b6-154">To set up and build the sample</span></span>

1. <span data-ttu-id="e69b6-155">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-155">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="e69b6-156">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend auszuführen, befolgen Sie die folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-156">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="e69b6-157">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="e69b6-157">To run the sample on the same computer</span></span>

1. <span data-ttu-id="e69b6-158">Führen Sie Setup. bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="e69b6-158">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="e69b6-159">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e69b6-159">This installs all the certificates required for running the sample.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e69b6-160">Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e69b6-160">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="e69b6-161">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e69b6-161">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

2. <span data-ttu-id="e69b6-162">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="e69b6-162">Launch Service.exe from service\bin.</span></span>

3. <span data-ttu-id="e69b6-163">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="e69b6-163">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="e69b6-164">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-164">Client activity is displayed on the client console application.</span></span>

4. <span data-ttu-id="e69b6-165">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-165">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="e69b6-166">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="e69b6-166">To run the sample across computers</span></span>

1. <span data-ttu-id="e69b6-167">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e69b6-167">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="e69b6-168">Kopieren Sie die Dienstprogrammdateien aus \service\bin in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="e69b6-168">Copy the service program files from \service\bin to the virtual directory on the service computer.</span></span> <span data-ttu-id="e69b6-169">Kopieren Sie außerdem die Dateien Setup.bat, Cleanup.bat, GetComputerName.vbs und ImportClientCert.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="e69b6-169">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="e69b6-170">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="e69b6-170">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="e69b6-171">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="e69b6-171">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="e69b6-172">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="e69b6-172">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="e69b6-173">Führen Sie auf dem-Server `setup.bat service` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e69b6-173">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e69b6-174">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-174">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>

6. <span data-ttu-id="e69b6-175">Bearbeiten Sie die Datei "Service. exe. config" so, dass Sie den neuen Zertifikat Namen (im-Attribut im) widerspiegelt, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist.</span><span class="sxs-lookup"><span data-stu-id="e69b6-175">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="e69b6-176">Ändern Sie auch den Computernamen im- \<service> / \<baseAddresses> Element von "localhost" in den voll qualifizierten Namen Ihres Dienst Computers.</span><span class="sxs-lookup"><span data-stu-id="e69b6-176">Also change the computer name in the \<service>/\<baseAddresses> element from localhost to fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="e69b6-177">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="e69b6-177">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="e69b6-178">Führen Sie auf dem Client `setup.bat client` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e69b6-178">On the client, run `setup.bat client` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e69b6-179">Durch Ausführen von  mit dem Argument  wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-179">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>

9. <span data-ttu-id="e69b6-180">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-180">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="e69b6-181">Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.</span><span class="sxs-lookup"><span data-stu-id="e69b6-181">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>

10. <span data-ttu-id="e69b6-182">Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="e69b6-182">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="e69b6-183">Führen Sie auf dem Client ImportServiceCert. bat in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e69b6-183">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e69b6-184">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-184">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>

12. <span data-ttu-id="e69b6-185">Führen Sie ImportClientCert. bat auf dem-Server in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="e69b6-185">On the server, run ImportClientCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="e69b6-186">Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="e69b6-186">This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>

13. <span data-ttu-id="e69b6-187">Starten Sie auf dem Servercomputer Service.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="e69b6-187">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="e69b6-188">Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="e69b6-188">On the client computer, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="e69b6-189">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="e69b6-189">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="e69b6-190">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="e69b6-190">To clean up after the sample</span></span>

1. <span data-ttu-id="e69b6-191">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="e69b6-191">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span> <span data-ttu-id="e69b6-192">Dadurch werden die Server- und Clientzertifikate aus dem Zertifikatspeicher entfernt.</span><span class="sxs-lookup"><span data-stu-id="e69b6-192">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="e69b6-193">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="e69b6-193">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="e69b6-194">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e69b6-194">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="e69b6-195">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="e69b6-195">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
