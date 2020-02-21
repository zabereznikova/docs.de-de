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
# <a name="self-hosted-grpc-applications"></a>Selbstgeh ostete GrpC-Anwendungen

Obwohl ASP.net Core 3,0-Anwendungen in IIS unter Windows Server gehostet werden können, ist es derzeit nicht möglich, eine GrpC-Anwendung in IIS zu hosten, da einige der http/2-Funktionen nicht unterstützt werden. Diese Funktion ist ein Ziel für ein zukünftiges Update von Windows Server.

Sie können Ihre Anwendung als Windows-Dienst ausführen. Oder Sie können Sie als Linux-Dienst ausführen, der von [systemd](https://en.wikipedia.org/wiki/Systemd)gesteuert wird, da neue Features in den .net Core 3,0-hostingerweiterungen enthalten sind.

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

Veröffentlichen Sie Ihre Anwendung nun mit einer der folgenden Methoden:

* Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt, und wählen Sie im Kontextmenü **veröffentlichen** aus.
* Aus dem .net Core-CLI.

Wenn Sie eine .net Core-Anwendung veröffentlichen, können Sie auswählen, ob Sie eine *Framework-abhängige* Bereitstellung oder eine *eigenständige* Bereitstellung erstellen möchten. Framework-abhängige bereit Stellungen erfordern, dass die freigegebene .net Core-Laufzeit auf dem Host installiert ist, auf dem Sie ausgeführt werden. Eigenständige bereit Stellungen werden mit einer kompletten Kopie der .net Core-Laufzeit und des .net Core-Frameworks veröffentlicht und können auf jedem Host ausgeführt werden. Weitere Informationen, einschließlich der vor-und Nachteile der einzelnen Ansätze, finden Sie in der Dokumentation zur [.net Core-Anwendungs Bereitstellung](../../core/deploying/index.md) .

Wenn Sie einen eigenständigen Build der Anwendung veröffentlichen möchten, für den die .net Core 3,0-Runtime nicht auf dem Host installiert werden muss, geben Sie die Runtime an, die in der Anwendung enthalten sein soll. Verwenden Sie das Flag `-r` (oder `--runtime`).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Wenn Sie einen Framework-abhängigen Build veröffentlichen möchten, lassen Sie das `-r`-Flag aus.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner. Verwenden Sie dann das [SC-Tool](/windows/desktop/services/controlling-a-service-using-sc) , um einen Windows-Dienst für die ausführbare Datei zu erstellen.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Im Windows-Ereignisprotokoll protokollieren

Die `UseWindowsService`-Methode fügt automatisch einen [Protokollierungs](/aspnet/core/fundamentals/logging/) Anbieter hinzu, der Protokollmeldungen in das Windows-Ereignisprotokoll schreibt. Sie können die Protokollierung für diesen Anbieter konfigurieren, indem Sie dem Abschnitt `Logging` von `appsettings.json` oder einer anderen Konfigurations Quelle einen `EventLog` Eintrag hinzufügen. 

Sie können den im Ereignisprotokoll verwendeten Quellnamen überschreiben, indem Sie in diesen Einstellungen eine `SourceName`-Eigenschaft festlegen. Wenn Sie keinen Namen angeben, wird der Standard Anwendungsname (normalerweise der Name der ausführbaren Assembly) verwendet.

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

Veröffentlichen Sie nun Ihre Anwendung. Die Anwendung kann entweder Framework-abhängig oder eigenständig für die relevante Linux-Laufzeit sein (z. b. `linux-x64`). Sie können mit einer der folgenden Methoden veröffentlichen:

* Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt, und wählen Sie im Kontextmenü **veröffentlichen** aus. 
* Verwenden Sie in der .net Core-CLI den folgenden Befehl:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
Kopieren Sie den gesamten Inhalt des `publish` Verzeichnisses in einen Installationsordner auf dem Linux-Host. Um den Dienst zu registrieren, muss eine spezielle Datei, eine so genannte *Einheits Datei*, dem `/etc/systemd/system` Verzeichnis hinzugefügt werden. Sie benötigen die root-Berechtigung, um eine Datei in diesem Ordner zu erstellen. Benennen Sie die Datei mit dem Bezeichner, den Sie verwenden `systemd` möchten, und `.service` Erweiterung. Verwenden Sie z. B. `/etc/systemd/system/myapp.service`.

Die Dienst Datei verwendet das INI-Format, wie im folgenden Beispiel gezeigt:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

Die `Type=notify`-Eigenschaft teilt `systemd` mit, dass die Anwendung Sie beim Starten und Herunterfahren benachrichtigt. Die `WantedBy=multi-user.target` Einstellung bewirkt, dass der Dienst gestartet wird, wenn das Linux-System "Runlevel 2" erreicht. Dies bedeutet, dass eine nicht grafische Multi-User-Shell aktiv ist.

Bevor `systemd` den Dienst erkennen kann, muss die Konfiguration erneut geladen werden. Sie steuern `systemd` mithilfe des `systemctl`-Befehls. Verwenden Sie nach dem erneuten Laden den Unterbefehl `status`, um zu bestätigen, dass die Anwendung erfolgreich registriert wurde.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Wenn Sie den Dienst ordnungsgemäß konfiguriert haben, erhalten Sie die folgende Ausgabe:

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
> Die `.service`-Erweiterung ist optional, wenn Sie `systemctl start`verwenden.

Wenn Sie `systemd` möchten, dass der Dienst beim Systemstart automatisch gestartet wird, verwenden Sie den `enable`-Befehl.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>In Journal Protokoll protokollieren

Die Linux-Entsprechung des Windows-Ereignis Protokolls ist `journald`, ein strukturierter Protokollierungs Systemdienst, der Teil von `systemd`ist. Protokollmeldungen, die von einem Linux-Daemon in die Standardausgabe geschrieben werden, werden automatisch in `journald`geschrieben. Verwenden Sie zum Konfigurieren von Protokolliergraden den `Console` Abschnitt der Protokollierungs Konfiguration. Mit der `UseSystemd` Host-Generator-Methode wird das Konsolenausgabe Format automatisch so konfiguriert, dass es dem Journal entspricht.

Da `journald` der Standard für Linux-Protokolle ist, sind eine Reihe von Tools integriert. Sie können Protokolle problemlos von `journald` an ein externes Protokollierungs System weiterleiten. Wenn Sie lokal auf dem Host arbeiten, können Sie den `journalctl`-Befehl verwenden, um Protokolle in der Befehlszeile anzuzeigen.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Wenn eine GUI-Umgebung auf dem Host verfügbar ist, sind einige grafische Protokoll-Viewer für Linux verfügbar, z. b. *qjournalctl* und *gnome-Logs*.

Weitere Informationen zum Abfragen des `systemd` Journal von der Befehlszeile aus mithilfe `journalctl`finden Sie auf [der Seite "man Pages](https://manpages.debian.org/buster/systemd/journalctl.1)".

## <a name="https-certificates-for-self-hosted-applications"></a>HTTPS-Zertifikate für selbst gehostete Anwendungen

Wenn Sie eine GrpC-Anwendung in der Produktionsumgebung ausführen, sollten Sie ein TLS-Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle (Certificate Authority, ca) verwenden. Diese Zertifizierungsstelle kann eine öffentliche Zertifizierungsstelle oder eine interne Zertifizierungsstelle für Ihre Organisation sein.

Auf Windows-Hosts können Sie das Zertifikat mit der <xref:System.Security.Cryptography.X509Certificates.X509Store>-Klasse aus einem sicheren [Zertifikat Speicher](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) laden. Sie können auch die `X509Store`-Klasse mit dem OpenSSL Key Store auf einigen Linux-Hosts verwenden.

Sie können Zertifikate auch mit einem der [X509Certificate2-Konstruktoren](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)erstellen, indem Sie Folgendes verwenden:

* Eine Datei, z. b. eine `.pfx` Datei, die durch ein sicheres Kennwort geschützt ist
* Von einem sicheren Speicherdienst abgerufene Binärdaten, wie z. b. [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)

Sie können Kestrel so konfigurieren, dass ein Zertifikat auf zweierlei Weise verwendet wird: aus Konfiguration oder Code.

### <a name="set-https-certificates-by-using-configuration"></a>Festlegen von HTTPS-Zertifikaten mithilfe der Konfiguration

Der Konfigurations Ansatz erfordert, dass der Pfad zum Zertifikat `.pfx` Datei und das Kennwort im Kestrel-Konfigurations Abschnitt festgelegt werden. In `appsettings.json`sieht dies wie folgt aus:

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

Geben Sie das Kennwort an, indem Sie eine sichere Konfigurations Quelle wie Azure Key Vault oder den hashicorp-Tresor verwenden.

> [!IMPORTANT]
> Speichern Sie unverschlüsselte Kenn Wörter nicht in Konfigurationsdateien.

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

Stellen Sie auch hier sicher, dass Sie das Kennwort für die `.pfx` Datei in speichern und aus einer sicheren Konfigurations Quelle abrufen.

>[!div class="step-by-step"]
>[Zurück](grpc-in-production.md)
>[Weiter](docker.md)
