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
# <a name="custom-token"></a>Benutzerdefiniertes Token

In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte tokenimplementierung einer Windows Communication Foundation (WCF)-Anwendung hinzugefügt wird. Im Beispiel wird ein `CreditCardToken` verwendet, um Informationen über Clientkreditkarten sicher an den Dienst zu übergeben. Das Token wird an den WS-Sicherheits-Nachrichtenkopf übergeben und zusammen mit Nachrichtentext und anderen Nachrichtenköpfen mithilfe des symmetrischen Sicherheitsbindungselements signiert und verschlüsselt. Dies ist in Fällen nützlich, in denen die integrierten Token nicht ausreichen. In diesem Beispiel wird veranschaulicht, wie anstelle eines der integrierten Token ein benutzerdefiniertes Sicherheitstoken für einen Dienst bereitgestellt werden kann. Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

 Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:

- Wie ein Client ein benutzerdefiniertes Sicherheitstoken an einen Dienst übergeben kann.

- Wie der Dienst ein benutzerdefiniertes Sicherheitstoken verwenden und überprüfen kann.

- Gibt an, wie der WCF-Dienst Code die Informationen über empfangene Sicherheits Token, einschließlich des benutzerdefinierten Sicherheits Tokens, abrufen kann.

- Wie das X.509-Zertifikat des Servers dazu verwendet wird, den zur Nachrichtenverschlüsselung und für die Signatur verwendeten symmetrischen Schlüssel zu schützen.

## <a name="client-authentication-using-a-custom-security-token"></a>Sicherheitsauthentifizierung mithilfe eines benutzerdefinierten Sicherheitstokens

 Der Dienst macht einen einzelnen Endpunkt verfügbar, der programmgesteuert mithilfe der `BindingHelper`-Klasse und der `EchoServiceHost`-Klasse erstellt wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einer benutzerdefinierten Bindung unter Verwendung von `SymmetricSecurityBindingElement` und `HttpTransportBindingElement` konfiguriert. In diesem Beispiel wird `SymmetricSecurityBindingElement` so eingestellt, dass es ein X.509-Zertifikat für den Dienst verwendet, um den symmetrischen Schlüssel während der Übertragung zu schützen und um in einem WS-Sicherheits-Nachrichtenkopf ein benutzerdefiniertes `CreditCardToken` als signiertes und verschlüsseltes Sicherheitstoken zu übergeben. Das Verhalten legt die Dienstanmeldeinformationen fest, die zur Clientauthentifizierung verwendet werden sollen, sowie Informationen über das X.509-Zertifikat des Diensts.

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

 Um ein Kreditkartentoken in der Nachricht zu nutzen, werden im Beispiel benutzerdefinierte Dienstanmeldeinformationen verwendet, um diese Funktion anzugeben. Die Dienstanmeldeinformationsklasse befindet sich in der Klasse `CreditCardServiceCredentials` und wird zu den Verhaltensauflistungen des Diensthosts in der `EchoServiceHost.InitializeRuntime`-Methode hinzugefügt.

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

 Der Clientendpunkt wird auf ähnliche Weise wie der Dienstendpunkt konfiguriert. Der Client verwendet die gleiche `BindingHelper`-Klasse, um eine Bindung zu erstellen. Der Rest des Setups befindet sich in der `Client`-Klasse. Der Client legt außerdem Informationen, die im `CreditCardToken` enthalten sein sollen, sowie Informationen zum X.509-Zertifikat des Diensts im Setupcode fest, indem eine `CreditCardClientCredentials`-Instanz mit den entsprechenden Daten zur Auflistung der Clientendpunktverhaltensweisen hinzugefügt wird. Im Beispiel wird das X.509-Zertifikat mit dem Antragstellernamen `CN=localhost` als Dienstzertifikat verwendet.

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

