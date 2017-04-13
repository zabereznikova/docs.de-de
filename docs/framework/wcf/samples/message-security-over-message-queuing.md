---
title: "Nachrichtensicherheit &#252;ber Message Queuing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 329aea9c-fa80-45c0-b2b9-e37fd7b85b38
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Nachrichtensicherheit &#252;ber Message Queuing
Dieses Beispiel zeigt, wie eine Anwendung implementiert wird, in der WS\-Sicherheit mit X.509v3\-Zertifikatauthentifizierung für den Client verwendet wird, und die eine Serverauthentifizierung mit dem X.509v3\-Zertifikat des Servers über MSMQ erfordert.Nachrichtensicherheit wird manchmal vorgezogen, um sicherzustellen, dass die Nachrichten im MSMQ\-Speicher verschlüsselt bleiben und die Anwendung ihre eigene Authentifizierung der Nachricht ausführt.  
  
 Dieses Beispiel basiert auf dem Beispiel [Abgewickelte MSMQ\-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).Die Nachrichten werden verschlüsselt und signiert.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Wenn der Dienst zuerst ausgeführt wird, wird überprüft, ob die Warteschlange vorhanden ist.Ist die Warteschlange nicht vorhanden, wird sie vom Dienst erstellt.Sie können zuerst den Dienst ausführen, um die Warteschlange zu erstellen, oder Sie können sie über den MSMQ\-Warteschlangen\-Manager erstellen.Führen Sie zum Erstellen einer Warteschlange in Windows 2008 die folgenden Schritte aus:  
  
    1.  Öffnen Sie Server\-Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Erweitern Sie die Registerkarte **Funktionen**.  
  
    3.  Klicken Sie mit der rechten Maustaste auf **Private Meldungswarteschlangen**, und klicken Sie anschließend auf **Neu** und **Private Warteschlange**.  
  
    4.  Aktivieren Sie das Kontrollkästchen **Transaktional**.  
  
    5.  Geben Sie `ServiceModelSamplesTransacted` als Namen der neuen Warteschlange ein.  
  
3.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### So führen Sie das Beispiel auf demselben Computer aus  
  
1.  Vergewissern Sie sich, dass der Pfad den Ordner enthält, in dem sich die Dateien Makecert.exe und FindPrivateKey.exe befinden.  
  
2.  Führen Sie "Setup.bat" im Beispielinstallationsordner aus.Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
    > [!NOTE]
    >  Wenn Sie mit dem Beispiel fertig sind, müssen Sie die Datei Cleanup.bat ausführen, um die Zertifikate zu entfernen.In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
3.  Starten Sie Service.exe aus dem Ordner \\service\\bin.  
  
