---
title: Autorisierungsrichtlinie
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 3744afb20c06e1ca85b91dadde6549d87ac89337
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809663"
---
# <a name="authorization-policy"></a>Autorisierungsrichtlinie
Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte Anspruchsautorisierungsrichtlinie und ein zugeordneter benutzerdefinierter Dienstautorisierungs-Manager implementiert werden. Das ist nützlich, wenn der Dienst anspruchsbasierte Zugriffsüberprüfungen an Dienstvorgängen vornimmt und vor den Zugriffsüberprüfungen dem Aufrufer bestimmte Rechte gewährt. Dieses Beispiel zeigt sowohl den Prozess zum Hinzufügen von Ansprüchen als auch den Prozess zum Durchführen einer Zugriffsüberprüfung anhand des finalisierten Satzes von Ansprüchen. Alle Anwendungsnachrichten zwischen dem Client und dem Server werden signiert und verschlüsselt. Standardmäßig werden mit der `wsHttpBinding`-Bindung ein vom Client angegebener Benutzername und ein Kennwort zum Anmelden an einem gültigen Windows NT-Konto verwendet. In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte <!--zz <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>--> `System.IdentityModel.Selectors.UsernamePasswordValidator` zum Authentifizieren des Clients. Außerdem zeigt dieses Beispiel die Clientauthentifizierung beim Dienst mit einem X.509-Zertifikat. Dieses Beispiel zeigt eine Implementierung von <xref:System.IdentityModel.Policy.IAuthorizationPolicy> und <xref:System.ServiceModel.ServiceAuthorizationManager>, das zwischen ihnen bestimmten Benutzern Zugriff auf bestimmte Methoden des Diensts gewährt. Dieses Beispiel basiert auf der [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md), jedoch wird veranschaulicht, wie Sie eine Transformation von Ansprüchen vor dem Ausführen der <xref:System.ServiceModel.ServiceAuthorizationManager> aufgerufen werden.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Insgesamt demonstriert dieses Beispiel Folgendes:  
  
-   Der Client kann mit einem Benutzernamen und einem Kennwort authentifiziert werden.  
  
-   Der Client kann mit einem X.509-Zertifikat authentifiziert werden.  
  
-   Der Server überprüft die Clientanmeldeinformationen mithilfe eines benutzerdefinierten `UsernamePassword`-Validierungssteuerelements.  
  
-   Der Server wird mit dem X.509-Zertifikat des Servers authentifiziert.  
  
-   Der Server kann <xref:System.ServiceModel.ServiceAuthorizationManager> verwenden, um den Zugriff auf bestimmte Methoden im Dienst zu steuern.  
  
