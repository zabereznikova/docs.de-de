---
title: Sicherheit mit benutzerdefinierten Bindungen
ms.date: 03/30/2017
ms.assetid: a6383dff-4308-46d2-bc6d-acd4e18b4b8d
ms.openlocfilehash: eb575594cec9ea714578bc104344acc14b00e9df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84592462"
---
# <a name="custom-binding-security"></a><span data-ttu-id="a598a-102">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a598a-102">Custom Binding Security</span></span>

<span data-ttu-id="a598a-103">In diesem Beispiel wird veranschaulicht, wie die Sicherheitsfunktion mit einer benutzerdefinierten Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="a598a-103">This sample demonstrates how to configure security by using a custom binding.</span></span> <span data-ttu-id="a598a-104">Es zeigt, wie Sicherheit auf Nachrichtenebene und ein sicherer Transport mithilfe einer benutzerdefinierten Bindung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="a598a-104">It shows how to use a custom binding to enable message-level security together with a secure transport.</span></span> <span data-ttu-id="a598a-105">Dies ist hilfreich, wenn ein sicherer Transport zum Übertragen von Nachrichten zwischen Client und Dienst erforderlich ist und daher die Nachrichten auf Nachrichtenebene gesichert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a598a-105">This is useful when a secure transport is required to transmit the messages between client and service and simultaneously the messages must be secure on the message level.</span></span> <span data-ttu-id="a598a-106">Diese Konfiguration wird nicht von Bindungen unterstützt, die vom System bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a598a-106">This configuration is not supported by system-provided bindings.</span></span>

<span data-ttu-id="a598a-107">Dieses Beispiel besteht aus einem Clientkonsolenprogramm (EXE) und einem Dienstkonsolenprogramm (EXE).</span><span class="sxs-lookup"><span data-stu-id="a598a-107">This sample consists of a client console program (EXE) and a service console program (EXE).</span></span> <span data-ttu-id="a598a-108">Der Dienst implementiert einen Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="a598a-108">The service implements a duplex contract.</span></span> <span data-ttu-id="a598a-109">Der Vertrag wird von der `ICalculatorDuplex`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="a598a-109">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="a598a-110">Durch die `ICalculatorDuplex`-Schnittstelle kann der Client mathematische Operationen ausführen (Berechnen eines laufenden Ergebnisses über eine Sitzung).</span><span class="sxs-lookup"><span data-stu-id="a598a-110">The `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over a session.</span></span> <span data-ttu-id="a598a-111">Unabhängig davon kann der Dienst Ergebnisse auf der `ICalculatorDuplexCallback`-Schnittstelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a598a-111">Independently, the service may return results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="a598a-112">Ein Duplexvertrag erfordert eine Sitzung, da ein Kontext eingerichtet werden muss, um die zwischen dem Client und dem Dienst gesendeten Nachrichten in Beziehung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="a598a-112">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between the client and the service.</span></span> <span data-ttu-id="a598a-113">Es wird eine benutzerdefinierte Bindung definiert, die Duplexkommunikation unterstützt und sicher ist.</span><span class="sxs-lookup"><span data-stu-id="a598a-113">A custom binding is defined that supports duplex communication and is secure.</span></span>

> [!NOTE]
> <span data-ttu-id="a598a-114">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="a598a-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="a598a-115">Die Dienstkonfiguration definiert eine benutzerdefinierte Bindung, die Folgendes unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a598a-115">The service configuration defines a custom binding that supports the following:</span></span>

- <span data-ttu-id="a598a-116">TCP-Kommunikation mit Schutz durch Verwendung des TLS/SSL-Protokolls.</span><span class="sxs-lookup"><span data-stu-id="a598a-116">TCP communication protected by using the TLS/SSL protocol.</span></span>

- <span data-ttu-id="a598a-117">Windows-Nachrichtensicherheit.</span><span class="sxs-lookup"><span data-stu-id="a598a-117">Windows message security.</span></span>

<span data-ttu-id="a598a-118">Durch die benutzerdefinierte Bindungskonfiguration wird der sichere Transport ermöglicht, da gleichzeitig die Sicherheit auf Nachrichtenebene aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="a598a-118">The custom binding configuration enables secure transport by simultaneously enabling the message-level security.</span></span> <span data-ttu-id="a598a-119">Die Reihenfolge der Bindungs Elemente ist beim Definieren einer benutzerdefinierten Bindung wichtig, da jede eine Ebene im Kanal Stapel darstellt (siehe [benutzerdefinierte Bindungen](../extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="a598a-119">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../extending/custom-bindings.md)).</span></span> <span data-ttu-id="a598a-120">Die benutzerdefinierte Bindung wird in den Dienst- und Clientkonfigurationsdateien definiert, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a598a-120">The custom binding is defined in the service and client configuration files, as shown in the following sample configuration.</span></span>

```xml
<bindings>
  <!-- Configure a custom binding. -->
  <customBinding>
    <binding name="Binding1">
      <security authenticationMode="SecureConversation"
                 requireSecurityContextCancellation="true">
      </security>
      <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>
      <sslStreamSecurity requireClientCertificate="false"/>
      <tcpTransport/>
    </binding>
  </customBinding>
