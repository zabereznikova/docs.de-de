---
title: Tokenanbieter
ms.date: 03/30/2017
ms.assetid: 947986cf-9946-4987-84e5-a14678d96edb
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d513ddd41d87da7274f961969d261724b49aab65
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807813"
---
# <a name="token-provider"></a><span data-ttu-id="30934-102">Tokenanbieter</span><span class="sxs-lookup"><span data-stu-id="30934-102">Token Provider</span></span>
<span data-ttu-id="30934-103">Dieses Beispiel veranschaulicht das Implementieren eines benutzerdefinierten Tokenanbieters.</span><span class="sxs-lookup"><span data-stu-id="30934-103">This sample demonstrates how to implement a custom token provider.</span></span> <span data-ttu-id="30934-104">Ein Tokenanbieter in Windows Communication Foundation (WCF) wird verwendet, um Sicherheitsinfrastruktur der Sicherheitsinfrastruktur Anmeldeinformationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="30934-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="30934-105">Der Tokenanbieter untersucht im Allgemeinen das Ziel und gibt die entsprechenden Anmeldeinformationen aus, sodass die Sicherheitsinfrastruktur die Nachricht sichern kann.</span><span class="sxs-lookup"><span data-stu-id="30934-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="30934-106">Im Lieferumfang von WCF ist der standardmäßige Tokenanbieter der Anmeldeinformationsverwaltung enthalten.</span><span class="sxs-lookup"><span data-stu-id="30934-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="30934-107">Auch Lieferumfang von WCF ein [!INCLUDE[infocard](../../../../includes/infocard-md.md)] Tokenanbieter.</span><span class="sxs-lookup"><span data-stu-id="30934-107">WCF also ships with an [!INCLUDE[infocard](../../../../includes/infocard-md.md)] token provider.</span></span> <span data-ttu-id="30934-108">Benutzerdefinierte Tokenanbieter sind in den folgenden Fällen nützlich:</span><span class="sxs-lookup"><span data-stu-id="30934-108">Custom token providers are useful in the following cases:</span></span>  
  
-   <span data-ttu-id="30934-109">Wenn Sie einen Speicher für Anmeldeinformationen verwenden, mit dem diese Tokenanbieter nicht umgehen können.</span><span class="sxs-lookup"><span data-stu-id="30934-109">If you have a credential store that these token providers cannot operate with.</span></span>  
  
-   <span data-ttu-id="30934-110">Wenn geben Sie eine eigene benutzerdefinierte Mechanismen zur Transformation angibt, bis die Anmeldeinformationen ab dem Punkt, der Benutzer die Details, wenn der WCF-Clientframework die Anmeldeinformationen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="30934-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>  
  
-   <span data-ttu-id="30934-111">Wenn Sie ein benutzerdefiniertes Token erstellen.</span><span class="sxs-lookup"><span data-stu-id="30934-111">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="30934-112">In diesem Beispiel wird gezeigt, wie Sie einen benutzerdefinierten Tokenanbieter erstellen können, der die Eingabe des Benutzers in ein anderes Format transformiert.</span><span class="sxs-lookup"><span data-stu-id="30934-112">This sample shows how to build a custom token provider that transforms the input from the user into a different format.</span></span>  
  
 <span data-ttu-id="30934-113">Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="30934-113">To summarize, this sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="30934-114">Wie sich ein Client mithilfe eines Benutzername/Kennwort-Paars authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="30934-114">How a client can authenticate using a username/password pair.</span></span>  
  
-   <span data-ttu-id="30934-115">Wie ein Client mit einem benutzerdefinierten Tokenanbieter konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="30934-115">How a client can be configured with a custom token provider.</span></span>  
  
-   <span data-ttu-id="30934-116">Wie der Server die Clientanmeldeinformationen anhand eines benutzerdefinierten <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> überprüfen kann, der die Übereinstimmung von Benutzername und Kennwort überprüft.</span><span class="sxs-lookup"><span data-stu-id="30934-116">How the server can validate the client credentials using a password with a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> that validates that the username and password match.</span></span>  
  
