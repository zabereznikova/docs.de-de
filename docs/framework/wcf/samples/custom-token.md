---
title: Benutzerdefiniertes Token
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: 1a8c312248b0c15bb2e366a3d9925014556b6dd8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553160"
---
# <a name="custom-token"></a><span data-ttu-id="0d298-102">Benutzerdefiniertes Token</span><span class="sxs-lookup"><span data-stu-id="0d298-102">Custom Token</span></span>

<span data-ttu-id="0d298-103">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte tokenimplementierung einer Windows Communication Foundation (WCF)-Anwendung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0d298-103">This sample demonstrates how to add a custom token implementation into a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="0d298-104">Im Beispiel wird ein `CreditCardToken` verwendet, um Informationen über Clientkreditkarten sicher an den Dienst zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0d298-104">The example uses a `CreditCardToken` to securely pass information about client credit cards to the service.</span></span> <span data-ttu-id="0d298-105">Das Token wird an den WS-Sicherheits-Nachrichtenkopf übergeben und zusammen mit Nachrichtentext und anderen Nachrichtenköpfen mithilfe des symmetrischen Sicherheitsbindungselements signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="0d298-105">The token is passed in the WS-Security message header and is signed and encrypted using the symmetric security binding element along with message body and other message headers.</span></span> <span data-ttu-id="0d298-106">Dies ist in Fällen nützlich, in denen die integrierten Token nicht ausreichen.</span><span class="sxs-lookup"><span data-stu-id="0d298-106">This is useful in cases where the built-in tokens are not sufficient.</span></span> <span data-ttu-id="0d298-107">In diesem Beispiel wird veranschaulicht, wie anstelle eines der integrierten Token ein benutzerdefiniertes Sicherheitstoken für einen Dienst bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0d298-107">This sample demonstrates how to provide a custom security token to a service instead of using one of the built-in tokens.</span></span> <span data-ttu-id="0d298-108">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="0d298-108">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
> <span data-ttu-id="0d298-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="0d298-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="0d298-110">Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="0d298-110">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="0d298-111">Wie ein Client ein benutzerdefiniertes Sicherheitstoken an einen Dienst übergeben kann.</span><span class="sxs-lookup"><span data-stu-id="0d298-111">How a client can pass a custom security token to a service.</span></span>

- <span data-ttu-id="0d298-112">Wie der Dienst ein benutzerdefiniertes Sicherheitstoken verwenden und überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="0d298-112">How the service can consume and validate a custom security token.</span></span>

- <span data-ttu-id="0d298-113">Gibt an, wie der WCF-Dienst Code die Informationen über empfangene Sicherheits Token, einschließlich des benutzerdefinierten Sicherheits Tokens, abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="0d298-113">How the WCF service code can obtain the information about received security tokens including the custom security token.</span></span>

- <span data-ttu-id="0d298-114">Wie das X.509-Zertifikat des Servers dazu verwendet wird, den zur Nachrichtenverschlüsselung und für die Signatur verwendeten symmetrischen Schlüssel zu schützen.</span><span class="sxs-lookup"><span data-stu-id="0d298-114">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

## <a name="client-authentication-using-a-custom-security-token"></a><span data-ttu-id="0d298-115">Sicherheitsauthentifizierung mithilfe eines benutzerdefinierten Sicherheitstokens</span><span class="sxs-lookup"><span data-stu-id="0d298-115">Client Authentication Using a Custom Security Token</span></span>

 <span data-ttu-id="0d298-116">Der Dienst macht einen einzelnen Endpunkt verfügbar, der programmgesteuert mithilfe der `BindingHelper`-Klasse und der `EchoServiceHost`-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0d298-116">The service exposes a single endpoint that is programmatically created using `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="0d298-117">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="0d298-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="0d298-118">Die Bindung wird mit einer benutzerdefinierten Bindung unter Verwendung von `SymmetricSecurityBindingElement` und `HttpTransportBindingElement` konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0d298-118">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="0d298-119">In diesem Beispiel wird `SymmetricSecurityBindingElement` so eingestellt, dass es ein X.509-Zertifikat für den Dienst verwendet, um den symmetrischen Schlüssel während der Übertragung zu schützen und um in einem WS-Sicherheits-Nachrichtenkopf ein benutzerdefiniertes `CreditCardToken` als signiertes und verschlüsseltes Sicherheitstoken zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="0d298-119">This sample sets the `SymmetricSecurityBindingElement` to use a service's X.509 certificate to protect the symmetric key during transmission and to pass a custom `CreditCardToken` in a WS-Security message header as a signed and encrypted security token.</span></span> <span data-ttu-id="0d298-120">Das Verhalten legt die Dienstanmeldeinformationen fest, die zur Clientauthentifizierung verwendet werden sollen, sowie Informationen über das X.509-Zertifikat des Diensts.</span><span class="sxs-lookup"><span data-stu-id="0d298-120">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span>

