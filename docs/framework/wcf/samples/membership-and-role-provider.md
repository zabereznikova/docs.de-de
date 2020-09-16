---
title: Mitgliedschafts- und Rollenanbieter
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: e532f35a2c4cd9f53006c088956eadff616d2005
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543588"
---
# <a name="membership-and-role-provider"></a><span data-ttu-id="6a842-102">Mitgliedschafts- und Rollenanbieter</span><span class="sxs-lookup"><span data-stu-id="6a842-102">Membership and Role Provider</span></span>
<span data-ttu-id="6a842-103">Das Beispiel für Mitgliedschafts-und Rollen Anbieter veranschaulicht, wie ein Dienst mithilfe der ASP.net-Mitgliedschafts-und Rollen Anbieter Clients authentifizieren und autorisieren kann.</span><span class="sxs-lookup"><span data-stu-id="6a842-103">The Membership and Role Provider sample demonstrates how a service can use the ASP.NET membership and role providers to authenticate and authorize clients.</span></span>  
  
 <span data-ttu-id="6a842-104">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="6a842-104">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a842-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="6a842-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6a842-106">In diesem Beispiel werden folgende Vorgänge veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6a842-106">The sample demonstrates how:</span></span>  
  
- <span data-ttu-id="6a842-107">Ein Client kann die Authentifizierung mithilfe einer Kombination aus Benutzername und Kennwort durchführen.</span><span class="sxs-lookup"><span data-stu-id="6a842-107">A client can authenticate by using the username-password combination.</span></span>  
  
- <span data-ttu-id="6a842-108">Der Server kann die Client Anmelde Informationen anhand des ASP.net-Mitgliedschafts Anbieters überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6a842-108">The server can validate the client credentials against the ASP.NET membership provider.</span></span>  
  
- <span data-ttu-id="6a842-109">Der Server kann über das X.509-Zertifikat des Servers authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="6a842-109">The server can be authenticated by using the server's X.509 certificate.</span></span>  
  
- <span data-ttu-id="6a842-110">Der Server kann den authentifizierten Client mit dem ASP.NET-Rollen Anbieter einer Rolle zuordnen.</span><span class="sxs-lookup"><span data-stu-id="6a842-110">The server can map the authenticated client to a role by using the ASP.NET role provider.</span></span>  
  
- <span data-ttu-id="6a842-111">Der Server kann mit `PrincipalPermissionAttribute` den Zugriff auf bestimmte Methoden steuern, die vom Dienst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="6a842-111">The server can use the `PrincipalPermissionAttribute` to control access to certain methods that are exposed by the service.</span></span>  
  
 <span data-ttu-id="6a842-112">Die Mitgliedschafts- und Rollenanbieter werden für die Verwendung eines Speichers konfiguriert, der von SQL Server unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6a842-112">The membership and role providers are configured to use a store backed by SQL Server.</span></span> <span data-ttu-id="6a842-113">Eine Verbindungszeichenfolge und verschiedene Optionen werden in der Dienstkonfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="6a842-113">A connection string and various options are specified in the service configuration file.</span></span> <span data-ttu-id="6a842-114">Dem Mitgliedschaftsanbieter wird der Name `SqlMembershipProvider` zugewiesen, und dem Rollenanbieter wird der Name `SqlRoleProvider` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6a842-114">The membership provider is given the name `SqlMembershipProvider` while the role provider is given the name `SqlRoleProvider`.</span></span>  
  
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
  
 <span data-ttu-id="6a842-115">Der Dienst macht einen einzigen Endpunkt für die Kommunikation mit dem Dienst verfügbar. Dieser wird mit der Konfigurationsdatei Web.config definiert.</span><span class="sxs-lookup"><span data-stu-id="6a842-115">The service exposes a single endpoint for communicating with the service, which is defined by using the Web.config configuration file.</span></span> <span data-ttu-id="6a842-116">Der Endpunkt besteht aus einer Adresse, einer Bindung und einem Vertrag.</span><span class="sxs-lookup"><span data-stu-id="6a842-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="6a842-117">Die Bindung wird mit einer Standard-`wsHttpBinding` konfiguriert, die standardmäßig die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a842-117">The binding is configured with a standard `wsHttpBinding`, which defaults to using Windows authentication.</span></span> <span data-ttu-id="6a842-118">In diesem Beispiel wird die Standard-`wsHttpBinding` auf die Verwendung der Benutzernamenauthentifizierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6a842-118">This sample sets the standard `wsHttpBinding` to use username authentication.</span></span> <span data-ttu-id="6a842-119">Das Verhalten gibt an, dass das Serverzertifikat für die Dienstauthentifizierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a842-119">The behavior specifies that the server certificate is to be used for service authentication.</span></span> <span data-ttu-id="6a842-120">Das Serverzertifikat muss den gleichen Wert für das- `SubjectName` `findValue` Attribut im- [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) Konfigurationselement enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a842-120">The server certificate must contain the same value for the `SubjectName` as the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) configuration element.</span></span> <span data-ttu-id="6a842-121">Außerdem gibt das Verhalten an, dass die Authentifizierung von Benutzername/Kennwort-Paaren durch den ASP.net-Mitgliedschafts Anbieter und die Rollen Zuordnung durch den ASP.NET-Rollen Anbieter durch Angabe der für die beiden Anbieter definierten Namen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a842-121">In addition the behavior specifies that authentication of username-password pairs is performed by the ASP.NET membership provider and role mapping is performed by the ASP.NET role provider by specifying the names defined for the two providers.</span></span>  
  
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
  
 <span data-ttu-id="6a842-122">Wenn Sie das Beispiel ausführen, ruft der Client die unterschiedlichen Dienstvorgänge unter drei verschiedenen Benutzerkonten auf: Alice, Bob und Charlie.</span><span class="sxs-lookup"><span data-stu-id="6a842-122">When you run the sample, the client calls the various service operations under three different user accounts: Alice, Bob, and Charlie.</span></span> <span data-ttu-id="6a842-123">Die Anforderungen und Antworten des Vorgangs werden im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a842-123">The operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6a842-124">Alle vier Aufrufe als Benutzer "Alice" sollten erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="6a842-124">All four calls made as user "Alice" should succeed.</span></span> <span data-ttu-id="6a842-125">Für Benutzer "Bob" sollte der Versuch, die Divide-Methode aufzurufen, zu einem Zugriffsverweigerungsfehler führen.</span><span class="sxs-lookup"><span data-stu-id="6a842-125">User "Bob" should get an access denied error when trying to call the Divide method.</span></span> <span data-ttu-id="6a842-126">Bei Benutzer "Charlie" sollte beim Versuch, die Multiply-Methode aufzurufen, ein Zugriffsverweigerungsfehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="6a842-126">User "Charlie" should get an access denied error when trying to call the Multiply method.</span></span> <span data-ttu-id="6a842-127">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6a842-127">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6a842-128">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6a842-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6a842-129">Um die c#-oder Visual Basic .NET-Edition der Projekt Mappe zu erstellen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a842-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