</bindings>
```

<span data-ttu-id="a598a-121">Die benutzerdefinierte Bindung verwendet ein Dienstzertifikat zum Authentifizieren des Diensts auf Transportebene und zum Sichern der Nachrichten während der Übertragung zwischen Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="a598a-121">The custom binding uses a service certificate to authenticate the service on the transport level and to protect the messages during the transmission between client and service.</span></span> <span data-ttu-id="a598a-122">Dies wird durch das `sslStreamSecurity`-Bindungselement umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a598a-122">This is accomplished by the `sslStreamSecurity` binding element.</span></span> <span data-ttu-id="a598a-123">Das Zertifikat des Diensts wird mit einem Dienstverhalten konfiguriert, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a598a-123">The service's certificate is configured using a service behavior as shown in the following sample configuration.</span></span>

```xml
<behaviors>
    <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
        <serviceMetadata />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>
        </serviceCredentials>
    </behavior>
    </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="a598a-124">Außerdem verwendet die benutzerdefinierte Bindung Nachrichtensicherheit mit dem Windows-Anmeldeinformationstyp. Dies ist der Standard-Anmeldeinformationstyp.</span><span class="sxs-lookup"><span data-stu-id="a598a-124">Additionally, the custom binding uses message security with Windows credential type - this is the default credential type.</span></span> <span data-ttu-id="a598a-125">Dies wird durch das `security`-Bindungselement umgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a598a-125">This is accomplished by the `security` binding element.</span></span> <span data-ttu-id="a598a-126">Sowohl der Client als auch der Dienst werden mithilfe von Sicherheitsfunktionen auf Nachrichtenebene authentifiziert, wenn der Kerberos-Authentifizierungsmechanismus verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a598a-126">Both client and service are authenticated using message-level security if the Kerberos authentication mechanism is available.</span></span> <span data-ttu-id="a598a-127">Dies geschieht, wenn das Beispiel in der Active Directory-Umgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a598a-127">This happens if the sample is run in the Active Directory environment.</span></span> <span data-ttu-id="a598a-128">Ist der Kerberos-Authentifizierungsmechanismus nicht verfügbar, wird die NTLM-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="a598a-128">If the Kerberos authentication mechanism is not available, NTLM authentication is used.</span></span> <span data-ttu-id="a598a-129">NTLM authentifiziert den Client für den Dienst, authentifiziert aber nicht den Dienst für den Client.</span><span class="sxs-lookup"><span data-stu-id="a598a-129">NTLM authenticates the client to the service but does not authenticate the service to the client.</span></span> <span data-ttu-id="a598a-130">Das `security` Bindungs Element ist für die Verwendung `SecureConversation` `authenticationType` von konfiguriert, was zur Erstellung einer Sicherheits Sitzung auf dem Client und dem Dienst führt.</span><span class="sxs-lookup"><span data-stu-id="a598a-130">The `security` binding element is configured to use `SecureConversation` `authenticationType`, which results in the creation of a security session on both the client and the service.</span></span> <span data-ttu-id="a598a-131">Dies ist erforderlich, damit der Duplexvertrag des Diensts funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a598a-131">This is required to enable the service's duplex contract to work.</span></span>

