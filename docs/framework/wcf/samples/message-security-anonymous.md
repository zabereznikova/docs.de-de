---
title: "Nachrichtensicherheit – anonym"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
caps.latest.revision: "52"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 769869fb00c5cc8352ebe8c3952b3d7a9aa75abc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-anonymous"></a>Nachrichtensicherheit – anonym
Das Beispiel "Nachrichtensicherheit – anonym" zeigt, wie eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung implementiert wird, die Sicherheit auf Nachrichtenebene ohne Clientauthentifizierung verwendet, aber Serverauthentifizierung mithilfe des Serverzertifikats X.509 erfordert. Alle Anwendungsnachrichten zwischen dem Client und dem Server werden signiert und verschlüsselt. Dieses Beispiel basiert auf der [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) Beispiel. Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll). Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dieses Beispiel fügt einen neuen Vorgang zur Rechnerschnittstelle hinzu, der `True` zurückgibt, wenn der Client nicht authentifiziert wurde.  
  
```  
public class CalculatorService : ICalculator  
{  
    public bool IsCallerAnonymous()  
    {  
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.  
        return ServiceSecurityContext.Current.IsAnonymous;  
    }  
    ...  
}  
```  
  
 Der Dienst macht einen einzigen Endpunkt zur Kommunikation mit dem Dienst verfügbar, der mit einer Konfigurationsdatei (Web.conf) definiert wird. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einer `wsHttpBinding`-Bindung konfiguriert. Der Standardsicherheitsmodus für die `wsHttpBinding`-Bindung ist `Message`. Das `clientCredentialType`-Attribut ist auf `None` festgelegt.  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
     <!--   
     <!--This configuration defines the security mode as Message and-->  
     <!--the clientCredentialType as None. This mode provides -- >  
     <!--server authentication only using the service certificate.-->  
  
     <binding>  
       <security mode="Message">  
         <message clientCredentialType="None" />  
       </security>  
     </binding>  
    </wsHttpBinding>  
  </bindings>  
  ...  
</system.serviceModel>  
```  
  
 Die Anmeldeinformationen für die Dienstauthentifizierung zu verwendende werden angegeben, der [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md). Der Wert für `SubjectName` des Serverzertifikats muss dem Wert des `findValue`-Attributs entsprechen (wie in folgendem Beispielcode gezeigt).  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>  
      <!--   
    The serviceCredentials behavior allows you to define a service certificate.  
    A service certificate is used by a client to authenticate the service and provide message protection.  
    This configuration references the "localhost" certificate installed during the setup instructions.  
    -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
      </serviceCredentials>  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Die Clientendpunktkonfiguration besteht aus einer absoluten Adresse für den Dienstendpunkt, der Bindung und dem Vertrag. Der Clientsicherheitsmodus für die `wsHttpBinding`-Bindung ist `Message`. Das `clientCredentialType`-Attribut ist auf `None` festgelegt.  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
             address="http://localhost/servicemodelsamples/service.svc"   
             binding="wsHttpBinding"   
             behaviorConfiguration="ClientCredentialsBehavior"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--This configuration defines the security mode as -->  
      <!--Message and the clientCredentialType as None. -->  
      <binding name="Binding1">  
        <security mode = "Message">  
          <message clientCredentialType="None"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>   
  ...  
</system.serviceModel>  
```  
  
 Das Beispiel setzt den <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> für die Authentifizierung des Dienstzertifikats auf <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust>. Dies erfolgt in der Datei "App.config" des Clients im Abschnitt `behaviors`. Wenn sich das Zertifikat also im Speicher für vertrauenswürdige Personen des Benutzers befindet, wird es als vertrauenswürdig eingestuft wird, ohne dass eine Validierung der Ausstellerkette des Zertifikats erfolgt. Diese Einstellung wird hier der Einfachheit halber verwendet. So kann das Beispiel ausgeführt werden, ohne dass Zertifikate erforderlich sind, die von einer Zertifizierungsstelle ausgestellt wurden. Diese Einstellung ist weniger sicher als die Standardeinstellung ChainTrust. Die aus dieser Einstellung resultierenden Sicherheitsauswirkungen sollten sorgfältig bedacht werden, bevor `PeerOrChainTrust` im Produktionscode verwendet wird.  
  
 Die Clientimplementierung Fügt einen Aufruf der `IsCallerAnonymous` Methode, und andernfalls unterscheidet sich nicht von der [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) Beispiel.  
  