## <a name="custom-security-token-implementation"></a>Implementierung des benutzerdefinierten Sicherheitstokens

 Wenn Sie ein benutzerdefiniertes Sicherheits Token in WCF aktivieren möchten, erstellen Sie eine Objektdarstellung des benutzerdefinierten Sicherheits Tokens. Das Beispiel enthält diese Darstellung in der `CreditCardToken`-Klasse. Die Objektdarstellung dient zur Aufnahme aller relevanten Informationen zu Sicherheitstoken und zur Bereitstellung einer Liste der im Sicherheitstoken enthaltenen Sicherheitsschlüssel. In diesem Fall enthält das Sicherheitstoken der Kreditkarte keinen Sicherheitsschlüssel.

 Im nächsten Abschnitt wird beschrieben, was durchgeführt werden muss, damit ein benutzerdefiniertes Token über das Netzwerk übertragen und von einem WCF-Endpunkt genutzt werden kann.

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

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a>Abrufen des benutzerdefinierte Kreditkartentokens aus der Nachricht und Einbinden des Tokens in die Nachricht

 Sicherheitstokenserialisierer in WCF sind dafür verantwortlich, eine Objektdarstellung von Sicherheits Token aus dem XML-Code in der Nachricht zu erstellen und ein XML-Formular der Sicherheits Token zu erstellen. Außerdem sind sie für andere Funktionen zuständig, wie beispielsweise das Lesen und Schreiben von Schlüsselbezeichnern, die auf Sicherheitstoken verweisen. In diesem Beispiel werden jedoch nur die Funktionen behandelt, die sich auf Sicherheitstoken beziehen. Um ein benutzerdefiniertes Token zu aktivieren, müssen Sie ein eigenes Sicherheitstoken-Serialisierungsprogramm implementieren. In diesem Beispiel wird zu diesem Zweck die `CreditCardSecurityTokenSerializer`-Klasse verwendet.

 Im Dienst liest das benutzerdefinierte Serialisierungsprogramm die XML-Form des benutzerdefinierten Tokens und erstellt daraus die Objektdarstellung des benutzerdefinierten Tokens.

 Auf dem Client schreibt die `CreditCardSecurityTokenSerializer`-Klasse die in der Objektdarstellung des benutzerdefinierten Tokens enthaltenen Informationen in den XML-Writer.

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

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a>So werden Tokenanbieter- und Tokenauthentifiziererklassen erstellt

 Client- und Dienstanmeldeinformationen sind für die Bereitstellung der Instanz des Sicherheitstoken-Managers zuständig. Die Instanz des Sicherheitstoken-Managers dient zum Abrufen von Tokenanbietern, Tokenauthentifizierern und Serialisierungsprogrammen für das Token.

 Der Tokenanbieter erstellt eine Objektdarstellung des Tokens basierend auf Daten in den Client- oder Dienstanmeldeinformationen. Anschließend wird die Objektdarstellung des Tokens mithilfe des Token-Serialisierungsprogramms (im vorigen Abschnitt erörtert) in die Nachricht geschrieben.

 Der Tokenauthentifizierer überprüft Token, die in der Nachricht ankommen. Die Objektdarstellung der eingehenden Token wird vom Token-Serialisierungsprogramm erstellt. Diese Objektdarstellung wird dann zur Validierung an den Tokenauthentifizierer übergeben. Nach der erfolgreichen Validierung des Tokens gibt der Tokenauthentifizierer eine Auflistung der `IAuthorizationPolicy`-Objekte zurück, die die im Token enthaltenen Informationen darstellen. Diese Informationen werden später während der Nachrichtenverarbeitung verwendet, um Autorisierungsentscheidungen durchzuführen und Ansprüche für die Anwendung bereitzustellen. In diesem Beispiel verwendet der Tokenauthentifizierer für Kreditkarten `CreditCardTokenAuthorizationPolicy` für diesen Zweck.

 Das Token-Serialisierungsprogramm ist zuständig für das Abrufen der Objektdarstellung des Tokens von der Verbindung und zum Einbinden der Darstellung in die Verbindung. Dies wird im vorherigen Abschnitt erläutert.

 In diesem Beispiel wird ein Tokenanbieter nur für den Client und ein Tokenauthentifizierer nur für den Dienst verwendet, da ein Kreditkartentoken nur in der Richtung vom Client zum Dienst übertragen werden soll.

 Die Funktionalität auf dem Client befindet sich in den Klassen `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` und `CreditCardTokenProvider`.

 Beim Dienst befindet sich die Funktionalität in den Klassen `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` und `CreditCardTokenAuthorizationPolicy`.

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

