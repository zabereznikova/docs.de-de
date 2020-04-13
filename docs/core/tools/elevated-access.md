---
title: Erhöhte Zugriffsrechte für dotnet-Befehle
description: Erfahren Sie mehr über die Best Practices für dotnet-Befehle, die erhöhte Zugriffsrechte erfordern.
author: wli3
ms.date: 06/26/2019
ms.openlocfilehash: f99e0b257772e0a73d4945f1129997d1d3308ed2
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805794"
---
# <a name="elevated-access-for-dotnet-commands"></a>Erhöhte Zugriffsrechte für dotnet-Befehle

Durch Best Practices in der Softwareentwicklung schreiben Entwickler Software, für die die geringsten Berechtigungen erforderlich sind. Einige Software, wie z.B. Tools zur Leistungsüberwachung, benötigen jedoch aufgrund von Betriebssystemregeln Administratorrechte. Die folgende Anleitung beschreibt unterstützte Szenarien für das Schreiben derartiger Software mit .NET Core.

Die folgenden Befehle können mit erhöhten Rechten ausgeführt werden:

- `dotnet tool`-Befehle wie [dotnet tool install](dotnet-tool-install.md).
- `dotnet run --no-build`
- `dotnet-core-uninstall`

Wir empfehlen nicht, andere Befehle mit erhöhten Rechten auszuführen. Insbesondere empfehlen wir keine Erhöhung der Rechte mit Befehlen, die MSBuild verwenden, wie z.B. [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md) und [dotnet run](dotnet-run.md). Das Hauptproblem ist die Berechtigungsverwaltung, wenn ein Benutzer nach der Ausgabe von dotnet-Befehlen zwischen einem Root- und einem eingeschränkten Konto hin und her wechselt. Sie stellen als eingeschränkter Benutzer möglicherweise fest, dass Sie keinen Zugriff auf die von einem Root-Benutzer erstellte Datei haben. Es gibt Möglichkeiten, diese Situation zu lösen, aber sie sind zunächst unnötig.

Sie können Befehle als Root ausführen, solange Sie nicht zwischen dem Stammkonto und einem eingeschränkten Konto hin und her wechseln. Beispielsweise werden Dockercontainer standardmäßig als Root ausgeführt, daher haben sie dieses Merkmal.

## <a name="global-tool-installation"></a>Installation des globalen Tools

Die folgenden Anweisungen zeigen die empfohlene Vorgehensweise bei der Installation, Ausführung und Deinstallation von.NET Core-Tools, die erhöhte Berechtigungen für die Ausführung erfordern.

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

### <a name="install-the-tool"></a>Installieren des Tools

Wenn der Ordner `%ProgramFiles%\dotnet-tools` bereits vorhanden ist, überprüfen Sie anhand der folgenden Schritte, ob die Gruppe „Benutzer“ die Berechtigung hat, dieses Verzeichnis zu schreiben oder zu ändern:

- Klicken Sie mit der rechten Maustaste auf den Ordner `%ProgramFiles%\dotnet-tools`, und wählen Sie **Eigenschaften** aus. Das Dialogfeld **Allgemeine Eigenschaften** wird geöffnet.
- Wählen Sie die Registerkarte **Sicherheit** aus. Überprüfen Sie unter **Gruppen-oder Benutzernamen**, ob die Gruppe „Benutzer“ die Berechtigung hat, dieses Verzeichnis zu schreiben oder zu ändern.
- Wenn die Gruppe „Benutzer“ das Verzeichnis schreiben oder ändern kann, verwenden Sie bei der Installation der Tools einen anderen Verzeichnisnamen als *dotnet-tools*.

Führen Sie den folgenden Befehl in einer Eingabeaufforderung mit erhöhten Rechten aus, um Tools zu installieren. Damit wird während der Installation der Ordner *dotnet-tools* erstellt.

```dotnetcli
dotnet tool install PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools".
```

### <a name="run-the-global-tool"></a>Ausführen des globalen Tools

**Option 1** Verwenden des vollständigen Pfads in einer Eingabeaufforderung mit erhöhten Rechten:

```cmd
"%ProgramFiles%\dotnet-tools\TOOLCOMMAND"
```

**Option 2** Hinzufügen des neu erstellten Ordners zu `%Path%`. Dieser Vorgang ist nur einmalig erforderlich.

```cmd
setx Path "%Path%;%ProgramFiles%\dotnet-tools\"
```

Und ausführen mit:

```cmd
TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Deinstallieren des globalen Tools

Geben Sie in der Eingabeaufforderung mit erhöhten Rechten folgenden Befehl ein:

```dotnetcli
dotnet tool uninstall PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools"
```

# <a name="linux"></a>[Linux](#tab/linux)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

# <a name="macos"></a>[macOS](#tab/macos)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

---

## <a name="local-tools"></a>Lokale Tools

Lokale Tools werden pro Unterverzeichnisstruktur und Benutzer definiert. Wenn die lokalen Tools mit erhöhten Rechten ausgeführt werden, verwenden sie eine eingeschränkte Benutzerumgebung zusammen mit der Umgebung mit erhöhten Rechten. In Linux und MacOS führt dies dazu, dass auf Dateien nur mit Root-Benutzerzugriff zugegriffen werden kann. Wenn der Benutzer zu einem eingeschränkten Konto zurückkehrt, kann der Benutzer nicht mehr auf die Dateien zugreifen oder in diese schreiben. Daher wird die Installation von Tools, die höhere Rechte als lokale Tools erfordern, nicht empfohlen. Verwenden Sie stattdessen die Option `--tool-path` und die vorherigen Richtlinien für globale Tools.

## <a name="elevation-during-development"></a>Erhöhung der Rechte während der Entwicklung

Während der Entwicklung benötigen Sie möglicherweise erhöhte Zugriffsrechte, um Ihre Anwendung zu testen. Dieses Szenario ist z.B. bei IoT-Apps üblich. Wir empfehlen Ihnen, die Anwendung ohne Erhöhung der Rechte zu erstellen und sie dann mit erhöhten Rechten auszuführen. Es gibt einige Muster, wie z.B.:

- Verwenden generierter ausführbaren Dateien (die bietet die beste Leistung beim Start):

   ```dotnetcli
   dotnet build
   sudo ./bin/Debug/netcoreapp3.0/APPLICATIONNAME
   ```

- Verwenden des Befehls [dotnet run](dotnet-run.md) mit dem Flag `—no-build`, um das Generieren neuer Binärdateien zu vermeiden:

   ```dotnetcli
   dotnet build
   sudo dotnet run --no-build
   ```

## <a name="see-also"></a>Siehe auch

- [Übersicht über globale .NET Core-Tools](global-tools.md)
