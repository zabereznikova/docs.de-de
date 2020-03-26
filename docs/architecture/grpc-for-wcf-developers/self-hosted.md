---
title: Selbstgehostete gRPC-Anwendungen - gRPC für WCF-Entwickler
description: Bereitstellen ASP.NET Core gRPC-Anwendungen als selbst gehostete Dienste.
ms.date: 09/02/2019
ms.openlocfilehash: 69f70e4077247fd07eba7abeee82f257dd1f4f90
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110905"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="e2732-103">Selbst gehostete gRPC-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e2732-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="e2732-104">Obwohl ASP.NET Core 3.0-Anwendungen in IIS unter Windows Server gehostet werden können, ist es derzeit nicht möglich, eine gRPC-Anwendung in IIS zu hosten, da einige der HTTP/2-Funktionen nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e2732-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="e2732-105">Diese Funktionalität ist ein Ziel für ein zukünftiges Update auf Windows Server.</span><span class="sxs-lookup"><span data-stu-id="e2732-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="e2732-106">Sie können Ihre Anwendung als Windows-Dienst ausführen.</span><span class="sxs-lookup"><span data-stu-id="e2732-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="e2732-107">Sie können ihn auch als Linux-Dienst ausführen, der von [systemd](https://en.wikipedia.org/wiki/Systemd)gesteuert wird, da die Hosterweiterungen von .NET Core 3.0 neue Funktionen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e2732-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="e2732-108">Ausführen Ihrer App als Windows-Dienst</span><span class="sxs-lookup"><span data-stu-id="e2732-108">Run your app as a Windows service</span></span>

<span data-ttu-id="e2732-109">Um die ASP.NET Core-Anwendung so zu konfigurieren, dass sie als Windows-Dienst ausgeführt wird, installieren Sie das Paket [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) aus NuGet.</span><span class="sxs-lookup"><span data-stu-id="e2732-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="e2732-110">Fügen Sie dann `UseWindowsService` einen `CreateHostBuilder` Aufruf `Program.cs`zur Methode in hinzu.</span><span class="sxs-lookup"><span data-stu-id="e2732-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="e2732-111">Wenn die Anwendung nicht als Windows-Dienst `UseWindowsService` ausgeführt wird, bewirkt die Methode nichts.</span><span class="sxs-lookup"><span data-stu-id="e2732-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="e2732-112">Veröffentlichen Sie nun Ihre Anwendung mit einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="e2732-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="e2732-113">Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt und wählen Sie im Kontextmenü **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="e2732-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="e2732-114">Aus der .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="e2732-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="e2732-115">Wenn Sie eine .NET Core-Anwendung veröffentlichen, können Sie eine *frameworkabhängige* Bereitstellung oder eine *eigenständige* Bereitstellung erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2732-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="e2732-116">Für Framework-abhängige Bereitstellungen muss die freigegebene .NET Core Runtime auf dem Host installiert werden, auf dem sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2732-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="e2732-117">Eigenständige Bereitstellungen werden mit einer vollständigen Kopie der .NET Core-Laufzeit und des Frameworks veröffentlicht und können auf jedem Host ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2732-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="e2732-118">Weitere Informationen, einschließlich der Vor- und Nachteile der einzelnen Ansätze, finden Sie in der [Dokumentation zu .NET Core-Anwendungsbereitstellung.](../../core/deploying/index.md)</span><span class="sxs-lookup"><span data-stu-id="e2732-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="e2732-119">Um einen eigenständigen Build der Anwendung zu veröffentlichen, für den die .NET Core 3.0-Laufzeit nicht auf dem Host installiert werden muss, geben Sie die Laufzeit an, die in die Anwendung eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2732-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="e2732-120">Verwenden `-r` Sie `--runtime`das Flag (oder ).</span><span class="sxs-lookup"><span data-stu-id="e2732-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="e2732-121">Um einen frameworkabhängigen Build zu `-r` veröffentlichen, lassen Sie das Flag weg.</span><span class="sxs-lookup"><span data-stu-id="e2732-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="e2732-122">Kopieren Sie den `publish` vollständigen Inhalt des Verzeichnisses in einen Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="e2732-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="e2732-123">Verwenden Sie dann das [sc-Tool,](/windows/desktop/services/controlling-a-service-using-sc) um einen Windows-Dienst für die ausführbare Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2732-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="e2732-124">Anmelden am Windows-Ereignisprotokoll</span><span class="sxs-lookup"><span data-stu-id="e2732-124">Log to the Windows event log</span></span>