## <a name="displaying-the-callers-information"></a>Anzeigen der Aufruferinformationen

 Um die Informationen zu den Aufrufern anzuzeigen, können Sie `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` verwenden, wie im folgenden Beispielcode gezeigt. `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` enthält dem aktuellen Aufrufer zugeordnete Autorisierungsansprüche. Die Ansprüche werden von der `CreditCardToken`-Klasse in der `AuthorizationPolicies`-Auflistung angegeben.

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

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

## <a name="setup-batch-file"></a>Setupbatchdatei

 Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer IIS-gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.

 Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.

- Erstellen des Serverzertifikats

     Mit den folgenden Zeilen aus der Batchdatei `Setup.bat` wird das zu verwendende Serverzertifikat erstellt. Die Variable `%SERVER_NAME%` gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. Standardmäßig lautet die Variable in dieser Batchdatei localhost. Wenn Sie die Variable `%SERVER_NAME%` ändern, müssen Sie die Dateien Client.cs und Service.cs durchgehen und alle Vorkommnisse von localhost durch den Servernamen ersetzen, den Sie im Setup.bat-Skript verwenden.

     Das Zertifikat wird im persönlichen Speicher unter dem Speicherort `LocalMachine` gespeichert. Das Zertifikat wird für die IIS-gehosteten Dienste im LocalMachine-Speicher gespeichert. Für selbst gehostete Dienste sollten Sie die Batchdatei so ändern, dass das Clientzertifikat im Speicherort CurrentUser gespeichert wird. Ersetzen Sie hierzu die Zeichenfolge LocalMachine durch CurrentUser.

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate:

     Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.

    ```bat
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Um den Zugriff vom IIS-gehosteten Dienst aus auf den privaten Schlüssel des Zertifikats zu aktivieren, müssen dem Benutzerkonto, unter dem der IIS-gehostete Prozess ausgeführt wird, entsprechende Berechtigungen für den privaten Schlüssel gewährt werden. Dies wird durch die letzten Schritte im Skript Setup.bat erreicht.

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
> Die Batchdatei Setup.bat ist für die Ausführung über eine Visual Studio 2012-Eingabeaufforderung konzipiert. Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Setup.bat Skript erforderlich sind.

#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

#### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus

1. Öffnen Sie ein Visual Studio 2012-Eingabe Aufforderungs Fenster mit Administratorrechten, und führen Sie Setup.bat aus dem Beispiel Installationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind. Stellen Sie sicher, dass der Pfad den Ordner enthält, in dem sich Makecert.exe befindet.

> [!NOTE]
> Entfernen Sie nach Abschluss des Beispiels unbedingt die Zertifikate, indem Sie Cleanup.bat ausführen. In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
1. Starten Sie Client.exe im Verzeichnis \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
2. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-run-the-sample-across-computer"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.  
  
2. Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer. Vergessen Sie nicht, die Datei CreditCardFile.txt zu kopieren. Andernfalls kann der Kreditkartenauthentifikator die vom Client gesendeten Kreditkartendaten nicht überprüfen. Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.  
  
3. Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält. Ein entsprechendes Zertifikat können Sie mithilfe von Setup.bat erstellen, indem Sie die Variable `%SERVER_NAME%` auf den vollqualifizierten Namen des Computers festlegen, auf dem der Dienst gehostet wird. Beachten Sie, dass die Setup.bat Datei in einem Developer-Eingabeaufforderung für Visual Studio ausgeführt werden muss, das mit Administratorrechten geöffnet ist.  
  
4. Kopieren Sie das Serverzertifikat in den Speicher CurrentUser-TrustedPeople auf dem Client. Sie müssen dies nur tun, wenn das Serverzertifikat nicht von einem vertrauenswürdigen Aussteller ausgegeben wurde.  
  
5. Ändern Sie in der Datei EchoServiceHost.cs den Wert des Zertifikatsantragstellers, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.  
  
6. Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
7. Ändern Sie in der Datei Client.cs den Adresswert des Endpunkts, sodass dieser mit der neuen Adresse Ihres Diensts übereinstimmt.  
  
8. Ändern Sie in der Datei Client.cs den Antragstellernamen des X.509-Dienstzertifikats, und geben Sie anstelle von localhost den vollqualifizierten Computernamen des Remotehosts an.  
  
9. Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.  
  
10. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1. Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.
