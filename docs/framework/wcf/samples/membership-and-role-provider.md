---
title: Mitgliedschafts- und Rollenanbieter
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: 117be783c2d4a72ff9d1c4509566274b1043a43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144460"
---
# <a name="membership-and-role-provider"></a>Mitgliedschafts- und Rollenanbieter
Das Beispiel Mitgliedschaft und Rollenanbieter veranschaulicht, wie ein Dienst die ASP.NET Mitgliedschafts- und Rollenanbieter verwenden kann, um Clients zu authentifizieren und zu autorisieren.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 In diesem Beispiel werden folgende Vorgänge veranschaulicht:  
  
- Ein Client kann die Authentifizierung mithilfe einer Kombination aus Benutzername und Kennwort durchführen.  
  
- Der Server kann die Clientanmeldeinformationen anhand des ASP.NET-Mitgliedschaftsanbieters überprüfen.  
  
- Der Server kann über das X.509-Zertifikat des Servers authentifiziert werden.  
  
- Der Server kann den authentifizierten Client einer Rolle zuordnen, indem er den ASP.NET Rollenanbieter verwendet.  
  
- Der Server kann mit `PrincipalPermissionAttribute` den Zugriff auf bestimmte Methoden steuern, die vom Dienst verfügbar gemacht werden.  
  
 Die Mitgliedschafts- und Rollenanbieter werden für die Verwendung eines Speichers konfiguriert, der von SQL Server unterstützt wird. Eine Verbindungszeichenfolge und verschiedene Optionen werden in der Dienstkonfigurationsdatei angegeben. Dem Mitgliedschaftsanbieter wird der Name `SqlMembershipProvider` zugewiesen, und dem Rollenanbieter wird der Name `SqlRoleProvider` zugewiesen.  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add
        name="SqlMembershipProvider"
        type="System.Web.Security.SqlMembershipProvider"
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 Der Dienst macht einen einzigen Endpunkt für die Kommunikation mit dem Dienst verfügbar. Dieser wird mit der Konfigurationsdatei Web.config definiert. Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag. Die Bindung wird mit einer Standard-`wsHttpBinding` konfiguriert, die standardmäßig die Windows-Authentifizierung verwendet. In diesem Beispiel wird die Standard-`wsHttpBinding` auf die Verwendung der Benutzernamenauthentifizierung festgelegt. Das Verhalten gibt an, dass das Serverzertifikat für die Dienstauthentifizierung verwendet werden soll. Das Serverzertifikat muss denselben Wert `SubjectName` für `findValue` das Attribut im [ \<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) Konfigurationselement enthalten. Darüber hinaus gibt das Verhalten an, dass die Authentifizierung von Benutzernamen-Kennwort-Paaren vom ASP.NET-Mitgliedschaftsanbieter s. und die Rollenzuordnung vom ASP.NET Rollenanbieter durchgeführt wird, indem die für die beiden Anbieter definierten Namen angegeben werden.  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"
                              storeName ="My"
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 Wenn Sie das Beispiel ausführen, ruft der Client die unterschiedlichen Dienstvorgänge unter drei verschiedenen Benutzerkonten auf: Alice, Bob und Charlie. Die Anforderungen und Antworten des Vorgangs werden im Clientkonsolenfenster angezeigt. Alle vier Aufrufe als Benutzer "Alice" sollten erfolgreich sein. Für Benutzer "Bob" sollte der Versuch, die Divide-Methode aufzurufen, zu einem Zugriffsverweigerungsfehler führen. Bei Benutzer "Charlie" sollte beim Versuch, die Multiply-Methode aufzurufen, ein Zugriffsverweigerungsfehler auftreten. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Befolgen Sie die Anweisungen unter Ausführen der Windows Communication [Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md), um die Edition von .NET oder Visual Basic zu erstellen.  
  
2. Stellen Sie sicher, dass Sie die [ASP.NET Application Services Database](https://go.microsoft.com/fwlink/?LinkId=94997)konfiguriert haben.  
  
    > [!NOTE]
    > Wenn Sie SQL Server Express Edition ausführen, lautet der Servername .\SQLEXPRESS. Dieser Server sollte beim Konfigurieren der ASP.NET Application Services-Datenbank sowie in der Verbindungszeichenfolge Web.config verwendet werden.  
  
    > [!NOTE]
    > Das ASP.NET Arbeitsprozesskonto muss über Berechtigungen für die Datenbank verfügen, die in diesem Schritt erstellt wird. Verwenden Sie hierzu das sqlcmd-Hilfsprogramm oder SQL Server Management Studio.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend auszuführen, befolgen Sie die folgenden Anweisungen.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Stellen Sie sicher, dass der Pfad den Ordner enthält, in dem sich Makecert.exe befindet.  
  
2. Führen Sie Setup.bat aus dem Beispielinstallationsordner in einer Entwicklereingabeaufforderung für Visual Studio aus, die mit Administratorrechten ausgeführt wird. Hierdurch werden die Dienstzertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.  
  
3. Starten Sie Client.exe aus dem Ordner \client\bin. In der Clientkonsolenanwendung wird Clientaktivität angezeigt.  
  
4. Wenn Client und Dienst nicht kommunizieren können, finden Sie weitere Informationen unter [Tipps zur Fehlerbehebung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein Verzeichnis. Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.  
  
2. Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren. Kopieren Sie außerdem die Dateien Setup.bat, GetComputerName.vbs und Cleanup.bat auf den Dienstcomputer.  
  
3. Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.  
  
4. Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer. Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.  
  
5. Öffnen Sie auf dem Server eine Developer-Eingabeaufforderung für `setup.bat service`Visual Studio mit Administratorrechten, und führen Sie aus. Wenn `setup.bat` Sie `service` mit dem Argument ausführen, wird ein Dienstzertifikat mit dem vollqualifizierten Domänennamen des Computers erstellt und das Dienstzertifikat in eine Datei mit dem Namen Service.cer exportiert.  
  
6. Bearbeiten Sie Web.config, um den `findValue` neuen Zertifikatnamen (im Attribut im [ \<dienstCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) widerzuspiegeln, der mit dem vollqualifizierten Domänennamen des Computers identisch ist.  
  
7. Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.  
  
8. Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.  
  
9. Öffnen Sie auf dem Client eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie ImportServiceCert.bat aus. Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.  
  
10. Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung. Wenn Client und Dienst nicht kommunizieren können, finden Sie weitere Informationen unter [Tipps zur Fehlerbehebung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.  
  
> [!NOTE]
> Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client. Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate auf computernder Basis verwenden, müssen Sie die Dienstzertifikate löschen, die im CurrentUser - TrustedPeople-Speicher installiert wurden. Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="the-setup-batch-file"></a>Die Setupbatchdatei  
 Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert. Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.  
  
 Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.  
  
- Erstellen des Serverzertifikats.  
  
     Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt. Die Variable %SERVER_NAME% gibt den Servernamen an. Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an. Standardmäßig lautet sie in dieser Batchdatei localhost.  
  
     Das Zertifikat wird im persönlichen Speicher unter dem Speicherort LocalMachine gespeichert.  
  
    ```console
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
- Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.  
  
     Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert. Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden. Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.  
  
    ```bat  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
