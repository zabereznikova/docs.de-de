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
# <a name="token-authenticator"></a>Tokenauthentifizierer
Dieses Beispiel veranschaulicht das Implementieren eines benutzerdefinierten Tokenauthentifizierers. Ein tokenauthentifikator in Windows Communication Foundation (WCF) wird zum Überprüfen des Tokens verwendet, das mit der Nachricht verwendet wird, um zu überprüfen, ob es selbst konsistent ist, und zum Authentifizieren der Identität, die dem Token zugeordnet ist.

 Benutzerdefinierte Tokenauthentifizierer sind in einer Vielzahl von Fällen nützlich, z. B.:

- Wenn Sie den einem Token zugeordneten Standardauthentifizierungsmechanismus überschreiben möchten.

- Wenn Sie ein benutzerdefiniertes Token erstellen.

 Dieses Beispiel zeigt Folgendes:

- Wie sich ein Client mithilfe eines Benutzername/Kennwort-Paars authentifizieren kann.

- Wie der Server die Clientanmeldeinformationen mit einem benutzerdefinierten Tokenauthentifizierer überprüfen kann.

- Gibt an, wie der WCF-Dienst Code mit dem benutzerdefinierten tokenauthentifikator verknüpft ist.

- Wie der Server mit dem X.509-Zertifikat des Servers authentifiziert werden kann.

 Dieses Beispiel zeigt auch, wie die Identität des Aufrufers nach dem benutzerdefinierten Tokenauthentifizierungsprozess von WCF aus zugänglich ist.

 Der Dienst macht einen einzelnen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit der App.conf-Konfigurationsdatei definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einem Standard-`wsHttpBinding` konfiguriert, wobei der Sicherheitsmodus auf „Nachricht“ festgelegt ist. Dies ist der Standardmodus von `wsHttpBinding`. In diesem Beispiel wird das Standard-`wsHttpBinding` auf die Verwendung der Clientbenutzernamenauthentifizierung festgelegt. Außerdem konfiguriert der Dienst das Dienstzertifikat mit `serviceCredentials`-Verhalten. Mit dem `securityCredentials`-Verhalten können Sie ein Dienstzertifikat angeben. Ein Dienstzertifikat wird von einem Client verwendet, um den Dienst zu authentifizieren und Nachrichtenschutz bereitzustellen. Die folgende Konfiguration verweist auf das Zertifikat localhost, das während des Beispielsetups installiert wird, wie im folgenden Setup beschrieben.

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

 Die Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag. Die Clientbindung wird mit dem entsprechenden `Mode` und `clientCredentialType` konfiguriert.

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

 Die Clientimplementierung legt den zu verwendenden Benutzernamen und das Kennwort fest.

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a>Benutzerdefinierter Tokenauthentifizierer
 Führen Sie die folgenden Schritte aus, um einen benutzerdefinierten Tokenauthentifizierer zu erstellen:

1. Erstellen Sie einen benutzerdefinierten Tokenauthentifizierer.

     Im Beispiel wird ein benutzerdefinierter Tokenauthentifizierer implementiert, der überprüft, ob der Benutzername ein gültiges E-Mail-Format hat. Er ermittelt den <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>. Die wichtigste Methode in dieser Klasse ist <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>. In dieser Methode überprüft der Authentifizierer das Format des Benutzernamens und kontrolliert, ob der Hostname von einer nicht autorisierten Domäne stammt. Wenn beide Bedingungen erfüllt sind, gibt er eine schreibgeschützte Auflistung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Instanzen zurück, mit der Ansprüche bereitgestellt werden, die die Informationen im Benutzernamentoken darstellen.

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

2. Geben Sie eine Autorisierungsrichtlinie an, die vom benutzerdefinierten Tokenauthentifizierer zurückgegeben wird.

     Dieses Beispiel enthält seine eigene Implementierung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, die als `UnconditionalPolicy` bezeichnet wird und Sätze von Ansprüchen und Identitäten zurückgibt, die in ihrem Konstruktor an sie übergeben wurden.

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

