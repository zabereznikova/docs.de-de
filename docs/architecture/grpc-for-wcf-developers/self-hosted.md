---
title: 'Selbstgeh ostete GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Bereitstellen von ASP.net Core GrpC-Anwendungen als selbstgeh ostete Dienste
ms.date: 09/02/2019
ms.openlocfilehash: 59f6275dbf85442bca3a98a1521597ef40e9675b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967213"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="7e0a3-103">Selbstgeh ostete GrpC-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7e0a3-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="7e0a3-104">Obwohl ASP.net Core 3,0-Anwendungen in IIS unter Windows Server gehostet werden können, ist es derzeit nicht möglich, eine GrpC-Anwendung in IIS zu hosten, da einige der http/2-Funktionen noch nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't yet supported.</span></span> <span data-ttu-id="7e0a3-105">Diese Funktionalität wird in einem zukünftigen Update von Windows Server erwartet.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-105">This functionality is expected in a future update to Windows Server.</span></span>

<span data-ttu-id="7e0a3-106">Dank einiger neuer Features in den .net Core 3,0-hostingerweiterungen können Sie die Anwendung als Windows-Dienst oder als Linux-Dienst ausführen, der von [systemd](https://en.wikipedia.org/wiki/Systemd)gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-106">You can run your application as a Windows Service, or as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), thanks to some new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="7e0a3-107">Ausführen der App als Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="7e0a3-107">Run your app as a Windows service</span></span>

<span data-ttu-id="7e0a3-108">Wenn Sie die ASP.net Core Anwendung für die Verwendung als Windows-Dienst konfigurieren möchten, installieren Sie das [Microsoft. Extensions. Hosting. Windows Server](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) -Paket von nuget.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-108">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="7e0a3-109">Fügen Sie dann der `CreateHostBuilder`-Methode in `Program.cs`einen aufzurufenden `UseWindowsService` hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-109">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="7e0a3-110">Wenn die Anwendung nicht als Windows-Dienst ausgeführt wird, wird von der `UseWindowsService`-Methode nichts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-110">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="7e0a3-111">Veröffentlichen Sie Ihre Anwendung jetzt entweder aus Visual Studio, indem Sie mit der rechten Maustaste auf das Projekt klicken und im Kontextmenü *veröffentlichen* auswählen, oder klicken Sie auf der .net Core-CLI.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-111">Now publish your application, either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI.</span></span>

<span data-ttu-id="7e0a3-112">Wenn Sie eine .net Core-Anwendung veröffentlichen, können Sie auswählen, ob Sie eine *Framework-abhängige* Bereitstellung oder eine *eigenständige* Bereitstellung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-112">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="7e0a3-113">Framework-abhängige bereit Stellungen erfordern, dass die freigegebene .net Core-Laufzeit auf dem Host installiert ist, auf dem Sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-113">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="7e0a3-114">Eigenständige bereit Stellungen werden mit einer kompletten Kopie der .net Core-Laufzeit und des .net Core-Frameworks veröffentlicht und können auf jedem Host ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-114">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="7e0a3-115">Weitere Informationen, einschließlich der vor-und Nachteile der einzelnen Ansätze, finden Sie in der Dokumentation zur [.net Core-Anwendungs Bereitstellung](https://docs.microsoft.com/dotnet/core/deploying/) .</span><span class="sxs-lookup"><span data-stu-id="7e0a3-115">For more information, including the advantages and disadvantages of each approach, refer to the [.NET Core application deployment](https://docs.microsoft.com/dotnet/core/deploying/) documentation.</span></span>

<span data-ttu-id="7e0a3-116">Um einen eigenständigen Build der Anwendung zu veröffentlichen, bei dem die .net Core 3,0-Runtime nicht auf dem Host installiert werden muss, geben Sie die Runtime an, die in die Anwendung eingeschlossen werden soll, indem Sie das Flag `-r` (oder `--runtime`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-116">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application using the `-r` (or `--runtime`) flag.</span></span>

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="7e0a3-117">Wenn Sie einen Framework-abhängigen Build veröffentlichen möchten, lassen Sie das `-r`-Flag aus.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-117">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```console
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="7e0a3-118">Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner, und erstellen Sie mit dem [Hilfsprogramm SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) einen Windows-Dienst für die ausführbare Datei.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-118">Copy the complete contents of the `publish` directory to an installation folder, and use the [sc utility](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a><span data-ttu-id="7e0a3-119">In Windows-Ereignisprotokoll protokollieren</span><span class="sxs-lookup"><span data-stu-id="7e0a3-119">Log to Windows Event Log</span></span>

<span data-ttu-id="7e0a3-120">Die `UseWindowsService`-Methode fügt automatisch einen [Protokollierungs](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) Anbieter hinzu, der Protokollmeldungen in das Windows-Ereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-120">The `UseWindowsService` method automatically adds a [Logging](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) provider that writes log messages to the Windows Event Log.</span></span> <span data-ttu-id="7e0a3-121">Sie können die Protokollierung für diesen Anbieter konfigurieren, indem Sie dem Abschnitt `Logging` von `appsettings.json` oder einer anderen Konfigurations Quelle einen `EventLog` Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-121">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or other configuration source.</span></span> <span data-ttu-id="7e0a3-122">Der im Ereignisprotokoll verwendete Quellname kann überschrieben werden, indem in diesen Einstellungen eine `SourceName`-Eigenschaft festgelegt wird. Wenn Sie keinen Namen angeben, wird der Standard Anwendungsname (normalerweise der Name der ausführbaren Assembly) verwendet.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-122">The source name used in Event Log can be overridden by setting a `SourceName` property in these settings; if you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="7e0a3-123">Weitere Informationen zur Protokollierung finden Sie am Ende dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-123">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="7e0a3-124">Ausführen der App als Linux-Dienst mit "systemd"</span><span class="sxs-lookup"><span data-stu-id="7e0a3-124">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="7e0a3-125">Installieren Sie das [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) -Paket von nuget, um die ASP.net Core Anwendung so zu konfigurieren, dass Sie als Linux-Dienst ausgeführt wird (oder als *Daemon* in einer Linux-Anwendung).</span><span class="sxs-lookup"><span data-stu-id="7e0a3-125">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="7e0a3-126">Fügen Sie dann der `CreateHostBuilder`-Methode in `Program.cs`einen aufzurufenden `UseSystemd` hinzu.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-126">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="7e0a3-127">Wenn die Anwendung nicht als Linux-Dienst ausgeführt wird, wird von der `UseSystemd`-Methode nichts ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-127">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="7e0a3-128">Veröffentlichen Sie nun Ihre Anwendung (entweder Framework-abhängig oder eigenständig für die relevante Linux-Laufzeit, z. b. `linux-x64`), indem Sie mit der rechten Maustaste auf das Projekt klicken und im Kontextmenü veröffentlichen auswählen. Sie können auch im .net Core-CLI mit dem folgenden Befehl *veröffentlichen* .</span><span class="sxs-lookup"><span data-stu-id="7e0a3-128">Now publish your application (either framework-dependent, or self-contained for the relevant Linux runtime, e.g. `linux-x64`), either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI using the following command.</span></span>

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

<span data-ttu-id="7e0a3-129">Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner auf dem Linux-Host.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-129">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="7e0a3-130">Um den Dienst zu registrieren, muss dem `/etc/systemd/system` Verzeichnis eine spezielle Datei ("Unit file") hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-130">Registering the service requires a special file, called a "unit file", to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="7e0a3-131">Sie benötigen die root-Berechtigung, um eine Datei in diesem Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-131">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="7e0a3-132">Benennen Sie die Datei mit dem Bezeichner, den Sie verwenden möchten `systemd` und der `.service` Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-132">Name the file with the identifier you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="7e0a3-133">Beispielsweise `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-133">For example, `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="7e0a3-134">Die Dienst Datei verwendet das INI-Format, wie in diesem Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-134">The service file uses INI format, as shown in this example.</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="7e0a3-135">Die `Type=notify`-Eigenschaft teilt `systemd` mit, dass die Anwendung Sie beim Starten und Herunterfahren benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-135">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="7e0a3-136">Die `WantedBy=multi-user.target` Einstellung bewirkt, dass der Dienst gestartet wird, wenn das Linux-System "Runlevel 2" erreicht, was bedeutet, dass eine nicht grafische Multi-User-Shell aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-136">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2", meaning a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="7e0a3-137">Bevor `systemd` den Dienst erkennen kann, muss die Konfiguration erneut geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-137">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="7e0a3-138">Sie steuern `systemd` mithilfe des `systemctl`-Befehls.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-138">You control `systemd` using the `systemctl` command.</span></span> <span data-ttu-id="7e0a3-139">Verwenden Sie nach dem erneuten Laden den Unterbefehl `status`, um zu bestätigen, dass die Anwendung erfolgreich registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-139">After reloading, use the `status` subcommand to confirm the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="7e0a3-140">Wenn Sie den Dienst ordnungsgemäß konfiguriert haben, wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7e0a3-140">If you've configured the service correctly, the following output will be shown:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="7e0a3-141">Verwenden Sie den `start`-Befehl, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-141">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="7e0a3-142">Die `.service`-Erweiterung ist optional, wenn `systemctl start`verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-142">The `.service` extension is optional when using `systemctl start`.</span></span>

<span data-ttu-id="7e0a3-143">Wenn Sie `systemd` möchten, dass der Dienst beim Systemstart automatisch gestartet wird, verwenden Sie den `enable`-Befehl.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-143">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="7e0a3-144">In Journal Protokoll protokollieren</span><span class="sxs-lookup"><span data-stu-id="7e0a3-144">Log to journald</span></span>

<span data-ttu-id="7e0a3-145">Die Linux-Entsprechung des Windows-Ereignis Protokolls ist `journald`, ein strukturierter Protokollierungs Systemdienst, der Teil von `systemd`ist.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-145">The Linux equivalent of the Windows Event Log is `journald`, a structured logging system service that is part of `systemd`.</span></span> <span data-ttu-id="7e0a3-146">Protokollmeldungen, die von einem Linux-Daemon in die Standardausgabe geschrieben werden, werden automatisch in `journald`geschrieben. verwenden Sie daher den Abschnitt `Console` der Protokollierungs Konfiguration, um Protokollierungs Ebenen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-146">Log messages written to the standard output by a Linux daemon are automatically written to `journald`, so to configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="7e0a3-147">Mit der `UseSystemd` Host-Generator-Methode wird das Konsolenausgabe Format automatisch so konfiguriert, dass es dem Journal entspricht.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-147">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="7e0a3-148">Da `journald` der Standard für Linux-Protokolle ist, gibt es eine Reihe von Tools, die integriert werden können, und Sie können Protokolle problemlos von `journald` an ein externes Protokollierungs System weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-148">Because `journald` is the standard for Linux logs, there are a variety of tools that integrate with it, and you can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="7e0a3-149">Wenn Sie lokal auf dem Host arbeiten, können Sie den `journalctl`-Befehl verwenden, um Protokolle in der Befehlszeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-149">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="7e0a3-150">Wenn eine GUI-Umgebung auf dem Host verfügbar ist, sind einige grafische Protokoll-Viewer für Linux verfügbar, z. b. *qjournalctl* und *gnome-Logs*.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-150">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="7e0a3-151">Weitere Informationen zum Abfragen des systemd-Journal von der Befehlszeile mit `journalctl`finden Sie auf [der Seite "man Pages](https://manpages.debian.org/buster/systemd/journalctl.1)".</span><span class="sxs-lookup"><span data-stu-id="7e0a3-151">To learn more about querying the systemd journal from the command line with `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="7e0a3-152">HTTPS-Zertifikate für selbst gehostete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7e0a3-152">HTTPS Certificates for self-hosted applications</span></span>

<span data-ttu-id="7e0a3-153">Wenn Sie eine GrpC-Anwendung in der Produktionsumgebung ausführen, sollten Sie ein TLS-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority, ca) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-153">When running a gRPC application in production, you should use a TLS certificate from a trusted Certificate Authority (CA).</span></span> <span data-ttu-id="7e0a3-154">Diese Zertifizierungsstelle kann eine öffentliche Zertifizierungsstelle oder eine interne Zertifizierungsstelle für Ihre Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-154">This CA could be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="7e0a3-155">Auf Windows-Hosts kann das Zertifikat mithilfe der [X509Store-Klasse](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0)aus einem sicheren [Zertifikat Speicher](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-155">On Windows hosts, the certificate may be loaded from a secure [Certificate Store](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) using the [X509Store class](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0).</span></span> <span data-ttu-id="7e0a3-156">Die `X509Store`-Klasse kann auch mit dem OpenSSL-Schlüsselspeicher auf einigen Linux-Hosts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-156">The `X509Store` class can also be used with the OpenSSL key-store on some Linux hosts.</span></span>

<span data-ttu-id="7e0a3-157">Zertifikate können auch mit einem der [X509Certificate2-Konstruktoren](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0)erstellt werden, entweder aus einer Datei (z. b. einer `.pfx` Datei, die durch ein sicheres Kennwort geschützt ist), oder aus Binärdaten, die von einem sicheren Speicherdienst wie [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-157">Certificates may also be created using one of the [X509Certificate2 constructors](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), either from a file (for example a `.pfx` file protected by a strong password), or from binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="7e0a3-158">Kestrel kann so konfiguriert werden, dass ein Zertifikat auf zweierlei Weise verwendet wird: von der Konfiguration oder im Code.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-158">Kestrel can be configured to use a certificate in two ways: from configuration, or in code.</span></span>

### <a name="set-https-certificates-using-configuration"></a><span data-ttu-id="7e0a3-159">Festlegen von HTTPS-Zertifikaten mithilfe der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7e0a3-159">Set HTTPS certificates using configuration</span></span>

<span data-ttu-id="7e0a3-160">Der Konfigurations Ansatz erfordert, dass der Pfad zum Zertifikat `.pfx` Datei und das Kennwort im Kestrel-Konfigurations Abschnitt festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-160">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="7e0a3-161">In `appsettings.json`, die wie folgt aussehen würde.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-161">In `appsettings.json` that would look like this.</span></span>

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

<span data-ttu-id="7e0a3-162">Das Kennwort sollte mithilfe einer sicheren Konfigurations Quelle, z. b. Azure keyvault oder hashicorp Vault, bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-162">The password should be provided using a secure configuration source such as Azure KeyVault or Hashicorp Vault.</span></span>

<span data-ttu-id="7e0a3-163">Unverschlüsselte Kenn Wörter sollten nicht in Konfigurationsdateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-163">You SHOULD NOT store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="7e0a3-164">Festlegen von HTTPS-Zertifikaten im Code</span><span class="sxs-lookup"><span data-stu-id="7e0a3-164">Set HTTPS certificates in code</span></span>

<span data-ttu-id="7e0a3-165">Verwenden Sie zum Konfigurieren von HTTPS für Kestrel im Code die `ConfigureKestrel`-Methode auf `IWebHostBuilder` in der `Program`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-165">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="7e0a3-166">Das Kennwort für die `.pfx` Datei sollte wiederum in einer sicheren Konfigurations Quelle gespeichert und aus dieser abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e0a3-166">Again, the password for the `.pfx` file should be stored in and retrieved from a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7e0a3-167">[Zurück](grpc-in-production.md)
>[Weiter](docker.md)</span><span class="sxs-lookup"><span data-stu-id="7e0a3-167">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
