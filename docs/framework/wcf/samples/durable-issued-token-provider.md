---
title: Dauerhaft ausgestellter Tokenanbieter
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: 7e0025eb4bc4918b977d9d8c4e2b1435b0425973
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96291673"
---
# <a name="durable-issued-token-provider"></a><span data-ttu-id="bb4e2-102">Dauerhaft ausgestellter Tokenanbieter</span><span class="sxs-lookup"><span data-stu-id="bb4e2-102">Durable Issued Token Provider</span></span>

<span data-ttu-id="bb4e2-103">Dieses Beispiel veranschaulicht das Implementieren eines Tokenanbieters, der von einem benutzerdefinierten Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-103">This sample demonstrates how to implement a custom client issued token provider.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="bb4e2-104">Diskussion</span><span class="sxs-lookup"><span data-stu-id="bb4e2-104">Discussion</span></span>  

 <span data-ttu-id="bb4e2-105">Ein Tokenanbieter in Windows Communication Foundation (WCF) wird verwendet, um Anmelde Informationen für die Sicherheitsinfrastruktur bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-105">A token provider in Windows Communication Foundation (WCF) is used to supply credentials to the security infrastructure.</span></span> <span data-ttu-id="bb4e2-106">Der Tokenanbieter untersucht im Allgemeinen das Ziel und gibt die entsprechenden Anmeldeinformationen aus, sodass die Sicherheitsinfrastruktur die Nachricht sichern kann.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-106">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="bb4e2-107">WCF ist mit einem CardSpace-Tokenanbieter ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-107">WCF ships with a CardSpace token provider.</span></span> <span data-ttu-id="bb4e2-108">Benutzerdefinierte Tokenanbieter sind in den folgenden Fällen nützlich:</span><span class="sxs-lookup"><span data-stu-id="bb4e2-108">Custom token providers are useful in the following cases:</span></span>  
  
- <span data-ttu-id="bb4e2-109">Wenn Sie einen Speicher für Anmeldeinformationen verwenden, mit dem der integrierte Tokenanbieter nicht umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-109">If you have a credential store that the built-in token provider cannot operate with.</span></span>  
  
- <span data-ttu-id="bb4e2-110">Wenn Sie einen eigenen benutzerdefinierten Mechanismus zum Transformieren der Anmelde Informationen von dem Punkt bereitstellen möchten, an dem der Benutzer die Details bereitstellt, wenn der WCF-Client die Anmelde Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client uses the credentials.</span></span>  
  
- <span data-ttu-id="bb4e2-111">Wenn Sie ein benutzerdefiniertes Token erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-111">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="bb4e2-112">Dieses Beispiel veranschaulicht die Erstellung eines benutzerdefinierten Tokenanbieters, der von einem Sicherheitstokendienst (STS, Security Token Service) ausgestellte Token zwischenspeichert.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-112">This sample shows how to build a custom token provider that caches tokens issued by a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="bb4e2-113">Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="bb4e2-113">To summarize, this sample demonstrates the following:</span></span>  
  
- <span data-ttu-id="bb4e2-114">Wie ein Client mit einem benutzerdefinierten Tokenanbieter konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-114">How a client can be configured with a custom token provider.</span></span>  
  
- <span data-ttu-id="bb4e2-115">Gibt an, wie ausgestellte Token zwischengespeichert und dem WCF-Client bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-115">How issued tokens can be cached and provided to the WCF client.</span></span>  
  
