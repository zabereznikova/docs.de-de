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
# <a name="saml-token-provider"></a>SAML-Tokenanbieter
Dieses Beispiel veranschaulicht das Implementieren eines benutzerdefinierten Client-SAML-Tokenanbieters. Ein Tokenanbieter in Windows Communication Foundation (WCF) wird zum Bereitstellen von Anmelde Informationen für die Sicherheitsinfrastruktur verwendet. Der Tokenanbieter untersucht im Allgemeinen das Ziel und gibt die entsprechenden Anmeldeinformationen aus, sodass die Sicherheitsinfrastruktur die Nachricht sichern kann. WCF wird mit dem standardmäßigen Anmelde Informations Manager-Tokenanbieter ausgeliefert. WCF ist auch mit einem CardSpace-Tokenanbieter ausgeliefert. Benutzerdefinierte Tokenanbieter sind in den folgenden Fällen nützlich:

- Wenn Sie einen Speicher für Anmeldeinformationen verwenden, mit dem diese Tokenanbieter nicht umgehen können.

- Wenn Sie einen eigenen benutzerdefinierten Mechanismus zum Transformieren der Anmelde Informationen von dem Punkt bereitstellen möchten, an dem der Benutzer die Details bereitstellt, wenn das WCF-Client Framework die Anmelde Informationen verwendet.

- Wenn Sie ein benutzerdefiniertes Token erstellen.

 Dieses Beispiel zeigt, wie Sie einen benutzerdefinierten Tokenanbieter erstellen, der es ermöglicht, ein SAML-Token zu verwenden, das von außerhalb des WCF-Client Frameworks abgerufen wird.

 Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:

- Wie ein Client mit einem benutzerdefinierten Tokenanbieter konfiguriert werden kann.

- Wie ein SAML-Token an die benutzerdefinierten Clientanmeldeinformationen übergeben werden kann.

- Gibt an, wie das SAML-Token für das WCF-Client Framework bereitgestellt wird.

- Wie der Server über das X.509-Zertifikat des Servers vom Client authentifiziert wird.

 Der Dienst macht zwei Endpunkte für die Kommunikation mit dem Dienst verfügbar, die mithilfe der Konfigurationsdatei "App. config" definiert werden. Jeder Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einer Standard-`wsFederationHttpBinding` konfiguriert, die Nachrichtensicherheit verwendet. Ein Endpunkt erwartet, dass der Client sich mit einem SAML-Token authentifiziert, das einen symmetrischen Prüfschlüssel verwendet, während der andere erwartet, dass sich der Client mit einem SAML-Token authentifiziert, das einen asymmetrischen Prüfschlüssel verwendet. Außerdem konfiguriert der Dienst das Dienstzertifikat mit `serviceCredentials`-Verhalten. Mit dem `serviceCredentials`-Verhalten können Sie ein Dienstzertifikat erstellen. Ein Dienstzertifikat wird von einem Client verwendet, um den Dienst zu authentifizieren und Nachrichtenschutz bereitzustellen. Die folgende Konfiguration verweist auf das Zertifikat localhost, das während des Beispielsetups installiert wird (in den Setupanweisungen am Ende dieses Themas beschrieben). Das `serviceCredentials`-Verhalten ermöglicht es Ihnen außerdem, Zertifikate zu konfigurieren, die die Befugnis zum signieren von SAML-Token haben. Die folgende Konfiguration verweist auf das im Beispiel installierte Zertifikat "Alice".

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

 In den folgenden Schritten wird gezeigt, wie Sie einen benutzerdefinierten SAML-Tokenanbieter entwickeln und in WCF: Security Framework integrieren:

1. Schreiben Sie einen benutzerdefinierten SAML-Tokenanbieter.

     Im Beispiel wird ein benutzerdefinierter SAML-Tokenanbieter implementiert, der auf der Basis einer SAML-Assertion, die zum Zeitpunkt der Erstellung angegeben wurde, ein Sicherheitstoken zurückgibt.

     Zur Ausführung dieser Aufgabe wird der benutzerdefinierte Tokenanbieter aus der <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse abgeleitet und setzt die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>-Methode außer Kraft. Diese Methode erstellt ein neues `SecurityToken`-Objekt und gibt es zurück.

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

