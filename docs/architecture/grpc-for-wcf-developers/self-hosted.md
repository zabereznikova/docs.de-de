---
title: Selbstgehostete gRPC-Anwendungen - gRPC für WCF-Entwickler
description: Bereitstellen ASP.NET Core gRPC-Anwendungen als selbst gehostete Dienste.
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147801"
---
# <a name="self-hosted-grpc-applications"></a>Selbst gehostete gRPC-Anwendungen

Obwohl ASP.NET Core 3.0-Anwendungen in IIS unter Windows Server gehostet werden können, ist es derzeit nicht möglich, eine gRPC-Anwendung in IIS zu hosten, da einige der HTTP/2-Funktionen nicht unterstützt werden. Diese Funktionalität ist ein Ziel für ein zukünftiges Update auf Windows Server.

Sie können Ihre Anwendung als Windows-Dienst ausführen. Sie können ihn auch als Linux-Dienst ausführen, der von [systemd](https://en.wikipedia.org/wiki/Systemd)gesteuert wird, da die Hosterweiterungen von .NET Core 3.0 neue Funktionen aufweisen.

## <a name="run-your-app-as-a-windows-service"></a>Ausführen Ihrer App als Windows-Dienst

Um die ASP.NET Core-Anwendung so zu konfigurieren, dass sie als Windows-Dienst ausgeführt wird, installieren Sie das Paket [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) aus NuGet. Fügen Sie dann `UseWindowsService` einen `CreateHostBuilder` Aufruf `Program.cs`zur Methode in hinzu.

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
> Wenn die Anwendung nicht als Windows-Dienst `UseWindowsService` ausgeführt wird, bewirkt die Methode nichts.

Veröffentlichen Sie nun Ihre Anwendung mit einer der folgenden Methoden:

* Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt und wählen Sie im Kontextmenü **Veröffentlichen** aus.
* Aus der .NET Core CLI.

Wenn Sie eine .NET Core-Anwendung veröffentlichen, können Sie eine *frameworkabhängige* Bereitstellung oder eine *eigenständige* Bereitstellung erstellen. Für Framework-abhängige Bereitstellungen muss die freigegebene .NET Core Runtime auf dem Host installiert werden, auf dem sie ausgeführt werden. Eigenständige Bereitstellungen werden mit einer vollständigen Kopie der .NET Core-Laufzeit und des Frameworks veröffentlicht und können auf jedem Host ausgeführt werden. Weitere Informationen, einschließlich der Vor- und Nachteile der einzelnen Ansätze, finden Sie in der [Dokumentation zu .NET Core-Anwendungsbereitstellung.](../../core/deploying/index.md)

Um einen eigenständigen Build der Anwendung zu veröffentlichen, für den die .NET Core 3.0-Laufzeit nicht auf dem Host installiert werden muss, geben Sie die Laufzeit an, die in die Anwendung eingeschlossen werden soll. Verwenden `-r` Sie `--runtime`das Flag (oder ).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Um einen frameworkabhängigen Build zu `-r` veröffentlichen, lassen Sie das Flag weg.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Kopieren Sie den `publish` vollständigen Inhalt des Verzeichnisses in einen Installationsordner. Verwenden Sie dann das [sc-Tool,](/windows/desktop/services/controlling-a-service-using-sc) um einen Windows-Dienst für die ausführbare Datei zu erstellen.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Anmelden am Windows-Ereignisprotokoll

Die `UseWindowsService` Methode fügt automatisch einen [Protokollierungsanbieter](/aspnet/core/fundamentals/logging/) hinzu, der Protokollnachrichten in das Windows-Ereignisprotokoll schreibt. Sie können die Protokollierung für `EventLog` diesen `Logging` Anbieter `appsettings.json` konfigurieren, indem Sie dem Abschnitt oder einer anderen Konfigurationsquelle einen Eintrag hinzufügen.

Sie können den im Ereignisprotokoll verwendeten Quellnamen `SourceName` überschreiben, indem Sie eine Eigenschaft in diesen Einstellungen festlegen. Wenn Sie keinen Namen angeben, wird der Standardanwendungsname (normalerweise der ausführbare Assemblyname) verwendet.

Weitere Informationen zur Protokollierung finden Sie am Ende dieses Kapitels.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Führen Sie Ihre App als Linux-Dienst mit systemd

Um Ihre ASP.NET Core-Anwendung so zu konfigurieren, dass sie als Linux-Dienst (oder *Daemon* in Linux-Sprache) ausgeführt wird, installieren Sie das Paket [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) von NuGet. Fügen Sie dann `UseSystemd` einen `CreateHostBuilder` Aufruf `Program.cs`zur Methode in hinzu.

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
> Wenn die Anwendung nicht als Linux-Dienst `UseSystemd` ausgeführt wird, tut die Methode nichts.

Veröffentlichen Sie nun Ihre Anwendung. Die Anwendung kann entweder frameworkabhängig oder für die jeweilige Linux-Laufzeit (z. B. `linux-x64`) in sich geschlossen sein. Sie können die Veröffentlichung mit einer der folgenden Methoden verwenden:

* Klicken Sie in Visual Studio mit der rechten Maustaste auf das Projekt und wählen Sie im Kontextmenü **Veröffentlichen** aus.
* Verwenden Sie in der .NET Core CLI den folgenden Befehl:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
Kopieren Sie den `publish` vollständigen Inhalt des Verzeichnisses in einen Installationsordner auf dem Linux-Host. Für das Registrieren des Dienstes muss eine spezielle Datei, `/etc/systemd/system` eine so genannte *Einheitendatei,* zum Verzeichnis hinzugefügt werden. Sie benötigen root-Berechtigung, um eine Datei in diesem Ordner zu erstellen. Benennen Sie die Datei mit `systemd` dem Bezeichner, den Sie verwenden möchten, und der `.service` Erweiterung. Verwenden Sie z. B. `/etc/systemd/system/myapp.service`.

Die Dienstdatei verwendet das INI-Format, wie in diesem Beispiel gezeigt:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

Die `Type=notify` Eigenschaft `systemd` teilt mit, dass die Anwendung sie beim Starten und Herunterfahren benachrichtigt. Die `WantedBy=multi-user.target` Einstellung bewirkt, dass der Dienst gestartet wird, wenn das Linux-System "runlevel 2" erreicht, was bedeutet, dass eine nicht-grafische Mehrbenutzer-Shell aktiv ist.

Bevor `systemd` der Dienst erkannt wird, muss er seine Konfiguration neu laden. Sie `systemd` steuern mit `systemctl` dem Befehl. Verwenden Sie nach `status` dem erneuten Laden den Unterbefehl, um zu bestätigen, dass die Anwendung erfolgreich registriert wurde.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Wenn Sie den Dienst richtig konfiguriert haben, erhalten Sie die folgende Ausgabe:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Verwenden `start` Sie den Befehl, um den Dienst zu starten.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> Die `.service` Erweiterung ist optional, `systemctl start`wenn Sie .

Um `systemd` den Dienst beim Systemstart automatisch `enable` zu starten, verwenden Sie den Befehl.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Protokollieren in Journald

Das Linux-Äquivalent des Windows-Ereignisprotokolls ist `journald`, ein `systemd`strukturierter Protokollierungssystemdienst, der Teil von ist. Protokollmeldungen, die von einem Linux-Daemon in `journald`die Standardausgabe geschrieben wurden, werden automatisch in geschrieben. Verwenden Sie zum Konfigurieren `Console` von Protokollierungsebenen den Abschnitt der Protokollierungskonfiguration. Die `UseSystemd` Host Builder-Methode konfiguriert das Konsolenausgabeformat automatisch entsprechend der Erfassung.

Da `journald` es sich um den Standard für Linux-Protokolle handelt, lassen sich eine Vielzahl von Tools integrieren. Sie können Protokolle `journald` einfach an ein externes Protokollierungssystem weiterleiten. Sie arbeiten lokal auf dem `journalctl` Host und können den Befehl verwenden, um Protokolle über die Befehlszeile anzuzeigen.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Wenn Auf Ihrem Host eine GUI-Umgebung verfügbar ist, stehen einige grafische Protokollbetrachter für Linux zur Verfügung, z. B. *QJournalctl* und *gnome-logs*.

Weitere Informationen zum Abfragen `systemd` des Journals über `journalctl`die Befehlszeile mithilfe von finden Sie unter [der Manpages](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>HTTPS-Zertifikate für selbst gehostete Anwendungen

Wenn Sie eine gRPC-Anwendung in der Produktion ausführen, sollten Sie ein TLS-Zertifikat einer vertrauenswürdigen Zertifizierungsstelle verwenden. Bei dieser Zertifizierungsstelle kann es sich um eine öffentliche Zertifizierungsstelle oder um eine interne Zertifizierungsstelle für Ihre Organisation erachten.

Auf Windows-Hosts können Sie das Zertifikat mithilfe der <xref:System.Security.Cryptography.X509Certificates.X509Store> Klasse aus einem sicheren [Zertifikatspeicher](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) laden. Sie können die `X509Store` Klasse auch mit dem OpenSSL-Schlüsselspeicher auf einigen Linux-Hosts verwenden.

Sie können Zertifikate auch erstellen, indem Sie einen der [X509Certificate2-Konstruktoren](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)verwenden, von einem der folgenden:

* Eine Datei, z. B. eine `.pfx` Datei, die durch ein sicheres Kennwort geschützt ist
* Binäre Daten, die von einem sicheren Speicherdienst wie [Azure Key Vault](https://azure.microsoft.com/services/key-vault/) abgerufen werden

Sie können Kestrel so konfigurieren, dass ein Zertifikat auf zwei Arten verwendet wird: von der Konfiguration bis zum Code.

### <a name="set-https-certificates-by-using-configuration"></a>Festlegen von HTTPS-Zertifikaten mithilfe der Konfiguration

Der Konfigurationsansatz erfordert das Festlegen `.pfx` des Pfads zur Zertifikatdatei und des Kennworts im Abschnitt Kestrel-Konfiguration. In `appsettings.json`würde das wie folgt aussehen:

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

Geben Sie das Kennwort mithilfe einer sicheren Konfigurationsquelle wie Azure Key Vault oder Hashicorp Vault ein.

> [!IMPORTANT]
> Speichern Sie keine unverschlüsselten Kennwörter in Konfigurationsdateien.

### <a name="set-https-certificates-in-code"></a>Festlegen von HTTPS-Zertifikaten im Code

Um HTTPS auf Kestrel im `ConfigureKestrel` Code `IWebHostBuilder` zu `Program` konfigurieren, verwenden Sie die Methode in der Klasse.

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

Achten Sie erneut darauf, das `.pfx` Kennwort für die Datei in einer sicheren Konfigurationsquelle zu speichern und aus dieser abzurufen.

>[!div class="step-by-step"]
>[VorherigeS](grpc-in-production.md)
>[Weiter](docker.md)
