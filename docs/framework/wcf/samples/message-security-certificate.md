---
title: Nachrichtensicherheitszertifikat
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
ms.openlocfilehash: 1dec66631368543eecd548ac1ec9bbcda466d746
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584847"
---
# <a name="message-security-certificate"></a>Nachrichtensicherheitszertifikat
Dieses Beispiel zeigt, wie eine Anwendung implementiert wird, die WS-Sicherheit mit X.509 v3-Zertifikatauthentifizierung für den Client verwendet und eine Serverauthentifizierung über das X.509 v3-Zertifikat des Servers erfordert. Es werden Standardeinstellungen so verwendet, dass alle Anwendungsnachrichten zwischen dem Client und dem Server signiert und verschlüsselt werden. Dieses Beispiel basiert auf [WSHttpBinding](wshttpbinding.md) und besteht aus einem Client Konsolenprogramm und einer von Internetinformationsdienste (IIS) gehosteten Dienst Bibliothek. Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Das Beispiel zeigt, wie die Authentifizierung mithilfe der Konfiguration gesteuert und wie die Identität des Aufrufers aus dem Sicherheitskontext ermittelt wird.  

```csharp
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 Der Dienst macht einen Endpunkt für die Kommunikation mit dem Dienst und einen Endpunkt für das Verfügbarmachen des WSDL-Dokuments des Diensts mithilfe des WS-MetadataExchange-Protokolls verfügbar, das in der Konfigurationsdatei (Web.config) definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einem Standard [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) Element konfiguriert, das standardmäßig die Nachrichten Sicherheit verwendet. In diesem Beispiel wird das `clientCredentialType`-Attribut auf "Certificate" festgelegt, um die Clientauthentifizierung anzufordern.  
  
```xml  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
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
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 Das Verhalten gibt die Anmeldeinformationen des Diensts an, die verwendet werden, wenn der Client den Dienst authentifiziert. Der Serverzertifikat-Antragsteller Name wird im- `findValue` Attribut im- [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) Element angegeben.  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
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
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag. Die Clientbindung wird mit dem entsprechenden Sicherheitsmodus und Authentifizierungsmodus konfiguriert. Stellen Sie beim Ausführen in einem computerübergreifenden Szenario sicher, dass die Dienstendpunktadresse entsprechend geändert wird.  
  
```xml  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
```  
  
 Die Clientimplementierung kann das zu verwendende Zertifikat entweder durch die Konfigurationsdatei oder durch Code festlegen. Im folgenden Beispiel wird gezeigt, wie das zu verwendende Zertifikat in der Konfigurationsdatei festgelegt wird.  
  
```xml  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
```  
  
 Im folgenden Beispiel wird gezeigt, wie der Dienst im Programm aufgerufen wird.  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 Mit der in den Beispielen für Nachrichtensicherheit enthaltenen Batchdatei Setup.bat können Sie den Client und den Server mit relevanten Zertifikaten zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Die Batchdatei kann in drei Modi ausgeführt werden. Um im Einzel Computer Modus auszuführen, geben Sie **Setup. bat** in einem Developer-Eingabeaufforderung für Visual Studio ein. Geben Sie für den Dienst Modus **Setup. bat Service ein.** und geben Sie für den Client Modus **Setup. bat Client**ein. Verwenden Sie den Client- und den Dienstmodus, wenn Sie das Beispiel computerübergreifend ausführen. Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas. Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:  
  
