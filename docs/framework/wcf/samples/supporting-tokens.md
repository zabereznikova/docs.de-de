---
title: Unterstützende Token
ms.date: 03/30/2017
ms.assetid: 65a8905d-92cc-4ab0-b6ed-1f710e40784e
ms.openlocfilehash: d7e2a824060f4be05e0b0e9d1765fcf271eacbd3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293662"
---
# <a name="supporting-tokens"></a><span data-ttu-id="1c347-102">Unterstützende Token</span><span class="sxs-lookup"><span data-stu-id="1c347-102">Supporting Tokens</span></span>

<span data-ttu-id="1c347-103">Im Beispiel für unterstützende Token wird veranschaulicht, wie einer Nachricht, die WS-Sicherheit verwendet, zusätzliche Token hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1c347-103">The Supporting Tokens sample demonstrates how to add additional tokens to a message that uses WS-Security.</span></span> <span data-ttu-id="1c347-104">Das Beispiel fügt zusätzlich zu einem Sicherheitstoken für den Benutzernamen ein binäres X.509-Sicherheitstoken hinzu.</span><span class="sxs-lookup"><span data-stu-id="1c347-104">The example adds an X.509 binary security token in addition to a username security token.</span></span> <span data-ttu-id="1c347-105">Das Token wird in einem WS-Sicherheit-Nachrichtenkopf vom Client zum Dienst übergeben, und ein Teil der Nachricht wird mit dem privaten Schlüssel signiert, der dem X.509-Sicherheitstoken zugeordnet ist, um dem Empfänger den Besitz des X.509-Zertifikats nachzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1c347-105">The token is passed in a WS-Security message header from the client to the service and part of the message is signed with the private key associated with the X.509 security token to prove the possession of the X.509 certificate to the receiver.</span></span> <span data-ttu-id="1c347-106">Dies ist nützlich, wenn die Anforderung besteht, dass einer Nachricht mehrere Ansprüche zugeordnet sein müssen, um den Absender zu authentifizieren oder zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="1c347-106">This is useful in the case when there is a requirement to have multiple claims associated with a message to authenticate or authorize the sender.</span></span> <span data-ttu-id="1c347-107">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-107">The service implements a contract that defines a request-reply communication pattern.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1c347-108">Zeigt</span><span class="sxs-lookup"><span data-stu-id="1c347-108">Demonstrates</span></span>

 <span data-ttu-id="1c347-109">Dieses Beispiel veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c347-109">The sample demonstrates:</span></span>

- <span data-ttu-id="1c347-110">Wie ein Client zusätzliche Sicherheitstoken an einen Dienst übergeben kann.</span><span class="sxs-lookup"><span data-stu-id="1c347-110">How a client can pass additional security tokens to a service.</span></span>

- <span data-ttu-id="1c347-111">Wie der Server auf zusätzlichen Sicherheitstoken zugeordnete Ansprüche zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="1c347-111">How the server can access claims associated with additional security tokens.</span></span>

- <span data-ttu-id="1c347-112">Wie das X.509-Zertifikat des Servers dazu verwendet wird, den zur Nachrichtenverschlüsselung und für die Signatur verwendeten symmetrischen Schlüssel zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1c347-112">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

> [!NOTE]
> <span data-ttu-id="1c347-113">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="1c347-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

