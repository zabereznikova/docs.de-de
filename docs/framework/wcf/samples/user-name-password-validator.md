---
title: Benutzernamen- und Kennwort-Validierungssteuerelement
ms.date: 03/30/2017
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
ms.openlocfilehash: 553ccd69a02e057c5131128378611a19502e713d
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424158"
---
# <a name="user-name-password-validator"></a>Benutzernamen- und Kennwort-Validierungssteuerelement
Dieses Beispiel veranschaulicht, wie ein benutzerdefiniertes UserNamePassword-Validierungssteuerelement implementiert wird. Dies ist nützlich, wenn keines der integrierten UserNamePassword-Validierungsmodi den Anforderungen der Anwendung entspricht (z. B. wenn Benutzername/Kennwort-Paare in externen Speichern wie einer Datenbank gespeichert werden). In diesem Beispiel wird ein Dienst gezeigt, der ein benutzerdefiniertes Validierungssteuerelement enthält, das auf zwei bestimmte Benutzername/Kennwort-Paare überprüft. Der Client verwendet solch ein Benutzername/Kennwort-Paar, um sich beim Dienst zu authentifizieren.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
> Da jeder eine Benutzername-Anmeldeinformation mit den Benutzername/Kennwort-Paaren erstellen kann, die das benutzerdefinierte Steuerelement akzeptiert, ist der Dienst weniger sicher als das Standardverhalten des normalen UserNamePassword-Validierungssteuerelements. Das normale UserNamePassword-Validierungssteuerelement versucht, das angegebene Benutzername/Kennwort-Paar einem Windows-Konto zuzuordnen. Schlägt diese Zuordnung fehl, wird die Authentifizierung mit einem Fehler abgebrochen. Das benutzerdefinierte UserNamePassword-Validierungssteuerelement aus diesem Beispiel DARF NICHT in Produktionscode verwendet werden, es dient nur zur Veranschaulichung.

 Insgesamt zeigt dieses Beispiel Folgendes:

- Der Client kann mit einem Benutzernamentoken authentifiziert werden.

- Der Server überprüft die Clientanmeldeinformationen anhand eines benutzerdefinierten UserNamePasswordValidator und wie benutzerdefinierte Fehler aus der Logik zur Validierung von Benutzername und Kennwort an den Client weitergegeben werden.

- Der Server wird mit dem X.509-Zertifikat des Servers authentifiziert.

 Der Dienst macht einen einzelnen Endpunkt für die Kommunikation mit dem Dienst verfügbar, der mithilfe der Konfigurationsdatei "App. config" definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einem Standard `wsHttpBinding` konfiguriert, der standardmäßig WS-Security und username-Authentifizierung verwendet. Das Dienstverhalten gibt den `Custom`-Modus zum Überprüfen von Benutzername/Kennwort-Paaren zusammen mit dem Typ der Validierungssteuerelementklasse an. Das Verhalten gibt auch das Serverzertifikat mit dem `serviceCertificate`-Element an. Das Serverzertifikat muss den gleichen Wert für die `SubjectName` enthalten wie die `findValue` im [\<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <!-- use host/baseAddresses to configure base address provided by host -->
      <host>
        <baseAddresses>
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />
        </baseAddresses>
      </host>
      <!-- use base address specified above, provide one endpoint -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- username binding -->
      <binding name="Binding">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceDebug includeExceptionDetailInFaults ="true"/>
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to
          specify a custom validator for username/password
          combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom"
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

 Die Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag. Die Clientbindung wird mit dem entsprechenden Modus und der `clientCredentialType`-Nachricht konfiguriert.

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
address="http://localhost:8001/servicemodelsamples/service/username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
```

 Die Clientimplementierung fordert den Benutzer auf, einen Benutzernamen und ein Kennwort einzugeben.

```csharp
// Get the username and password
Console.WriteLine("Username authentication required.");
Console.WriteLine("Provide a username.");
Console.WriteLine("   Enter username: (test1)");
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
            password = password.Substring(0, password.Length - 1);
        }
        info = Console.ReadKey(true);
    }
}
for (int i = 0; i < password.Length; i++)
{
    Console.Write("*");
}
Console.WriteLine();
// Create a proxy with Certificate endpoint configuration
CalculatorProxy proxy = new CalculatorProxy("Username")
try
{
  proxy.ClientCredentials.Username.Username = username;
  proxy.ClientCredentials.Username.Password = password;
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = proxy.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
  }
  catch (Exception e)
  {
      Console.WriteLine("Call failed:");
      while (e != null)
      {
          Console.WriteLine("\t{0}", e.Message);
          e = e.InnerException;
      }
      proxy.Abort();
  }
}
```

 In diesem Beispiel wird ein benutzerdefinierter UserNamePasswordValidator verwendet, um Benutzername/Kennwort-Paare zu überprüfen. Das Beispiel implementiert `CustomUserNamePasswordValidator`, das von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> abgeleitet ist. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Dieses Beispiel zu einem benutzerdefinierten Validierungssteuerelement implementiert die `Validate`-Methode zum Akzeptieren zweier bestimmter Benutzername/Kennwort-Paare, wie im folgenden Code gezeigt.

```csharp
public class CustomUserNameValidator : UserNamePasswordValidator
{
 // This method validates users. It allows in two users,
 // test1 and test2 with passwords 1tset and 2tset respectively.
 // This code is for illustration purposes only and
 // MUST NOT be used in a production environment because it
 // is NOT secure.
 public override void Validate(string userName, string password)
 {
  if (null == userName || null == password)
  {
   throw new ArgumentNullException();
  }

  if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
  {
   throw new FaultException("Unknown Username or Incorrect Password");
   }
  }
 }