```csharp
public static class BindingHelper
{
    public static Binding CreateCreditCardBinding()
    {
        var httpTransport = new HttpTransportBindingElement();

        // The message security binding element will be configured to require a credit card.
        // The token that is encrypted with the service's certificate.
        var messageSecurity = new SymmetricSecurityBindingElement();
        messageSecurity.EndpointSupportingTokenParameters.SignedEncrypted.Add(new CreditCardTokenParameters());
        X509SecurityTokenParameters x509ProtectionParameters = new X509SecurityTokenParameters();
        x509ProtectionParameters.InclusionMode = SecurityTokenInclusionMode.Never;
        messageSecurity.ProtectionTokenParameters = x509ProtectionParameters;
        return new CustomBinding(messageSecurity, httpTransport);
    }
}
```

 <span data-ttu-id="0d298-121">Um ein Kreditkartentoken in der Nachricht zu nutzen, werden im Beispiel benutzerdefinierte Dienstanmeldeinformationen verwendet, um diese Funktion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0d298-121">To consume a credit card token in the message, the sample uses custom service credentials to provide this functionality.</span></span> <span data-ttu-id="0d298-122">Die Dienstanmeldeinformationsklasse befindet sich in der Klasse `CreditCardServiceCredentials` und wird zu den Verhaltensauflistungen des Diensthosts in der `EchoServiceHost.InitializeRuntime`-Methode hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0d298-122">The service credentials class is located in the `CreditCardServiceCredentials` class and is added to the behaviors collections of the service host in the `EchoServiceHost.InitializeRuntime` method.</span></span>

```csharp
class EchoServiceHost : ServiceHost
{
    string creditCardFile;

    public EchoServiceHost(parameters Uri[] addresses)
        : base(typeof(EchoService), addresses)
    {
        creditCardFile = ConfigurationManager.AppSettings["creditCardFile"];
        if (string.IsNullOrEmpty(creditCardFile))
        {
            throw new ConfigurationErrorsException("creditCardFile not specified in service config");
        }

        creditCardFile = String.Format("{0}\\{1}", System.Web.Hosting.HostingEnvironment.ApplicationPhysicalPath, creditCardFile);
    }

    override protected void InitializeRuntime()
    {
        // Create a credit card service credentials and add it to the behaviors.
        CreditCardServiceCredentials serviceCredentials = new CreditCardServiceCredentials(this.creditCardFile);
        serviceCredentials.ServiceCertificate.SetCertificate("CN=localhost", StoreLocation.LocalMachine, StoreName.My);
        this.Description.Behaviors.Remove((typeof(ServiceCredentials)));
        this.Description.Behaviors.Add(serviceCredentials);

        // Register a credit card binding for the endpoint.
        Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
        this.AddServiceEndpoint(typeof(IEchoService), creditCardBinding, string.Empty);

        base.InitializeRuntime();
    }
}
```

 <span data-ttu-id="0d298-123">Der Clientendpunkt wird auf ähnliche Weise wie der Dienstendpunkt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0d298-123">The client endpoint is configured in a similar manner as the service endpoint.</span></span> <span data-ttu-id="0d298-124">Der Client verwendet die gleiche `BindingHelper`-Klasse, um eine Bindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d298-124">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="0d298-125">Der Rest des Setups befindet sich in der `Client`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0d298-125">The rest of the setup is located in the `Client` class.</span></span> <span data-ttu-id="0d298-126">Der Client legt außerdem Informationen, die im `CreditCardToken` enthalten sein sollen, sowie Informationen zum X.509-Zertifikat des Diensts im Setupcode fest, indem eine `CreditCardClientCredentials`-Instanz mit den entsprechenden Daten zur Auflistung der Clientendpunktverhaltensweisen hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0d298-126">The client also sets information to be contained in the `CreditCardToken` and information about the service X.509 certificate in the setup code by adding a `CreditCardClientCredentials` instance with the proper data to the client endpoint behaviors collection.</span></span> <span data-ttu-id="0d298-127">Im Beispiel wird das X.509-Zertifikat mit dem Antragstellernamen `CN=localhost` als Dienstzertifikat verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d298-127">The sample uses X.509 certificate with subject name set to `CN=localhost` as the service certificate.</span></span>

```csharp
Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
var serviceAddress = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");

// Create a client with given client endpoint configuration.
channelFactory = new ChannelFactory<IEchoService>(creditCardBinding, serviceAddress);

// Configure the credit card credentials on the channel factory.
var credentials =
      new CreditCardClientCredentials(
      new CreditCardInfo(creditCardNumber, issuer, expirationTime));
// Configure the service certificate on the credentials.
credentials.ServiceCertificate.SetDefaultCertificate(
      "CN=localhost", StoreLocation.LocalMachine, StoreName.My);

// Replace ClientCredentials with CreditCardClientCredentials.
channelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
channelFactory.Endpoint.Behaviors.Add(credentials);

client = channelFactory.CreateChannel();

Console.WriteLine($"Echo service returned: {client.Echo()}");

((IChannel)client).Close();
channelFactory.Close();
```