## <a name="client-authenticates-with-username-token-and-supporting-x509-security-token"></a><span data-ttu-id="1c347-114">Client wird mit Benutzernamentoken und dem unterstützenden X.509-Sicherheitstoken authentifiziert</span><span class="sxs-lookup"><span data-stu-id="1c347-114">Client Authenticates with Username Token and Supporting X.509 Security Token</span></span>

 <span data-ttu-id="1c347-115">Der Dienst macht einen einzelnen Endpunkt für die Kommunikation verfügbar, der programmgesteuert mithilfe der `BindingHelper`-Klasse und der `EchoServiceHost`-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1c347-115">The service exposes a single endpoint for communicating that is programmatically created using the `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="1c347-116">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="1c347-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="1c347-117">Die Bindung wird mit einer benutzerdefinierten Bindung unter Verwendung von `SymmetricSecurityBindingElement` und `HttpTransportBindingElement` konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1c347-117">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="1c347-118">In diesem Beispiel wird `SymmetricSecurityBindingElement` so eingestellt, dass es ein X.509-Zertifikat für den Dienst verwendet, um den symmetrischen Schlüssel während der Übertragung zu schützen und um in einem WS-Sicherheit-Nachrichtenkopf zusammen mit dem unterstützenden `UserNameToken` ein `X509SecurityToken` zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1c347-118">This sample sets the `SymmetricSecurityBindingElement` to use a service X.509 certificate to protect the symmetric key during transmission and to pass a `UserNameToken` along with the supporting `X509SecurityToken` in a WS-Security message header.</span></span> <span data-ttu-id="1c347-119">Der symmetrische Schlüssel wird verwendet, um den Nachrichtentext und das Sicherheitstoken für den Benutzernamen zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1c347-119">The symmetric key is used to encrypt the message body and the username security token.</span></span> <span data-ttu-id="1c347-120">Das unterstützende Token wird im WS-Sicherheit-Nachrichtenkopf als zusätzliches binäres Sicherheitstoken übergeben.</span><span class="sxs-lookup"><span data-stu-id="1c347-120">The supporting token is passed as an additional binary security token in the WS-Security message header.</span></span> <span data-ttu-id="1c347-121">Der Nachweis für die Authentizität des unterstützenden Tokens wird durch Signieren eines Teils der Nachricht mit dem privaten Schlüssel erbracht, der dem unterstützenden X.509-Sicherheitstoken zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1c347-121">The authenticity of the supporting token is proved by signing part of the message with the private key associated with the supporting X.509 security token.</span></span>

```csharp
public static Binding CreateMultiFactorAuthenticationBinding()
{
    HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();

    // the message security binding element will be configured to require 2 tokens:
    // 1) A username-password encrypted with the service token
    // 2) A client certificate used to sign the message

    // Instantiate a binding element that will require the username/password token in the message (encrypted with the server cert)
    SymmetricSecurityBindingElement messageSecurity = SecurityBindingElement.CreateUserNameForCertificateBindingElement();

    // Create supporting token parameters for the client X509 certificate.
    X509SecurityTokenParameters clientX509SupportingTokenParameters = new X509SecurityTokenParameters();
    // Specify that the supporting token is passed in message send by the client to the service
    clientX509SupportingTokenParameters.InclusionMode = SecurityTokenInclusionMode.AlwaysToRecipient;
    // Turn off derived keys
    clientX509SupportingTokenParameters.RequireDerivedKeys = false;
    // Augment the binding element to require the client's X509 certificate as an endorsing token in the message
    messageSecurity.EndpointSupportingTokenParameters.Endorsing.Add(clientX509SupportingTokenParameters);

    // Create a CustomBinding based on the constructed security binding element.
    return new CustomBinding(messageSecurity, httpTransport);
}
```

 <span data-ttu-id="1c347-122">Das Verhalten legt die Dienstanmeldeinformationen fest, die zur Clientauthentifizierung verwendet werden sollen, sowie Informationen über das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="1c347-122">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span> <span data-ttu-id="1c347-123">Im Beispiel wird `CN=localhost` als Betreffname im X.509-Zertifikat für den Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c347-123">The sample uses `CN=localhost` as a subject name in the service X.509 certificate.</span></span>

