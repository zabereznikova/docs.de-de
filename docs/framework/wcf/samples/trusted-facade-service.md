---
title: Vertrauenswürdiger Fassadendienst
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: 80f139ace43d5f8d2136528681386711bea7a1e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295053"
---
# <a name="trusted-facade-service"></a>Vertrauenswürdiger Fassadendienst

Dieses Szenariobeispiel veranschaulicht, wie die Identitätsinformationen des Aufrufers mithilfe Windows Communication Foundation (WCF)-Sicherheitsinfrastruktur von einem Dienst zu einem anderen weitergeleitet werden.  
  
 Ein allgemeines Entwurfsmuster besteht darin, dem öffentlichen Netzwerk die Funktionalität, die von einem Dienst bereitgestellt wird, mithilfe eines Fassadendiensts verfügbar zu machen. Der Fassadendienst befindet sich üblicherweise im Perimeternetzwerk (auch bekannt als DMZ (Demilitarized Zone; deutsch: entmilitarisierte Zone) und geschirmtes Unternetz) und kommuniziert mit einem Back-End-Dienst, der die Geschäftslogik implementiert und Zugriff auf interne Daten hat. Der Kommunikationskanal zwischen dem Fassadendienst und dem Back-End-Dienst führt durch eine Firewall und wird üblicherweise auf einen Zweck begrenzt.  
  
 Dieses Beispiel besteht aus den folgenden Komponenten:  
  
- Rechnerclient  
  
- Rechnerfassadendienst  
  
- Rechner-Back-End-Dienst  
  
 Der Fassadendienst ist für die Überprüfung der Anforderung und die Authentifizierung des Aufrufers verantwortlich. Nach erfolgreicher Authentifizierung und Validierung leitet er die Anforderung an den Back-End-Dienst mithilfe des gesteuerten Kommunikationskanals vom Perimeternetzwerk zum internen Netzwerk weiter. Als Teil der weitergeleiteten Anforderung beinhaltet der Fassadendienst Informationen über die Identität des Aufrufers. So kann der Back-End-Dienst diese Informationen in der Verarbeitung verwenden. Die Identität des Aufrufers wird mit einem `Username` -Sicherheitstoken im Nachrichten- `Security` -Header gesendet. Im Beispiel wird die WCF-Sicherheitsinfrastruktur verwendet, um diese Informationen aus dem-Header zu übertragen und zu extrahieren `Security` .  
  
> [!IMPORTANT]
> Der Back-End-Dienst vertraut darauf, dass der Fassadendienst den Aufrufer authentifiziert. Daher authentifiziert der Back-End-Dienst den Aufrufer nicht erneut, sondern nutzt die Identitätsinformationen, die vom Fassadendienst in der weitergeleiteten Anforderung bereitgestellt werden. Aufgrund dieser Vertrauensbeziehung muss der Back-End-Dienst den Fassadendienst authentifizieren, um sicherzustellen, dass die weitergeleitete Nachricht von einer vertrauenswürdigen Quelle stammt, in diesem Fall vom Fassadendienst.  
  
## <a name="implementation"></a>Implementierung  

 Es gibt zwei Kommunikationspfade in diesem Beispiel. Der erste Kommunikationspfad besteht zwischen dem Client und dem Fassadendienst, der zweite zwischen dem Fassadendienst und dem Back-End-Dienst.  
  