- <span data-ttu-id="bb4e2-116">Wie der Server über das X.509-Zertifikat des Servers vom Client authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-116">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="bb4e2-117">Das Beispiel besteht aus einem Clientkonsolenprogramm (Client.exe), einem Konsolenprogramm für den Sicherheitstokendienst (Securitytokenservice.exe) und einem Dienstkonsolenprogramm (Service.exe).</span><span class="sxs-lookup"><span data-stu-id="bb4e2-117">This sample consists of a client console program (Client.exe), a security token service console program (Securitytokenservice.exe) and a service console program (Service.exe).</span></span> <span data-ttu-id="bb4e2-118">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-118">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="bb4e2-119">Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-119">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="bb4e2-120">Der Client empfängt ein Sicherheitstoken vom STS und fordert beim Dienst asynchron einen bestimmten mathematischen Vorgang an. Der Dienst antwortet mit dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-120">The client gets a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation and the service replies with the result.</span></span> <span data-ttu-id="bb4e2-121">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-121">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb4e2-122">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-122">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="bb4e2-123">In diesem Beispiel wird der ICalculator-Vertrag mithilfe von verfügbar gemacht [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="bb4e2-123">This sample exposes the ICalculator contract using the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="bb4e2-124">Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-124">The configuration of this binding on the client is shown in the following code.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuer address="http://localhost:8000/sts/windows"
                  binding="wsHttpBinding" />
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="bb4e2-125">Im `security`-Element von `wsFederationHttpBinding` konfiguriert der `mode`-Wert, welcher Sicherheitsmodus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-125">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="bb4e2-126">In diesem Beispiel wird die Nachrichtensicherheit verwendet. Daher wird das `message`-Element von `wsFederationHttpBinding` im `security`-Element von `wsFederationHttpBinding` angegeben.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-126">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="bb4e2-127">Das `issuer`-Element von `wsFederationHttpBinding` im `message`-Element von `wsFederationHttpBinding` gibt die Adresse und die Bindung für den Sicherheitstokendienst an, der ein Sicherheitstoken an den Client ausgibt, damit der Client beim Rechnerdienst authentifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-127">The `issuer` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and binding for the Security Token Service that issues a security token to the client so that the client can authenticate to the Calculator service.</span></span>  
  
 <span data-ttu-id="bb4e2-128">Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-128">The configuration of this binding on the service is shown in the following code.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuerMetadata address="http://localhost:8000/sts/mex">
            <identity>
              <certificateReference storeLocation="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType="FindBySubjectDistinguishedName"
                                    findValue="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 <span data-ttu-id="bb4e2-129">Im `security`-Element von `wsFederationHttpBinding` konfiguriert der `mode`-Wert, welcher Sicherheitsmodus verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-129">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="bb4e2-130">In diesem Beispiel wird die Nachrichtensicherheit verwendet. Daher wird das `message`-Element von `wsFederationHttpBinding` im `security`-Element von `wsFederationHttpBinding` angegeben.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-130">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="bb4e2-131">Das `issuerMetadata`-Element von `wsFederationHttpBinding` im `message`-Element von `wsFederationHttpBinding` gibt die Adresse und Identität für einen Endpunkt an, mit dem Metadaten für den Sicherheitstokendienst abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-131">The `issuerMetadata` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and identity for an endpoint that can be used to retrieve metadata for the Security Token Service.</span></span>  
  
 <span data-ttu-id="bb4e2-132">Das Verhalten für den Dienst wird im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-132">The behavior for the service is shown in the following code.</span></span>  
  