4.  Starten Sie Client.exe aus dem Ordner \\client\\bin.In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
5.  Wenn der Client und der Dienst nicht miteinander kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](http://msdn.microsoft.com/de-de/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### So führen Sie das Beispiel computerübergreifend aus  
  
1.  Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportClientCert.bat auf den Dienstcomputer.  
  
2.  Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
3.  Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.  
  
4.  Führen Sie auf dem Server `setup.bat service` aus.Durch Ausführen von `setup.bat` mit dem Argument `service` wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und in die Datei Service.cer exportiert.  
  
5.  Bearbeiten Sie die Datei service.exe.config des Diensts so, dass sie den neuen Zertifikatnamen \(im `findValue`\-Attribut im [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\) enthält, der dem vollqualifizierten Domänennamen des Computers entspricht.  
  
6.  Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
7.  Führen Sie auf dem Client `setup.bat client` aus.Durch Ausführen von `setup.bat` mit dem Argument `client` wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.  
  
8.  Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers.Sie müssen auch den Zertifikatnamen des Diensts so ändern, dass er mit dem vollqualifizierten Domänennamen des Dienstcomputers übereinstimmt \(im `findValue`\-Attribut im `defaultCertificate`\-Element von `serviceCertificate` unter `clientCredentials`\).  
  
9. Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
10. Führen Sie auf dem Client `ImportServiceCert.bat` aus.Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
11. Führen Sie auf dem Server `ImportClientCert.bat` aus. Dadurch wird das Clientzertifikat aus der Datei Client.cer in den Speicher LocalMachine – TrustedPeople importiert.  
  
12. Starten Sie auf dem Dienstcomputer Service.exe an einer Eingabeaufforderung.  
  
13. Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.Wenn der Client und der Dienst nicht miteinander kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](http://msdn.microsoft.com/de-de/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    >  Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.Wenn Sie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Beispiele ausgeführt haben, die Zertifikate computerübergreifend verwenden, müssen Sie die Dienstzertifikate entfernen, die im Speicher CurrentUser – TrustedPeople installiert wurden.Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## Anforderungen  
 Für dieses Beispiel ist es erforderlich, dass MSMQ installiert ist und ausgeführt wird.  
  
## Veranschaulicht  
 Der Client verschlüsselt die Nachricht mit dem öffentlichen Schlüssel des Diensts und signiert sie mit seinem eigenen Zertifikat.Der Dienst, der die Nachricht aus der Warteschlange liest, authentifiziert das Clientzertifikat mit dem Zertifikat in seinem Speicher für vertrauenswürdige Personen.Anschließend entschlüsselt er die Nachricht und leitet sie an den Dienstvorgang weiter.  
  
 Da die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Nachricht als Nutzlast im Text der MSMQ\-Nachricht enthalten ist, bleibt der Text im MSMQ\-Speicher verschlüsselt.Dadurch wird sichergestellt, dass die Nachricht von unerwünschter Seite aus eingesehen werden kann.Beachten Sie, dass es für MSMQ selbst keine Rolle spielt, ob die enthaltene Nachricht verschlüsselt ist.  
  
 Im Beispiel wird veranschaulicht, wie gegenseitige Authentifizierung auf Nachrichtenebene mit MSMQ verwendet werden kann.Die Zertifikate werden "Out\-of\-Band" ausgetauscht.Dies ist bei Anwendungen in einer Warteschlange stets der Fall, da der Dienst und der Client nicht zum selben Zeitpunkt aktiv sein müssen.  
  
## Beschreibung  
 Der Beispielclient\- und Dienstcode sind bis auf einen Unterschied mit dem aus dem Beispiel [Abgewickelte MSMQ\-Bindung](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) identisch.Der Vorgangsvertrag ist mit einer Schutzebene versehen, die anzeigt, dass die Nachricht signiert und verschlüsselt werden muss.  
  
```  
// Define a service contract.   
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```  
  
 Um sicherzustellen, dass die Nachricht mit dem erforderlichen Token zum Identifizieren des Diensts und des Clients gesichert wird, enthält die "App.config" Anmeldeinformationen.  
  
 Die Clientkonfiguration gibt das Dienstzertifikat zum Authentifizieren des Diensts an.Dabei wird der eigene LocalMachine\-Speicher als vertrauenswürdiger Speicher verwendet, damit die Gültigkeit des Diensts sichergestellt ist.Außerdem wird das Clientzertifikat angegeben, das zur Dienstauthentifizierung des Clients an die Nachricht angefügt wird.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <system.serviceModel>  
  
    <client>  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"   
                binding="netMsmqBinding"   
                bindingConfiguration="messageSecurityBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor"  
                behaviorConfiguration="ClientCertificateBehavior" />  
    </client>  
  
    <bindings>  
        <netMsmqBinding>  
            <binding name="messageSecurityBinding">  
                <security mode="Message">  
                    <message clientCredentialType="Certificate"/>  
                </security>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
                <defaultCertificate findValue="localhost" storeLocation="CurrentUser" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it is trusted without performing a  
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
</configuration>  
```  
  
 Beachten Sie, dass der Sicherheitsmodus auf "Nachricht" und der ClientCredentialType auf "Zertifikat" festgelegt werden.  
  
 Die Dienstkonfiguration enthält ein Dienstverhalten, das die Anmeldeinformationen des Diensts angibt, die beim Authentifizieren des Diensts durch den Client verwendet werden.Der Serverzertifikat\-Antragstellername wird im `findValue`\-Attribut im [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) angegeben.  
  
```  
  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName" value=".\private$\ServiceModelSamplesMessageSecurity" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService"  
          behaviorConfiguration="PurchaseOrderServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesMessageSecurity"  
                  binding="netMsmqBinding"  
                  bindingConfiguration="messageSecurityBinding"  
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
        <netMsmqBinding>  
            <binding name="messageSecurityBinding">  
                <security mode="Message">  
                    <message clientCredentialType="Certificate" />  
                </security>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="PurchaseOrderServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <!--   
               The serviceCredentials behavior allows one to define a service certificate.  
               A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
               This configuration references the "localhost" certificate installed during the setup instructions.  
          -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
                <certificate findValue="client.com" storeLocation="LocalMachine" storeName="TrustedPeople" x509FindType="FindBySubjectName"/>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it is trusted without performing a  
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
  
</configuration>  
  
```  
  
 Das Beispiel zeigt, wie die Authentifizierung mithilfe der Konfiguration gesteuert und wie die Identität des Aufrufers aus dem Sicherheitskontext ermittelt wird:  
  
```  
    // Service class which implements the service contract.  
    // Added code to write output to the console window.  
    public class OrderProcessorService : IOrderProcessor  
    {  
        private string GetCallerIdentity()  
        {  
            // The client certificate is not mapped to a Windows identity by default.  
            // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
            // in the certificate that the client used to authenticate itself to the service.  
            return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void SubmitPurchaseOrder(PurchaseOrder po)  
        {  
            Console.WriteLine("Client's Identity {0} ", GetCallerIdentity());  
            Orders.Add(po);  
            Console.WriteLine("Processing {0} ", po);  
        }  
  //…  
}  
```  
  
 Beim Ausführen zeigt der Dienstcode die Clientidentifikation an.Nachfolgend sehen Sie eine Beispielausgabe vom Dienstcode:  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Client's Identity CN=client.com; ECA6629A3C695D01832D77EEE836E04891DE9D3C  
Processing Purchase Order: 6536e097-da96-4773-9da3-77bab4345b5d  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
## Kommentare  
  
-   Erstellen des Clientzertifikats.  
  
     Die folgende Zeile in der Batchdatei erstellt das Clientzertifikat.Der angegebene Clientname wird im Antragstellernamen des erstellten Zertifikats verwendet.Das Zertifikat wird im `My`\-Speicher am Speicherort `CurrentUser` gespeichert.  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
  
    ```  
  
-   Installieren des Clientzertifikats in den Serverspeicher für vertrauenswürdige Zertifikate.  
  
     Die folgende Zeile in der Batchdatei kopiert das Clientzertifikat in den TrustedPeople\-Speicher des Servers, damit der Server selbst entscheiden kann, was vertrauenswürdig ist und was nicht.Damit ein im Speicher TrustedPeople installiertes Zertifikat für einen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienst vertrauenswürdig ist, muss der Clientzertifikat\-Validierungsmodus auf den Wert `PeerOrChainTrust` oder `PeerTrust` festgelegt werden.Wie dies mithilfe einer Konfigurationsdatei durchgeführt werden kann, wurde im vorherigen Dienstkonfigurationsbeispiel gezeigt.  
  
    ```  
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
  
    ```  
  
-   Erstellen des Serverzertifikats.  
  
     Die folgenden Zeilen aus der Batchdatei "Setup.bat" erstellen das zu verwendende Serverzertifikat:  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     Die Variable %SERVER\_NAME% gibt den Servernamen an.Das Zertifikat wird im LocalMachine\-Speicher gespeichert.Wenn die Setupbatchdatei mit einem Dienstargument ausgeführt wird \(wie `setup.bat service`\), enthält %SERVER\_NAME% den vollqualifizierten Domänennamen des Computers.Andernfalls wird standardmäßig localhost verwendet.  
  
-   Installieren des Serverzertifikats im Clientspeicher für vertrauenswürdige Zertifikate.  
  
     Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen.Dieser Schritt ist erforderlich, da von Makecert.exe generierten Zertifikaten nicht implizit vom Clientsystem vertraut wird.Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt \(z. B. ein von Microsoft ausgegebenes Zertifikat\), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
    > [!NOTE]
    >  Bei Verwendung einer anderen als derenglischsprachigen US\-Version von Microsoft Windows müssen Sie in der Datei Setup.bat den Kontonamen "NT AUTHORITY\\NETWORK SERVICE" durch den äquivalenten Kontonamen in der entsprechenden Sprache ersetzen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\MessageSecurity`  
  
## Siehe auch