---
title: SAML-Tokenanbieter
ms.date: 03/30/2017
ms.assetid: eb16e5e2-4c8d-4f61-a479-9c965fcec80c
ms.openlocfilehash: db1307b0f440f8bd55f1728b6645aec706dfe442
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602413"
---
# <a name="saml-token-provider"></a><span data-ttu-id="8acbf-102">SAML-Tokenanbieter</span><span class="sxs-lookup"><span data-stu-id="8acbf-102">SAML Token Provider</span></span>
<span data-ttu-id="8acbf-103">Dieses Beispiel veranschaulicht das Implementieren eines benutzerdefinierten Client-SAML-Tokenanbieters.</span><span class="sxs-lookup"><span data-stu-id="8acbf-103">This sample demonstrates how to implement a custom client SAML token provider.</span></span> <span data-ttu-id="8acbf-104">Ein Tokenanbieter in Windows Communication Foundation (WCF) wird zum Bereitstellen von Anmelde Informationen für die Sicherheitsinfrastruktur verwendet.</span><span class="sxs-lookup"><span data-stu-id="8acbf-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="8acbf-105">Der Tokenanbieter untersucht im Allgemeinen das Ziel und gibt die entsprechenden Anmeldeinformationen aus, sodass die Sicherheitsinfrastruktur die Nachricht sichern kann.</span><span class="sxs-lookup"><span data-stu-id="8acbf-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="8acbf-106">WCF wird mit dem standardmäßigen Anmelde Informations Manager-Tokenanbieter ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="8acbf-107">WCF ist auch mit einem CardSpace-Tokenanbieter ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-107">WCF also ships with a CardSpace token provider.</span></span> <span data-ttu-id="8acbf-108">Benutzerdefinierte Tokenanbieter sind in den folgenden Fällen nützlich:</span><span class="sxs-lookup"><span data-stu-id="8acbf-108">Custom token providers are useful in the following cases:</span></span>

- <span data-ttu-id="8acbf-109">Wenn Sie einen Speicher für Anmeldeinformationen verwenden, mit dem diese Tokenanbieter nicht umgehen können.</span><span class="sxs-lookup"><span data-stu-id="8acbf-109">If you have a credential store that these token providers cannot operate with.</span></span>

- <span data-ttu-id="8acbf-110">Wenn Sie einen eigenen benutzerdefinierten Mechanismus zum Transformieren der Anmelde Informationen von dem Punkt bereitstellen möchten, an dem der Benutzer die Details bereitstellt, wenn das WCF-Client Framework die Anmelde Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8acbf-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>

- <span data-ttu-id="8acbf-111">Wenn Sie ein benutzerdefiniertes Token erstellen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-111">If you are building a custom token.</span></span>

 <span data-ttu-id="8acbf-112">Dieses Beispiel zeigt, wie Sie einen benutzerdefinierten Tokenanbieter erstellen, der es ermöglicht, ein SAML-Token zu verwenden, das von außerhalb des WCF-Client Frameworks abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8acbf-112">This sample shows how to build a custom token provider that allows a SAML token obtained from outside of the WCF client framework to be used.</span></span>

 <span data-ttu-id="8acbf-113">Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="8acbf-113">To summarize, this sample demonstrates the following:</span></span>

- <span data-ttu-id="8acbf-114">Wie ein Client mit einem benutzerdefinierten Tokenanbieter konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8acbf-114">How a client can be configured with a custom token provider.</span></span>

- <span data-ttu-id="8acbf-115">Wie ein SAML-Token an die benutzerdefinierten Clientanmeldeinformationen übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="8acbf-115">How a SAML token can be passed to the custom client credentials.</span></span>

- <span data-ttu-id="8acbf-116">Gibt an, wie das SAML-Token für das WCF-Client Framework bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8acbf-116">How the SAML token is provided to the WCF client framework.</span></span>