```xml  
<behavior name="ServiceBehavior">
  <serviceDebug includeExceptionDetailInFaults="true" />
  <serviceMetadata httpGetEnabled="true" />
  <serviceCredentials>
    <issuedTokenAuthentication>
      <knownCertificates>
        <add storeLocation="LocalMachine"
              storeName="TrustedPeople"
              x509FindType="FindBySubjectDistinguishedName"
              findValue="CN=STS" />
      </knownCertificates>
    </issuedTokenAuthentication>
    <serviceCertificate storeLocation="LocalMachine"
                        storeName="My"
                        x509FindType="FindBySubjectDistinguishedName"
                        findValue="CN=localhost" />
  </serviceCredentials>
</behavior>  
```  
  
 <span data-ttu-id="bb4e2-133">Mit dem `issuedTokenAuthentication`-Element im `serviceCredentials`-Element kann der Dienst Einschränkungen für die Token angeben, die Clients bei der Authentifizierung angeben dürfen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-133">The `issuedTokenAuthentication` element inside the `serviceCredentials` element allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="bb4e2-134">In dieser Konfiguration wird angegeben, dass von einem Zertifikat mit dem Ausstellernamen CN=STS signierte Token vom Dienst akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-134">This configuration specifies that tokens signed by a certificate whose Subject Name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="bb4e2-135">Der Sicherheitstokendienst (STS, Security Token Service) macht mit Standard-wsHttpBinding einen einzelnen Endpunkt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-135">The Security Token Service exposes a single endpoint using the standard wsHttpBinding.</span></span> <span data-ttu-id="bb4e2-136">Der STS reagiert auf eine Tokenanforderung von Clients. Wenn der Client mit einem Windows-Konto authentifiziert wird, gibt der STS ein Token mit dem Benutzernamen des Clients als Anspruch im herausgegebenen Token heraus.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-136">The Security Token Service responds to request from clients for tokens and, provided the client authenticates using a Windows account, issues a token that contains the client's user name as a claim in the issued token.</span></span> <span data-ttu-id="bb4e2-137">Beim Erstellen des Tokens signiert der STS das Token mit dem privaten Schlüssel, der dem CN=STS-Zertifikat zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-137">As part of creating the token, the Security Token Service signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="bb4e2-138">Außerdem wird ein symmetrischer Schlüssel erstellt und mit dem öffentlichen Schlüssel verschlüsselt, der dem CN=localhost-Zertifikat zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-138">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="bb4e2-139">Beim Zurückgeben des Tokens an den Client gibt der STS auch den symmetrischen Schlüssel zurück.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-139">In returning the token to the client, the Security Token Service also returns the symmetric key.</span></span> <span data-ttu-id="bb4e2-140">Der Client stellt das herausgegebene Token für den Rechnerdienst bereit und beweist, dass der symmetrische Schlüssel bekannt ist, indem die Nachricht mit diesem Schlüssel signiert wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-140">The client presents the issued token to the Calculator service, and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
## <a name="custom-client-credentials-and-token-provider"></a><span data-ttu-id="bb4e2-141">Benutzerdefinierte Clientanmeldeinformationen und Tokenanbieter</span><span class="sxs-lookup"><span data-stu-id="bb4e2-141">Custom Client Credentials and Token Provider</span></span>  

 <span data-ttu-id="bb4e2-142">Die folgenden Schritte zeigen, wie Sie einen benutzerdefinierten Tokenanbieter entwickeln, der ausgestellte Token zwischenspeichert und in WCF: Security integriert.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-142">The following steps show how to develop a custom token provider that caches issued tokens and integrate it with WCF: security.</span></span>  
  
### <a name="to-develop-a-custom-token-provider"></a><span data-ttu-id="bb4e2-143">So entwickeln Sie einen benutzerdefinierten Tokenanbieter</span><span class="sxs-lookup"><span data-stu-id="bb4e2-143">To develop a custom token provider</span></span>  
  
1. <span data-ttu-id="bb4e2-144">Schreiben Sie einen benutzerdefinierten Tokenanbieter.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-144">Write a custom token provider.</span></span>  
  
     <span data-ttu-id="bb4e2-145">Das Beispiel implementiert einen benutzerdefinierten Tokenanbieter, der ein Sicherheitstoken zurückgibt, das aus dem Cache abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-145">The sample implements a custom token provider that returns a security token retrieved from a cache.</span></span>  
  
     <span data-ttu-id="bb4e2-146">Zur Ausführung dieser Aufgabe leitet der benutzerdefinierte Tokenanbieter die <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse ab und überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-146">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="bb4e2-147">Bei dieser Methode wird versucht, ein Token aus dem Cache abzurufen. Wenn im Cache kein Token gefunden wird, wird ein Token vom zugrunde liegenden Anbieter abgerufen und anschließend im Cache gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-147">This method tries to get a token from the cache, or if a token cannot be found in the cache, retrieves a token from the underlying provider and then caches that token.</span></span> <span data-ttu-id="bb4e2-148">In diesem Fall gibt die Methode ein `SecurityToken` zurück.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-148">In both cases the method returns a `SecurityToken`.</span></span>  
  
    ```csharp  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
      GenericXmlSecurityToken token;  
      if (!this.cache.TryGetToken(target, issuer, out token))  
      {  
        token = (GenericXmlSecurityToken) this.innerTokenProvider.GetToken(timeout);  
        this.cache.AddToken(token, target, issuer);  
      }  
      return token;  
    }  
    ```  
  