<span data-ttu-id="a598a-132">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Konsolenfenster des Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a598a-132">When you run the sample, the operation requests and responses are displayed in the client's console window.</span></span> <span data-ttu-id="a598a-133">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a598a-133">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client.
Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="a598a-134">Wenn Sie das Beispiel ausführen, werden die vom Client zurückgegebenen Nachrichten in der vom Dienst gesendeten Rückrufschnittstelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a598a-134">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="a598a-135">Alle Zwischenergebnisse werden angezeigt, gefolgt von der ganzen Formel nach Abschluss aller Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="a598a-135">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="a598a-136">Drücken Sie die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a598a-136">Press ENTER to shut down the client.</span></span>

<span data-ttu-id="a598a-137">Mit der in diesem Beispiel enthaltenen Datei Setup.bat können Sie Client und Server mit relevanten Dienstzertifikaten zum Ausführen einer gehosteten Anwendung konfigurieren, die serverzertifikatbasierte Sicherheit erfordert.</span><span class="sxs-lookup"><span data-stu-id="a598a-137">The included Setup.bat file enables you to configure the client and server with the relevant service certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="a598a-138">Diese Batchdatei muss angepasst werden, wenn sie computerübergreifend oder in einem nicht gehosteten Szenario verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a598a-138">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

<span data-ttu-id="a598a-139">Nachfolgend erhalten Sie einen kurzen Überblick über die verschiedenen Abschnitte der Batchdateien für dieses Beispiel, damit Sie sie so ändern können, dass sie in der entsprechenden Konfiguration ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a598a-139">The following provides a brief overview of the different sections of the batch files that apply to this sample so that they can be modified to run in the appropriate configuration:</span></span>

- <span data-ttu-id="a598a-140">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="a598a-140">Creating the server certificate.</span></span>

  <span data-ttu-id="a598a-141">Mit den folgenden Zeilen aus der Datei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="a598a-141">The following lines from the Setup.bat file create the server certificate to be used.</span></span> <span data-ttu-id="a598a-142">Die Variable `%SERVER_NAME%` gibt den Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="a598a-142">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="a598a-143">Ändern Sie diese Variable, und geben Sie Ihren eigenen Servernamen an.</span><span class="sxs-lookup"><span data-stu-id="a598a-143">Change this variable to specify your own server name.</span></span> <span data-ttu-id="a598a-144">In dieser Batchdatei ist der Servername standardmäßig auf localhost festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a598a-144">This batch file defaults the server name to localhost.</span></span>

  <span data-ttu-id="a598a-145">Das Zertifikat wird im Speicher CurrentUser für im Internet gehostete Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a598a-145">The certificate is stored in the CurrentUser store for the Web-hosted services.</span></span>

  ```bat
  echo ************
  echo Server cert setup starting
  echo %SERVER_NAME%
  echo ************
  echo making server cert
  echo ************
  makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
  ```

- <span data-ttu-id="a598a-146">Installieren Sie das Serverzertifikat im Speicher für vertrauenswürdige Zertifikate des Clients.</span><span class="sxs-lookup"><span data-stu-id="a598a-146">Installing the server certificate into the client's trusted certificate store.</span></span>

  <span data-ttu-id="a598a-147">Mit den folgenden Zeilen in der Datei "Setup.bat" wird das Serverzertifikat in den Clientspeicher für vertrauenswürdige Personen kopiert.</span><span class="sxs-lookup"><span data-stu-id="a598a-147">The following lines in the Setup.bat file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="a598a-148">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="a598a-148">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="a598a-149">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a598a-149">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

  ```console
  certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
  ```

  > [!NOTE]
  > <span data-ttu-id="a598a-150">Die Batchdatei Setup.bat ist darauf ausgelegt, an einer Visual Studio-Eingabeaufforderung (2010) ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="a598a-150">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="a598a-151">Die MSSDK-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a598a-151">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="a598a-152">Diese Umgebungsvariable ist innerhalb einer Visual Studio-Eingabeaufforderung (2010) automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a598a-152">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a598a-153">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="a598a-153">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="a598a-154">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="a598a-154">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="a598a-155">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a598a-155">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="a598a-156">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a598a-156">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="a598a-157">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="a598a-157">To run the sample on the same computer</span></span>