- <span data-ttu-id="8acbf-117">Wie der Server über das X.509-Zertifikat des Servers vom Client authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8acbf-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>

 <span data-ttu-id="8acbf-118">Der Dienst macht zwei Endpunkte für die Kommunikation mit dem Dienst verfügbar, die mithilfe der Konfigurationsdatei "App. config" definiert werden. Jeder Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="8acbf-118">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="8acbf-119">Die Bindung wird mit einer Standard-`wsFederationHttpBinding` konfiguriert, die Nachrichtensicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="8acbf-119">The binding is configured with a standard `wsFederationHttpBinding`, which uses Message security.</span></span> <span data-ttu-id="8acbf-120">Ein Endpunkt erwartet, dass der Client sich mit einem SAML-Token authentifiziert, das einen symmetrischen Prüfschlüssel verwendet, während der andere erwartet, dass sich der Client mit einem SAML-Token authentifiziert, das einen asymmetrischen Prüfschlüssel verwendet.</span><span class="sxs-lookup"><span data-stu-id="8acbf-120">One endpoint expects the client to authenticate with a SAML token that uses a symmetric proof key while the other expects the client to authenticate with a SAML token that uses an asymmetric proof key.</span></span> <span data-ttu-id="8acbf-121">Außerdem konfiguriert der Dienst das Dienstzertifikat mit `serviceCredentials`-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="8acbf-121">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="8acbf-122">Mit dem `serviceCredentials`-Verhalten können Sie ein Dienstzertifikat erstellen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-122">The `serviceCredentials` behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="8acbf-123">Ein Dienstzertifikat wird von einem Client verwendet, um den Dienst zu authentifizieren und Nachrichtenschutz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-123">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="8acbf-124">Die folgende Konfiguration verweist auf das Zertifikat localhost, das während des Beispielsetups installiert wird (in den Setupanweisungen am Ende dieses Themas beschrieben).</span><span class="sxs-lookup"><span data-stu-id="8acbf-124">The following configuration references the "localhost" certificate installed during the sample setup as described in the setup instructions at the end of this topic.</span></span> <span data-ttu-id="8acbf-125">Das `serviceCredentials`-Verhalten ermöglicht es Ihnen außerdem, Zertifikate zu konfigurieren, die die Befugnis zum signieren von SAML-Token haben.</span><span class="sxs-lookup"><span data-stu-id="8acbf-125">The `serviceCredentials` behavior also allows you to configure certificates that are trusted to sign SAML tokens.</span></span> <span data-ttu-id="8acbf-126">Die folgende Konfiguration verweist auf das im Beispiel installierte Zertifikat "Alice".</span><span class="sxs-lookup"><span data-stu-id="8acbf-126">The following configuration references the 'Alice' certificate installed during the sample.</span></span>