2. <span data-ttu-id="bb4e2-149">Schreiben Sie den benutzerdefiniertem Sicherheitstoken-Manager.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-149">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="bb4e2-150">Der <xref:System.IdentityModel.Selectors.SecurityTokenManager> wird zur Erstellung von einem <xref:System.IdentityModel.Selectors.SecurityTokenProvider> für eine bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> verwendet, die in der `CreateSecurityTokenProvider`-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-150">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for a specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in the `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="bb4e2-151">Der Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenauthentifizierern und Token-Serialisierungsprogrammen. Diese Vorgänge werden jedoch in diesem Beispiel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-151">Security token manager is also used to create token authenticators and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="bb4e2-152">In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> und setzt die Methode `CreateSecurityTokenProvider` außer Kraft, um den benutzerdefinierten Tokenanbieter zurückzugeben, wenn die übergebenen Tokenanforderungen angeben, dass ein ausgestelltes Token angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-152">In this sample, the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom token provider when the passed token requirements indicate that an issued token is requested.</span></span>  
  
    ```csharp
    class DurableIssuedTokenClientCredentialsTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentialsTokenManager ( DurableIssuedTokenClientCredentials creds ): base(creds)  
      {  
        this.cache = creds.IssuedTokenCache;  
      }  
  
      public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
      {  
        if (IsIssuedSecurityTokenRequirement(tokenRequirement))  
        {  
          return new DurableIssuedSecurityTokenProvider ((IssuedSecurityTokenProvider)base.CreateSecurityTokenProvider( tokenRequirement), this.cache);  
        }  
        else
        {  
          return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
      }  
    }  
    ```  
  
3. <span data-ttu-id="bb4e2-153">Schreiben Sie benutzerdefinierte Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-153">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="bb4e2-154">Eine Klasse der Clientanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Clientproxy konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-154">A client credentials class is used to represent the credentials that are configured for the client proxy and creates the security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>  
  
    ```csharp
    public class DurableIssuedTokenClientCredentials : ClientCredentials  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentials() : base()  
      {  
      }  
  
      DurableIssuedTokenClientCredentials ( DurableIssuedTokenClientCredentials other) : base(other)  
      {  
        this.cache = other.cache;  
      }  
  
      public IssuedTokenCache IssuedTokenCache  
      {  
        get  
        {  
          return this.cache;  
        }  
        set  
        {  
          this.cache = value;  
        }  
      }  
  
      protected override ClientCredentials CloneCore()  
      {  
        return new DurableIssuedTokenClientCredentials(this);  
      }  
  
      public override SecurityTokenManager CreateSecurityTokenManager()  
      {  
        return new DurableIssuedTokenClientCredentialsTokenManager ((DurableIssuedTokenClientCredentials)this.Clone());  
      }  
    }  
    ```  
  
4. <span data-ttu-id="bb4e2-155">Implementieren Sie den Tokencache.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-155">Implement the token cache.</span></span> <span data-ttu-id="bb4e2-156">Die Beispielimplementierung verwendet eine abstrakte Basisklasse, über die Consumer eines bestimmten Tokencaches mit dem Cache interagieren.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-156">The sample implementation uses an abstract base class through which consumers of a given token cache interact with the cache.</span></span>  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     <span data-ttu-id="bb4e2-157">Im Beispiel wird die Standardklasse für die Clientanmeldeinformationen gelöscht und die neue Klasse für Clientanmeldeinformationen angegeben, sodass der Client die benutzerdefinierten Clientanmeldeinformationen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-157">For the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a><span data-ttu-id="bb4e2-158">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="bb4e2-158">Running the sample</span></span>  

 <span data-ttu-id="bb4e2-159">In den folgenden Anweisungen finden Sie Informationen zum Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-159">See the following instructions to run the sample.</span></span> <span data-ttu-id="bb4e2-160">Wenn Sie das Beispiel ausführen, wird die Anforderung des Sicherheitstokens im STS-Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-160">When you run the sample, the request for the security token is shown in the Security Token Service console window.</span></span> <span data-ttu-id="bb4e2-161">Die Anforderungen und Antworten des Vorgangs werden im Client- und Dienstkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-161">The operation requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="bb4e2-162">Drücken Sie die EINGABETASTE in einem der Konsolenfenster, um die Anwendung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-162">Press ENTER in any of the console windows to shut down the application.</span></span>  
  
## <a name="the-setupcmd-batch-file"></a><span data-ttu-id="bb4e2-163">Die Batchdatei Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="bb4e2-163">The Setup.cmd Batch File</span></span>  

 <span data-ttu-id="bb4e2-164">Mit der in diesem Beispiel enthaltenen Batchdatei "Setup.cmd" können Sie den Server und den STS mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-164">The Setup.cmd batch file included with this sample allows you to configure the server and security token service with relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="bb4e2-165">Die Batchdatei erstellt zwei Zertifikate im Zertifikatspeicher CurrentUser/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-165">The batch file creates two certificates both in the CurrentUser/TrustedPeople certificate store.</span></span> <span data-ttu-id="bb4e2-166">Der Antragstellername des ersten Zertifikats lautet CN=STS und wird vom STS zum Signieren des Sicherheitstokens verwendet, das an den Client herausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-166">The first certificate has a subject name of CN=STS and is used by the Security Token Service to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="bb4e2-167">Der Antragstellername des zweiten Zertifikats lautet CN=localhost und wird vom STS zum Verschlüsseln eines Geheimnisses verwendet, das dann vom Dienst entschlüsselt werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-167">The second certificate has a subject name of CN=localhost and is used by the Security Token Service to encrypt a secret so that the service can decrypt it.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bb4e2-168">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="bb4e2-168">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bb4e2-169">Führen Sie die Datei "Setup.cmd" aus, um die erforderlichen Zertifikate zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-169">Run the Setup.cmd file to create the required certificates.</span></span>  
  
2. <span data-ttu-id="bb4e2-170">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span> <span data-ttu-id="bb4e2-171">Stellen Sie sicher, dass alle Projekte in der Projektmappe erstellt werden (Shared, RSTRSTR, Service, SecurityTokenService und Client).</span><span class="sxs-lookup"><span data-stu-id="bb4e2-171">Ensure that all the projects in the solution are built (Shared, RSTRSTR, Service, SecurityTokenService, and Client).</span></span>  
  
3. <span data-ttu-id="bb4e2-172">Stellen Sie sicher, dass Service.exe und SecurityTokenService.exe mit Administratorrechten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-172">Ensure that Service.exe and SecurityTokenService.exe are both running with administrator privileges.</span></span>  
  
4. <span data-ttu-id="bb4e2-173">Führen Sie Client.exe aus.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-173">Run Client.exe.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="bb4e2-174">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="bb4e2-174">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="bb4e2-175">Führen Sie "Cleanup.cmd" im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-175">Run Cleanup.cmd in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bb4e2-176">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-176">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bb4e2-177">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-177">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bb4e2-178">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb4e2-178">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bb4e2-179">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bb4e2-179">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