1. <span data-ttu-id="a598a-158">Öffnen Sie eine Developer-Eingabeaufforderung für das Visual Studio-Fenster mit Administratorrechten, und führen Sie Setup. bat aus dem Beispiel Installationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="a598a-158">Open a Developer Command Prompt for Visual Studio window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="a598a-159">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a598a-159">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a598a-160">Die Batchdatei "Setup. bat" ist so konzipiert, dass Sie über eine Visual Studio 2012-Eingabeaufforderung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a598a-160">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="a598a-161">Die in der Visual Studio 2012-Eingabeaufforderung festgelegte PATH-Umgebungsvariable verweist auf das Verzeichnis, das ausführbare Dateien enthält, die für das Skript "Setup. bat" erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a598a-161">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

2. <span data-ttu-id="a598a-162">Starten Sie Service.exe aus dem Ordner \service\bin.</span><span class="sxs-lookup"><span data-stu-id="a598a-162">Launch Service.exe from \service\bin.</span></span>

3. <span data-ttu-id="a598a-163">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="a598a-163">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="a598a-164">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a598a-164">Client activity is displayed on the client console application.</span></span>

4. <span data-ttu-id="a598a-165">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="a598a-165">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="a598a-166">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="a598a-166">To run the sample across computers</span></span>

1. <span data-ttu-id="a598a-167">Auf dem Dienstcomputer:</span><span class="sxs-lookup"><span data-stu-id="a598a-167">On the service computer:</span></span>

    1. <span data-ttu-id="a598a-168">Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis mit dem Namen servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="a598a-168">Create a virtual directory named servicemodelsamples on the service computer.</span></span>

    2. <span data-ttu-id="a598a-169">Kopieren Sie die Dienstprogrammdateien aus \inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="a598a-169">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="a598a-170">Stellen Sie sicher, dass Sie die Dateien in das Unterverzeichnis \bin kopieren.</span><span class="sxs-lookup"><span data-stu-id="a598a-170">Ensure that you copy the files in the \bin subdirectory.</span></span>

    3. <span data-ttu-id="a598a-171">Kopieren Sie die Dateien Setup.bat und Cleanup.bat auf den Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="a598a-171">Copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>

    4. <span data-ttu-id="a598a-172">Führen Sie den folgenden Befehl in einem Developer-Eingabeaufforderung für Visual Studio aus, das mit Administratorrechten geöffnet wurde: `Setup.bat service` .</span><span class="sxs-lookup"><span data-stu-id="a598a-172">Run the following command in a Developer Command Prompt for Visual Studio opened with administrator privileges: `Setup.bat service`.</span></span> <span data-ttu-id="a598a-173">Hiermit wird das Dienstzertifikat erstellt, dessen Antragstellername mit dem Namen des Computers übereinstimmt, auf dem die Batchdatei ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="a598a-173">This creates the service certificate with the subject name matching the name of the computer the batch file was run on.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a598a-174">Die Batchdatei Setup.bat ist darauf ausgelegt, an einer Visual Studio-Eingabeaufforderung (2010) ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="a598a-174">The Setup.bat batch file is designed to be run from a Visual Studio 2010 Command Prompt.</span></span> <span data-ttu-id="a598a-175">Die PATH-Umgebungsvariable muss auf das Verzeichnis zeigen, in dem das SDK installiert ist.</span><span class="sxs-lookup"><span data-stu-id="a598a-175">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="a598a-176">Diese Umgebungsvariable ist innerhalb einer Visual Studio-Eingabeaufforderung (2010) automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a598a-176">This environment variable is automatically set within a Visual Studio 2010 Command Prompt.</span></span>

    5. <span data-ttu-id="a598a-177">Ändern [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) Sie in der Datei Service. exe. config den Antragsteller Namen des Zertifikats, das Sie im vorherigen Schritt generiert haben.</span><span class="sxs-lookup"><span data-stu-id="a598a-177">Change the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) inside the Service.exe.config file to reflect the subject name of the certificate generated in the previous step.</span></span>

    6. <span data-ttu-id="a598a-178">Führen Sie Service.exe an einer Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="a598a-178">Run Service.exe from a command prompt.</span></span>