```xml
<system.serviceModel>
 <services>
  <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
   <host>
    <baseAddresses>
     <!-- configure base address provided by host -->
     <add
  baseAddress="http://localhost:8000/servicemodelsamples/service/" />
    </baseAddresses>
   </host>
   <!-- use base address provided by host -->
   <!-- Endpoint that expect SAML tokens with Symmetric proof keys -->
   <endpoint address="calc/symm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
   <!-- Endpoint that expect SAML tokens with Asymmetric proof keys -->
   <endpoint address="calc/asymm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding2"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
 </services>

 <bindings>
  <wsFederationHttpBinding>
   <!-- Binding that expect SAML tokens with Symmetric proof keys -->
   <binding name="Binding1">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="SymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
   <!-- Binding that expect SAML tokens with Asymmetric proof keys -->
   <binding name="Binding2">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="AsymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
  </wsFederationHttpBinding>
 </bindings>

 <behaviors>
  <serviceBehaviors>
   <behavior name="CalculatorServiceBehavior">
    <!--
    The serviceCredentials behavior allows one to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
    <serviceCredentials>
     <!-- Set allowUntrustedRsaIssuers to true to allow self-signed, asymmetric key based SAML tokens -->
     <issuedTokenAuthentication allowUntrustedRsaIssuers ="true" >
      <!-- Add Alice to the list of certs trusted to issue SAML tokens -->
      <knownCertificates>
       <add storeLocation="LocalMachine"
            storeName="TrustedPeople"
            x509FindType="FindBySubjectName"
            findValue="Alice"/>
      </knownCertificates>
     </issuedTokenAuthentication>
     <serviceCertificate storeLocation="LocalMachine"
                         storeName="My"
                         x509FindType="FindBySubjectName"
                         findValue="localhost"  />
    </serviceCredentials>
   </behavior>
  </serviceBehaviors>
 </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="8acbf-127">In den folgenden Schritten wird gezeigt, wie Sie einen benutzerdefinierten SAML-Tokenanbieter entwickeln und in WCF: Security Framework integrieren:</span><span class="sxs-lookup"><span data-stu-id="8acbf-127">The following steps show how to develop a custom SAML token provider and integrate it with WCF: security framework:</span></span>

1. <span data-ttu-id="8acbf-128">Schreiben Sie einen benutzerdefinierten SAML-Tokenanbieter.</span><span class="sxs-lookup"><span data-stu-id="8acbf-128">Write a custom SAML token provider.</span></span>

     <span data-ttu-id="8acbf-129">Im Beispiel wird ein benutzerdefinierter SAML-Tokenanbieter implementiert, der auf der Basis einer SAML-Assertion, die zum Zeitpunkt der Erstellung angegeben wurde, ein Sicherheitstoken zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-129">The sample implements a custom SAML token provider that returns a security token based on a SAML assertion that is provided at construction time.</span></span>

     <span data-ttu-id="8acbf-130">Zur Ausführung dieser Aufgabe wird der benutzerdefinierte Tokenanbieter aus der <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse abgeleitet und setzt die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>-Methode außer Kraft.</span><span class="sxs-lookup"><span data-stu-id="8acbf-130">To perform this task, the custom token provider is derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="8acbf-131">Diese Methode erstellt ein neues `SecurityToken`-Objekt und gibt es zurück.</span><span class="sxs-lookup"><span data-stu-id="8acbf-131">This method creates and returns a new `SecurityToken`.</span></span>

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
     // Create a SamlSecurityToken from the provided assertion
     SamlSecurityToken samlToken = new SamlSecurityToken(assertion);

     // Create a SecurityTokenSerializer that will be used to
     // serialize the SamlSecurityToken
     WSSecurityTokenSerializer ser = new WSSecurityTokenSerializer();
     // Create a memory stream to write the serialized token into
     // Use an initial size of 64Kb
     MemoryStream s = new MemoryStream(UInt16.MaxValue);

     // Create an XmlWriter over the stream
     XmlWriter xw = XmlWriter.Create(s);

     // Write the SamlSecurityToken into the stream
     ser.WriteToken(xw, samlToken);

     // Seek back to the beginning of the stream
     s.Seek(0, SeekOrigin.Begin);

     // Load the serialized token into a DOM
     XmlDocument dom = new XmlDocument();
     dom.Load(s);

     // Create a KeyIdentifierClause for the SamlSecurityToken
     SamlAssertionKeyIdentifierClause samlKeyIdentifierClause = samlToken.CreateKeyIdentifierClause<SamlAssertionKeyIdentifierClause>();

    // Return a GenericXmlToken from the XML for the
    // SamlSecurityToken, the proof token, the valid from and valid
    // until times from the assertion and the key identifier clause
    // created above
    return new GenericXmlSecurityToken(dom.DocumentElement, proofToken, assertion.Conditions.NotBefore, assertion.Conditions.NotOnOrAfter, samlKeyIdentifierClause, samlKeyIdentifierClause, null);
    }
    ```