- Erstellen des Clientzertifikats.  
  
     Die folgende Zeile in der Batchdatei erstellt das Clientzertifikat. Der angegebene Clientname wird im Antragstellernamen des erstellten Zertifikats verwendet. Das Zertifikat wird im `My`-Speicher am Speicherort `CurrentUser` gespeichert.  
  
    ```bat
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
- Installieren Sie das Clientzertifikat im Speicher für vertrauenswürdige Zertifikate des Servers.  
  
     Die folgende Zeile in der Batchdatei kopiert das Clientzertifikat in den Speicher TrustedPeople des Servers, damit der Server selbst entscheiden kann, was vertrauenswürdig ist. Damit ein im Trust dpeople-Speicher installiertes Zertifikat von einem Windows Communication Foundation (WCF)-Dienst als vertrauenswürdig eingestuft wird, muss der Validierungs Modus des Client Zertifikats auf oder festgelegt werden `PeerOrChainTrust` `PeerTrust` . Wie dies mithilfe einer Konfigurationsdatei durchgeführt werden kann, wurde im vorherigen Dienstkonfigurationsbeispiel gezeigt.  
  
    ```bat
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```  
  
- Erstellen des Serverzertifikats.  
  
     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     Die Variable %SERVER_NAME% gibt den Servernamen an. Das Zertifikat wird im LocalMachine-Speicher gespeichert. Wenn die Batchdatei Setup. bat mit einem Dienst Argument (z. b. **Setup. bat-Dienst**) ausgeführt wird, enthält der% SERVER_NAME% den voll qualifizierten Domänen Namen des Computers. Andernfalls wird standardmäßig localhost verwendet.  
  
- Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.  
  
     Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- Gewähren von Berechtigungen auf dem privaten Schlüssel des Zertifikats.  
  
     In den folgenden Zeilen in der Datei "Setup. bat" wird das Serverzertifikat, das im LocalMachine-Speicher gespeichert ist, für das ASP.NET-Worker-Prozess Konto zugänglich.  
  
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
    > Wenn Sie eine nicht-U. S. English-Edition von Windows verwenden, müssen Sie die Datei "Setup. bat" Bearbeiten und den Kontonamen "NT-Autorität \ Netzwerkdienst" durch Ihr regionales Äquivalent ersetzen.  
  
> [!NOTE]
> In dieser Batchdatei verwendete Tools befinden sich entweder unter C:\Programme\Microsoft Visual Studio 8\Common7\tools oder unter C:\Programme\Microsoft SDKs\Windows\v6.0\bin. Eines dieser Verzeichnisse muss im Systempfad enthalten sein. Wenn Sie Visual Studio installiert haben, ist es am einfachsten, dieses Verzeichnis in Ihrem Pfad zu öffnen, indem Sie die Developer-Eingabeaufforderung für Visual Studio öffnen. Klicken Sie auf **Start**, und wählen Sie dann **Alle Programme**, **Visual Studio 2012**, **Tools**aus. Innerhalb dieser Eingabeaufforderung sind die entsprechenden Pfade bereits konfiguriert. Andernfalls müssen Sie dem Pfad das entsprechende Verzeichnis manuell hinzufügen.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Öffnen Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie Setup. bat aus dem Beispiel Installationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
    > [!NOTE]
    > Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie von einem Developer-Eingabeaufforderung für Visual Studio ausgeführt wird. Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable wird automatisch innerhalb einer Developer-Eingabeaufforderung für Visual Studio (2010) festgelegt.  
  
2. Überprüfen Sie den Zugriff auf den Dienst mithilfe eines Browsers, indem Sie die Adresse eingeben `http://localhost/servicemodelsamples/service.svc` .  
  
3. Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis. Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.  
  
2. Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren. Kopieren Sie auch die Dateien Setup.bat, Cleanup.bat und ImportClientCert.bat auf den Dienstcomputer.  
  
3. Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
4. Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer. Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.  
  
5. Führen Sie auf dem-Server den **Dienst Setup. bat** in einem Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus. Wenn Sie **Setup. bat** mit dem **Dienst** Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.  
  
6. Bearbeiten Sie die Datei Web. config so, dass Sie den neuen Zertifikat Namen (im-Attribut im) widerspiegelt, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist.  
  
7. Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
8. Führen Sie auf dem Client **Setup. bat Client** in einem Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus. Wenn Sie **Setup. bat** mit dem- **Client** Argument ausführen, wird ein Client Zertifikat mit dem Namen Client.com erstellt und das Client Zertifikat in eine Datei mit dem Namen Client. CER exportiert.  
  
9. Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.  
  
10. Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
11. Führen Sie auf dem Client ImportServiceCert. bat in einem Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
12. Führen Sie ImportClientCert. bat auf dem-Server in einem Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten aus. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
13. Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.  
  
    > [!NOTE]
    > Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden. Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