-   <span data-ttu-id="30934-117">Wie der Server über das X.509-Zertifikat des Servers vom Client authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="30934-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="30934-118">In diesem Beispiel wird auch gezeigt, wie auf die Identität des Aufrufers nach dem benutzerdefinierten Tokenauthentifizierungsprozess zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="30934-118">This sample also shows how the caller's identity is accessible after the custom token authentication process.</span></span>  
  
 <span data-ttu-id="30934-119">Der Dienst macht einen einzelnen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit der App.conf-Konfigurationsdatei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="30934-119">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="30934-120">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="30934-120">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="30934-121">Die Bindung wird mit einer Standard-`wsHttpBinding` konfiguriert, die standardmäßig Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="30934-121">The binding is configured with a standard `wsHttpBinding`, which uses message security by default.</span></span> <span data-ttu-id="30934-122">In diesem Beispiel wird das Standard-`wsHttpBinding` auf die Verwendung der Clientbenutzernamenauthentifizierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="30934-122">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="30934-123">Außerdem konfiguriert der Dienst das Dienstzertifikat mit dem serviceCredentials-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="30934-123">The service also configures the service certificate using the serviceCredentials behavior.</span></span> <span data-ttu-id="30934-124">Mit dem serviceCredentials-Verhalten können Sie ein Dienstzertifikat konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="30934-124">The serviceCredentials behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="30934-125">Ein Dienstzertifikat wird von einem Client verwendet, um den Dienst zu authentifizieren und Nachrichtenschutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="30934-125">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="30934-126">Die folgende Konfiguration verweist auf das Zertifikat localhost, das während des Beispielsetups installiert wird, wie im folgenden Setup beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30934-126">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <!-- configure base address provided by host -->  
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- use base address provided by host -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
    </services>  
  
    <bindings>  
      <wsHttpBinding>  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="30934-127">Die Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="30934-127">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="30934-128">Die Clientbindung wird mit dem entsprechenden `Mode` und der entsprechenden `clientCredentialType`-Nachricht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="30934-128">The client binding is configured with the appropriate `Mode` and message `clientCredentialType`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="http://localhost:8000/servicemodelsamples/service"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator">  
    </endpoint>  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="30934-129">Die folgenden Schritte wird die Entwicklung eines benutzerdefinierten tokenanbieters und seine Integration mit dem WCF-Sicherheitsframework gezeigt:</span><span class="sxs-lookup"><span data-stu-id="30934-129">The following steps show how to develop a custom token provider and integrate it with the WCF security framework:</span></span>  
  
1.  <span data-ttu-id="30934-130">Schreiben Sie einen benutzerdefinierten Tokenanbieter.</span><span class="sxs-lookup"><span data-stu-id="30934-130">Write a custom token provider.</span></span>  
  
     <span data-ttu-id="30934-131">Im Beispiel wird ein benutzerdefinierter Tokenanbieter implementiert, der den Benutzernamen und das Kennwort erhält.</span><span class="sxs-lookup"><span data-stu-id="30934-131">The sample implements a custom token provider that obtains the username and password.</span></span> <span data-ttu-id="30934-132">Das Kennwort muss mit diesem Benutzernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="30934-132">The password must match this username.</span></span> <span data-ttu-id="30934-133">Dieser benutzerdefinierte Tokenanbieter ist nur für Demonstrationszwecke gedacht und wird nicht zur realen Bereitstellung empfohlen.</span><span class="sxs-lookup"><span data-stu-id="30934-133">This custom token provider is for demonstration purposes only and is not recommended for real world deployment.</span></span>  
  
     <span data-ttu-id="30934-134">Zur Ausführung dieser Aufgabe leitet der benutzerdefinierte Tokenanbieter die <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse ab und überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>-Methode.</span><span class="sxs-lookup"><span data-stu-id="30934-134">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="30934-135">Diese Methode erstellt ein neues `UserNameSecurityToken`-Objekt und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="30934-135">This method creates and returns a new `UserNameSecurityToken`.</span></span>  
  
    ```  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
        // obtain username and password from the user using console window  
        string username = GetUserName();  
        string password = GetPassword();  
        Console.WriteLine("username: {0}", username);  
  
        // return new UserNameSecurityToken containing information obtained from user  
        return new UserNameSecurityToken(username, password);  
    }  
    ```  
  