-   So wird <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementiert.  
  
 Der Dienst macht zwei Endpunkte zur Kommunikation mit dem Dienst verfügbar, die mit der Konfigurationsdatei "App.conf" definiert werden. Jeder Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die eine Bindung wird mit einer normalen `wsHttpBinding`-Bindung konfiguriert, die WS-Security und Clientbenutzernamenauthentifizierung verwendet. Die andere Bindung wird mit einer normalen `wsHttpBinding`-Bindung konfiguriert, die WS-Security und Clientzertifikatauthentifizierung verwendet. Die [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) gibt an, dass die Anmeldeinformationen des Benutzers für die Dienstauthentifizierung verwendet werden. Das Serverzertifikat muss für den gleichen Wert enthalten die `SubjectName` -Eigenschaft der `findValue` Attribut in der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
      <host>  
        <baseAddresses>  
          <!-- configure base address provided by host -->  
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>  
        </baseAddresses>  
      </host>  
      <!-- use base address provided by host, provide two endpoints -->  
      <endpoint address="username"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding1"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      <endpoint address="certificate"  
                binding="wsHttpBinding"  
                bindingConfiguration="Binding2"   
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Username binding -->  
      <binding name="Binding1">  
        <security mode="Message">  
    <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
      <!-- X509 certificate binding -->  
      <binding name="Binding2">  
        <security mode="Message">  
          <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior" >  
        <serviceDebug includeExceptionDetailInFaults ="true" />  
        <serviceCredentials>  
          <!--   
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.    
          -->  
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />  
          <!--   
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.  
          -->  
          <clientCertificate>  
            <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </clientCertificate>  
          <!--   
          The serviceCredentials behavior allows one to define a service certificate.  
          A service certificate is used by a client to authenticate the service and provide message protection.  
          This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
        </serviceCredentials>  
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
          <!--   
          The serviceAuthorization behavior allows one to specify custom authorization policies.  
          -->  
          <authorizationPolicies>  
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  
</system.serviceModel>  
```  
  
 Jede Clientendpunktkonfiguration besteht aus einem Konfigurationsnamen, einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag. Die Clientbindung wird mit dem entsprechenden Sicherheitsmodus entsprechend den Angaben in diesem Fall in konfiguriert die [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) und `clientCredentialType` nach den Angaben in der [ \<Nachricht >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- Username based endpoint -->  
      <endpoint name="Username"  
            address="http://localhost:8001/servicemodelsamples/service/username"   
    binding="wsHttpBinding"   
    bindingConfiguration="Binding1"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator" >  
      </endpoint>  
      <!-- X509 certificate based endpoint -->  
      <endpoint name="Certificate"  
                        address="http://localhost:8001/servicemodelsamples/service/certificate"   
                binding="wsHttpBinding"   
            bindingConfiguration="Binding2"   
                behaviorConfiguration="ClientCertificateBehavior"  
                contract="Microsoft.ServiceModel.Samples.ICalculator">  
      </endpoint>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- Username binding -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
        <!-- X509 certificate binding -->  
        <binding name="Binding2">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
    </wsHttpBinding>  
    </bindings>  
  
    <behaviors>  
      <behavior name="ClientCertificateBehavior">  
        <clientCredentials>  
          <serviceCertificate>  
            <!--   
            Setting the certificateValidationMode to PeerOrChainTrust  
            means that if the certificate   
            is in the user's Trusted People store, then it will be   
            trusted without performing a  
            validation of the certificate's issuer chain. This setting   
            is used here for convenience so that the   
            sample can be run without having to have certificates   
            issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust.   
            The security implications of this   
            setting should be carefully considered before using   
            PeerOrChainTrust in production code.   
            -->  
            <authentication certificateValidationMode = "PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 Für den benutzernamenbasierten Endpunkt legt die Clientimplementierung den zu verwendenden Benutzernamen und das Kennwort fest.  
  
```  
// Create a client with Username endpoint configuration  
CalculatorClient client1 = new CalculatorClient("Username");  
  
client1.ClientCredentials.UserName.UserName = "test1";  
client1.ClientCredentials.UserName.Password = "1tset";  
  
try  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client1.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
    ...  
}  
catch (Exception e)  
{  
    Console.WriteLine("Call failed : {0}", e.Message);  
}  
  
client1.Close();  
```  
  
 Für den zertifikatbasierten Endpunkt legt die Clientimplementierung das zu verwendende Clientzertifikat fest.  
  
```  
// Create a client with Certificate endpoint configuration  
CalculatorClient client2 = new CalculatorClient("Certificate");  
  
client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");  
  
try  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client2.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
    ...  
}  
catch (Exception e)  
{  
    Console.WriteLine("Call failed : {0}", e.Message);  
}  
  
client2.Close();  
```  
  
 In diesem Beispiel wird ein benutzerdefinierter <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> verwendet, um Benutzernamen und Kennwörter zu überprüfen. Das Beispiel implementiert `MyCustomUserNamePasswordValidator`, das von <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> abgeleitet ist. Weitere Informationen zu <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> finden Sie in der Dokumentation. Um die Integration mit dem <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> zu demonstrieren, implementiert dieses benutzerdefinierte Validierungssteuerelement-Beispiel die <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>-Methode zum Entgegennehmen von Kombinationen aus Benutzername und Kennwort, wobei der Benutzername wie im folgenden Code gezeigt mit dem Kennwort übereinstimmt.  
  
```  
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator  
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
      throw new SecurityTokenException("Unknown Username or Password");  
    }  
  }  
}  
```  
  
 Nachdem das Validierungssteuerelement im Dienstcode implementiert ist, muss der Diensthost über die zu verwendende Validierungssteuerelementinstanz informiert werden. Dies wird mit dem folgenden Code durchgeführt.  
  
```  
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;  
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();  
```  
  
 Sie können dasselbe aber auch in der Konfiguration vornehmen.  
  
```xml  
<behavior ...>  
    <serviceCredentials>  
      <!--   
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.    
      -->  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />  
    ...  
    </serviceCredentials>  
