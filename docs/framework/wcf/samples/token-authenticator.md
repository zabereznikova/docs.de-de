---
title: Tokenauthentifizierer
ms.date: 03/30/2017
ms.assetid: 84382f2c-f6b1-4c32-82fa-aebc8f6064db
ms.openlocfilehash: 835a158ba668a3aef749602c73fd9157e8d83a40
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425031"
---
# <a name="token-authenticator"></a><span data-ttu-id="924d1-102">Tokenauthentifizierer</span><span class="sxs-lookup"><span data-stu-id="924d1-102">Token Authenticator</span></span>
<span data-ttu-id="924d1-103">Dieses Beispiel veranschaulicht das Implementieren eines benutzerdefinierten Tokenauthentifizierers.</span><span class="sxs-lookup"><span data-stu-id="924d1-103">This sample demonstrates how to implement a custom token authenticator.</span></span> <span data-ttu-id="924d1-104">Ein tokenauthentifikator in Windows Communication Foundation (WCF) wird zum Überprüfen des Tokens verwendet, das mit der Nachricht verwendet wird, um zu überprüfen, ob es selbst konsistent ist, und zum Authentifizieren der Identität, die dem Token zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="924d1-104">A token authenticator in Windows Communication Foundation (WCF) is used for validating the token used with the message, verifying that it is self-consistent, and authenticating the identity associated with the token.</span></span>

 <span data-ttu-id="924d1-105">Benutzerdefinierte Tokenauthentifizierer sind in einer Vielzahl von Fällen nützlich, z. B.:</span><span class="sxs-lookup"><span data-stu-id="924d1-105">Custom token authenticators are useful in a variety of cases, such as:</span></span>

- <span data-ttu-id="924d1-106">Wenn Sie den einem Token zugeordneten Standardauthentifizierungsmechanismus überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="924d1-106">When you want to override the default authentication mechanism associated with a token.</span></span>

- <span data-ttu-id="924d1-107">Wenn Sie ein benutzerdefiniertes Token erstellen.</span><span class="sxs-lookup"><span data-stu-id="924d1-107">When you are building a custom token.</span></span>

 <span data-ttu-id="924d1-108">Dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="924d1-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="924d1-109">Wie sich ein Client mithilfe eines Benutzername/Kennwort-Paars authentifizieren kann.</span><span class="sxs-lookup"><span data-stu-id="924d1-109">How a client can authenticate using a username/password pair.</span></span>

- <span data-ttu-id="924d1-110">Wie der Server die Clientanmeldeinformationen mit einem benutzerdefinierten Tokenauthentifizierer überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="924d1-110">How the server can validate the client credentials using a custom token authenticator.</span></span>

- <span data-ttu-id="924d1-111">Gibt an, wie der WCF-Dienst Code mit dem benutzerdefinierten tokenauthentifikator verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="924d1-111">How the WCF service code ties in with the custom token authenticator.</span></span>