<span data-ttu-id="e2732-125">Die `UseWindowsService` Methode fügt automatisch einen [Protokollierungsanbieter](/aspnet/core/fundamentals/logging/) hinzu, der Protokollnachrichten in das Windows-Ereignisprotokoll schreibt.</span><span class="sxs-lookup"><span data-stu-id="e2732-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="e2732-126">Sie können die Protokollierung für `EventLog` diesen `Logging` Anbieter `appsettings.json` konfigurieren, indem Sie dem Abschnitt oder einer anderen Konfigurationsquelle einen Eintrag hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e2732-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="e2732-127">Sie können den im Ereignisprotokoll verwendeten Quellnamen `SourceName` überschreiben, indem Sie eine Eigenschaft in diesen Einstellungen festlegen.</span><span class="sxs-lookup"><span data-stu-id="e2732-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="e2732-128">Wenn Sie keinen Namen angeben, wird der Standardanwendungsname (normalerweise der ausführbare Assemblyname) verwendet.</span><span class="sxs-lookup"><span data-stu-id="e2732-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="e2732-129">Weitere Informationen zur Protokollierung finden Sie am Ende dieses Kapitels.</span><span class="sxs-lookup"><span data-stu-id="e2732-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="e2732-130">Führen Sie Ihre App als Linux-Dienst mit systemd</span><span class="sxs-lookup"><span data-stu-id="e2732-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="e2732-131">Um Ihre ASP.NET Core-Anwendung so zu konfigurieren, dass sie als Linux-Dienst (oder *Daemon* in Linux-Sprache) ausgeführt wird, installieren Sie das Paket [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) von NuGet.</span><span class="sxs-lookup"><span data-stu-id="e2732-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="e2732-132">Fügen Sie dann `UseSystemd` einen `CreateHostBuilder` Aufruf `Program.cs`zur Methode in hinzu.</span><span class="sxs-lookup"><span data-stu-id="e2732-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="e2732-133">Wenn die Anwendung nicht als Linux-Dienst `UseSystemd` ausgeführt wird, tut die Methode nichts.</span><span class="sxs-lookup"><span data-stu-id="e2732-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="e2732-134">Veröffentlichen Sie nun Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e2732-134">Now publish your application.</span></span> <span data-ttu-id="e2732-135">Die Anwendung kann entweder frameworkabhängig oder für die jeweilige Linux-Laufzeit (z. B. `linux-x64`) in sich geschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="e2732-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="e2732-136">Sie können die Veröffentlichung mit einer der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="e2732-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="e2732-137">Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt und wählen Sie im Kontextmenü **Veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="e2732-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="e2732-138">Verwenden Sie in der .NET Core CLI den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="e2732-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="e2732-139">Kopieren Sie den `publish` vollständigen Inhalt des Verzeichnisses in einen Installationsordner auf dem Linux-Host.</span><span class="sxs-lookup"><span data-stu-id="e2732-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="e2732-140">Für das Registrieren des Dienstes muss eine spezielle Datei, `/etc/systemd/system` eine so genannte *Einheitendatei,* zum Verzeichnis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e2732-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="e2732-141">Sie benötigen root-Berechtigung, um eine Datei in diesem Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2732-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="e2732-142">Benennen Sie die Datei mit `systemd` dem Bezeichner, den Sie verwenden möchten, und der `.service` Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="e2732-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="e2732-143">Verwenden Sie z. B. `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="e2732-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="e2732-144">Die Dienstdatei verwendet das INI-Format, wie in diesem Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e2732-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="e2732-145">Die `Type=notify` Eigenschaft `systemd` teilt mit, dass die Anwendung sie beim Starten und Herunterfahren benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="e2732-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="e2732-146">Die `WantedBy=multi-user.target` Einstellung bewirkt, dass der Dienst gestartet wird, wenn das Linux-System "runlevel 2" erreicht, was bedeutet, dass eine nicht-grafische, Mehrbenutzer-Shell aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e2732-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical, multi-user shell is active.</span></span>

<span data-ttu-id="e2732-147">Bevor `systemd` der Dienst erkannt wird, muss er seine Konfiguration neu laden.</span><span class="sxs-lookup"><span data-stu-id="e2732-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="e2732-148">Sie `systemd` steuern mit `systemctl` dem Befehl.</span><span class="sxs-lookup"><span data-stu-id="e2732-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="e2732-149">Verwenden Sie nach `status` dem erneuten Laden den Unterbefehl, um zu bestätigen, dass die Anwendung erfolgreich registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="e2732-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="e2732-150">Wenn Sie den Dienst richtig konfiguriert haben, erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e2732-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="e2732-151">Verwenden `start` Sie den Befehl, um den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="e2732-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="e2732-152">Die `.service` Erweiterung ist optional, `systemctl start`wenn Sie .</span><span class="sxs-lookup"><span data-stu-id="e2732-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="e2732-153">Um `systemd` den Dienst beim Systemstart automatisch `enable` zu starten, verwenden Sie den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e2732-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="e2732-154">Protokollieren in Journald</span><span class="sxs-lookup"><span data-stu-id="e2732-154">Log to journald</span></span>