```csharp
override protected void InitializeRuntime()
{
    // Extract the ServiceCredentials behavior or create one.
    ServiceCredentials serviceCredentials =
        this.Description.Behaviors.Find<ServiceCredentials>();
    if (serviceCredentials == null)
    {
        serviceCredentials = new ServiceCredentials();
        this.Description.Behaviors.Add(serviceCredentials);
    }

    // Set the service certificate
    serviceCredentials.ServiceCertificate.SetCertificate(
                                       "CN=localhost");

/*
Setting the CertificateValidationMode to PeerOrChainTrust means that if the certificate is in the Trusted People store, then it will be trusted without performing a validation of the certificate's issuer chain. This setting is used here for convenience so that the sample can be run without having to have certificates issued by a certification authority (CA).
This setting is less secure than the default, ChainTrust. The security implications of this setting should be carefully considered before using PeerOrChainTrust in production code.
*/
    serviceCredentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;

    // Create the custom binding and add an endpoint to the service.
    Binding multipleTokensBinding =
         BindingHelper.CreateMultiFactorAuthenticationBinding();
    this.AddServiceEndpoint(typeof(IEchoService),
                          multipleTokensBinding, string.Empty);
    base.InitializeRuntime();
}
```

 <span data-ttu-id="1c347-124">Dienstcode:</span><span class="sxs-lookup"><span data-stu-id="1c347-124">Service code:</span></span>

```csharp
[ServiceBehavior(IncludeExceptionDetailInFaults = true)]
public class EchoService : IEchoService
{
    public string Echo()
    {
        string userName;
        string certificateSubjectName;
        GetCallerIdentities(
            OperationContext.Current.ServiceSecurityContext,
            out userName,
            out certificateSubjectName);
            return $"Hello {userName}, {certificateSubjectName}";
    }

    public void Dispose()
    {
    }

    bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet,
            string claimType, out TClaimResource resourceValue)
            where TClaimResource : class
    {
        resourceValue = default(TClaimResource);
        IEnumerable<Claim> matchingClaims =
            claimSet.FindClaims(claimType, Rights.PossessProperty);
        if(matchingClaims == null)
            return false;
        IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
        if (enumerator.MoveNext())
        {
            resourceValue =
              (enumerator.Current.Resource == null) ? null :
              (enumerator.Current.Resource as TClaimResource);
            return true;
        }
        else
        {
            return false;
        }
    }

    // Returns the username and certificate subject name provided by
    //the client
    void GetCallerIdentities(ServiceSecurityContext
        callerSecurityContext,
        out string userName, out string certificateSubjectName)
    {
        userName = null;
        certificateSubjectName = null;

       // Look in all the claimsets in the authorization context
       foreach (ClaimSet claimSet in
               callerSecurityContext.AuthorizationContext.ClaimSets)
       {
            if (claimSet is WindowsClaimSet)
            {
                // Try to find a Name claim. This will have been
                // generated from the windows username.
                string tmpName;
                if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,
                                                      out tmpName))
                {
                    userName = tmpName;
                }
            }
            else if (claimSet is X509CertificateClaimSet)
            {
                // Try to find an X500DistinguishedName claim. This will
                // have been generated from the client certificate.
                X500DistinguishedName tmpDistinguishedName;
                if (TryGetClaimValue<X500DistinguishedName>(claimSet,
                               ClaimTypes.X500DistinguishedName,
                               out tmpDistinguishedName))
                {
                    certificateSubjectName = tmpDistinguishedName.Name;
                }
            }
        }
    }
}
```

 <span data-ttu-id="1c347-125">Der Clientendpunkt wird auf ähnliche Weise wie der Dienstendpunkt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="1c347-125">The client endpoint is configured in a similar way to the service endpoint.</span></span> <span data-ttu-id="1c347-126">Der Client verwendet die gleiche `BindingHelper`-Klasse, um eine Bindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c347-126">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="1c347-127">Der Rest des Setups befindet sich in der `Client`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1c347-127">The rest of the setup is located in `Client` class.</span></span> <span data-ttu-id="1c347-128">Der Client legt Informationen über das Sicherheitstoken für den Benutzernamen und das unterstützende X.509-Sicherheitstoken sowie Informationen über das X.509-Zertifikat für den Dienst im Setupcode für die Auflistung der Clientendpunkt-Verhaltensweisen fest.</span><span class="sxs-lookup"><span data-stu-id="1c347-128">The client sets information about the user name security token, the supporting X.509 security token and information about the service X.509 certificate in the setup code to the client endpoint behaviors collection.</span></span>