3. Schreiben Sie den benutzerdefinierten Sicherheitstoken-Manager.

     Mit dem <xref:System.IdentityModel.Selectors.SecurityTokenManager> wird ein <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> für bestimmte <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>-Objekte erstellt, die in der `CreateSecurityTokenAuthenticator`-Methode an ihn übergeben werden. Der Sicherheitstoken-Manager dient außerdem zum Erstellen von Tokenanbietern und Token-Serialisierungsprogrammen. Diese Vorgänge werden in diesem Beispiel jedoch nicht behandelt. In diesem Beispiel erbt der benutzerdefinierte Sicherheitstoken-Manager aus der Klasse <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> und überschreibt die Methode `CreateSecurityTokenAuthenticator`, um benutzerdefinierte Benutzernamen-Tokenauthentifizierer zurückzugeben, wenn die übergebenen Tokenanforderungen angeben, dass der Benutzernamenauthentifizierer angefordert wird.

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

4. Erstellen Sie benutzerdefinierte Dienstanmeldeinformationen.

     Die Klasse der Dienstanmeldeinformationen stellt die Anmeldeinformationen dar, die für den Dienst konfiguriert werden, und erstellt einen Sicherheitstoken-Manager, mit dem Tokenauthentifizierer, Tokenanbieter und Token-Serialisierungsprogramme abgerufen werden können.

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

5. Konfigurieren Sie den Dienst für die Verwendung der benutzerdefinierten Dienstanmeldeinformationen.

     Damit der Dienst die benutzerdefinierten Dienstanmeldeinformationen verwenden kann, wird die standardmäßige Dienstanmeldeinformationen-Klasse nach dem Abrufen des in den standardmäßigen Dienstanmeldeinformationen vorkonfigurierten Dienstzertifikats gelöscht. Anschließend wird die neue Dienstanmeldeinformationen-Instanz zum Verwenden der vorkonfigurierten Dienstzertifikate konfiguriert und zum Dienstverhalten hinzugefügt.

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 Um die Informationen zu den Aufrufern anzuzeigen, können Sie <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> verwenden, wie im folgenden Code gezeigt. <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> enthält Informationen zu den Ansprüchen des aktuellen Aufrufers.

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

## <a name="setup-batch-file"></a>Setupbatchdatei
 Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.

 Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.

- Erstellen des Serverzertifikats.

     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt. Die Variable `%SERVER_NAME%` gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. Standardmäßig lautet die Variable in dieser Batchdatei localhost.

    ```console
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate.

     Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > Die Setupbatchdatei ist darauf ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden. Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt.

#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.

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
  
3. Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält. Die Datei App.config des Diensts muss so aktualisiert werden, dass sie diesem neuen Zertifikatnamen entspricht. Erstellen Sie sie mithilfe der Datei Setup.bat, indem Sie die Variable `%SERVER_NAME%` auf den vollqualifizierten Hostnamen des Computers festlegen, auf dem der Dienst ausgeführt werden soll. Beachten Sie, dass die Datei "Setup. bat" von einem Developer-Eingabeaufforderung für Visual Studio ausgeführt werden muss, das mit Administratorrechten geöffnet wurde.  
  
4. Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients. Sie müssen diesen Schritt nur dann ausführen, wenn das Serverzertifikat von einem Aussteller stammt, der vom Client als vertrauenswürdig eingestuft wurde.  
  
5. Ändern Sie in der Datei App.config auf dem Dienstcomputer den Wert der Basisadresse, und geben Sie anstelle von localhost einen vollqualifizierten Computernamen an.  
  
6. Führen Sie auf dem Dienstcomputer service.exe an einer Eingabeaufforderung aus.  
  
7. Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
8. Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.  
  
9. Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.  
  
10. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1. Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