```

 Nachdem das Validierungssteuerelement im Dienstcode implementiert ist, muss der Diensthost über die zu verwendende Validierungssteuerelementinstanz informiert werden. Dies wird mit dem folgenden Code durchgeführt.

```csharp
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();
```

 Sie können dasselbe aber auch wie folgt in der Konfiguration vornehmen.

```xml
<behaviors>
 <serviceBehaviors>
  <behavior name="CalculatorServiceBehavior">
  ...
   <serviceCredentials>
    <!--
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.
    -->
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />
   ...
  </behavior>
 </serviceBehaviors>
</behaviors>
```

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Der Client sollte alle Methoden erfolgreich aufrufen. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.

## <a name="setup-batch-file"></a>Setupbatchdatei
 Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Diese Batchdatei muss so geändert werden, dass sie computerübergreifend oder in einem nicht selbst gehosteten Fall funktioniert.

 Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.

- Erstellen des Serverzertifikats

     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt. Die Variable %SERVER_NAME% gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. Der Standardwert ist localhost.

    ```console
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

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es

1. Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.

2. Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, folgen Sie den folgenden Anweisungen.

#### <a name="to-run-the-sample-on-the-same-machine"></a>So führen Sie das Beispiel auf demselben Computer aus

1. Führen Sie Setup. bat aus dem Beispiel Installationsordner innerhalb einer Visual Studio 2012-Eingabeaufforderung aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.

    > [!NOTE]
    > Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird. Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.  
  
2. Starten Sie Service.exe aus dem Ordner \service\bin.  
  
3. Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-run-the-sample-across-machines"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.  
  
2. Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Dienstcomputer. Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.  
  
3. Sie benötigen ein Serverzertifikat mit dem Antragstellernamen, das den vollqualifizierten Domänennamen des Computers enthält. Die Konfigurationsdatei für den Server muss entsprechend aktualisiert werden, dass sie diesen neuen Zertifikatsnamen wiedergibt.  
  
4. Kopieren Sie das Serverzertifikat in den Speicher CurrentUser – TrustedPeople des Clients. Dies ist nur dann erforderlich, wenn das Serverzertifikat nicht von einem vertrauenswürdigen Aussteller ausgegeben wurde.  
  
5. Ändern Sie in der Datei "App.config" auf dem Dienstcomputer den Wert der Basisadresse, um anstelle von "localhost" einen vollqualifizierten Computernamen anzugeben.  
  
6. Starten Sie auf dem Dienstcomputer Service.exe in einem Eingabeaufforderungsfenster.  
  
7. Kopieren Sie die Clientprogrammdateien aus dem Ordner "\client\bin\" (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
8. Ändern Sie in der Datei "Client.exe.config" auf dem Clientcomputer den Wert für die Adresse des Endpunkts so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt.  
  
9. Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.  
  
10. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1. Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben. Dadurch wird das Serverzertifikat aus dem Zertifikatspeicher entfernt.  