### <a name="communication-path-between-client-and-faade-service"></a>Kommunikationspfad zwischen Client und Fassadendienst  

 Der Kommunikationspfad zwischen Client und Fassadendienst nutzt `wsHttpBinding` mit einem `UserName` -Clientanmeldeinformationstyp. Dies bedeutet, dass der Client Benutzername und Kennwort für die Authentifizierung zum Fassadendienst nutzt und der Fassadendienst die X.509-Zertifizierung für die Authentifizierung zum Client verwendet. Die Bindungskonfiguration sieht wie das folgende Beispiel aus.  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 Der Fassadendienst authentifiziert den Aufrufer mithilfe benutzerdefinierter `UserNamePasswordValidator` -Implementierung. Zu Demonstrationszwecken stellt die Authentifizierung nur sicher, dass der Benutzername des Aufrufers zum vorgelegten Kennwort passt. In realen Situationen wird der Benutzer wahrscheinlich mithilfe von Active Directory oder einem benutzerdefinierten ASP.NET-Mitgliedschaftsanbieter authentifiziert. Die Implementierung des Validierungssteuerelements befindet sich in der Datei `FacadeService.cs` .  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 Das benutzerdefinierte Validierungssteuerelement ist so konfiguriert, dass es innerhalb des `serviceCredentials` -Verhaltens in der Konfigurationsdatei des Fassadendiensts verwendet wird. Dieses Verhalten wird darüber hinaus verwendet, um das X.509-Zertifikat des Diensts zu konfigurieren.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate
               findValue="localhost"
               storeLocation="LocalMachine"
               storeName="My"
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a>Kommunikationspfad zwischen Fassadendienst und Back-End-Dienst  

 Der Kommunikationspfad zwischen Fassadendienst und Back-End-Dienst nutzt die `customBinding` , die aus mehreren Bindungselementen besteht. Diese Bindung erfüllt zwei Zwecke. Sie authentifiziert den Fassadendienst und den Back-End-Dienst, um sicherzustellen, dass die Kommunikation sicher ist und aus einer vertrauenswürdigen Quelle stammt. Darüber hinaus überträgt sie die Identität des ursprünglichen Aufrufers im `Username` -Sicherheitstoken. In diesem Fall wird nur der Benutzername des ursprünglichen Aufrufers zum Back-End-Dienst übertragen. Das Kennwort ist in der Nachricht nicht enthalten. Grund hierfür ist, dass der Back-End-Dienst dem Fassadendienst die Authentifizierung des Aufrufers anvertraut, bevor die Anforderung weitergeleitet wird. Da der Fassadendienst sich selbst gegenüber dem Back-End-Dienst authentifiziert, kann der Back-End-Dienst die in der weitergeleiteten Anforderung enthaltenen Informationen als vertrauenswürdig einstufen.  
  
 Im Folgenden ist die Bindungskonfiguration für diesen Kommunikationspfad dargestellt.  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 Das [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Bindungs Element übernimmt die Übertragung und Extraktion des ersten Benutzernamens des Aufrufers. [\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md)Und [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) kümmern sich um die Authentifizierung von Fassaden-und Back-End-Diensten und Nachrichten Schutz.  
  
 Um die Anforderung weiterzuleiten, muss die Fassaden Dienst Implementierung den Benutzernamen des ursprünglichen Aufrufers bereitstellen, damit die WCF-Sicherheitsinfrastruktur dies in die weitergeleitete Nachricht versetzen kann. Der Benutzername des ursprünglichen Aufrufers wird in der Fassadendienstimplementierung bereitgestellt, indem er in der `ClientCredentials` -Eigenschaft auf der Clientproxyinstanz festgelegt wird, die der Fassadendienst für die Kommunikation mit dem Back-End-Dienst nutzt.  
  
 Der folgende Code zeigt, wie die `GetCallerIdentity` -Methode auf dem Fassadendienst implementiert wird. Andere Methoden verwenden das gleiche Muster.  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 Wie bereits im vorherigen Code gezeigt, ist das Kennwort nicht für die `ClientCredentials` -Eigenschaft festgelegt, sondern nur der Benutzername. Die WCF-Sicherheitsinfrastruktur erstellt in diesem Fall ein Benutzernamen-Sicherheits Token ohne Kennwort. Dies ist genau das, was in diesem Szenario erforderlich ist.  
  
 Auf dem Back-End-Dienst müssen die Informationen authentifiziert werden, die im Benutzernamen-Sicherheitstoken enthalten sind. Standardmäßig versucht die WCF-Sicherheit, den Benutzer mit dem bereitgestellten Kennwort einem Windows-Konto zuzuordnen. In diesem Fall ist kein Kennwort angegeben, und der Back-End-Dienst muss den Benutzernamen nicht authentifizieren, da die Authentifizierung bereits vom Fassadendienst durchgeführt wurde. Um diese Funktionalität in WCF zu implementieren, wird ein benutzerdefiniertes `UserNamePasswordValidator` bereitgestellt, das nur erzwingt, dass ein Benutzername im Token angegeben ist, und keine zusätzliche Authentifizierung ausführt.  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 Das benutzerdefinierte Validierungssteuerelement ist so konfiguriert, dass es innerhalb des `serviceCredentials` -Verhaltens in der Konfigurationsdatei des Fassadendiensts verwendet wird.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Zur Extraktion der Benutzernameninformationen und der Informationen über das vertrauenswürdige Fassadendienstkonto nutzt die Back-End-Dienst-Implementierung die `ServiceSecurityContext` -Klasse. Im folgenden Codebeispiel wird die Implementierung der `GetCallerIdentity` -Methode veranschaulicht.  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 Die Informationen über das Fassadendienstkonto werden mithilfe der `ServiceSecurityContext.Current.WindowsIdentity` -Eigenschaft extrahiert. Um auf die Informationen über den ursprünglichen Aufrufer zuzugreifen, verwendet der Back-End-Dienst die `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` -Eigenschaft. Hier wird nach einem `Identity` -Anspruch mit dem Typ `Name`gesucht. Dieser Anspruch wird automatisch von der WCF-Sicherheitsinfrastruktur aus den Informationen generiert, die im- `Username` Sicherheits Token enthalten sind.  
  
## <a name="running-the-sample"></a>Ausführen des Beispiels  

 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen. Sie können die EINGABETASTE in den Konsolenfenstern des Fassaden- und Back-End-Diensts drücken, um die Dienste zu schließen.  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 Die im Beispiel zu Szenarios mit vertrauenswürdigen Fassaden enthaltene Batchdatei "Setup.bat" ermöglicht es Ihnen, den Server mit einem relevanten Zertifikat zu konfigurieren, damit der Fassadendienst ausgeführt wird, der zertifikatbasierte Sicherheit für die eigene Authentifizierung gegenüber dem Client erfordert. Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas.  
  
 Im Folgenden wird eine kurze Übersicht über die verschiedenen Abschnitte der Batchdateien bereitgestellt.  
  
- Erstellen des Serverzertifikats.  
  
     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     Die `%SERVER_NAME%` -Variable gibt den Servernamen an – der Standardwert ist "localhost". Das Zertifikat wird im LocalMachine-Speicher gespeichert.  
  
- Installieren des Fassadendienstzertifikats im Speicher für vertrauenswürdige Zertifikate des Clients.  
  
     Die folgenden Zeilen kopieren das Fassadendienstzertifikat in den Clientspeicher für vertrauenswürdige Personen. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Stellen Sie sicher, dass der Pfad den Ordner enthält, indem sich "Makecert.exe" befindet.  
  
2. Führen Sie "Setup.bat" im Beispielinstallationsordner aus. Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
3. Starten Sie "BackendService.exe" aus dem Verzeichnis "\BackendService\bin" in einem separaten Konsolenfenster  
  
4. Starten Sie "FacadeService.exe" aus dem Verzeichnis "\FacadeService\bin" in einem separaten Konsolenfenster  
  
5. Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
6. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
1. Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`