## <a name="custom-security-token-implementation"></a><span data-ttu-id="0d298-128">Implementierung des benutzerdefinierten Sicherheitstokens</span><span class="sxs-lookup"><span data-stu-id="0d298-128">Custom Security Token Implementation</span></span>

 <span data-ttu-id="0d298-129">Wenn Sie ein benutzerdefiniertes Sicherheits Token in WCF aktivieren möchten, erstellen Sie eine Objektdarstellung des benutzerdefinierten Sicherheits Tokens.</span><span class="sxs-lookup"><span data-stu-id="0d298-129">To enable a custom security token in WCF, create an object representation of the custom security token.</span></span> <span data-ttu-id="0d298-130">Das Beispiel enthält diese Darstellung in der `CreditCardToken`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0d298-130">The sample has this representation in the `CreditCardToken` class.</span></span> <span data-ttu-id="0d298-131">Die Objektdarstellung dient zur Aufnahme aller relevanten Informationen zu Sicherheitstoken und zur Bereitstellung einer Liste der im Sicherheitstoken enthaltenen Sicherheitsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="0d298-131">The object representation is responsible for holding all relevant security token information and to provide a list of security keys contained in the security token.</span></span> <span data-ttu-id="0d298-132">In diesem Fall enthält das Sicherheitstoken der Kreditkarte keinen Sicherheitsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="0d298-132">In this case, the credit card security token does not contain any security key.</span></span>

 <span data-ttu-id="0d298-133">Im nächsten Abschnitt wird beschrieben, was durchgeführt werden muss, damit ein benutzerdefiniertes Token über das Netzwerk übertragen und von einem WCF-Endpunkt genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0d298-133">The next section describes what must be done to enable a custom token to be transmitted over the wire and consumed by a WCF endpoint.</span></span>

```csharp
class CreditCardToken : SecurityToken
{
    CreditCardInfo cardInfo;
    DateTime effectiveTime = DateTime.UtcNow;
    string id;
    ReadOnlyCollection<SecurityKey> securityKeys;

    public CreditCardToken(CreditCardInfo cardInfo) : this(cardInfo, Guid.NewGuid().ToString()) { }

    public CreditCardToken(CreditCardInfo cardInfo, string id)
    {
        if (cardInfo == null)
            throw new ArgumentNullException(nameof(cardInfo));

        if (id == null)
            throw new ArgumentNullException(nameof(id));

        this.cardInfo = cardInfo;
        this.id = id;

        // The credit card token is not capable of any cryptography.
        this.securityKeys = new ReadOnlyCollection<SecurityKey>(new List<SecurityKey>());
    }

    public CreditCardInfo CardInfo { get { return this.cardInfo; } }

    public override ReadOnlyCollection<SecurityKey> SecurityKeys { get { return this.securityKeys; } }

    public override DateTime ValidFrom { get { return this.effectiveTime; } }
    public override DateTime ValidTo { get { return this.cardInfo.ExpirationDate; } }
    public override string Id { get { return this.id; } }
}
```

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a><span data-ttu-id="0d298-134">Abrufen des benutzerdefinierte Kreditkartentokens aus der Nachricht und Einbinden des Tokens in die Nachricht</span><span class="sxs-lookup"><span data-stu-id="0d298-134">Getting the Custom Credit Card Token to and from the Message</span></span>

 <span data-ttu-id="0d298-135">Sicherheitstokenserialisierer in WCF sind dafür verantwortlich, eine Objektdarstellung von Sicherheits Token aus dem XML-Code in der Nachricht zu erstellen und ein XML-Formular der Sicherheits Token zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d298-135">Security token serializers in WCF are responsible for creating an object representation of security tokens from the XML in the message and creating a XML form of the security tokens.</span></span> <span data-ttu-id="0d298-136">Außerdem sind sie für andere Funktionen zuständig, wie beispielsweise das Lesen und Schreiben von Schlüsselbezeichnern, die auf Sicherheitstoken verweisen. In diesem Beispiel werden jedoch nur die Funktionen behandelt, die sich auf Sicherheitstoken beziehen.</span><span class="sxs-lookup"><span data-stu-id="0d298-136">They are also responsible for other functionality such as reading and writing key identifiers pointing to security tokens, but this example uses only security token-related functionality.</span></span> <span data-ttu-id="0d298-137">Um ein benutzerdefiniertes Token zu aktivieren, müssen Sie ein eigenes Sicherheitstoken-Serialisierungsprogramm implementieren.</span><span class="sxs-lookup"><span data-stu-id="0d298-137">To enable a custom token you must implement your own security token serializer.</span></span> <span data-ttu-id="0d298-138">In diesem Beispiel wird zu diesem Zweck die `CreditCardSecurityTokenSerializer`-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d298-138">This sample uses the `CreditCardSecurityTokenSerializer` class for this purpose.</span></span>

 <span data-ttu-id="0d298-139">Im Dienst liest das benutzerdefinierte Serialisierungsprogramm die XML-Form des benutzerdefinierten Tokens und erstellt daraus die Objektdarstellung des benutzerdefinierten Tokens.</span><span class="sxs-lookup"><span data-stu-id="0d298-139">On the service, the custom serializer reads the XML form of the custom token and creates the custom token object representation from it.</span></span>

 <span data-ttu-id="0d298-140">Auf dem Client schreibt die `CreditCardSecurityTokenSerializer`-Klasse die in der Objektdarstellung des benutzerdefinierten Tokens enthaltenen Informationen in den XML-Writer.</span><span class="sxs-lookup"><span data-stu-id="0d298-140">On the client, the `CreditCardSecurityTokenSerializer` class writes the information contained in the security token object representation into the XML writer.</span></span>