</behavior>  
```  
  
 Windows Communication Foundation (WCF) stellt eine umfangreiche anspruchsbasiertes Modell zum Durchführen von zugriffsüberprüfungen bereit. Das <xref:System.ServiceModel.ServiceAuthorizationManager>-Objekt wird verwendet, um die Zugriffsüberprüfung durchzuführen und zu bestimmen, ob die dem Client zugeordneten Ansprüche die Anforderungen erfüllen, die für den Zugriff auf die Dienstmethode erforderlich sind.  
  
 Für die Zwecke der Demo können Sie dieses Beispiel zeigt eine Implementierung von <xref:System.ServiceModel.ServiceAuthorizationManager> , implementiert die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> Methode, um ein Benutzer den Zugriff auf Methoden ermöglichen auf der Grundlage von Ansprüchen des Typs http://example.com/claims/allowedoperation , dessen Wert ist der Aktions-URI des Vorgangs, der Sie können aufgerufen werden.  
  
```  
public class MyServiceAuthorizationManager : ServiceAuthorizationManager  
{  
  protected override bool CheckAccessCore(OperationContext operationContext)  
  {                  
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;  
    Console.WriteLine("action: {0}", action);  
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)  
    {  
      if ( cs.Issuer == ClaimSet.System )  
      {  
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))  
        {  
          Console.WriteLine("resource: {0}", c.Resource.ToString());  
          if (action == c.Resource.ToString())  
            return true;  
        }  
      }  
    }  
    return false;                   
  }  
}  
```  
  
 Wenn der benutzerdefinierte <xref:System.ServiceModel.ServiceAuthorizationManager> implementiert ist, muss der Diensthost über den zu verwendenden <xref:System.ServiceModel.ServiceAuthorizationManager> informiert werden. Dies wird wie im folgenden Code gezeigt durchgeführt.  
  
```xml  
<behavior ...>  
    ...  
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
        ...  
    </serviceAuthorization>  
</behavior>  
```  
  
 Die primäre <xref:System.IdentityModel.Policy.IAuthorizationPolicy>-Methode, die implementiert werden soll, ist die <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>-Methode.  
  
```  
public class MyAuthorizationPolicy : IAuthorizationPolicy  
{  
    string id;  
  
    public MyAuthorizationPolicy()  
    {  
    id =  Guid.NewGuid().ToString();  
    }  
  
    public bool Evaluate(EvaluationContext evaluationContext,   
                                            ref object state)  
    {  
        bool bRet = false;  
        CustomAuthState customstate = null;  
  
        if (state == null)  
        {  
            customstate = new CustomAuthState();  
            state = customstate;  
        }  
        else  
            customstate = (CustomAuthState)state;  
        Console.WriteLine("In Evaluate");  
        if (!customstate.ClaimsAdded)  
        {  
           IList<Claim> claims = new List<Claim>();  
  
           foreach (ClaimSet cs in evaluationContext.ClaimSets)  
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,   
                                         Rights.PossessProperty))  
                  foreach (string s in   
                        GetAllowedOpList(c.Resource.ToString()))  
                  {  
                       claims.Add(new  
               Claim("http://example.com/claims/allowedoperation",   
                                    s, Rights.PossessProperty));  
                            Console.WriteLine("Claim added {0}", s);  
                      }  
                   evaluationContext.AddClaimSet(this,   
                           new DefaultClaimSet(this.Issuer,claims));  
                   customstate.ClaimsAdded = true;  
                   bRet = true;  
                }  
         else  
         {  
              bRet = true;  
         }  
         return bRet;  
     }  
...  
}  
```  
  
 Der oben aufgeführte Code zeigt, wie die <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>-Methode prüft, dass keine neuen Ansprüche hinzugefügt wurden, die sich auf die Verarbeitung auswirken, und bestimmte Ansprüche hinzufügt. Die Ansprüche, die zulässig sind, werden aus der `GetAllowedOpList`-Methode abgerufen, die so implementiert ist, dass sie eine Liste der Vorgänge zurückgibt, die der Benutzer ausführen darf. Die Autorisierungsrichtlinie fügt Ansprüche zum Zugreifen auf den jeweiligen Vorgang hinzu. Dies wird später vom <xref:System.ServiceModel.ServiceAuthorizationManager> verwendet, um Zugriffsprüfungsentscheidungen auszuführen.  
  
 Wenn der benutzerdefinierte <xref:System.IdentityModel.Policy.IAuthorizationPolicy> implementiert ist, muss der Diensthost über die zu verwendenden Autorisierungsrichtlinien informiert werden.  
  
```xml  
<serviceAuthorization ...>  
       <authorizationPolicies>   
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />  
       </authorizationPolicies>   
</serviceAuthorization>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Der Client ruft erfolgreich die Add-, Subtract- und Multiple-Methoden auf und erhält beim Versuch, die Divide-Methode aufzurufen, eine Nachricht vom Typ "Zugriff verweigert". Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
## <a name="setup-batch-file"></a>Setupbatchdatei  
 Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.  
  
 Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:  
  