- <span data-ttu-id="924d1-112">Wie der Server mit dem X.509-Zertifikat des Servers authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="924d1-112">How the server can be authenticated using the server's X.509 certificate.</span></span>

 <span data-ttu-id="924d1-113">Dieses Beispiel zeigt auch, wie die Identität des Aufrufers nach dem benutzerdefinierten Tokenauthentifizierungsprozess von WCF aus zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="924d1-113">This sample also shows how the caller's identity is accessible from WCF after the custom token authentication process.</span></span>

 <span data-ttu-id="924d1-114">Der Dienst macht einen einzelnen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit der App.conf-Konfigurationsdatei definiert wird.</span><span class="sxs-lookup"><span data-stu-id="924d1-114">The service exposes a single endpoint for communicating with the service, defined using the App.config configuration file.</span></span> <span data-ttu-id="924d1-115">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="924d1-115">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="924d1-116">Die Bindung wird mit einem Standard-`wsHttpBinding` konfiguriert, wobei der Sicherheitsmodus auf „Nachricht“ festgelegt ist. Dies ist der Standardmodus von `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="924d1-116">The binding is configured with a standard `wsHttpBinding`, with the security mode set to message - the default mode of the `wsHttpBinding`.</span></span> <span data-ttu-id="924d1-117">In diesem Beispiel wird das Standard-`wsHttpBinding` auf die Verwendung der Clientbenutzernamenauthentifizierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="924d1-117">This sample sets the standard `wsHttpBinding` to use client username authentication.</span></span> <span data-ttu-id="924d1-118">Außerdem konfiguriert der Dienst das Dienstzertifikat mit `serviceCredentials`-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="924d1-118">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="924d1-119">Mit dem `securityCredentials`-Verhalten können Sie ein Dienstzertifikat angeben.</span><span class="sxs-lookup"><span data-stu-id="924d1-119">The `securityCredentials` behavior allows you to specify a service certificate.</span></span> <span data-ttu-id="924d1-120">Ein Dienstzertifikat wird von einem Client verwendet, um den Dienst zu authentifizieren und Nachrichtenschutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="924d1-120">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="924d1-121">Die folgende Konfiguration verweist auf das Zertifikat localhost, das während des Beispielsetups installiert wird, wie im folgenden Setup beschrieben.</span><span class="sxs-lookup"><span data-stu-id="924d1-121">The following configuration references the localhost certificate installed during the sample setup as described in the following setup instructions.</span></span>

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service" />
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
....        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

 <span data-ttu-id="924d1-122">Die Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="924d1-122">The client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="924d1-123">Die Clientbindung wird mit dem entsprechenden `Mode` und `clientCredentialType` konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="924d1-123">The client binding is configured with the appropriate `Mode` and `clientCredentialType`.</span></span>

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

 <span data-ttu-id="924d1-124">Die Clientimplementierung legt den zu verwendenden Benutzernamen und das Kennwort fest.</span><span class="sxs-lookup"><span data-stu-id="924d1-124">The client implementation sets the user name and password to use.</span></span>

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a><span data-ttu-id="924d1-125">Benutzerdefinierter Tokenauthentifizierer</span><span class="sxs-lookup"><span data-stu-id="924d1-125">Custom Token Authenticator</span></span>
 <span data-ttu-id="924d1-126">Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Tokenauthentifizierer zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="924d1-126">Use the following steps to create a custom token authenticator:</span></span>

1. <span data-ttu-id="924d1-127">Erstellen Sie einen benutzerdefinierten Tokenauthentifizierer.</span><span class="sxs-lookup"><span data-stu-id="924d1-127">Write a custom token authenticator.</span></span>

     <span data-ttu-id="924d1-128">Im Beispiel wird ein benutzerdefinierter Tokenauthentifizierer implementiert, der überprüft, ob der Benutzername ein gültiges E-Mail-Format hat.</span><span class="sxs-lookup"><span data-stu-id="924d1-128">The sample implements a custom token authenticator that validates that the username has a valid email format.</span></span> <span data-ttu-id="924d1-129">Er ermittelt den <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>.</span><span class="sxs-lookup"><span data-stu-id="924d1-129">It derives the <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>.</span></span> <span data-ttu-id="924d1-130">Die wichtigste Methode in dieser Klasse ist <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="924d1-130">The most important method in this class is <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>.</span></span> <span data-ttu-id="924d1-131">In dieser Methode überprüft der Authentifizierer das Format des Benutzernamens und kontrolliert, ob der Hostname von einer nicht autorisierten Domäne stammt.</span><span class="sxs-lookup"><span data-stu-id="924d1-131">In this method, the authenticator validates the format of the username and also that the host name is not from a rogue domain.</span></span> <span data-ttu-id="924d1-132">Wenn beide Bedingungen erfüllt sind, gibt er eine schreibgeschützte Auflistung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Instanzen zurück, mit der Ansprüche bereitgestellt werden, die die Informationen im Benutzernamentoken darstellen.</span><span class="sxs-lookup"><span data-stu-id="924d1-132">If both conditions are met, then it returns a read-only collection of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> instances that is then used to provide claims that represent the information stored inside the username token.</span></span>

    ```csharp
    protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateUserNamePasswordCore(string userName, string password)
    {
        if (!ValidateUserNameFormat(userName))
            throw new SecurityTokenValidationException("Incorrect UserName format");

        ClaimSet claimSet = new DefaultClaimSet(ClaimSet.System, new Claim(ClaimTypes.Name, userName, Rights.PossessProperty));
        List<IIdentity> identities = new List<IIdentity>(1);
        identities.Add(new GenericIdentity(userName));
        List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
        policies.Add(new UnconditionalPolicy(ClaimSet.System, claimSet, DateTime.MaxValue.ToUniversalTime(), identities));
        return policies.AsReadOnly();
    }
    ```

2. <span data-ttu-id="924d1-133">Geben Sie eine Autorisierungsrichtlinie an, die vom benutzerdefinierten Tokenauthentifizierer zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="924d1-133">Provide an authorization policy that is returned by custom token authenticator.</span></span>

     <span data-ttu-id="924d1-134">Dieses Beispiel enthält seine eigene Implementierung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, die als `UnconditionalPolicy` bezeichnet wird und Sätze von Ansprüchen und Identitäten zurückgibt, die in ihrem Konstruktor an sie übergeben wurden.</span><span class="sxs-lookup"><span data-stu-id="924d1-134">This sample provides its own implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> called `UnconditionalPolicy` that returns set of claims and identities that were passed to it in its constructor.</span></span>

    ```csharp
    class UnconditionalPolicy : IAuthorizationPolicy
    {
        String id = Guid.NewGuid().ToString();
        ClaimSet issuer;
        ClaimSet issuance;
        DateTime expirationTime;
        IList<IIdentity> identities;

        public UnconditionalPolicy(ClaimSet issuer, ClaimSet issuance, DateTime expirationTime, IList<IIdentity> identities)
        {
            if (issuer == null)
                throw new ArgumentNullException("issuer");
            if (issuance == null)
                throw new ArgumentNullException("issuance");

            this.issuer = issuer;
            this.issuance = issuance;
            this.identities = identities;
            this.expirationTime = expirationTime;
        }

        public string Id
        {
            get { return this.id; }
        }

        public ClaimSet Issuer
        {
            get { return this.issuer; }
        }

        public DateTime ExpirationTime
        {
            get { return this.expirationTime; }
        }

        public bool Evaluate(EvaluationContext evaluationContext, ref object state)
        {
            evaluationContext.AddToTarget(this, this.issuance);

            if (this.identities != null)
            {
                object value;
                IList<IIdentity> contextIdentities;
                if (!evaluationContext.Properties.TryGetValue("Identities", out value))
                {
                    contextIdentities = new List<IIdentity>(this.identities.Count);
                    evaluationContext.Properties.Add("Identities", contextIdentities);
                }
                else
                {
                    contextIdentities = value as IList<IIdentity>;
                }
                foreach (IIdentity identity in this.identities)
                {
                    contextIdentities.Add(identity);
                }
            }

            evaluationContext.RecordExpirationTime(this.expirationTime);
            return true;
        }
    }
    ```

3. <span data-ttu-id="924d1-135">Schreiben Sie den benutzerdefinierten Sicherheitstoken-Manager.</span><span class="sxs-lookup"><span data-stu-id="924d1-135">Write a custom security token manager.</span></span>

     <span data-ttu-id="924d1-136">Mit dem <xref:System.IdentityModel.Selectors.SecurityTokenManager> wird ein <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> für bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>-Objekte erstellt, die in der `CreateSecurityTokenAuthenticator`-Methode an ihn übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="924d1-136">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> objects that are passed to it in the `CreateSecurityTokenAuthenticator` method.</span></span> <span data-ttu-id="924d1-137">Der Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenanbietern und Token-Serialisierungsprogrammen. Diese Vorgänge werden in diesem Beispiel jedoch nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="924d1-137">The security token manager is also used to create token providers and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="924d1-138">In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> und überschreibt die Methode `CreateSecurityTokenAuthenticator`, um benutzerdefinierte Benutzernamen-Tokenauthentifizierer zurückzugeben, wenn die übergebenen Tokenanforderungen angeben, dass der Benutzernamenauthentifizierer angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="924d1-138">In this sample, the custom security token manager inherits from <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenAuthenticator` method to return custom username token authenticator when the passed token requirements indicate that username authenticator is requested.</span></span>

    ```csharp
    public class MySecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        MyUserNameCredential myUserNameCredential;

        public MySecurityTokenManager(MyUserNameCredential myUserNameCredential)
            : base(myUserNameCredential)
        {
            this.myUserNameCredential = myUserNameCredential;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType ==  SecurityTokenTypes.UserName)
            {
                outOfBandTokenResolver = null;
                return new MyTokenAuthenticator();
            }
            else
            {
                return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
            }
        }
    }
    ```