2. <span data-ttu-id="8acbf-132">Schreiben Sie den benutzerdefiniertem Sicherheitstoken-Manager.</span><span class="sxs-lookup"><span data-stu-id="8acbf-132">Write custom security token manager.</span></span>

     <span data-ttu-id="8acbf-133">Die <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Klasse dient zur Erstellung von <xref:System.IdentityModel.Selectors.SecurityTokenProvider> für eine bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, die in der `CreateSecurityTokenProvider`-Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="8acbf-133">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> class is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="8acbf-134">Ein Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenauthentifizierern und eines Token-Serialisierungsprogramms. Diese Vorgänge werden jedoch in diesem Beispiel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-134">A security token manager is also used to create token authenticators and token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="8acbf-135">In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> und setzt die Methode `CreateSecurityTokenProvider` außer Kraft, um den benutzerdefinierten SAML-Tokenanbieter zurückzugeben, wenn die übergebenen Sicherheitstokenanforderungen angeben, dass das SAML-Token angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="8acbf-135">In this sample the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom SAML token provider when the passed token requirements indicate that the SAML token is requested.</span></span> <span data-ttu-id="8acbf-136">Wenn die Clientanmeldeinformationsklasse (siehe Schritt 3) keine Assertion angegeben hat, erstellt der Sicherheitstoken-Manager eine entsprechende Instanz.</span><span class="sxs-lookup"><span data-stu-id="8acbf-136">If the client credentials class (see step 3) has not specified an assertion, the security token manager creates an appropriate instance.</span></span>

    ```csharp
    public class SamlSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
     SamlClientCredentials samlClientCredentials;

     public SamlSecurityTokenManager ( SamlClientCredentials samlClientCredentials)
      : base(samlClientCredentials)
     {
      // Store the creating client credentials
      this.samlClientCredentials = samlClientCredentials;
     }

     public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )
     {
      // If token requirement matches SAML token return the
      // custom SAML token provider
      if (tokenRequirement.TokenType == SecurityTokenTypes.Saml ||
          tokenRequirement.TokenType == "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1")
      {
       // Retrieve the SAML assertion and proof token from the
       // client credentials
       SamlAssertion assertion = this.samlClientCredentials.Assertion;
       SecurityToken prooftoken = this.samlClientCredentials.ProofToken;

       // If either the assertion of proof token is null...
       if (assertion == null || prooftoken == null)
       {
        // ...get the SecurityBindingElement and then the
        // specified algorithm suite
        SecurityBindingElement sbe = null;
        SecurityAlgorithmSuite sas = null;

        if ( tokenRequirement.TryGetProperty<SecurityBindingElement> ( "http://schemas.microsoft.com/ws/2006/05/servicemodel/securitytokenrequirement/SecurityBindingElement", out sbe))
        {
         sas = sbe.DefaultAlgorithmSuite;
        }

        // If the token requirement is for a SymmetricKey based token..
        if (tokenRequirement.KeyType == SecurityKeyType.SymmetricKey)
        {
         // Create a symmetric proof token
         prooftoken = SamlUtilities.CreateSymmetricProofToken ( tokenRequirement.KeySize );
         // and a corresponding assertion based on the claims specified in the client credentials
         assertion = SamlUtilities.CreateSymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, new X509SecurityToken ( samlClientCredentials.ClientCertificate.Certificate ), new X509SecurityToken ( samlClientCredentials.ServiceCertificate.DefaultCertificate ), (BinarySecretSecurityToken)prooftoken, sas);
        }
        // otherwise...
        else
        {
         // Create an asymmetric proof token
         prooftoken = SamlUtilities.CreateAsymmetricProofToken();
         // and a corresponding assertion based on the claims
         // specified in the client credentials
         assertion = SamlUtilities.CreateAsymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, prooftoken, sas );
        }
       }

       // Create a SamlSecurityTokenProvider based on the assertion and proof token
       return new SamlSecurityTokenProvider(assertion, prooftoken);
      }
      // otherwise use base implementation
      else
      {
       return base.CreateSecurityTokenProvider(tokenRequirement);
      }
    }
    ```

3. <span data-ttu-id="8acbf-137">Schreiben Sie benutzerdefinierte Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-137">Write a custom client credential.</span></span>

     <span data-ttu-id="8acbf-138">Die Klasse der Clientanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Clientproxy konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="8acbf-138">Client credentials class is used to represent the credentials that are configured for the client proxy and creates a security token manager that is used to obtain token authenticators, token providers and token serializer.</span></span>

    ```csharp
    public class SamlClientCredentials : ClientCredentials
    {
     ClaimSet claims;
     SamlAssertion assertion;
     SecurityToken proofToken;

     public SamlClientCredentials() : base()
     {
      // Set SupportInteractive to false to suppress Cardspace UI
      base.SupportInteractive = false;
     }

     protected SamlClientCredentials(SamlClientCredentials other) : base ( other )
     {
      // Just do reference copy given sample nature
      this.assertion = other.assertion;
      this.claims = other.claims;
      this.proofToken = other.proofToken;
     }

     public SamlAssertion Assertion { get { return assertion; } set { assertion = value; } }

     public SecurityToken ProofToken { get { return proofToken; } set { proofToken = value; } }
     public ClaimSet Claims { get { return claims; } set { claims = value; } }

     protected override ClientCredentials CloneCore()
     {
      return new SamlClientCredentials(this);
     }

     public override SecurityTokenManager CreateSecurityTokenManager()
     {
      // return custom security token manager
      return new SamlSecurityTokenManager(this);
     }
    }
    ```