```csharp
public class CreditCardSecurityTokenSerializer : WSSecurityTokenSerializer
{
    public CreditCardSecurityTokenSerializer(SecurityTokenVersion version) : base() { }

    protected override bool CanReadTokenCore(XmlReader reader)
    {
        XmlDictionaryReader localReader = XmlDictionaryReader.CreateDictionaryReader(reader);

        if (reader == null)
            throw new ArgumentNullException(nameof(reader));

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
            return true;

        return base.CanReadTokenCore(reader);
    }

    protected override SecurityToken ReadTokenCore(XmlReader reader, SecurityTokenResolver tokenResolver)
    {
        if (reader == null)
            throw new ArgumentNullException(nameof(reader));

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
        {
            string id = reader.GetAttribute(Constants.Id, Constants.WsUtilityNamespace);

            reader.ReadStartElement();

            // Read the credit card number.
            string creditCardNumber = reader.ReadElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace);

            // Read the expiration date.
            string expirationTimeString = reader.ReadElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace);
            DateTime expirationTime = XmlConvert.ToDateTime(expirationTimeString, XmlDateTimeSerializationMode.Utc);

            // Read the issuer of the credit card.
            string creditCardIssuer = reader.ReadElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace);
            reader.ReadEndElement();

            var cardInfo = new CreditCardInfo(creditCardNumber, creditCardIssuer, expirationTime);

            return new CreditCardToken(cardInfo, id);
        }
        else
        {
            return WSSecurityTokenSerializer.DefaultInstance.ReadToken(reader, tokenResolver);
        }
    }

    protected override bool CanWriteTokenCore(SecurityToken token)
    {
        if (token is CreditCardToken)
            return true;
        return base.CanWriteTokenCore(token);
    }

    protected override void WriteTokenCore(XmlWriter writer, SecurityToken token)
    {
        if (writer == null)
            throw new ArgumentNullException(nameof(writer));
        if (token == null)
            throw new ArgumentNullException(nameof(token));

        CreditCardToken c = token as CreditCardToken;
        if (c != null)
        {
            writer.WriteStartElement(Constants.CreditCardTokenPrefix, Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace);
            writer.WriteAttributeString(Constants.WsUtilityPrefix, Constants.Id, Constants.WsUtilityNamespace, token.Id);
            writer.WriteElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardNumber);
            writer.WriteElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace, XmlConvert.ToString(c.CardInfo.ExpirationDate, XmlDateTimeSerializationMode.Utc));
            writer.WriteElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardIssuer);
            writer.WriteEndElement();
            writer.Flush();
        }
        else
        {
            base.WriteTokenCore(writer, token);
        }
    }
}
```

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a><span data-ttu-id="0d298-141">So werden Tokenanbieter- und Tokenauthentifiziererklassen erstellt</span><span class="sxs-lookup"><span data-stu-id="0d298-141">How Token Provider and Token Authenticator Classes are Created</span></span>

 <span data-ttu-id="0d298-142">Client- und Dienstanmeldeinformationen sind für die Bereitstellung der Instanz des Sicherheitstoken-Managers zuständig.</span><span class="sxs-lookup"><span data-stu-id="0d298-142">Client and service credentials are responsible for providing the security token manager instance.</span></span> <span data-ttu-id="0d298-143">Die Instanz des Sicherheitstoken-Managers dient zum Abrufen von Tokenanbietern, Tokenauthentifizierern und Serialisierungsprogrammen für das Token.</span><span class="sxs-lookup"><span data-stu-id="0d298-143">The security token manager instance is used to get token providers, token authenticators and token serializers.</span></span>

 <span data-ttu-id="0d298-144">Der Tokenanbieter erstellt eine Objektdarstellung des Tokens basierend auf Daten in den Client- oder Dienstanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="0d298-144">The token provider creates an object representation of the token based on the information contained in the client or service credentials.</span></span> <span data-ttu-id="0d298-145">Anschließend wird die Objektdarstellung des Tokens mithilfe des Token-Serialisierungsprogramms (im vorigen Abschnitt erörtert) in die Nachricht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d298-145">The token object representation is then written to the message using the token serializer (discussed in the previous section).</span></span>

 <span data-ttu-id="0d298-146">Der Tokenauthentifizierer überprüft Token, die in der Nachricht ankommen.</span><span class="sxs-lookup"><span data-stu-id="0d298-146">The token authenticator validates tokens that arrive in the message.</span></span> <span data-ttu-id="0d298-147">Die Objektdarstellung der eingehenden Token wird vom Token-Serialisierungsprogramm erstellt.</span><span class="sxs-lookup"><span data-stu-id="0d298-147">The incoming token object representation is created by the token serializer.</span></span> <span data-ttu-id="0d298-148">Diese Objektdarstellung wird dann zur Validierung an den Tokenauthentifizierer übergeben.</span><span class="sxs-lookup"><span data-stu-id="0d298-148">This object representation is then passed to the token authenticator for validation.</span></span> <span data-ttu-id="0d298-149">Nach der erfolgreichen Validierung des Tokens gibt der Tokenauthentifizierer eine Auflistung der `IAuthorizationPolicy`-Objekte zurück, die die im Token enthaltenen Informationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="0d298-149">After the token is successfully validated, the token authenticator returns a collection of `IAuthorizationPolicy` objects that represent the information contained in the token.</span></span> <span data-ttu-id="0d298-150">Diese Informationen werden später während der Nachrichtenverarbeitung verwendet, um Autorisierungsentscheidungen durchzuführen und Ansprüche für die Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d298-150">This information is used later during the message processing to perform authorization decisions and to provide claims for the application.</span></span> <span data-ttu-id="0d298-151">In diesem Beispiel verwendet der Tokenauthentifizierer für Kreditkarten `CreditCardTokenAuthorizationPolicy` für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="0d298-151">In this example, the credit card token authenticator uses `CreditCardTokenAuthorizationPolicy` for this purpose.</span></span>

 <span data-ttu-id="0d298-152">Das Token-Serialisierungsprogramm ist zuständig für das Abrufen der Objektdarstellung des Tokens von der Verbindung und zum Einbinden der Darstellung in die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="0d298-152">The token serializer is responsible for getting the object representation of the token to and from the wire.</span></span> <span data-ttu-id="0d298-153">Dies wird im vorherigen Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="0d298-153">This is discussed in the previous section.</span></span>

 <span data-ttu-id="0d298-154">In diesem Beispiel wird ein Tokenanbieter nur für den Client und ein Tokenauthentifizierer nur für den Dienst verwendet, da ein Kreditkartentoken nur in der Richtung vom Client zum Dienst übertragen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d298-154">In this sample, we use a token provider only on the client and a token authenticator only on the service, because we want to transmit a credit card token only in the client-to-service direction.</span></span>

 <span data-ttu-id="0d298-155">Die Funktionalität auf dem Client befindet sich in den Klassen `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` und `CreditCardTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="0d298-155">The functionality on the client is located in the `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` and `CreditCardTokenProvider` classes.</span></span>

 <span data-ttu-id="0d298-156">Beim Dienst befindet sich die Funktionalität in den Klassen `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` und `CreditCardTokenAuthorizationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="0d298-156">On the service, the functionality resides in the `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` and `CreditCardTokenAuthorizationPolicy` classes.</span></span>