4. <span data-ttu-id="924d1-139">Erstellen Sie benutzerdefinierte Dienstanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="924d1-139">Write a custom service credential.</span></span>

     <span data-ttu-id="924d1-140">Die Klasse der Dienstanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Dienst konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="924d1-140">The service credentials class is used to represent the credentials that are configured for the service and creates a security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>

    ```csharp
    public class MyUserNameCredential : ServiceCredentials
    {

        public MyUserNameCredential()
            : base()
        {
        }

        protected override ServiceCredentials CloneCore()
        {
            return new MyUserNameCredential();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new MySecurityTokenManager(this);
        }

    }
    ```

5. <span data-ttu-id="924d1-141">Konfigurieren Sie den Dienst für die Verwendung der benutzerdefinierten Dienstanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="924d1-141">Configure the service to use the custom service credential.</span></span>

     <span data-ttu-id="924d1-142">Damit der Dienst die benutzerdefinierten Dienstanmeldeinformationen verwenden kann, wird die standardmäßige Dienstanmeldeinformationen-Klasse nach dem Abrufen des in den standardmäßigen Dienstanmeldeinformationen vorkonfigurierten Dienstzertifikats gelöscht. Anschließend wird die neue Dienstanmeldeinformationen-Instanz zum Verwenden der vorkonfigurierten Dienstzertifikate konfiguriert und zum Dienstverhalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="924d1-142">In order for the service to use the custom service credential, we delete the default service credential class after capturing the service certificate that is already preconfigured in the default service credential, and configure the new service credential instance to use the preconfigured service certificates and add this new service credential instance to service behaviors.</span></span>

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 <span data-ttu-id="924d1-143">Um die Informationen zu den Aufrufern anzuzeigen, können Sie <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> verwenden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="924d1-143">To display the caller's information, you can use the <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> as shown in the following code.</span></span> <span data-ttu-id="924d1-144"><xref:System.ServiceModel.ServiceSecurityContext.Current%2A> enthält Informationen zu den Ansprüchen des aktuellen Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="924d1-144">The <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> contains claims information about the current caller.</span></span>

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 <span data-ttu-id="924d1-145">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="924d1-145">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="924d1-146">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="924d1-146">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="924d1-147">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="924d1-147">Setup Batch File</span></span>
 <span data-ttu-id="924d1-148">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="924d1-148">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate based security.</span></span> <span data-ttu-id="924d1-149">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="924d1-149">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="924d1-150">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="924d1-150">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration.</span></span>