4. <span data-ttu-id="8acbf-139">Konfigurieren Sie den Client für die Verwendung der benutzerdefinierten Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-139">Configure the client to use the custom client credential.</span></span>

     <span data-ttu-id="8acbf-140">Im Beispiel wird die Standardklasse für die Clientanmeldeinformationen gelöscht und die neue Klasse für Clientanmeldeinformationen angegeben, sodass der Client die benutzerdefinierten Clientanmeldeinformationen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="8acbf-140">The sample deletes the default client credential class and supplies the new client credential class so the client can use the custom client credential.</span></span>

    ```csharp
    // Create new credentials class
    SamlClientCredentials samlCC = new SamlClientCredentials();

    // Set the client certificate. This is the cert that will be used to sign the SAML token in the symmetric proof key case
    samlCC.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "Alice");

    // Set the service certificate. This is the cert that will be used to encrypt the proof key in the symmetric proof key case
    samlCC.ServiceCertificate.SetDefaultCertificate(StoreLocation.CurrentUser, StoreName.TrustedPeople, X509FindType.FindBySubjectName, "localhost");

    // Create some claims to put in the SAML assertion
    IList<Claim> claims = new List<Claim>();
    claims.Add(Claim.CreateNameClaim(samlCC.ClientCertificate.Certificate.Subject));
    ClaimSet claimset = new DefaultClaimSet(claims);
    samlCC.Claims = claimset;

    // set new credentials
    client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
    client.ChannelFactory.Endpoint.Behaviors.Add(samlCC);
    ```

 <span data-ttu-id="8acbf-141">Beim Dienst werden die dem Aufrufer zugeordneten Ansprüche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-141">On the service, the claims associated with the caller are displayed.</span></span> <span data-ttu-id="8acbf-142">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-142">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8acbf-143">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-143">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="8acbf-144">Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="8acbf-144">Setup Batch File</span></span>
 <span data-ttu-id="8acbf-145">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit dem relevanten Zertifikat zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-145">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="8acbf-146">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8acbf-146">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="8acbf-147">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8acbf-147">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