2.  <span data-ttu-id="30934-136">Schreiben Sie den benutzerdefiniertem Sicherheitstoken-Manager.</span><span class="sxs-lookup"><span data-stu-id="30934-136">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="30934-137">Die <xref:System.IdentityModel.Selectors.SecurityTokenManager> wird zur Erstellung von <xref:System.IdentityModel.Selectors.SecurityTokenProvider> für eine bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> verwendet, die in der `CreateSecurityTokenProvider`-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="30934-137">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="30934-138">Der Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenauthentifizierern und eines Token-Serialisierungsprogramms. Diese Vorgänge werden jedoch in diesem Beispiel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="30934-138">Security token manager is also used to create token authenticators and a token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="30934-139">In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> und überschreibt die Methode `CreateSecurityTokenProvider`, um benutzerdefinierte Benutzernamen-Tokenanbieter zurückzugeben, wenn die übergebenen Tokenanforderungen angeben, dass der Benutzernamenanbieter angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="30934-139">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return custom username token provider when the passed token requirements indicate that username provider is requested.</span></span>  
  
    ```  
    public class MyUserNameSecurityTokenManager : ClientCredentialsSecurityTokenManager  
    {  
        MyUserNameClientCredentials myUserNameClientCredentials;  
  
        public MyUserNameSecurityTokenManager(MyUserNameClientCredentials myUserNameClientCredentials)  
            : base(myUserNameClientCredentials)  
        {  
            this.myUserNameClientCredentials = myUserNameClientCredentials;  
        }  
  
        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)  
        {  
            // if token requirement matches username token return custom username token provider  
            // otherwise use base implementation  
            if (tokenRequirement.TokenType == SecurityTokenTypes.UserName)  
            {  
                return new MyUserNameTokenProvider();  
            }  
            else  
            {  
                return base.CreateSecurityTokenProvider(tokenRequirement);  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="30934-140">Schreiben Sie benutzerdefinierte Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="30934-140">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="30934-141">Die Klasse der Clientanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Clientproxy konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="30934-141">Client credentials class is used to represent the credentials that are configured for the client proxy and creates security token manager that is used to obtain token authenticators, token providers and a token serializer.</span></span>  
  
    ```  
    public class MyUserNameClientCredentials : ClientCredentials  
    {  
        public MyUserNameClientCredentials()  
            : base()  
        {  
        }  
  
        protected override ClientCredentials CloneCore()  
        {  
            return new MyUserNameClientCredentials();  
        }  
  
        public override SecurityTokenManager CreateSecurityTokenManager()  
        {  
            // return custom security token manager  
            return new MyUserNameSecurityTokenManager(this);  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="30934-142">Konfigurieren Sie den Client für die Verwendung der benutzerdefinierten Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="30934-142">Configure the client to use the custom client credential.</span></span>  
  
     <span data-ttu-id="30934-143">Damit der Client die benutzerdefinierten Clientanmeldeinformationen verwenden kann, wird im Beispiel die Standardklasse für die Clientanmeldeinformationen gelöscht und die neue Klasse für Clientanmeldeinformationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="30934-143">In order for the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>  
  
    ```  
    static void Main()  
    {  
        // ...  
           // Create a client with given client endpoint configuration  
          CalculatorClient client = new CalculatorClient();  
  
          // set new credentials  
           client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));  
         client.ChannelFactory.Endpoint.Behaviors.Add(new MyUserNameClientCredentials());  
       // ...  
    }  
    ```  
  
 <span data-ttu-id="30934-144">Um beim Dienst die Informationen zu den Aufrufern anzuzeigen, können Sie <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> verwenden, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="30934-144">On the service, to display the caller's information, use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code example.</span></span> <span data-ttu-id="30934-145"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A> enthält Informationen zu den Ansprüchen des aktuellen Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="30934-145">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>  
  
```  
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tSecurity context identity  :  {0}",   
        ServiceSecurityContext.Current.PrimaryIdentity.Name);  
}  
```  
  
 <span data-ttu-id="30934-146">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30934-146">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="30934-147">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="30934-147">Press ENTER in the client window to shut down the client.</span></span>  
  
## <a name="setup-batch-file"></a><span data-ttu-id="30934-148">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="30934-148">Setup Batch File</span></span>  
 <span data-ttu-id="30934-149">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit dem relevanten Zertifikat zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="30934-149">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="30934-150">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30934-150">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="30934-151">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="30934-151">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>  
  
-   <span data-ttu-id="30934-152">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="30934-152">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="30934-153">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="30934-153">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="30934-154">Die Variable `%SERVER_NAME%` gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="30934-154">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="30934-155">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="30934-155">Change this variable to specify your own server name.</span></span> <span data-ttu-id="30934-156">Der Standardwert in dieser Batchdatei lautet localhost.</span><span class="sxs-lookup"><span data-stu-id="30934-156">The default value in this batch file is localhost.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="30934-157">Installieren des Serverzertifikats im Speicher für vertrauenswürdige Zertifikate des Clients:</span><span class="sxs-lookup"><span data-stu-id="30934-157">Installing the server certificate into the client's trusted certificate store:</span></span>  
  
     <span data-ttu-id="30934-158">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="30934-158">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="30934-159">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="30934-159">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="30934-160">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30934-160">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="30934-161">Die Batchdatei "Setup.bat" ist dafür ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="30934-161">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="30934-162">Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="30934-162">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="30934-163">Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="30934-163">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="30934-164">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="30934-164">To set up and build the sample</span></span>  
  
1.  <span data-ttu-id="30934-165">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30934-165">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="30934-166">Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30934-166">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="30934-167">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="30934-167">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="30934-168">Öffnen Sie eine [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung mit Administratorrechten, und führen Sie Setup.bat aus dem Beispielinstallationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="30934-168">Run Setup.bat from the sample installation folder inside a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt opened with administrator privileges.</span></span> <span data-ttu-id="30934-169">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="30934-169">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30934-170">Die Batchdatei Setup.bat ist darauf ausgelegt, an einer [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="30934-170">The Setup.bat batch file is designed to be run from a [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt.</span></span> <span data-ttu-id="30934-171">Die innerhalb der [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung festgelegte PATH-Umgebungsvariable zeigt auf das Verzeichnis mit den ausführbaren Dateien, die für das Skript Setup.bat erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="30934-171">The PATH environment variable set within the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2.  <span data-ttu-id="30934-172">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="30934-172">Launch service.exe from service\bin.</span></span>  
  
3.  <span data-ttu-id="30934-173">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="30934-173">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="30934-174">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="30934-174">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="30934-175">Geben Sie an der Benutzernamen-Eingabeaufforderung einen Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="30934-175">At the username prompt, type a user name.</span></span>  
  
5.  <span data-ttu-id="30934-176">Verwenden Sie an der Kennworteingabeaufforderung dieselbe Zeichenfolge, die an der Benutzernamen-Eingabeaufforderung eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="30934-176">At the password prompt, use the same string that was typed for the username prompt.</span></span>  
  
6.  <span data-ttu-id="30934-177">Wenn Client und Dienst nicht miteinander kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="30934-177">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="30934-178">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="30934-178">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="30934-179">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="30934-179">Create a directory on the service computer for the service binaries.</span></span>  
  
2.  <span data-ttu-id="30934-180">Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="30934-180">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="30934-181">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="30934-181">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="30934-182">Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält.</span><span class="sxs-lookup"><span data-stu-id="30934-182">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="30934-183">Die Datei Service.exe.config muss so aktualisiert werden, dass sie diesem neuen Zertifikatsnamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="30934-183">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="30934-184">Sie können das Serverzertifikat erstellen, indem Sie die Batchdatei Setup.bat ändern.</span><span class="sxs-lookup"><span data-stu-id="30934-184">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="30934-185">Beachten Sie, dass die Datei setup.bat an einer Visual Studio-Eingabeaufforderung mit Administratorrechten ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="30934-185">Note that the setup.bat file must be run from a Visual Studio command prompt opened with administrator privileges.</span></span> <span data-ttu-id="30934-186">Sie müssen die Variable `%SERVER_NAME%` auf den vollqualifizierten Hostnamen des Computers festlegen, der als Host für den Dienst dienen soll.</span><span class="sxs-lookup"><span data-stu-id="30934-186">You must set `%SERVER_NAME%` variable to fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4.  <span data-ttu-id="30934-187">Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients.</span><span class="sxs-lookup"><span data-stu-id="30934-187">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="30934-188">Dieser Schritt muss nicht ausgeführt werden, wenn das Serverzertifikat von einem Aussteller stammt, der vom Client als vertrauenswürdig eingestuft wurde.</span><span class="sxs-lookup"><span data-stu-id="30934-188">You do not need to do this when the server certificate is issued by a client trusted issuer.</span></span>  
  
5.  <span data-ttu-id="30934-189">Ändern Sie in der Datei Service.exe.config auf dem Dienstcomputer den Wert der Basisadresse, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="30934-189">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6.  <span data-ttu-id="30934-190">Führen Sie auf dem Dienstcomputer service.exe an einer Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="30934-190">On the service computer, run service.exe from a command prompt.</span></span>  
  
7.  <span data-ttu-id="30934-191">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="30934-191">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8.  <span data-ttu-id="30934-192">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="30934-192">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="30934-193">Starten Sie auf dem Clientcomputer `Client.exe` in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="30934-193">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="30934-194">Wenn Client und Dienst nicht miteinander kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="30934-194">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="30934-195">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="30934-195">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="30934-196">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="30934-196">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30934-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30934-197">See Also</span></span>