- <span data-ttu-id="924d1-151">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="924d1-151">Creating the server certificate.</span></span>

     <span data-ttu-id="924d1-152">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="924d1-152">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="924d1-153">Die Variable `%SERVER_NAME%` gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="924d1-153">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="924d1-154">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="924d1-154">Change this variable to specify your own server name.</span></span> <span data-ttu-id="924d1-155">Standardmäßig lautet die Variable in dieser Batchdatei localhost.</span><span class="sxs-lookup"><span data-stu-id="924d1-155">The default in this batch file is localhost.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="924d1-156">Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="924d1-156">Installing the server certificate into client's trusted certificate store.</span></span>

     <span data-ttu-id="924d1-157">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="924d1-157">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="924d1-158">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="924d1-158">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="924d1-159">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="924d1-159">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > <span data-ttu-id="924d1-160">Die Setupbatchdatei ist darauf ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="924d1-160">The setup batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="924d1-161">Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="924d1-161">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="924d1-162">Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="924d1-162">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="924d1-163">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="924d1-163">To set up and build the sample</span></span>

1. <span data-ttu-id="924d1-164">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="924d1-164">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="924d1-165">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="924d1-165">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="924d1-166">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="924d1-166">To run the sample on the same computer</span></span>

1. <span data-ttu-id="924d1-167">Führen Sie Setup. bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="924d1-167">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt opened with administrator privileges.</span></span> <span data-ttu-id="924d1-168">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="924d1-168">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="924d1-169">Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="924d1-169">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="924d1-170">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="924d1-170">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="924d1-171">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="924d1-171">Launch service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="924d1-172">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="924d1-172">Launch client.exe from \client\bin.</span></span> <span data-ttu-id="924d1-173">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="924d1-173">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="924d1-174">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="924d1-174">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="924d1-175">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="924d1-175">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="924d1-176">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="924d1-176">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="924d1-177">Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="924d1-177">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="924d1-178">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="924d1-178">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="924d1-179">Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält.</span><span class="sxs-lookup"><span data-stu-id="924d1-179">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="924d1-180">Die Datei App.config des Diensts muss so aktualisiert werden, dass sie diesem neuen Zertifikatnamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="924d1-180">The service App.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="924d1-181">Erstellen Sie sie mithilfe der Datei Setup.bat, indem Sie die Variable `%SERVER_NAME%` auf den vollqualifizierten Hostnamen des Computers festlegen, auf dem der Dienst ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="924d1-181">You can create one by using the Setup.bat if you set the `%SERVER_NAME%` variable to fully-qualified host name of the computer on which the service will run.</span></span> <span data-ttu-id="924d1-182">Beachten Sie, dass die Datei "Setup. bat" von einem Developer-Eingabeaufforderung für Visual Studio ausgeführt werden muss, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="924d1-182">Note that the setup.bat file must be run from a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>  
  
4. <span data-ttu-id="924d1-183">Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients.</span><span class="sxs-lookup"><span data-stu-id="924d1-183">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="924d1-184">Sie müssen diesen Schritt nur dann ausführen, wenn das Serverzertifikat von einem Aussteller stammt, der vom Client als vertrauenswürdig eingestuft wurde.</span><span class="sxs-lookup"><span data-stu-id="924d1-184">You do not need to do this except when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="924d1-185">Ändern Sie in der Datei App.config auf dem Dienstcomputer den Wert der Basisadresse, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="924d1-185">In the App.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="924d1-186">Führen Sie auf dem Dienstcomputer service.exe an einer Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="924d1-186">On the service computer, run service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="924d1-187">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="924d1-187">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="924d1-188">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="924d1-188">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="924d1-189">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="924d1-189">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
10. <span data-ttu-id="924d1-190">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="924d1-190">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="924d1-191">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="924d1-191">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="924d1-192">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="924d1-192">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