- <span data-ttu-id="8acbf-148">Erstellen des Serverzertifikats</span><span class="sxs-lookup"><span data-stu-id="8acbf-148">Creating the server certificate:</span></span>

     <span data-ttu-id="8acbf-149">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-149">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="8acbf-150">Die Variable `%SERVER_NAME%` gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="8acbf-150">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="8acbf-151">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="8acbf-151">Change this variable to specify your own server name.</span></span> <span data-ttu-id="8acbf-152">Der Standardwert in dieser Batchdatei lautet localhost.</span><span class="sxs-lookup"><span data-stu-id="8acbf-152">The default value in this batch file is localhost.</span></span>

     <span data-ttu-id="8acbf-153">Das Zertifikat wird im persönlichen Speicher unter dem Speicherort LocalMachine gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-153">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="8acbf-154">Installieren des Serverzertifikats im Speicher für vertrauenswürdige Zertifikate des Clients:</span><span class="sxs-lookup"><span data-stu-id="8acbf-154">Installing the server certificate into the client's trusted certificate store:</span></span>

     <span data-ttu-id="8acbf-155">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-155">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="8acbf-156">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="8acbf-156">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="8acbf-157">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8acbf-157">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople
    ```

- <span data-ttu-id="8acbf-158">Erstellen des Herausgeberzertifikats.</span><span class="sxs-lookup"><span data-stu-id="8acbf-158">Creating the issuer certificate.</span></span>

     <span data-ttu-id="8acbf-159">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Herausgeberzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-159">The following lines from the Setup.bat batch file create the issuer certificate to be used.</span></span> <span data-ttu-id="8acbf-160">Die Variable `%USER_NAME%` gibt den Herausgebernamen an.</span><span class="sxs-lookup"><span data-stu-id="8acbf-160">The `%USER_NAME%` variable specifies the issuer name.</span></span> <span data-ttu-id="8acbf-161">Ändern Sie diese Variable, und geben Sie Ihren eigenen Herausgebernamen an.</span><span class="sxs-lookup"><span data-stu-id="8acbf-161">Change this variable to specify your own issuer name.</span></span> <span data-ttu-id="8acbf-162">Der Standardwert in dieser Batchdatei lautet "Alice".</span><span class="sxs-lookup"><span data-stu-id="8acbf-162">The default value in this batch file is Alice.</span></span>

     <span data-ttu-id="8acbf-163">Das Zertifikat wird im persönlichen Speicher unter dem Speicherort CurrentUser gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-163">The certificate is stored in My store under the CurrentUser store location.</span></span>

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- <span data-ttu-id="8acbf-164">Installieren des Herausgeberzertifikats im Speicher für vertrauenswürdige Zertifikate des Servers.</span><span class="sxs-lookup"><span data-stu-id="8acbf-164">Installing the issuer certificate into the server's trusted certificate store.</span></span>

     <span data-ttu-id="8acbf-165">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="8acbf-165">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="8acbf-166">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="8acbf-166">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="8acbf-167">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Serverzertifikatspeichers mit dem Herausgeberzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8acbf-167">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the server certificate store with the issuer certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="8acbf-168">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="8acbf-168">To set up and build the sample</span></span>

1. <span data-ttu-id="8acbf-169">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="8acbf-169">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="8acbf-170">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8acbf-171">Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-171">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="8acbf-172">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="8acbf-172">To run the sample on the same computer</span></span>

1. <span data-ttu-id="8acbf-173">Führen Sie Setup. bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus.</span><span class="sxs-lookup"><span data-stu-id="8acbf-173">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="8acbf-174">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8acbf-174">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8acbf-175">Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8acbf-175">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="8acbf-176">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8acbf-176">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="8acbf-177">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="8acbf-177">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="8acbf-178">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="8acbf-178">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="8acbf-179">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-179">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="8acbf-180">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-180">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="8acbf-181">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="8acbf-181">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="8acbf-182">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="8acbf-182">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="8acbf-183">Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="8acbf-183">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="8acbf-184">Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="8acbf-184">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="8acbf-185">Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält.</span><span class="sxs-lookup"><span data-stu-id="8acbf-185">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="8acbf-186">Die Datei Service.exe.config muss so aktualisiert werden, dass sie diesem neuen Zertifikatsnamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="8acbf-186">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="8acbf-187">Sie können das Serverzertifikat erstellen, indem Sie die Batchdatei Setup.bat ändern.</span><span class="sxs-lookup"><span data-stu-id="8acbf-187">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="8acbf-188">Beachten Sie, dass die Datei Setup. bat in einem Developer-Eingabeaufforderung für das Visual Studio-Fenster ausgeführt werden muss, das mit Administratorrechten geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="8acbf-188">Note that the setup.bat file must be run in a Developer Command Prompt for Visual Studio window opened with administrator privileges.</span></span> <span data-ttu-id="8acbf-189">Sie müssen die Variable `%SERVER_NAME%` auf den vollqualifizierten Hostnamen des Computers festlegen, der als Host für den Dienst dienen soll.</span><span class="sxs-lookup"><span data-stu-id="8acbf-189">You must set the `%SERVER_NAME%` variable to the fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4. <span data-ttu-id="8acbf-190">Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients.</span><span class="sxs-lookup"><span data-stu-id="8acbf-190">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="8acbf-191">Dieser Schritt ist nicht notwendig, wenn das Serverzertifikat von einem Aussteller stammt, der vom Client als vertrauenswürdig eingestuft wurde.</span><span class="sxs-lookup"><span data-stu-id="8acbf-191">This step is not necessary when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="8acbf-192">Ändern Sie in der Datei Service.exe.config auf dem Dienstcomputer den Wert der Basisadresse, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.</span><span class="sxs-lookup"><span data-stu-id="8acbf-192">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="8acbf-193">Führen Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="8acbf-193">On the service computer, run Service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="8acbf-194">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="8acbf-194">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="8acbf-195">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="8acbf-195">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="8acbf-196">Starten Sie auf dem Clientcomputer `Client.exe` in einem Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="8acbf-196">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="8acbf-197">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="8acbf-197">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="8acbf-198">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="8acbf-198">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="8acbf-199">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="8acbf-199">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