```csharp
 static void Main()
 {
     // Create the custom binding and an endpoint address for
     // the service.
     Binding multipleTokensBinding =
         BindingHelper.CreateMultiFactorAuthenticationBinding();
         EndpointAddress serviceAddress = new EndpointAddress(
         "http://localhost/servicemodelsamples/service.svc");
       ChannelFactory<IEchoService> channelFactory = null;
       IEchoService client = null;

       Console.WriteLine("Username authentication required.");
       Console.WriteLine(
         "Provide a valid machine or domain account. [domain\\user]");
       Console.WriteLine("   Enter username:");
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
                    password =
                       password.Substring(0, password.Length - 1);
                }
                info = Console.ReadKey(true);
            }
         }
         for (int i = 0; i < password.Length; i++)
            Console.Write("*");
         Console.WriteLine();
         try
         {
           // Create a proxy with the previously create binding and
           // endpoint address
              channelFactory =
                 new ChannelFactory<IEchoService>(
                     multipleTokensBinding, serviceAddress);
           // configure the username credentials, the client
           // certificate and the server certificate on the channel
           // factory
           channelFactory.Credentials.UserName.UserName = username;
           channelFactory.Credentials.UserName.Password = password;
           channelFactory.Credentials.ClientCertificate.SetCertificate(
           "CN=client.com", StoreLocation.CurrentUser, StoreName.My);
              channelFactory.Credentials.ServiceCertificate.SetDefaultCertificate(
           "CN=localhost", StoreLocation.LocalMachine, StoreName.My);
           client = channelFactory.CreateChannel();
           Console.WriteLine("Echo service returned: {0}",
                                           client.Echo());

           ((IChannel)client).Close();
           channelFactory.Close();
        }
        catch (CommunicationException e)
        {
         Abort((IChannel)client, channelFactory);
         // if there is a fault then print it out
         FaultException fe = null;
         Exception tmp = e;
         while (tmp != null)
         {
            fe = tmp as FaultException;
            if (fe != null)
            {
                break;
            }
            tmp = tmp.InnerException;
        }
        if (fe != null)
        {
           Console.WriteLine("The server sent back a fault: {0}",
         fe.CreateMessageFault().Reason.GetMatchingTranslation().Text);
        }
        else
        {
         Console.WriteLine("The request failed with exception: {0}",e);
        }
    }
    catch (TimeoutException)
    {
        Abort((IChannel)client, channelFactory);
        Console.WriteLine("The request timed out");
    }
    catch (Exception e)
    {
         Abort((IChannel)client, channelFactory);
          Console.WriteLine(
          "The request failed with unexpected exception: {0}", e);
    }
    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();
}
```

## <a name="displaying-callers-information"></a><span data-ttu-id="1c347-129">Anzeigen von Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="1c347-129">Displaying Callers' Information</span></span>

 <span data-ttu-id="1c347-130">Um die Informationen zu den Aufrufern anzuzeigen, können Sie `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` verwenden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c347-130">To display the caller's information, you can use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following code.</span></span> <span data-ttu-id="1c347-131">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` enthält dem aktuellen Aufrufer zugeordnete Autorisierungsansprüche.</span><span class="sxs-lookup"><span data-stu-id="1c347-131">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="1c347-132">Diese Ansprüche werden automatisch von Windows Communication Foundation (WCF) für jedes Token bereitgestellt, das in der Nachricht empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="1c347-132">Those claims are supplied automatically by Windows Communication Foundation (WCF) for every token received in the message.</span></span>