```csharp
    public class CreditCardClientCredentials : ClientCredentials
    {
        CreditCardInfo creditCardInfo;

        public CreditCardClientCredentials(CreditCardInfo creditCardInfo)
            : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException(nameof(creditCardInfo));

            this.creditCardInfo = creditCardInfo;
        }

        public CreditCardInfo CreditCardInfo
        {
            get { return this.creditCardInfo; }
        }

        protected override ClientCredentials CloneCore()
        {
            return new CreditCardClientCredentials(this.creditCardInfo);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardClientCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardClientCredentialsSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        CreditCardClientCredentials creditCardClientCredentials;

        public CreditCardClientCredentialsSecurityTokenManager(CreditCardClientCredentials creditCardClientCredentials)
            : base (creditCardClientCredentials)
        {
            this.creditCardClientCredentials = creditCardClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // Handle this token for Custom.
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
                return new CreditCardTokenProvider(this.creditCardClientCredentials.CreditCardInfo);
            // Return server cert.
            else if (tokenRequirement is InitiatorServiceModelSecurityTokenRequirement)
            {
                if (tokenRequirement.TokenType == SecurityTokenTypes.X509Certificate)
                {
                    return new X509SecurityTokenProvider(creditCardClientCredentials.ServiceCertificate.DefaultCertificate);
                }
            }

            return base.CreateSecurityTokenProvider(tokenRequirement);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {

            return new CreditCardSecurityTokenSerializer(version);
        }

    }

    class CreditCardTokenProvider : SecurityTokenProvider
    {
        CreditCardInfo creditCardInfo;

        public CreditCardTokenProvider(CreditCardInfo creditCardInfo) : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException(nameof(creditCardInfo));

            this.creditCardInfo = creditCardInfo;
        }

        protected override SecurityToken GetTokenCore(TimeSpan timeout)
        {
            SecurityToken result = new CreditCardToken(this.creditCardInfo);
            return result;
        }
    }

    public class CreditCardServiceCredentials : ServiceCredentials
    {
        string creditCardFile;

        public CreditCardServiceCredentials(string creditCardFile)
            : base()
        {
            if (creditCardFile == null)
                throw new ArgumentNullException(nameof(creditCardFile));

            this.creditCardFile = creditCardFile;
        }

        public string CreditCardDataFile
        {
            get { return this.creditCardFile; }
        }

        protected override ServiceCredentials CloneCore()
        {
            return new CreditCardServiceCredentials(this.creditCardFile);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardServiceCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardServiceCredentialsSecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        CreditCardServiceCredentials creditCardServiceCredentials;

        public CreditCardServiceCredentialsSecurityTokenManager(CreditCardServiceCredentials creditCardServiceCredentials)
            : base(creditCardServiceCredentials)
        {
            this.creditCardServiceCredentials = creditCardServiceCredentials;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
            {
                outOfBandTokenResolver = null;
                return new CreditCardTokenAuthenticator(creditCardServiceCredentials.CreditCardDataFile);
            }

            return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {
            return new CreditCardSecurityTokenSerializer(version);
        }
    }

    class CreditCardTokenAuthenticator : SecurityTokenAuthenticator
    {
        string creditCardsFile;
        public CreditCardTokenAuthenticator(string creditCardsFile)
        {
            this.creditCardsFile = creditCardsFile;
        }

        protected override bool CanValidateTokenCore(SecurityToken token)
        {
            return (token is CreditCardToken);
        }

        protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateTokenCore(SecurityToken token)
        {
            CreditCardToken creditCardToken = token as CreditCardToken;

            if (creditCardToken.CardInfo.ExpirationDate < DateTime.UtcNow)
                throw new SecurityTokenValidationException("The credit card has expired.");
            if (!IsCardNumberAndExpirationValid(creditCardToken.CardInfo))
                throw new SecurityTokenValidationException("Unknown or invalid credit card.");

            // the credit card token has only 1 claim - the card number. The issuer for the claim is the
            // credit card issuer

            var cardIssuerClaimSet = new DefaultClaimSet(new Claim(ClaimTypes.Name, creditCardToken.CardInfo.CardIssuer, Rights.PossessProperty));
            var cardClaimSet = new DefaultClaimSet(cardIssuerClaimSet, new Claim(Constants.CreditCardNumberClaim, creditCardToken.CardInfo.CardNumber, Rights.PossessProperty));
            var policies = new List<IAuthorizationPolicy>(1);
            policies.Add(new CreditCardTokenAuthorizationPolicy(cardClaimSet));
            return policies.AsReadOnly();
        }

        /// <summary>
        /// Helper method to check if a given credit card entry is present in the User DB
        /// </summary>
        private bool IsCardNumberAndExpirationValid(CreditCardInfo cardInfo)
        {
            try
            {
                using (var myStreamReader = new StreamReader(this.creditCardsFile))
                {
                    string line = "";
                    while ((line = myStreamReader.ReadLine()) != null)
                    {
                        string[] splitEntry = line.Split('#');
                        if (splitEntry[0] == cardInfo.CardNumber)
                        {
                            string expirationDateString = splitEntry[1].Trim();
                            DateTime expirationDateOnFile = DateTime.Parse(expirationDateString, System.Globalization.DateTimeFormatInfo.InvariantInfo, System.Globalization.DateTimeStyles.AdjustToUniversal);
                            if (cardInfo.ExpirationDate == expirationDateOnFile)
                            {
                                string issuer = splitEntry[2];
                                return issuer.Equals(cardInfo.CardIssuer, StringComparison.InvariantCultureIgnoreCase);
                            }
                            else
                            {
                                return false;
                            }
                        }
                    }
                    return false;
                }
            }
            catch (Exception e)
            {
                throw new Exception("BookStoreService: Error while retrieving credit card information from User DB " + e.ToString());
            }
        }
    }

    public class CreditCardTokenAuthorizationPolicy : IAuthorizationPolicy
    {
        string id;
        ClaimSet issuer;
        IEnumerable<ClaimSet> issuedClaimSets;

        public CreditCardTokenAuthorizationPolicy(ClaimSet issuedClaims)
        {
            if (issuedClaims == null)
                throw new ArgumentNullException(nameof(issuedClaims));
            this.issuer = issuedClaims.Issuer;
            this.issuedClaimSets = new ClaimSet[] { issuedClaims };
            this.id = Guid.NewGuid().ToString();
        }

        public ClaimSet Issuer { get { return this.issuer; } }

        public string Id { get { return this.id; } }

        public bool Evaluate(EvaluationContext context, ref object state)
        {
            foreach (ClaimSet issuance in this.issuedClaimSets)
            {
                context.AddClaimSet(this, issuance);
            }

            return true;
        }
    }
```

