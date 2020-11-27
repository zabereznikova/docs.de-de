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
# <a name="durable-issued-token-provider"></a>Dauerhaft ausgestellter Tokenanbieter

Dieses Beispiel veranschaulicht das Implementieren eines Tokenanbieters, der von einem benutzerdefinierten Client ausgestellt wird.  
  
## <a name="discussion"></a>Diskussion  

 Ein Tokenanbieter in Windows Communication Foundation (WCF) wird verwendet, um Anmelde Informationen für die Sicherheitsinfrastruktur bereitzustellen. Der Tokenanbieter untersucht im Allgemeinen das Ziel und gibt die entsprechenden Anmeldeinformationen aus, sodass die Sicherheitsinfrastruktur die Nachricht sichern kann. WCF ist mit einem CardSpace-Tokenanbieter ausgeliefert. Benutzerdefinierte Tokenanbieter sind in den folgenden Fällen nützlich:  
  
- Wenn Sie einen Speicher für Anmeldeinformationen verwenden, mit dem der integrierte Tokenanbieter nicht umgehen kann.  
  
- Wenn Sie einen eigenen benutzerdefinierten Mechanismus zum Transformieren der Anmelde Informationen von dem Punkt bereitstellen möchten, an dem der Benutzer die Details bereitstellt, wenn der WCF-Client die Anmelde Informationen verwendet.  
  
- Wenn Sie ein benutzerdefiniertes Token erstellen.  
  
 Dieses Beispiel veranschaulicht die Erstellung eines benutzerdefinierten Tokenanbieters, der von einem Sicherheitstokendienst (STS, Security Token Service) ausgestellte Token zwischenspeichert.  
  
 Kurz gesagt, veranschaulicht dieses Beispiel folgende Punkte:  
  
- Wie ein Client mit einem benutzerdefinierten Tokenanbieter konfiguriert werden kann.  
  
- Gibt an, wie ausgestellte Token zwischengespeichert und dem WCF-Client bereitgestellt werden können.  
  