```csharp
bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet, string
                         claimType, out TClaimResource resourceValue)
    where TClaimResource : class
{
    resourceValue = default(TClaimResource);
    IEnumerable<Claim> matchingClaims =
    claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
          return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    if (enumerator.MoveNext())
    {
        resourceValue = (enumerator.Current.Resource == null) ? null : (enumerator.Current.Resource as TClaimResource);
        return true;
    }
    else
    {
         return false;
    }
}

// Returns the username and certificate subject name provided by the client
void GetCallerIdentities(ServiceSecurityContext callerSecurityContext, out string userName, out string certificateSubjectName)
{
    userName = null;
    certificateSubjectName = null;

    // Look in all the claimsets in the authorization context
    foreach (ClaimSet claimSet in
      callerSecurityContext.AuthorizationContext.ClaimSets)
    {
        if (claimSet is WindowsClaimSet)
        {
            // Try to find a Name claim. This will have been generated
            //from the windows username.
            string tmpName;
            if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,
                                                     out tmpName))
            {
                userName = tmpName;
            }
        }
        else if (claimSet is X509CertificateClaimSet)
         {
            //Try to find an X500DistinguishedName claim.
            //This will have been generated from the client
            //certificate.
            X500DistinguishedName tmpDistinguishedName;
            if (TryGetClaimValue<X500DistinguishedName>(claimSet,
               ClaimTypes.X500DistinguishedName,
               out tmpDistinguishedName))
            {
                    certificateSubjectName = tmpDistinguishedName.Name;
            }
        }
    }
}
```

## <a name="running-the-sample"></a><span data-ttu-id="1c347-133">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="1c347-133">Running the Sample</span></span>

 <span data-ttu-id="1c347-134">Wenn Sie das Beispiel ausführen, fordert der Client Sie zuerst auf, den Benutzernamen und das Kennwort für das Benutzernamentoken anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1c347-134">When you run the sample, the client first prompts you to provide user name and password for the user name token.</span></span> <span data-ttu-id="1c347-135">Stellen Sie sicher, dass Sie für Ihr Systemkonto korrekte Werte angeben, da WCF auf dem Dienst die im Benutzernamen Token bereitgestellten Werte der vom System bereitgestellten Identität zuordnet.</span><span class="sxs-lookup"><span data-stu-id="1c347-135">Be sure to provide correct values for your system account, because WCF on the service maps the values supplied in the user name token into the identity provided by the system.</span></span> <span data-ttu-id="1c347-136">Danach zeigt der Client die Antwort vom Dienst an.</span><span class="sxs-lookup"><span data-stu-id="1c347-136">After that, the client displays the response from the service.</span></span> <span data-ttu-id="1c347-137">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1c347-137">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="1c347-138">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="1c347-138">Setup Batch File</span></span>

 <span data-ttu-id="1c347-139">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer von Internetinformationsdiensten (IIS) gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="1c347-139">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run Internet Information Services (IIS) hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="1c347-140">Diese Batchdatei muss so geändert werden, dass sie computerübergreifend oder in einem nicht gehosteten Fall funktioniert.</span><span class="sxs-lookup"><span data-stu-id="1c347-140">This batch file must be modified to work across machines or to work in a non-hosted case.</span></span>

 <span data-ttu-id="1c347-141">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1c347-141">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in appropriate configuration.</span></span>

### <a name="creating-the-client-certificate"></a><span data-ttu-id="1c347-142">Erstellen des Clientzertifikats</span><span class="sxs-lookup"><span data-stu-id="1c347-142">Creating the Client Certificate</span></span>

 <span data-ttu-id="1c347-143">Die folgenden Zeilen aus der Batchdatei Setup.bat erstellen das zu verwendende Clientzertifikat.</span><span class="sxs-lookup"><span data-stu-id="1c347-143">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="1c347-144">Die `%CLIENT_NAME%`-Variable gibt den Betreff des Clientzertifikats an.</span><span class="sxs-lookup"><span data-stu-id="1c347-144">The `%CLIENT_NAME%` variable specifies the subject of the client certificate.</span></span> <span data-ttu-id="1c347-145">In diesem Beispiel wird "client.com" als Betreffname verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c347-145">This sample uses "client.com" as the subject name.</span></span>

 <span data-ttu-id="1c347-146">Das Zertifikat wird im persönlichen Speicher unter dem Speicherort `CurrentUser` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c347-146">The certificate is stored in My (Personal) store under the `CurrentUser` store location.</span></span>