-   Erstellen des Serverzertifikats.  
  
     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt. Die Variable %SERVER_NAME% gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. Der Standardwert ist localhost.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   Installieren des Serverzertifikats in den Clientspeicher für vertrauenswürdige Zertifikate.  
  
     Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von Makecert.exe generierten Zertifikaten nicht implizit vom Clientsystem vertraut wird. Wenn Sie bereits über ein Zertifikat verfügen, dass von einem vertrauenswürdigen Clientstammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   Erstellen des Clientzertifikats.  
  
     Die folgenden Zeilen aus der Batchdatei Setup.bat erstellen das zu verwendende Clientzertifikat. Die Variable %USER_NAME% gibt den Servernamen an. Dieser Wert wird auf "test1" festgelegt, da dies der Name ist, nach dem die `IAuthorizationPolicy` sucht. Wenn Sie den Wert  von % USER_NAME% ändern, müssen Sie in der `IAuthorizationPolicy.Evaluate`-Methode den entsprechenden Wert ändern.  
  
     Das Zertifikat wird im persönlichen Speicher unterhalb von CurrentUser gespeichert.  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   Installieren des Clientzertifikats in den Serverspeicher für vertrauenswürdige Zertifikate.  
  
     Die folgenden Zeilen in der Batchdatei Setup.bat kopieren das Clientzertifikat in den Speicher für vertrauenswürdige Personen. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierten Zertifikaten nicht implizit vom Serversystem vertraut wird. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Stammzertifikat abstammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Auffüllen des Serverzertifikatspeichers mit dem Clientzertifikat nicht erforderlich.  
  
    ```  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es  
  
1.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend auszuführen, befolgen Sie die folgenden Anweisungen.  
  
> [!NOTE]
>  Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1.  Öffnen Sie eine [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung mit Administratorrechten, und führen Sie Setup.bat aus dem Beispielinstallationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
    > [!NOTE]
    >  Die Batchdatei Setup.bat ist darauf ausgelegt, an einer [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung ausgeführt zu werden. Die innerhalb der [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung festgelegte PATH-Umgebungsvariable zeigt auf das Verzeichnis mit den ausführbaren Dateien, die für das Skript Setup.bat erforderlich sind.  
  
2.  Führen Sie Setup.bat aus dem Beispielinstallationsordner an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
3.  Starten Sie Service.exe aus dem Ordner \service\bin.  
  
4.  Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
5.  Wenn Client und Dienst nicht miteinander kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1.  Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.  
  
2.  Kopieren Sie die Dienstprogrammdateien aus \service\bin in das Verzeichnis auf dem Dienstcomputer. Kopieren Sie außerdem die Dateien Setup.bat, Cleanup.bat, GetComputerName.vbs und ImportClientCert.bat auf den Dienstcomputer.  
  
3.  Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
4.  Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer. Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.  
  
5.  Führen Sie auf dem Server `setup.bat service` an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Ausführen `setup.bat` mit der `service` Argument erstellt ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und Exporte das Dienstzertifikat in eine Datei "Service.cer" exportiert.  
  
6.  Bearbeiten Service.exe.config, um den neuen Zertifikatnamen entspricht (in der `findValue` Attribut in der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) die ist identisch mit den vollqualifizierten Domänennamen des Computers. Ändern Sie auch den Computernamen im die \<Service > /\<BaseAddresses >-Element von "localhost" auf den vollqualifizierten Namen Ihres dienstcomputers.  
  
7.  Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
8.  Führen Sie auf dem Client `setup.bat client` an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Ausführen `setup.bat` mit der `client` Argument wird ein Clientzertifikat mit dem Namen test1 erstellt und das Clientzertifikat in der Datei Client.cer exportiert.  
  
9. Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.  
  
10. Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
11. Führen Sie auf dem Client ImportServiceCert.bat an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
12. Führen Sie auf dem Server ImportClientCert.bat an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
13. Starten Sie auf dem Servercomputer Service.exe in einem Eingabeaufforderungsfenster.  
  
14. Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster. Wenn Client und Dienst nicht miteinander kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1.  Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben. Dadurch werden die Server- und Clientzertifikate aus dem Zertifikatspeicher entfernt.  
  
> [!NOTE]
>  Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie über WCF-Beispiele, die Zertifikate computerübergreifend verwenden, achten Sie darauf, dass Sie die Dienstzertifikate entfernen, die in den Speicher CurrentUser – installiert wurden ausgeführt haben, TrustedPeople speichern. Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="see-also"></a>Siehe auch