- Wie der Server über das X.509-Zertifikat des Servers vom Client authentifiziert wird.  
  
 Das Beispiel besteht aus einem Clientkonsolenprogramm (Client.exe), einem Konsolenprogramm für den Sicherheitstokendienst (Securitytokenservice.exe) und einem Dienstkonsolenprogramm (Service.exe). Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht. Der Client empfängt ein Sicherheitstoken vom STS und fordert beim Dienst asynchron einen bestimmten mathematischen Vorgang an. Der Dienst antwortet mit dem Ergebnis. Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel wird der ICalculator-Vertrag mithilfe von verfügbar gemacht [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Client.  
  
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
  
 Im `security`-Element von `wsFederationHttpBinding` konfiguriert der `mode`-Wert, welcher Sicherheitsmodus verwendet werden soll. In diesem Beispiel wird die Nachrichtensicherheit verwendet. Daher wird das `message`-Element von `wsFederationHttpBinding` im `security`-Element von `wsFederationHttpBinding` angegeben. Das `issuer`-Element von `wsFederationHttpBinding` im `message`-Element von `wsFederationHttpBinding` gibt die Adresse und die Bindung für den Sicherheitstokendienst an, der ein Sicherheitstoken an den Client ausgibt, damit der Client beim Rechnerdienst authentifiziert werden kann.  
  
 Das folgende Codebeispiel zeigt die Konfiguration dieser Bindung auf dem Dienst.  
  
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
  
 Im `security`-Element von `wsFederationHttpBinding` konfiguriert der `mode`-Wert, welcher Sicherheitsmodus verwendet werden soll. In diesem Beispiel wird die Nachrichtensicherheit verwendet. Daher wird das `message`-Element von `wsFederationHttpBinding` im `security`-Element von `wsFederationHttpBinding` angegeben. Das `issuerMetadata`-Element von `wsFederationHttpBinding` im `message`-Element von `wsFederationHttpBinding` gibt die Adresse und Identität für einen Endpunkt an, mit dem Metadaten für den Sicherheitstokendienst abgerufen werden können.  
  
 Das Verhalten für den Dienst wird im folgenden Code gezeigt.  
  
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
  
 Mit dem `issuedTokenAuthentication`-Element im `serviceCredentials`-Element kann der Dienst Einschränkungen für die Token angeben, die Clients bei der Authentifizierung angeben dürfen. In dieser Konfiguration wird angegeben, dass von einem Zertifikat mit dem Ausstellernamen CN=STS signierte Token vom Dienst akzeptiert werden.  
  
 Der Sicherheitstokendienst (STS, Security Token Service) macht mit Standard-wsHttpBinding einen einzelnen Endpunkt verfügbar. Der STS reagiert auf eine Tokenanforderung von Clients. Wenn der Client mit einem Windows-Konto authentifiziert wird, gibt der STS ein Token mit dem Benutzernamen des Clients als Anspruch im herausgegebenen Token heraus. Beim Erstellen des Tokens signiert der STS das Token mit dem privaten Schlüssel, der dem CN=STS-Zertifikat zugeordnet ist. Außerdem wird ein symmetrischer Schlüssel erstellt und mit dem öffentlichen Schlüssel verschlüsselt, der dem CN=localhost-Zertifikat zugeordnet ist. Beim Zurückgeben des Tokens an den Client gibt der STS auch den symmetrischen Schlüssel zurück. Der Client stellt das herausgegebene Token für den Rechnerdienst bereit und beweist, dass der symmetrische Schlüssel bekannt ist, indem die Nachricht mit diesem Schlüssel signiert wird.  
  
## <a name="custom-client-credentials-and-token-provider"></a>Benutzerdefinierte Clientanmeldeinformationen und Tokenanbieter  

 Die folgenden Schritte zeigen, wie Sie einen benutzerdefinierten Tokenanbieter entwickeln, der ausgestellte Token zwischenspeichert und in WCF: Security integriert.  
  
### <a name="to-develop-a-custom-token-provider"></a>So entwickeln Sie einen benutzerdefinierten Tokenanbieter  
  
1. Schreiben Sie einen benutzerdefinierten Tokenanbieter.  
  
     Das Beispiel implementiert einen benutzerdefinierten Tokenanbieter, der ein Sicherheitstoken zurückgibt, das aus dem Cache abgerufen wird.  
  
     Zur Ausführung dieser Aufgabe leitet der benutzerdefinierte Tokenanbieter die <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse ab und überschreibt die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>-Methode. Bei dieser Methode wird versucht, ein Token aus dem Cache abzurufen. Wenn im Cache kein Token gefunden wird, wird ein Token vom zugrunde liegenden Anbieter abgerufen und anschließend im Cache gespeichert. In diesem Fall gibt die Methode ein `SecurityToken` zurück.  
  
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
  
2. Schreiben Sie den benutzerdefiniertem Sicherheitstoken-Manager.  
  
     Der <xref:System.IdentityModel.Selectors.SecurityTokenManager> wird zur Erstellung von einem <xref:System.IdentityModel.Selectors.SecurityTokenProvider> für eine bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> verwendet, die in der `CreateSecurityTokenProvider`-Methode übergeben wird. Der Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenauthentifizierern und Token-Serialisierungsprogrammen. Diese Vorgänge werden jedoch in diesem Beispiel nicht behandelt. In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> und setzt die Methode `CreateSecurityTokenProvider` außer Kraft, um den benutzerdefinierten Tokenanbieter zurückzugeben, wenn die übergebenen Tokenanforderungen angeben, dass ein ausgestelltes Token angefordert wird.  
  
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
  
3. Schreiben Sie benutzerdefinierte Clientanmeldeinformationen.  
  
     Eine Klasse der Clientanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Clientproxy konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.  
  
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
  
4. Implementieren Sie den Tokencache. Die Beispielimplementierung verwendet eine abstrakte Basisklasse, über die Consumer eines bestimmten Tokencaches mit dem Cache interagieren.  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     Im Beispiel wird die Standardklasse für die Clientanmeldeinformationen gelöscht und die neue Klasse für Clientanmeldeinformationen angegeben, sodass der Client die benutzerdefinierten Clientanmeldeinformationen verwenden kann.  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  

 In den folgenden Anweisungen finden Sie Informationen zum Ausführen des Beispiels. Wenn Sie das Beispiel ausführen, wird die Anforderung des Sicherheitstokens im STS-Konsolenfenster angezeigt. Die Anforderungen und Antworten des Vorgangs werden im Client- und Dienstkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in einem der Konsolenfenster, um die Anwendung zu schließen.  
  
## <a name="the-setupcmd-batch-file"></a>Die Batchdatei Setup.cmd  

 Mit der in diesem Beispiel enthaltenen Batchdatei "Setup.cmd" können Sie den Server und den STS mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren. Die Batchdatei erstellt zwei Zertifikate im Zertifikatspeicher CurrentUser/TrustedPeople. Der Antragstellername des ersten Zertifikats lautet CN=STS und wird vom STS zum Signieren des Sicherheitstokens verwendet, das an den Client herausgegeben wird. Der Antragstellername des zweiten Zertifikats lautet CN=localhost und wird vom STS zum Verschlüsseln eines Geheimnisses verwendet, das dann vom Dienst entschlüsselt werden kann.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Führen Sie die Datei "Setup.cmd" aus, um die erforderlichen Zertifikate zu erstellen.  
  
2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](building-the-samples.md), um die Lösung zu erstellen. Stellen Sie sicher, dass alle Projekte in der Projektmappe erstellt werden (Shared, RSTRSTR, Service, SecurityTokenService und Client).  
  
3. Stellen Sie sicher, dass Service.exe und SecurityTokenService.exe mit Administratorrechten ausgeführt werden.  
  
4. Führen Sie Client.exe aus.  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1. Führen Sie "Cleanup.cmd" im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