<span data-ttu-id="e2732-155">Das Linux-Äquivalent des Windows-Ereignisprotokolls ist `journald`, ein `systemd`strukturierter Protokollierungssystemdienst, der Teil von ist.</span><span class="sxs-lookup"><span data-stu-id="e2732-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="e2732-156">Protokollmeldungen, die von einem Linux-Daemon in `journald`die Standardausgabe geschrieben wurden, werden automatisch in geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2732-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="e2732-157">Verwenden Sie zum Konfigurieren `Console` von Protokollierungsebenen den Abschnitt der Protokollierungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="e2732-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="e2732-158">Die `UseSystemd` Host Builder-Methode konfiguriert das Konsolenausgabeformat automatisch entsprechend der Erfassung.</span><span class="sxs-lookup"><span data-stu-id="e2732-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="e2732-159">Da `journald` es sich um den Standard für Linux-Protokolle handelt, lassen sich eine Vielzahl von Tools integrieren.</span><span class="sxs-lookup"><span data-stu-id="e2732-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="e2732-160">Sie können Protokolle `journald` einfach an ein externes Protokollierungssystem weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="e2732-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="e2732-161">Sie arbeiten lokal auf dem `journalctl` Host und können den Befehl verwenden, um Protokolle über die Befehlszeile anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e2732-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="e2732-162">Wenn Auf Ihrem Host eine GUI-Umgebung verfügbar ist, stehen einige grafische Protokollbetrachter für Linux zur Verfügung, z. B. *QJournalctl* und *gnome-logs*.</span><span class="sxs-lookup"><span data-stu-id="e2732-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="e2732-163">Weitere Informationen zum Abfragen `systemd` des Journals über `journalctl`die Befehlszeile mithilfe von finden Sie unter [Die Manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="e2732-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="e2732-164">HTTPS-Zertifikate für selbst gehostete Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e2732-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="e2732-165">Wenn Sie eine gRPC-Anwendung in der Produktion ausführen, sollten Sie ein TLS-Zertifikat einer vertrauenswürdigen Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2732-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="e2732-166">Bei dieser Zertifizierungsstelle kann es sich um eine öffentliche Zertifizierungsstelle oder um eine interne Zertifizierungsstelle für Ihre Organisation erachten.</span><span class="sxs-lookup"><span data-stu-id="e2732-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="e2732-167">Auf Windows-Hosts können Sie das Zertifikat mithilfe der <xref:System.Security.Cryptography.X509Certificates.X509Store> Klasse aus einem sicheren [Zertifikatspeicher](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) laden.</span><span class="sxs-lookup"><span data-stu-id="e2732-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="e2732-168">Sie können die `X509Store` Klasse auch mit dem OpenSSL-Schlüsselspeicher auf einigen Linux-Hosts verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2732-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="e2732-169">Sie können Zertifikate auch erstellen, indem Sie einen der [X509Certificate2-Konstruktoren](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)verwenden, von einem der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e2732-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="e2732-170">Eine Datei, z. B. eine `.pfx` Datei, die durch ein sicheres Kennwort geschützt ist</span><span class="sxs-lookup"><span data-stu-id="e2732-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="e2732-171">Binäre Daten, die von einem sicheren Speicherdienst wie [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="e2732-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="e2732-172">Sie können Kestrel so konfigurieren, dass ein Zertifikat auf zwei Arten verwendet wird: von der Konfiguration bis zum Code.</span><span class="sxs-lookup"><span data-stu-id="e2732-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="e2732-173">Festlegen von HTTPS-Zertifikaten mithilfe der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e2732-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="e2732-174">Der Konfigurationsansatz erfordert das Festlegen `.pfx` des Pfads zur Zertifikatdatei und des Kennworts im Abschnitt Kestrel-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e2732-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="e2732-175">In `appsettings.json`würde das wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="e2732-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="e2732-176">Geben Sie das Kennwort mithilfe einer sicheren Konfigurationsquelle wie Azure Key Vault oder Hashicorp Vault ein.</span><span class="sxs-lookup"><span data-stu-id="e2732-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2732-177">Speichern Sie keine unverschlüsselten Kennwörter in Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="e2732-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="e2732-178">Festlegen von HTTPS-Zertifikaten im Code</span><span class="sxs-lookup"><span data-stu-id="e2732-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="e2732-179">Um HTTPS auf Kestrel im `ConfigureKestrel` Code `IWebHostBuilder` zu `Program` konfigurieren, verwenden Sie die Methode in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="e2732-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="e2732-180">Achten Sie erneut darauf, das `.pfx` Kennwort für die Datei in einer sicheren Konfigurationsquelle zu speichern und aus dieser abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e2732-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e2732-181">[VorherigeS](grpc-in-production.md)
>[Weiter](docker.md)</span><span class="sxs-lookup"><span data-stu-id="e2732-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