```console
echo ************
echo making client cert
echo ************
makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
```

### <a name="installing-the-client-certificate-into-the-servers-trusted-store"></a><span data-ttu-id="1c347-147">Installieren des Clientzertifikats im vertrauenswürdigen Speicher des Servers</span><span class="sxs-lookup"><span data-stu-id="1c347-147">Installing the Client Certificate into the Server's Trusted Store</span></span>

 <span data-ttu-id="1c347-148">Die folgende Zeile in der Batchdatei Setup.bat kopiert das Clientzertifikat in den Serverspeicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="1c347-148">The following line in the Setup.bat batch file copies the client certificate into the server’s trusted people store.</span></span> <span data-ttu-id="1c347-149">Dieser Schritt ist erforderlich, da das Serversystem von Makecert.exe generierten Zertifikaten nicht implizit vertraut.</span><span class="sxs-lookup"><span data-stu-id="1c347-149">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the server’s system.</span></span> <span data-ttu-id="1c347-150">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c347-150">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

```console
echo ************
echo copying client cert to server's CurrentUserstore
echo ************
certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
```

### <a name="creating-the-server-certificate"></a><span data-ttu-id="1c347-151">Erstellen des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="1c347-151">Creating the Server Certificate</span></span>

 <span data-ttu-id="1c347-152">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="1c347-152">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="1c347-153">Die Variable `%SERVER_NAME%` gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="1c347-153">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="1c347-154">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="1c347-154">Change this variable to specify your own server name.</span></span> <span data-ttu-id="1c347-155">Standardmäßig lautet die Variable in dieser Batchdatei localhost.</span><span class="sxs-lookup"><span data-stu-id="1c347-155">The default in this batch file is localhost.</span></span>

 <span data-ttu-id="1c347-156">Das Zertifikat wird im persönlichen Speicher unter dem Speicherort LocalMachine gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c347-156">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span> <span data-ttu-id="1c347-157">Das Zertifikat wird für die IIS-gehosteten Dienste im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c347-157">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="1c347-158">Für selbst gehostete Dienste sollten Sie die Batchdatei so ändern, dass das Serverzertifikat im Speicherort CurrentUser gespeichert wird. Ersetzen Sie hierzu die Zeichenfolge LocalMachine durch CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="1c347-158">For self-hosted services, you should modify the batch file to store the server certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

```console
echo ************
echo Server cert setup starting
echo %SERVER_NAME%
echo ************
echo making server cert
echo ************
makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
```

### <a name="installing-server-certificate-into-clients-trusted-certificate-store"></a><span data-ttu-id="1c347-159">Installieren des Serverzertifikats im Clientspeicher für vertrauenswürdige Zertifikate</span><span class="sxs-lookup"><span data-stu-id="1c347-159">Installing Server Certificate into Client's Trusted Certificate Store</span></span>

 <span data-ttu-id="1c347-160">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-160">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="1c347-161">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="1c347-161">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="1c347-162">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c347-162">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

```console
echo ************
echo copying server cert to client's TrustedPeople store
echo ************certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
```

### <a name="enabling-access-to-the-certificates-private-key"></a><span data-ttu-id="1c347-163">Aktivieren des Zugriffs auf den privaten Schlüssel des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="1c347-163">Enabling Access to the Certificate's Private Key</span></span>

 <span data-ttu-id="1c347-164">Um den Zugriff vom IIS-gehosteten Dienst aus auf den privaten Schlüssel des Zertifikats zu aktivieren, müssen dem Benutzerkonto, unter dem der IIS-gehostete Prozess ausgeführt wird, entsprechende Berechtigungen für den privaten Schlüssel gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="1c347-164">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="1c347-165">Dies wird durch die letzten Schritte im Skript Setup.bat erreicht.</span><span class="sxs-lookup"><span data-stu-id="1c347-165">This is accomplished by last steps in the Setup.bat script.</span></span>

```console
echo ************
echo setting privileges on server certificates
echo ************
for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i
set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
(ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
iisreset
```

