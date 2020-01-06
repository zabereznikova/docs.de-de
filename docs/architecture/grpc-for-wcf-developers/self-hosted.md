---
title: 'Selbstgeh ostete GrpC-Anwendungen: GrpC für WCF-Entwickler'
description: Bereitstellen von ASP.net Core GrpC-Anwendungen als selbstgeh ostete Dienste
ms.date: 09/02/2019
ms.openlocfilehash: 00b4ad50eae629b5b36a890d1eecf7119386c74c
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545062"
---
# <a name="self-hosted-grpc-applications"></a>Selbstgeh ostete GrpC-Anwendungen

Obwohl ASP.net Core 3,0-Anwendungen in IIS unter Windows Server gehostet werden können, ist es derzeit nicht möglich, eine GrpC-Anwendung in IIS zu hosten, da einige der http/2-Funktionen noch nicht unterstützt werden. Diese Funktionalität wird in einem zukünftigen Update von Windows Server erwartet.

Dank einiger neuer Features in den .net Core 3,0-hostingerweiterungen können Sie die Anwendung als Windows-Dienst oder als Linux-Dienst ausführen, der von [systemd](https://en.wikipedia.org/wiki/Systemd)gesteuert wird.

## <a name="run-your-app-as-a-windows-service"></a>Ausführen der App als Windows-Dienst

Wenn Sie die ASP.net Core Anwendung für die Verwendung als Windows-Dienst konfigurieren möchten, installieren Sie das [Microsoft. Extensions. Hosting. Windows Server](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) -Paket von nuget. Fügen Sie dann der `CreateHostBuilder`-Methode in `Program.cs`einen aufzurufenden `UseWindowsService` hinzu.

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
> Wenn die Anwendung nicht als Windows-Dienst ausgeführt wird, wird von der `UseWindowsService`-Methode nichts ausgeführt.

Veröffentlichen Sie Ihre Anwendung jetzt entweder aus Visual Studio, indem Sie mit der rechten Maustaste auf das Projekt klicken und im Kontextmenü *veröffentlichen* auswählen, oder klicken Sie auf der .net Core-CLI.

Wenn Sie eine .net Core-Anwendung veröffentlichen, können Sie auswählen, ob Sie eine *Framework-abhängige* Bereitstellung oder eine *eigenständige* Bereitstellung erstellen möchten. Framework-abhängige bereit Stellungen erfordern, dass die freigegebene .net Core-Laufzeit auf dem Host installiert ist, auf dem Sie ausgeführt werden. Eigenständige bereit Stellungen werden mit einer kompletten Kopie der .net Core-Laufzeit und des .net Core-Frameworks veröffentlicht und können auf jedem Host ausgeführt werden. Weitere Informationen, einschließlich der vor-und Nachteile der einzelnen Ansätze, finden Sie in der Dokumentation zur [.net Core-Anwendungs Bereitstellung](../../core/deploying/index.md) .

Um einen eigenständigen Build der Anwendung zu veröffentlichen, bei dem die .net Core 3,0-Runtime nicht auf dem Host installiert werden muss, geben Sie die Runtime an, die in die Anwendung eingeschlossen werden soll, indem Sie das Flag `-r` (oder `--runtime`) verwenden.

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

Wenn Sie einen Framework-abhängigen Build veröffentlichen möchten, lassen Sie das `-r`-Flag aus.

```console
dotnet publish -c Release -o ./publish
```

Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner, und erstellen Sie mit dem [Hilfsprogramm SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) einen Windows-Dienst für die ausführbare Datei.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a>In Windows-Ereignisprotokoll protokollieren

Die `UseWindowsService`-Methode fügt automatisch einen [Protokollierungs](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) Anbieter hinzu, der Protokollmeldungen in das Windows-Ereignisprotokoll schreibt. Sie können die Protokollierung für diesen Anbieter konfigurieren, indem Sie dem Abschnitt `Logging` von `appsettings.json` oder einer anderen Konfigurations Quelle einen `EventLog` Eintrag hinzufügen. Der im Ereignisprotokoll verwendete Quellname kann überschrieben werden, indem in diesen Einstellungen eine `SourceName`-Eigenschaft festgelegt wird. Wenn Sie keinen Namen angeben, wird der Standard Anwendungsname (normalerweise der Name der ausführbaren Assembly) verwendet.

Weitere Informationen zur Protokollierung finden Sie am Ende dieses Kapitels.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Ausführen der App als Linux-Dienst mit "systemd"

Installieren Sie das [Microsoft. Extensions. Hosting. systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) -Paket von nuget, um die ASP.net Core Anwendung so zu konfigurieren, dass Sie als Linux-Dienst ausgeführt wird (oder als *Daemon* in einer Linux-Anwendung). Fügen Sie dann der `CreateHostBuilder`-Methode in `Program.cs`einen aufzurufenden `UseSystemd` hinzu.

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
> Wenn die Anwendung nicht als Linux-Dienst ausgeführt wird, wird von der `UseSystemd`-Methode nichts ausgeführt.

Veröffentlichen Sie nun Ihre Anwendung (entweder Framework-abhängig oder eigenständig für die relevante Linux-Laufzeit, z. b. `linux-x64`), indem Sie mit der rechten Maustaste auf das Projekt klicken und im Kontextmenü veröffentlichen auswählen. Sie können auch im .net Core-CLI mit dem folgenden Befehl *veröffentlichen* .

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner auf dem Linux-Host. Um den Dienst zu registrieren, muss dem `/etc/systemd/system` Verzeichnis eine spezielle Datei ("Unit file") hinzugefügt werden. Sie benötigen die root-Berechtigung, um eine Datei in diesem Ordner zu erstellen. Benennen Sie die Datei mit dem Bezeichner, den Sie verwenden möchten `systemd` und der `.service` Erweiterung. Beispielsweise `/etc/systemd/system/myapp.service`.

Die Dienst Datei verwendet das INI-Format, wie in diesem Beispiel gezeigt.

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

Die `Type=notify`-Eigenschaft teilt `systemd` mit, dass die Anwendung Sie beim Starten und Herunterfahren benachrichtigt. Die `WantedBy=multi-user.target` Einstellung bewirkt, dass der Dienst gestartet wird, wenn das Linux-System "Runlevel 2" erreicht, was bedeutet, dass eine nicht grafische Multi-User-Shell aktiv ist.

Bevor `systemd` den Dienst erkennen kann, muss die Konfiguration erneut geladen werden. Sie steuern `systemd` mithilfe des `systemctl`-Befehls. Verwenden Sie nach dem erneuten Laden den Unterbefehl `status`, um zu bestätigen, dass die Anwendung erfolgreich registriert wurde.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Wenn Sie den Dienst ordnungsgemäß konfiguriert haben, wird die folgende Ausgabe angezeigt:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Verwenden Sie den `start`-Befehl, um den Dienst zu starten.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> Die `.service`-Erweiterung ist optional, wenn `systemctl start`verwendet wird.

Wenn Sie `systemd` möchten, dass der Dienst beim Systemstart automatisch gestartet wird, verwenden Sie den `enable`-Befehl.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>In Journal Protokoll protokollieren

Die Linux-Entsprechung des Windows-Ereignis Protokolls ist `journald`, ein strukturierter Protokollierungs Systemdienst, der Teil von `systemd`ist. Protokollmeldungen, die von einem Linux-Daemon in die Standardausgabe geschrieben werden, werden automatisch in `journald`geschrieben. verwenden Sie daher den Abschnitt `Console` der Protokollierungs Konfiguration, um Protokollierungs Ebenen zu konfigurieren. Mit der `UseSystemd` Host-Generator-Methode wird das Konsolenausgabe Format automatisch so konfiguriert, dass es dem Journal entspricht.

Da `journald` der Standard für Linux-Protokolle ist, gibt es eine Reihe von Tools, die integriert werden können, und Sie können Protokolle problemlos von `journald` an ein externes Protokollierungs System weiterleiten. Wenn Sie lokal auf dem Host arbeiten, können Sie den `journalctl`-Befehl verwenden, um Protokolle in der Befehlszeile anzuzeigen.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Wenn eine GUI-Umgebung auf dem Host verfügbar ist, sind einige grafische Protokoll-Viewer für Linux verfügbar, z. b. *qjournalctl* und *gnome-Logs*.

Weitere Informationen zum Abfragen des systemd-Journal von der Befehlszeile mit `journalctl`finden Sie auf [der Seite "man Pages](https://manpages.debian.org/buster/systemd/journalctl.1)".

## <a name="https-certificates-for-self-hosted-applications"></a>HTTPS-Zertifikate für selbst gehostete Anwendungen

Wenn Sie eine GrpC-Anwendung in der Produktionsumgebung ausführen, sollten Sie ein TLS-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority, ca) verwenden. Diese Zertifizierungsstelle kann eine öffentliche Zertifizierungsstelle oder eine interne Zertifizierungsstelle für Ihre Organisation sein.

Auf Windows-Hosts kann das Zertifikat mithilfe der <xref:System.Security.Cryptography.X509Certificates.X509Store>-Klasse aus einem sicheren [Zertifikat Speicher](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) geladen werden. Die `X509Store`-Klasse kann auch mit dem OpenSSL-Schlüsselspeicher auf einigen Linux-Hosts verwendet werden.

Zertifikate können auch mit einem der [X509Certificate2-Konstruktoren](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0)erstellt werden, entweder aus einer Datei (z. b. einer `.pfx` Datei, die durch ein sicheres Kennwort geschützt ist), oder aus Binärdaten, die von einem sicheren Speicherdienst wie [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)abgerufen werden.

Kestrel kann so konfiguriert werden, dass ein Zertifikat auf zweierlei Weise verwendet wird: von der Konfiguration oder im Code.

### <a name="set-https-certificates-using-configuration"></a>Festlegen von HTTPS-Zertifikaten mithilfe der Konfiguration

Der Konfigurations Ansatz erfordert, dass der Pfad zum Zertifikat `.pfx` Datei und das Kennwort im Kestrel-Konfigurations Abschnitt festgelegt werden. In `appsettings.json`, die wie folgt aussehen würde.

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

Das Kennwort sollte mithilfe einer sicheren Konfigurations Quelle, z. b. Azure keyvault oder hashicorp Vault, bereitgestellt werden.

Unverschlüsselte Kenn Wörter sollten nicht in Konfigurationsdateien gespeichert werden.

### <a name="set-https-certificates-in-code"></a>Festlegen von HTTPS-Zertifikaten im Code

Verwenden Sie zum Konfigurieren von HTTPS für Kestrel im Code die `ConfigureKestrel`-Methode auf `IWebHostBuilder` in der `Program`-Klasse.

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

Das Kennwort für die `.pfx` Datei sollte wiederum in einer sicheren Konfigurations Quelle gespeichert und aus dieser abgerufen werden.

>[!div class="step-by-step"]
>[Zurück](grpc-in-production.md)
>[Weiter](docker.md)
