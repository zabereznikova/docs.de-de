---
title: Beispiel für Nachrichtensicherheit
ms.date: 03/30/2017
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
ms.openlocfilehash: 02e758633f810d785c914152cbd4fbe687bea4f9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558627"
---
# <a name="message-security-sample"></a>Beispiel für Nachrichtensicherheit
In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die `basicHttpBinding` und Nachrichtensicherheit verwendet. Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Der Sicherheitsmodus von `basicHttpBinding` kann auf die folgenden Werte festgelegt werden: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` und `None`. In der folgenden Datei "App.config" des Beispieldiensts gibt die Endpunktdefinition die `basicHttpBinding` an und verweist auf die Bindungskonfiguration `Binding1` (wie in folgender Beispielkonfiguration gezeigt).  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 Die Bindungs Konfiguration legt das `mode` -Attribut des [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) auf fest `Message` und legt das- `clientCredentialType` Attribut von [\<message>](../../configure-apps/file-schema/wcf/message-of-basichttpbinding.md) auf fest, `Certificate` wie in der folgenden Beispielkonfiguration gezeigt:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 Das vom Dienst zum Authentifizieren beim Client verwendete Zertifikat wird im Verhaltensabschnitt der Konfigurationsdatei im Element `serviceCredentials` festgelegt. Der Validierungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im Verhaltensabschnitt im `clientCertificate`-Element festgelegt.  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.  
  
 Die Identität des Aufrufers wird im Dienstkonsolenfenster angezeigt, indem folgender Code verwendet wird:  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
### <a name="to-run-the-sample-on-the-same-machine"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Führen Sie "Setup.bat" im Beispielinstallationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
    > [!NOTE]
    > Die Batchdatei "Setup.bat" ist dafür ausgelegt, von einer Windows SDK-Eingabeaufforderung ausgeführt zu werden. Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist. Diese Umgebungsvariable wird automatisch innerhalb einer Windows SDK-Eingabeaufforderung festgelegt.  
  
2. Führen Sie die Dienstanwendung in "\service\bin" aus.  
  
3. Führen Sie die Clientanwendung in "\client\bin" aus. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
5. Wenn Sie mit dem Beispiel fertig sind, führen Sie die Datei Cleanup.bat aus, um die Zertifikate zu entfernen. In anderen Sicherheitsbeispielen werden die gleichen Zertifikate verwendet.  
  
### <a name="to-run-the-sample-across-machines"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis für die Dienstbinärdateien.  
  
2. Kopieren Sie die Dienstprogrammdateien in das Dienstverzeichnis auf dem Server. Kopieren Sie auch die Dateien "Setup.bat", "Cleanup.bat" und "ImportClientCert.bat" auf den Server.  
  
3. Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
4. Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer. Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.  
  
5. Führen Sie auf dem Server `setup.bat service` aus. Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.  
  
6. Bearbeiten Sie Service.exe.config, um den neuen Zertifikat Namen (im-Attribut im-Element) widerzuspiegeln, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist. Ändern Sie auch den Wert der Basisadresse, um anstelle von "localhost" einen vollqualifizierten Computernamen anzugeben`.`  
  
7. Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
8. Führen Sie auf dem Client `setup.bat client` aus. Durch Ausführen von  mit dem Argument  wird ein Clientzertifikat mit dem Namen client.com erstellt und in die Datei Client.cer exportiert.  
  
9. Ändern Sie in der Datei "Client.exe.config" auf dem Clientcomputer den Wert für die Adresse des Endpunkts so, dass er mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie dazu localhost durch den vollqualifizierten Domänennamen des Servers. Ändern Sie auch das- `findValue` Attribut von [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) in den neuen Dienst Zertifikat Namen, der den voll qualifizierten Domänen Namen des Servers ist.  
  
10. Kopieren Sie die Datei Client.cer aus dem Clientverzeichnis in das Dienstverzeichnis auf dem Server.  
  
11. Führen Sie auf dem Client "ImportServiceCert.bat" aus. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
12. Führen Sie auf dem Server "ImportClientCert.bat" aus. Dadurch wird das Clientzertifikat von der Datei "Client.cer" in den LocalMachine &#8211; TrustedPeople-Speicher importiert.  
  
13. Führen Sie auf dem Dienstcomputer die Datei "Service.exe" über eine Eingabeaufforderung aus.  
  
14. Starten Sie auf dem Clientcomputer Client.exe in einem Eingabeaufforderungsfenster.  
  
    1. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
    > [!NOTE]
    > Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, stellen Sie sicher, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden. Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`