## <a name="displaying-the-callers-information"></a><span data-ttu-id="0d298-157">Anzeigen der Aufruferinformationen</span><span class="sxs-lookup"><span data-stu-id="0d298-157">Displaying the Callers' Information</span></span>

 <span data-ttu-id="0d298-158">Um die Informationen zu den Aufrufern anzuzeigen, können Sie `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` verwenden, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d298-158">To display the caller's information, use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following sample code.</span></span> <span data-ttu-id="0d298-159">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` enthält dem aktuellen Aufrufer zugeordnete Autorisierungsansprüche.</span><span class="sxs-lookup"><span data-stu-id="0d298-159">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="0d298-160">Die Ansprüche werden von der `CreditCardToken`-Klasse in der `AuthorizationPolicies`-Auflistung angegeben.</span><span class="sxs-lookup"><span data-stu-id="0d298-160">The claims are supplied by the `CreditCardToken` class in its `AuthorizationPolicies` collection.</span></span>

```csharp
bool TryGetStringClaimValue(ClaimSet claimSet, string claimType, out string claimValue)
{
    claimValue = null;
    IEnumerable<Claim> matchingClaims = claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
        return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    enumerator.MoveNext();
    claimValue = (enumerator.Current.Resource == null) ? null :
        enumerator.Current.Resource.ToString();
    return true;
}

string GetCallerCreditCardNumber()
{
     foreach (ClaimSet claimSet in
         ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)
     {
         string creditCardNumber = null;
         if (TryGetStringClaimValue(claimSet,
             Constants.CreditCardNumberClaim, out creditCardNumber))
             {
                 string issuer;
                 if (!TryGetStringClaimValue(claimSet.Issuer,
                        ClaimTypes.Name, out issuer))
                 {
                     issuer = "Unknown";
                 }
                 return $"Credit card '{creditCardNumber}' issued by '{issuer}'";
        }
    }
    return "Credit card is not known";
}
```

 <span data-ttu-id="0d298-161">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d298-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0d298-162">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0d298-162">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="0d298-163">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="0d298-163">Setup Batch File</span></span>

 <span data-ttu-id="0d298-164">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer IIS-gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="0d298-164">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run the IIS-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="0d298-165">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d298-165">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="0d298-166">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0d298-166">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="0d298-167">Erstellen des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="0d298-167">Creating the server certificate:</span></span>

     <span data-ttu-id="0d298-168">Mit den folgenden Zeilen aus der Batchdatei `Setup.bat` wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="0d298-168">The following lines from the `Setup.bat` batch file create the server certificate to be used.</span></span> <span data-ttu-id="0d298-169">Die Variable `%SERVER_NAME%` gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="0d298-169">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="0d298-170">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="0d298-170">Change this variable to specify your own server name.</span></span> <span data-ttu-id="0d298-171">Standardmäßig lautet die Variable in dieser Batchdatei localhost.</span><span class="sxs-lookup"><span data-stu-id="0d298-171">The default in this batch file is localhost.</span></span> <span data-ttu-id="0d298-172">Wenn Sie die Variable `%SERVER_NAME%` ändern, müssen Sie die Dateien Client.cs und Service.cs durchgehen und alle Vorkommnisse von localhost durch den Servernamen ersetzen, den Sie im Setup.bat-Skript verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d298-172">If you change the `%SERVER_NAME%` variable, you must go through the Client.cs and Service.cs files and replace all instances of localhost with the server name that you use in the Setup.bat script.</span></span>

     <span data-ttu-id="0d298-173">Das Zertifikat wird im persönlichen Speicher unter dem Speicherort `LocalMachine` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0d298-173">The certificate is stored in My (Personal) store under the `LocalMachine` store location.</span></span> <span data-ttu-id="0d298-174">Das Zertifikat wird für die IIS-gehosteten Dienste im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0d298-174">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="0d298-175">Für selbst gehostete Dienste sollten Sie die Batchdatei so ändern, dass das Clientzertifikat im Speicherort CurrentUser gespeichert wird. Ersetzen Sie hierzu die Zeichenfolge LocalMachine durch CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="0d298-175">For self-hosted services, you should modify the batch file to store the client certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="0d298-176">Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate:</span><span class="sxs-lookup"><span data-stu-id="0d298-176">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="0d298-177">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="0d298-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="0d298-178">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="0d298-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="0d298-179">Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d298-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```bat
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="0d298-180">Um den Zugriff vom IIS-gehosteten Dienst aus auf den privaten Schlüssel des Zertifikats zu aktivieren, müssen dem Benutzerkonto, unter dem der IIS-gehostete Prozess ausgeführt wird, entsprechende Berechtigungen für den privaten Schlüssel gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="0d298-180">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="0d298-181">Dies wird durch die letzten Schritte im Skript Setup.bat erreicht.</span><span class="sxs-lookup"><span data-stu-id="0d298-181">This is accomplished by last steps in the Setup.bat script.</span></span>

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
> <span data-ttu-id="0d298-182">Die Batchdatei Setup.bat ist für die Ausführung über eine Visual Studio 2012-Eingabeaufforderung konzipiert.</span><span class="sxs-lookup"><span data-stu-id="0d298-182">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="0d298-183">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Setup.bat Skript erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0d298-183">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="0d298-184">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="0d298-184">To set up and build the sample</span></span>

1. <span data-ttu-id="0d298-185">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0d298-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="0d298-186">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d298-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="0d298-187">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="0d298-187">To run the sample on the same computer</span></span>

1. <span data-ttu-id="0d298-188">Öffnen Sie ein Visual Studio 2012-Eingabe Aufforderungs Fenster mit Administratorrechten, und führen Sie Setup.bat aus dem Beispiel Installationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="0d298-188">Open a Visual Studio 2012 Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="0d298-189">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind. Stellen Sie sicher, dass der Pfad den Ordner enthält, in dem sich Makecert.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="0d298-189">This installs all the certificates required for running the sample.Make sure that the path includes the folder where Makecert.exe is located.</span></span>

> [!NOTE]
> <span data-ttu-id="0d298-190">Entfernen Sie nach Abschluss des Beispiels unbedingt die Zertifikate, indem Sie Cleanup.bat ausführen.</span><span class="sxs-lookup"><span data-stu-id="0d298-190">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="0d298-191">In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d298-191">Other security samples use the same certificates.</span></span>  
  
1. <span data-ttu-id="0d298-192">Starten Sie Client.exe im Verzeichnis \client\bin.</span><span class="sxs-lookup"><span data-stu-id="0d298-192">Launch Client.exe from client\bin directory.</span></span> <span data-ttu-id="0d298-193">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d298-193">Client activity is displayed on the client console application.</span></span>  
  
2. <span data-ttu-id="0d298-194">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0d298-194">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computer"></a><span data-ttu-id="0d298-195">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="0d298-195">To run the sample across computer</span></span>  
  
1. <span data-ttu-id="0d298-196">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="0d298-196">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="0d298-197">Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="0d298-197">Copy the service program files into the service directory on the service computer.</span></span> <span data-ttu-id="0d298-198">Vergessen Sie nicht, die Datei CreditCardFile.txt zu kopieren. Andernfalls kann der Kreditkartenauthentifikator die vom Client gesendeten Kreditkartendaten nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0d298-198">Do not forget to copy CreditCardFile.txt; otherwise the credit card authenticator cannot validate credit card information sent from the client.</span></span> <span data-ttu-id="0d298-199">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="0d298-199">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="0d298-200">Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält.</span><span class="sxs-lookup"><span data-stu-id="0d298-200">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="0d298-201">Ein entsprechendes Zertifikat können Sie mithilfe von Setup.bat erstellen, indem Sie die Variable `%SERVER_NAME%` auf den vollqualifizierten Namen des Computers festlegen, auf dem der Dienst gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0d298-201">You can create one using the Setup.bat if you change the `%SERVER_NAME%` variable to fully-qualified name of the computer where the service is hosted.</span></span> <span data-ttu-id="0d298-202">Beachten Sie, dass die Setup.bat Datei in einem Developer-Eingabeaufforderung für Visual Studio ausgeführt werden muss, das mit Administratorrechten geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="0d298-202">Note that the Setup.bat file must be run in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>  
  
4. <span data-ttu-id="0d298-203">Kopieren Sie das Serverzertifikat in den Speicher CurrentUser-TrustedPeople auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="0d298-203">Copy the server certificate into the CurrentUser-TrustedPeople store on the client.</span></span> <span data-ttu-id="0d298-204">Sie müssen dies nur tun, wenn das Serverzertifikat nicht von einem vertrauenswürdigen Aussteller ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0d298-204">You must do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5. <span data-ttu-id="0d298-205">Ändern Sie in der Datei EchoServiceHost.cs den Wert des Zertifikatsantragstellers, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="0d298-205">In the EchoServiceHost.cs file, change the value of the certificate subject name to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="0d298-206">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="0d298-206">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
7. <span data-ttu-id="0d298-207">Ändern Sie in der Datei Client.cs den Adresswert des Endpunkts, sodass dieser mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="0d298-207">In the Client.cs file, change the address value of the endpoint to match the new address of your service.</span></span>  
  
8. <span data-ttu-id="0d298-208">Ändern Sie in der Datei Client.cs den Antragstellernamen des X.509-Dienstzertifikats, und geben Sie anstelle von localhost den vollqualifizierten Computernamen des Remotehosts an.</span><span class="sxs-lookup"><span data-stu-id="0d298-208">In the Client.cs file change the subject name of the service X.509 certificate to match the fully-qualified computer name of the remote host instead of localhost.</span></span>  
  
9. <span data-ttu-id="0d298-209">Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="0d298-209">On the client computer, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="0d298-210">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="0d298-210">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="0d298-211">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="0d298-211">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="0d298-212">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0d298-212">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>
