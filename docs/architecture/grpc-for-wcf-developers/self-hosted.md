---
title: 'Selbstgeh ostete GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Bereitstellen von ASP.net Core GrpC-Anwendungen als selbstgeh ostete Dienste
ms.date: 09/02/2019
ms.openlocfilehash: 2244f161ad4b5d60138ae0f7b4d6a9c8c8829aa8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503403"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="b1eb6-103">Selbstgeh ostete GrpC-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b1eb6-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="b1eb6-104">Obwohl ASP.net Core 3,0-Anwendungen in IIS unter Windows Server gehostet werden können, ist es derzeit nicht möglich, eine GrpC-Anwendung in IIS zu hosten, da einige der http/2-Funktionen nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="b1eb6-105">Diese Funktion ist ein Ziel für ein zukünftiges Update von Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="b1eb6-106">Sie können Ihre Anwendung als Windows-Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="b1eb6-107">Oder Sie können Sie als Linux-Dienst ausführen, der von [systemd](https://en.wikipedia.org/wiki/Systemd)gesteuert wird, da neue Features in den .net Core 3,0-hostingerweiterungen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="b1eb6-108">Ausführen der App als Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="b1eb6-108">Run your app as a Windows service</span></span>

<span data-ttu-id="b1eb6-109">Wenn Sie die ASP.net Core Anwendung für die Verwendung als Windows-Dienst konfigurieren möchten, installieren Sie das [Microsoft. Extensions. Hosting. Windows Server](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) -Paket von nuget.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="b1eb6-110">Fügen Sie dann der `CreateHostBuilder`-Methode in `Program.cs`einen aufzurufenden `UseWindowsService` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="b1eb6-111">Wenn die Anwendung nicht als Windows-Dienst ausgeführt wird, wird von der `UseWindowsService`-Methode nichts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="b1eb6-112">Veröffentlichen Sie Ihre Anwendung nun mit einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="b1eb6-113">Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt, und wählen Sie im Kontextmenü **veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="b1eb6-114">Aus dem .net Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="b1eb6-115">Wenn Sie eine .net Core-Anwendung veröffentlichen, können Sie auswählen, ob Sie eine *Framework-abhängige* Bereitstellung oder eine *eigenständige* Bereitstellung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="b1eb6-116">Framework-abhängige bereit Stellungen erfordern, dass die freigegebene .net Core-Laufzeit auf dem Host installiert ist, auf dem Sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="b1eb6-117">Eigenständige bereit Stellungen werden mit einer kompletten Kopie der .net Core-Laufzeit und des .net Core-Frameworks veröffentlicht und können auf jedem Host ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="b1eb6-118">Weitere Informationen, einschließlich der vor-und Nachteile der einzelnen Ansätze, finden Sie in der Dokumentation zur [.net Core-Anwendungs Bereitstellung](../../core/deploying/index.md) .</span><span class="sxs-lookup"><span data-stu-id="b1eb6-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="b1eb6-119">Wenn Sie einen eigenständigen Build der Anwendung veröffentlichen möchten, für den die .net Core 3,0-Runtime nicht auf dem Host installiert werden muss, geben Sie die Runtime an, die in der Anwendung enthalten sein soll.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="b1eb6-120">Verwenden Sie das Flag `-r` (oder `--runtime`).</span><span class="sxs-lookup"><span data-stu-id="b1eb6-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="b1eb6-121">Wenn Sie einen Framework-abhängigen Build veröffentlichen möchten, lassen Sie das `-r`-Flag aus.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="b1eb6-122">Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="b1eb6-123">Verwenden Sie dann das [SC-Tool](/windows/desktop/services/controlling-a-service-using-sc) , um einen Windows-Dienst für die ausführbare Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="b1eb6-124">Im Windows-Ereignisprotokoll protokollieren</span><span class="sxs-lookup"><span data-stu-id="b1eb6-124">Log to the Windows event log</span></span>

<span data-ttu-id="b1eb6-125">Die `UseWindowsService`-Methode fügt automatisch einen [Protokollierungs](/aspnet/core/fundamentals/logging/) Anbieter hinzu, der Protokollmeldungen in das Windows-Ereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="b1eb6-126">Sie können die Protokollierung für diesen Anbieter konfigurieren, indem Sie dem Abschnitt `Logging` von `appsettings.json` oder einer anderen Konfigurations Quelle einen `EventLog` Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span> 