2. Schreiben Sie den benutzerdefiniertem Sicherheitstoken-Manager.

     Die <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Klasse dient zur Erstellung von <xref:System.IdentityModel.Selectors.SecurityTokenProvider> für eine bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, die in der `CreateSecurityTokenProvider`-Methode übergeben wird. Ein Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenauthentifizierern und eines Token-Serialisierungsprogramms. Diese Vorgänge werden jedoch in diesem Beispiel nicht behandelt. In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> und setzt die Methode `CreateSecurityTokenProvider` außer Kraft, um den benutzerdefinierten SAML-Tokenanbieter zurückzugeben, wenn die übergebenen Sicherheitstokenanforderungen angeben, dass das SAML-Token angefordert wird. Wenn die Clientanmeldeinformationsklasse (siehe Schritt 3) keine Assertion angegeben hat, erstellt der Sicherheitstoken-Manager eine entsprechende Instanz.

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

3. Schreiben Sie benutzerdefinierte Clientanmeldeinformationen.

     Die Klasse der Clientanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Clientproxy konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.

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

4. Konfigurieren Sie den Client für die Verwendung der benutzerdefinierten Clientanmeldeinformationen.

     Im Beispiel wird die Standardklasse für die Clientanmeldeinformationen gelöscht und die neue Klasse für Clientanmeldeinformationen angegeben, sodass der Client die benutzerdefinierten Clientanmeldeinformationen verwenden kann.

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

 Beim Dienst werden die dem Aufrufer zugeordneten Ansprüche angezeigt. Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

## <a name="setup-batch-file"></a>Setupbatchdatei
 Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit dem relevanten Zertifikat zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.

 Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.

- Erstellen des Serverzertifikats

     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt. Die Variable `%SERVER_NAME%` gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. Der Standardwert in dieser Batchdatei lautet localhost.

     Das Zertifikat wird im persönlichen Speicher unter dem Speicherort LocalMachine gespeichert.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Installieren des Serverzertifikats im Speicher für vertrauenswürdige Zertifikate des Clients:

     Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople
    ```

- Erstellen des Herausgeberzertifikats.

     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Herausgeberzertifikat erstellt. Die Variable `%USER_NAME%` gibt den Herausgebernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Herausgebernamen an. Der Standardwert in dieser Batchdatei lautet "Alice".

     Das Zertifikat wird im persönlichen Speicher unter dem Speicherort CurrentUser gespeichert.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

- Installieren des Herausgeberzertifikats im Speicher für vertrauenswürdige Zertifikate des Servers.

     Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Serverzertifikatspeichers mit dem Herausgeberzertifikat nicht erforderlich.

    ```console
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen.

> [!NOTE]
> Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.

#### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus

1. Führen Sie Setup. bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung mit Administratorrechten aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.

    > [!NOTE]
    > Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird. Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.  
  
2. Starten Sie Service.exe aus dem Ordner \service\bin.  
  
3. Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.  
  
2. Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer. Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.  
  
3. Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält. Die Datei Service.exe.config muss so aktualisiert werden, dass sie diesem neuen Zertifikatsnamen entspricht. Sie können das Serverzertifikat erstellen, indem Sie die Batchdatei Setup.bat ändern. Beachten Sie, dass die Datei Setup. bat in einem Developer-Eingabeaufforderung für das Visual Studio-Fenster ausgeführt werden muss, das mit Administratorrechten geöffnet wurde. Sie müssen die Variable `%SERVER_NAME%` auf den vollqualifizierten Hostnamen des Computers festlegen, der als Host für den Dienst dienen soll.  
  
4. Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients. Dieser Schritt ist nicht notwendig, wenn das Serverzertifikat von einem Aussteller stammt, der vom Client als vertrauenswürdig eingestuft wurde.  
  
5. Ändern Sie in der Datei Service.exe.config auf dem Dienstcomputer den Wert der Basisadresse, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.  
  
6. Führen Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung aus.  
  
7. Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
8. Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.  
  
9. Starten Sie auf dem Clientcomputer `Client.exe` in einem Eingabeaufforderungsfenster.  
  
10. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1. Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