2. <span data-ttu-id="6a842-130">Stellen Sie sicher, dass Sie die [ASP.NET-Anwendungsdienste Datenbank](https://go.microsoft.com/fwlink/?LinkId=94997)konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="6a842-130">Ensure that you have configured the [ASP.NET Application Services Database](https://go.microsoft.com/fwlink/?LinkId=94997).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6a842-131">Wenn Sie SQL Server Express Edition ausführen, lautet der Servername .\SQLEXPRESS.</span><span class="sxs-lookup"><span data-stu-id="6a842-131">If you are running SQL Server Express Edition, your server name is .\SQLEXPRESS.</span></span> <span data-ttu-id="6a842-132">Dieser Server sollte verwendet werden, wenn die ASP.NET-Anwendungsdienste-Datenbank sowie in der Verbindungs Zeichenfolge Web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="6a842-132">This server should be used when configuring the ASP.NET Application Services Database as well as in the Web.config connection string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6a842-133">Das ASP.NET-Arbeitsprozess Konto muss über Berechtigungen für die Datenbank verfügen, die in diesem Schritt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="6a842-133">The ASP.NET worker process account must have permissions on the database that is created in this step.</span></span> <span data-ttu-id="6a842-134">Verwenden Sie hierzu das sqlcmd-Hilfsprogramm oder SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="6a842-134">Use the sqlcmd utility or SQL Server Management Studio to do this.</span></span>  
  
3. <span data-ttu-id="6a842-135">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder computerübergreifend auszuführen, befolgen Sie die folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6a842-135">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="6a842-136">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="6a842-136">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="6a842-137">Stellen Sie sicher, dass der Pfad den Ordner enthält, in dem sich Makecert.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="6a842-137">Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="6a842-138">Führen Sie Setup.bat aus dem Beispiel Installationsordner in einer Developer-Eingabeaufforderung für Visual Studio aus, die mit Administratorrechten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6a842-138">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="6a842-139">Hierdurch werden die Dienstzertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6a842-139">This installs the service certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="6a842-140">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="6a842-140">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="6a842-141">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a842-141">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="6a842-142">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="6a842-142">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="6a842-143">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="6a842-143">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="6a842-144">Erstellen Sie auf dem Dienstcomputer ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6a842-144">Create a directory on the service computer.</span></span> <span data-ttu-id="6a842-145">Erstellen Sie mithilfe des Verwaltungstools für Internetinformationsdienste (IIS) für dieses Verzeichnis eine virtuelle Anwendung mit dem Namen servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="6a842-145">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="6a842-146">Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="6a842-146">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="6a842-147">Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.</span><span class="sxs-lookup"><span data-stu-id="6a842-147">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="6a842-148">Kopieren Sie außerdem die Dateien Setup.bat, GetComputerName.vbs und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="6a842-148">Also copy the Setup.bat, GetComputerName.vbs, and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="6a842-149">Erstellen Sie auf dem Clientcomputer ein Verzeichnis für die Clientbinärdateien.</span><span class="sxs-lookup"><span data-stu-id="6a842-149">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="6a842-150">Kopieren Sie die Clientprogrammdateien in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="6a842-150">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="6a842-151">Kopieren Sie die Dateien Setup.bat, Cleanup.bat und ImportServiceCert.bat ebenfalls auf den Client.</span><span class="sxs-lookup"><span data-stu-id="6a842-151">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="6a842-152">Öffnen Sie auf dem-Server eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie aus `setup.bat service` .</span><span class="sxs-lookup"><span data-stu-id="6a842-152">On the server, open a Developer Command Prompt for Visual Studio with administrative privileges and run `setup.bat service`.</span></span> <span data-ttu-id="6a842-153">Wenn `setup.bat` Sie mit dem- `service` Argument ausführen, wird ein Dienst Zertifikat mit dem voll qualifizierten Domänen Namen des Computers erstellt und in die Datei Service. CER exportiert.</span><span class="sxs-lookup"><span data-stu-id="6a842-153">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="6a842-154">Bearbeiten Sie Web.config, um den neuen Zertifikat Namen (im-Attribut im) widerzuspiegeln, der mit dem `findValue` [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) voll qualifizierten Domänen Namen des Computers identisch ist.</span><span class="sxs-lookup"><span data-stu-id="6a842-154">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="6a842-155">Kopieren Sie die Datei Service.cer aus dem Dienstverzeichnis in das Clientverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="6a842-155">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="6a842-156">Ändern Sie in der Datei Client.exe.config auf dem Clientcomputer den Wert für die Adresse des Endpunkts, sodass er mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="6a842-156">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="6a842-157">Öffnen Sie auf dem Client eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten, und führen Sie ImportServiceCert.bat aus.</span><span class="sxs-lookup"><span data-stu-id="6a842-157">On the client, open a Developer Command Prompt for Visual Studio with administrative privileges and run ImportServiceCert.bat.</span></span> <span data-ttu-id="6a842-158">Dadurch wird das Dienstzertifikat aus der Datei Service.cer in den Speicher CurrentUser – TrustedPeople importiert.</span><span class="sxs-lookup"><span data-stu-id="6a842-158">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="6a842-159">Starten Sie auf dem Clientcomputer Client.exe an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="6a842-159">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="6a842-160">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="6a842-160">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="6a842-161">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="6a842-161">To clean up after the sample</span></span>  
  
- <span data-ttu-id="6a842-162">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="6a842-162">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a842-163">Wenn dieses Beispiel computerübergreifend ausgeführt wird, entfernt dieses Skript keine Dienstzertifikate auf einem Client.</span><span class="sxs-lookup"><span data-stu-id="6a842-163">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="6a842-164">Wenn Sie Windows Communication Foundation (WCF)-Beispiele ausgeführt haben, die Zertifikate Computer übergreifend verwenden, müssen Sie sicherstellen, dass Sie die Dienst Zertifikate löschen, die im Speicher CurrentUser-treudpeople installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a842-164">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="6a842-165">Verwenden Sie dazu den folgenden Befehl: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` Beispiel: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="6a842-165">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="the-setup-batch-file"></a><span data-ttu-id="6a842-166">Die Setupbatchdatei</span><span class="sxs-lookup"><span data-stu-id="6a842-166">The Setup Batch File</span></span>  
 <span data-ttu-id="6a842-167">Mit der in diesem Beispiel enthaltenen Batchdatei Setup.bat können Sie den Server mit relevanten Zertifikaten zum Ausführen einer selbst gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="6a842-167">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="6a842-168">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a842-168">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="6a842-169">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6a842-169">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
- <span data-ttu-id="6a842-170">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="6a842-170">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="6a842-171">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="6a842-171">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="6a842-172">Die Variable %SERVER_NAME% gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="6a842-172">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="6a842-173">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="6a842-173">Change this variable to specify your own server name.</span></span> <span data-ttu-id="6a842-174">Standardmäßig lautet sie in dieser Batchdatei localhost.</span><span class="sxs-lookup"><span data-stu-id="6a842-174">This batch file defaults it to localhost.</span></span>  
  
     <span data-ttu-id="6a842-175">Das Zertifikat wird im persönlichen Speicher unter dem Speicherort LocalMachine gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6a842-175">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```console
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
- <span data-ttu-id="6a842-176">Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.</span><span class="sxs-lookup"><span data-stu-id="6a842-176">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="6a842-177">Mit den folgenden Zeilen in der Batchdatei Setup.bat wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="6a842-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="6a842-178">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="6a842-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="6a842-179">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a842-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```bat  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```