```  
// Create a client with a client endpoint configuration.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity operation.  
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
...  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
IsCallerAnonymous returned: True  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 Mit der im Beispiel "Nachrichtensicherheit – anonym" enthaltenen Batchdatei Setup.bat können Sie den Server mit einem relevanten Zertifikat zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Die Batchdatei kann in zwei Modi ausgeführt werden. Um die Batchdatei im Einzelcomputermodus auszuführen, geben Sie in der Befehlszeile `setup.bat` ein. Um sie im Dienstmodus auszuführen, geben Sie `setup.bat service` ein. Verwenden Sie diesen Modus, wenn Sie das Beispiel computerübergreifend ausführen. Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas.  
  
 Im Folgenden wird eine kurze Übersicht über die verschiedenen Abschnitte der Batchdateien bereitgestellt:  
  
-   Erstellen des Serverzertifikats.  
  
     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     Die Variable %SERVER_NAME% gibt den Servernamen an. Das Zertifikat wird im LocalMachine-Speicher gespeichert. Wenn die Setupbatchdatei mit dem service-Argument ausgeführt wird (z. B. `setup.bat service`), enthält %SERVER_NAME% den vollqualifizierten Domänennamen des Computers. Andernfalls wird standardmäßig localhost verwendet.  
  
-   Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.  
  
     Die folgenden Zeilen kopieren das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   Gewähren von Berechtigungen auf dem privaten Schlüssel des Zertifikats.  
  
     Die folgenden Zeilen in der Batchdatei Setup.bat sorgen dafür, dass das Serverzertifikat, das im Speicher LocalMachine gespeichert ist, für das [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Arbeitsprozesskonto verfügbar ist.  
  
    ```  
    echo ************  
    echo setting privileges on server certificates  
    echo ************  
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE  
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET  
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R  
    iisreset  
    ```  
  
> [!NOTE]
>  Bei Verwendung einer anderen als der englischsprachigen US-Version von Windows müssen Sie in der Datei "Setup.bat" den Kontonamen `NT AUTHORITY\NETWORK SERVICE` durch den äquivalenten Kontonamen in der entsprechenden Sprache ersetzen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1.  Vergewissern Sie sich, dass der Pfad den Ordner enthält, in dem sich die Dateien Makecert.exe und FindPrivateKey.exe befinden.  
  
2.  Führen Sie Setup.bat aus dem Beispielinstallationsordner an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
    > [!NOTE]
    >  Die Setupbatchdatei ist dafür gedacht, an einer [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung ausgeführt zu werden. Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable wird automatisch innerhalb einer [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]-Eingabeaufforderung festgelegt.  
  
3.  Überprüfen Sie den Zugriff auf den Dienst, indem Sie in einem Browser die Adresse http://localhost/servicemodelsamples/service.svc eingeben.  
  
4.  Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
5.  Wenn der Client und der Dienst nicht kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1.  Erstellen Sie auf dem Dienstcomputer ein Verzeichnis. Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.  
  
2.  Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren. Kopieren Sie außerdem die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.  
  
3.  Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
4.  Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer. Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.  
  
5.  Führen Sie auf dem Server `setup.bat service` an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Ausführen `setup.bat` mit der `service` Argument wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und das Dienstzertifikat in eine Datei "Service.cer" exportiert exportiert.  
  
6.  Bearbeiten der Datei "Web.config", um den neuen Zertifikatnamen entspricht (in der `findValue` Attribut in der [ \<ServiceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), also den voll qualifizierten Domänennamen des Computers identisch.  
  
7.  Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
8.  Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.  
  
9. Führen Sie auf dem Client ImportServiceCert.bat an einer Visual Studio-Eingabeaufforderung mit Administratorrechten aus. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
10. Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie weitere Informationen unter [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.  
  
> [!NOTE]
>  Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Beispiele ausgeführt haben, die Zertifikate computerübergreifend verwenden, müssen Sie die Dienstzertifikate entfernen, die im Speicher CurrentUser – TrustedPeople installiert wurden. Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`.  
  
## <a name="see-also"></a>Siehe auch