<span data-ttu-id="b1eb6-127">Sie können den im Ereignisprotokoll verwendeten Quellnamen überschreiben, indem Sie in diesen Einstellungen eine `SourceName`-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="b1eb6-128">Wenn Sie keinen Namen angeben, wird der Standard Anwendungsname (normalerweise der Name der ausführbaren Assembly) verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="b1eb6-129">Weitere Informationen zur Protokollierung finden Sie am Ende dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="b1eb6-130">Ausführen der App als Linux-Dienst mit "systemd"</span><span class="sxs-lookup"><span data-stu-id="b1eb6-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="b1eb6-131">Installieren Sie das [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) -Paket von nuget, um die ASP.net Core Anwendung so zu konfigurieren, dass Sie als Linux-Dienst ausgeführt wird (oder als *Daemon* in einer Linux-Anwendung).</span><span class="sxs-lookup"><span data-stu-id="b1eb6-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="b1eb6-132">Fügen Sie dann der `CreateHostBuilder`-Methode in `Program.cs`einen aufzurufenden `UseSystemd` hinzu.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="b1eb6-133">Wenn die Anwendung nicht als Linux-Dienst ausgeführt wird, wird von der `UseSystemd`-Methode nichts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="b1eb6-134">Veröffentlichen Sie nun Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-134">Now publish your application.</span></span> <span data-ttu-id="b1eb6-135">Die Anwendung kann entweder Framework-abhängig oder eigenständig für die relevante Linux-Laufzeit sein (z. b. `linux-x64`).</span><span class="sxs-lookup"><span data-stu-id="b1eb6-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="b1eb6-136">Sie können mit einer der folgenden Methoden veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="b1eb6-137">Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt, und wählen Sie im Kontextmenü **veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span> 
* <span data-ttu-id="b1eb6-138">Verwenden Sie in der .net Core-CLI den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
<span data-ttu-id="b1eb6-139">Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner auf dem Linux-Host.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="b1eb6-140">Um den Dienst zu registrieren, muss eine spezielle Datei, eine so genannte *Einheits Datei*, dem `/etc/systemd/system` Verzeichnis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="b1eb6-141">Sie benötigen die root-Berechtigung, um eine Datei in diesem Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="b1eb6-142">Benennen Sie die Datei mit dem Bezeichner, den Sie verwenden `systemd` möchten, und `.service` Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="b1eb6-143">Verwenden Sie z. B. `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="b1eb6-144">Die Dienst Datei verwendet das INI-Format, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="b1eb6-145">Die `Type=notify`-Eigenschaft teilt `systemd` mit, dass die Anwendung Sie beim Starten und Herunterfahren benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="b1eb6-146">Die `WantedBy=multi-user.target` Einstellung bewirkt, dass der Dienst gestartet wird, wenn das Linux-System "Runlevel 2" erreicht. Dies bedeutet, dass eine nicht grafische Multi-User-Shell aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="b1eb6-147">Bevor `systemd` den Dienst erkennen kann, muss die Konfiguration erneut geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="b1eb6-148">Sie steuern `systemd` mithilfe des `systemctl`-Befehls.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="b1eb6-149">Verwenden Sie nach dem erneuten Laden den Unterbefehl `status`, um zu bestätigen, dass die Anwendung erfolgreich registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="b1eb6-150">Wenn Sie den Dienst ordnungsgemäß konfiguriert haben, erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="b1eb6-151">Verwenden Sie den `start`-Befehl, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="b1eb6-152">Die `.service`-Erweiterung ist optional, wenn Sie `systemctl start`verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="b1eb6-153">Wenn Sie `systemd` möchten, dass der Dienst beim Systemstart automatisch gestartet wird, verwenden Sie den `enable`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="b1eb6-154">In Journal Protokoll protokollieren</span><span class="sxs-lookup"><span data-stu-id="b1eb6-154">Log to journald</span></span>

<span data-ttu-id="b1eb6-155">Die Linux-Entsprechung des Windows-Ereignis Protokolls ist `journald`, ein strukturierter Protokollierungs Systemdienst, der Teil von `systemd`ist.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="b1eb6-156">Protokollmeldungen, die von einem Linux-Daemon in die Standardausgabe geschrieben werden, werden automatisch in `journald`geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="b1eb6-157">Verwenden Sie zum Konfigurieren von Protokolliergraden den `Console` Abschnitt der Protokollierungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="b1eb6-158">Mit der `UseSystemd` Host-Generator-Methode wird das Konsolenausgabe Format automatisch so konfiguriert, dass es dem Journal entspricht.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="b1eb6-159">Da `journald` der Standard für Linux-Protokolle ist, sind eine Reihe von Tools integriert.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="b1eb6-160">Sie können Protokolle problemlos von `journald` an ein externes Protokollierungs System weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="b1eb6-161">Wenn Sie lokal auf dem Host arbeiten, können Sie den `journalctl`-Befehl verwenden, um Protokolle in der Befehlszeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="b1eb6-162">Wenn eine GUI-Umgebung auf dem Host verfügbar ist, sind einige grafische Protokoll-Viewer für Linux verfügbar, z. b. *qjournalctl* und *gnome-Logs*.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="b1eb6-163">Weitere Informationen zum Abfragen des `systemd` Journal von der Befehlszeile aus mithilfe `journalctl`finden Sie auf [der Seite "man Pages](https://manpages.debian.org/buster/systemd/journalctl.1)".</span><span class="sxs-lookup"><span data-stu-id="b1eb6-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="b1eb6-164">HTTPS-Zertifikate für selbst gehostete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b1eb6-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="b1eb6-165">Wenn Sie eine GrpC-Anwendung in der Produktionsumgebung ausführen, sollten Sie ein TLS-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority, ca) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="b1eb6-166">Diese Zertifizierungsstelle kann eine öffentliche Zertifizierungsstelle oder eine interne Zertifizierungsstelle für Ihre Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="b1eb6-167">Auf Windows-Hosts können Sie das Zertifikat mit der <xref:System.Security.Cryptography.X509Certificates.X509Store>-Klasse aus einem sicheren [Zertifikat Speicher](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) laden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="b1eb6-168">Sie können auch die `X509Store`-Klasse mit dem OpenSSL Key Store auf einigen Linux-Hosts verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="b1eb6-169">Sie können Zertifikate auch mit einem der [X509Certificate2-Konstruktoren](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)erstellen, indem Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="b1eb6-170">Eine Datei, z. b. eine `.pfx` Datei, die durch ein sicheres Kennwort geschützt ist</span><span class="sxs-lookup"><span data-stu-id="b1eb6-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="b1eb6-171">Von einem sicheren Speicherdienst abgerufene Binärdaten, wie z. b. [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="b1eb6-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="b1eb6-172">Sie können Kestrel so konfigurieren, dass ein Zertifikat auf zweierlei Weise verwendet wird: aus Konfiguration oder Code.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="b1eb6-173">Festlegen von HTTPS-Zertifikaten mithilfe der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b1eb6-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="b1eb6-174">Der Konfigurations Ansatz erfordert, dass der Pfad zum Zertifikat `.pfx` Datei und das Kennwort im Kestrel-Konfigurations Abschnitt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="b1eb6-175">In `appsettings.json`sieht dies wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="b1eb6-175">In `appsettings.json`, that would look like this:</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="b1eb6-176">Geben Sie das Kennwort an, indem Sie eine sichere Konfigurations Quelle wie Azure Key Vault oder den hashicorp-Tresor verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1eb6-177">Speichern Sie unverschlüsselte Kenn Wörter nicht in Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="b1eb6-178">Festlegen von HTTPS-Zertifikaten im Code</span><span class="sxs-lookup"><span data-stu-id="b1eb6-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="b1eb6-179">Verwenden Sie zum Konfigurieren von HTTPS für Kestrel im Code die `ConfigureKestrel`-Methode auf `IWebHostBuilder` in der `Program`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="b1eb6-180">Stellen Sie auch hier sicher, dass Sie das Kennwort für die `.pfx` Datei in speichern und aus einer sicheren Konfigurations Quelle abrufen.</span><span class="sxs-lookup"><span data-stu-id="b1eb6-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b1eb6-181">[Zurück](grpc-in-production.md)
>[Weiter](docker.md)</span><span class="sxs-lookup"><span data-stu-id="b1eb6-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