2. <span data-ttu-id="a598a-179">Auf dem Clientcomputer:</span><span class="sxs-lookup"><span data-stu-id="a598a-179">On the client computer:</span></span>

    1. <span data-ttu-id="a598a-180">Kopieren Sie die Clientprogrammdateien aus dem Ordner \client\bin\ auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="a598a-180">Copy the client program files from the \client\bin\ folder to the client computer.</span></span> <span data-ttu-id="a598a-181">Kopieren Sie auch die Datei Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="a598a-181">Also copy the Cleanup.bat file.</span></span>

    2. <span data-ttu-id="a598a-182">Führen Sie Cleanup.bat aus, um alte Zertifikate aus vorherigen Beispielen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a598a-182">Run Cleanup.bat to remove any old certificates from previous samples.</span></span>

    3. <span data-ttu-id="a598a-183">Exportieren Sie das Zertifikat des Diensts, indem Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten öffnen und den folgenden Befehl auf dem Dienstcomputer ausführen (ersetzen Sie durch `%SERVER_NAME%` den voll qualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird):</span><span class="sxs-lookup"><span data-stu-id="a598a-183">Export the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the service computer (substitute `%SERVER_NAME%` with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr -put -r LocalMachine -s My -c -n %SERVER_NAME% %SERVER_NAME%.cer
        ```

    4. <span data-ttu-id="a598a-184">Kopieren Sie %SERVER_NAME%.cer auf den Clientcomputer (ersetzen Sie %SERVER_NAME% durch den vollqualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird).</span><span class="sxs-lookup"><span data-stu-id="a598a-184">Copy %SERVER_NAME%.cer to the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running).</span></span>

    5. <span data-ttu-id="a598a-185">Importieren Sie das Dienst Zertifikat, indem Sie eine Developer-Eingabeaufforderung für Visual Studio mit Administratorrechten öffnen und den folgenden Befehl auf dem Client Computer ausführen (ersetzen Sie% server_name% durch den voll qualifizierten Namen des Computers, auf dem der Dienst ausgeführt wird):</span><span class="sxs-lookup"><span data-stu-id="a598a-185">Import the service's certificate by opening a Developer Command Prompt for Visual Studio with administrative privileges, and running the following command on the client computer (substitute %SERVER_NAME% with the fully-qualified name of the computer where the service is running):</span></span>

        ```console
        certmgr.exe -add -c %SERVER_NAME%.cer -s -r CurrentUser TrustedPeople
        ```

        <span data-ttu-id="a598a-186">Die Schritte c, d und e sind nicht erforderlich, wenn das Zertifikat von einem vertrauenswürdigen Aussteller stammt.</span><span class="sxs-lookup"><span data-stu-id="a598a-186">Steps c, d, and e are not necessary if the certificate is issued by a Trusted Issuer.</span></span>

    6. <span data-ttu-id="a598a-187">Ändern Sie die Datei App.config des Clients wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a598a-187">Modify the client’s App.config file as follows:</span></span>

        ```xml
        <client>
            <endpoint name="default"
                address="net.tcp://ReplaceThisWithServiceMachineName:8000/ServiceModelSamples/Service"
                binding="customBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex"
                behaviorConfiguration="CalculatorClientBehavior" />
        </client>
        ```

    7. <span data-ttu-id="a598a-188">Wenn der Dienst unter einem anderen Konto als NetworkService oder LocalSystem in einer Domänenumgebung ausgeführt wird, müssen Sie möglicherweise die Endpunktidentität für den Dienstendpunkt in der Datei App.config des Clients ändern und den entsprechenden UPN oder SPN für das Konto angeben, unter dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a598a-188">If the service is running under an account other than the NetworkService or LocalSystem account in a domain environment, you might need to modify the endpoint identity for the service endpoint inside the client's App.config file to set the appropriate UPN or SPN based on the account that is used to run the service.</span></span> <span data-ttu-id="a598a-189">Weitere Informationen zur Endpunkt Identität finden Sie im Thema [Dienst Identität und Authentifizierung](../feature-details/service-identity-and-authentication.md) .</span><span class="sxs-lookup"><span data-stu-id="a598a-189">For more information about endpoint identity, see the [Service Identity and Authentication](../feature-details/service-identity-and-authentication.md) topic.</span></span>

    8. <span data-ttu-id="a598a-190">Führen Sie an einer Eingabeaufforderung Client.exe aus.</span><span class="sxs-lookup"><span data-stu-id="a598a-190">Run Client.exe from a command prompt.</span></span>

### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="a598a-191">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="a598a-191">To clean up after the sample</span></span>

- <span data-ttu-id="a598a-192">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie die Ausführung des Beispiels abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="a598a-192">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>