##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1c347-166">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="1c347-166">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1c347-167">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="1c347-167">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="1c347-168">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c347-168">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="1c347-169">Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1c347-169">To run the sample in a single- or cross-machine configuration, use the following instructions.</span></span>

##### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="1c347-170">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="1c347-170">To run the sample on the same machine</span></span>

1. <span data-ttu-id="1c347-171">Führen Sie Setup.bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="1c347-171">Run Setup.bat from the sample install folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="1c347-172">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1c347-172">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c347-173">Die Batchdatei Setup.bat ist für die Ausführung über eine Visual Studio 2012-Eingabeaufforderung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-173">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="1c347-174">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Setup.bat Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1c347-174">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span> <span data-ttu-id="1c347-175">Entfernen Sie nach Abschluss des Beispiels unbedingt die Zertifikate, indem Sie Cleanup.bat ausführen.</span><span class="sxs-lookup"><span data-stu-id="1c347-175">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="1c347-176">In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c347-176">Other security samples use the same certificates.</span></span>  
  
2. <span data-ttu-id="1c347-177">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="1c347-177">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="1c347-178">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c347-178">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="1c347-179">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1c347-179">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
##### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="1c347-180">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="1c347-180">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="1c347-181">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1c347-181">Create a directory on the service machine.</span></span> <span data-ttu-id="1c347-182">Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung namens "servicemodelsamples".</span><span class="sxs-lookup"><span data-stu-id="1c347-182">Create a virtual application named servicemodelsamples for this directory using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="1c347-183">Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="1c347-183">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service machine.</span></span> <span data-ttu-id="1c347-184">Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.</span><span class="sxs-lookup"><span data-stu-id="1c347-184">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="1c347-185">Kopieren Sie außerdem die Dateien Setup.bat, Cleanup.bat und ImportClientCert.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="1c347-185">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the service machine.</span></span>  
  
3. <span data-ttu-id="1c347-186">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="1c347-186">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="1c347-187">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="1c347-187">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="1c347-188">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="1c347-188">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="1c347-189">Führen Sie auf dem-Server `setup.bat service` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1c347-189">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="1c347-190">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-190">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="1c347-191">Bearbeiten Sie Web.config, um den neuen Zertifikat Namen (im-Attribut im) widerzuspiegeln, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist.</span><span class="sxs-lookup"><span data-stu-id="1c347-191">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully-qualified domain name of the machine.</span></span>  
  
7. <span data-ttu-id="1c347-192">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="1c347-192">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="1c347-193">Führen Sie auf dem Client `setup.bat client` in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1c347-193">On the client, run `setup.bat client` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="1c347-194">Durch Ausführen von  mit dem Argument  wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-194">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="1c347-195">Ändern Sie in der Datei "Client.exe.config" auf dem Clientcomputer den Wert für die Adresse des Endpunkts so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1c347-195">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="1c347-196">Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.</span><span class="sxs-lookup"><span data-stu-id="1c347-196">Do this by replacing localhost with the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="1c347-197">Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="1c347-197">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="1c347-198">Führen Sie auf dem Client "ImportServiceCert.bat" aus.</span><span class="sxs-lookup"><span data-stu-id="1c347-198">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="1c347-199">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-199">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="1c347-200">Führen Sie auf dem Server "ImportClientCert.bat" aus. Dadurch wird das Clientzertifikat von der Datei "Client.cer" in den LocalMachine &#8211; TrustedPeople-Speicher importiert.</span><span class="sxs-lookup"><span data-stu-id="1c347-200">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="1c347-201">Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="1c347-201">On the client machine, launch Client.exe from a command prompt window.</span></span> <span data-ttu-id="1c347-202">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1c347-202">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
##### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="1c347-203">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="1c347-203">To clean up after the sample</span></span>  
  
- <span data-ttu-id="1c347-204">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="1c347-204">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c347-205">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="1c347-205">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="1c347-206">Wenn Sie WCF-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, stellen Sie sicher, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1c347-206">If you have run WCF samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="1c347-207">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="1c347-207">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>
