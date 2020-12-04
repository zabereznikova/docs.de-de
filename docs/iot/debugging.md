---
title: Debuggen von .net-apps auf Raspberry Pi
description: Erfahren Sie, wie Sie .net-apps auf Raspberry Pi und ähnlichen Geräten Debuggen.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
zone_pivot_groups: ide-set-one
ms.openlocfilehash: 7b9872304ee53071452772e3da02081a7def4d80
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "96592072"
---
# <a name="debug-net-apps-on-raspberry-pi"></a>Debuggen von .net-apps auf Raspberry Pi

Das Debuggen von .net-apps auf ARM-basierten IOT-Geräten wie Raspberry Pi stellt eine besondere Herausforderung dar. Es ist möglich, .net-apps auf Arm-Geräten zu entwickeln. Allerdings ist omnisharp, das zum Debuggen von .net-apps außerhalb von Visual Studio erforderlich ist, nicht mit Arm-Geräten kompatibel. Folglich müssen apps Remote von einer kompatiblen Plattform deentschlbelt werden.

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a>Debuggen von Visual Studio Code (plattformübergreifend)

Das Debuggen von .net auf Raspberry Pi über Visual Studio Code erfordert Konfigurationsschritte auf dem Raspberry Pi und in der *launch.js* Datei des Projekts.

### <a name="enable-ssh-on-the-raspberry-pi"></a>Aktivieren von SSH auf dem Raspberry Pi

SSH ist für das Remote Debuggen erforderlich. Informationen zum Aktivieren von SSH [finden Sie unter *Aktivieren von SSH* in der Raspberry Pi-Dokumentation](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span> .

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a>Installieren des Visual Studio Remote Debugger auf dem Raspberry Pi

Führen Sie in einer bash-Konsole auf dem Raspberry PI (entweder lokal oder über SSH) die folgenden Schritte aus:

1. Führen Sie den folgenden Befehl aus, um die Visual Studio Remote Debugger auf dem Raspberry Pi herunterzuladen und zu installieren:

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. Der Debugger erfordert, dass als ausgeführt wird `root` . Standardmäßig `root` hat kein Kennwort für Raspberry Pi. Legen Sie ein Kennwort für fest, `root` indem Sie den folgenden Befehl ausführen und den Anweisungen folgen.

    ```bash
    sudo passwd root
    ```

1. Visual Studio Code verwendet das SSH-Protokoll für die Remote Debuggen. Aus Sicherheitsgründen `root` ist nicht berechtigt, sich standardmäßig über SSH anzumelden. Führen Sie `root` die folgenden Schritte aus, um die Anmeldung über SSH zu aktivieren:

    1. Führen Sie den folgenden Befehl aus, um */etc/ssh/sshd_config* in [Nano](https://www.nano-editor.org/docs.php) zu öffnen <span class="docon docon-navigate-external x-hidden-focus"></span> .

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. Drücken Sie <kbd>STRG + W</kbd> , und suchen Sie nach **PermitRootLogin**.
    1. Heben Sie die Auskommentierung der Zeile mit **PermitRootLogin** auf, falls erforderlich.
    1. Ändern Sie die Zeile wie folgt:

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > Wenn in */etc/ssh/sshd_config* keine **PermitRootLogin** -Zeile vorhanden ist, fügen Sie eine neue Zeile mit dem oben gezeigten Wert hinzu.

    1. Drücken Sie <kbd>STRG + X</kbd> , um zu beenden und Ihre Wahrscheinlichkeit zu sparen. Wenn Sie zum **Speichern des geänderten Puffers** aufgefordert werden, drücken Sie <kbd>Y</kbd> zur Bestätigung. Drücken <kbd>Sie die Eingabe</kbd> Taste, um das Überschreiben der ursprünglichen Datei zu bestätigen
    1. Starten Sie den Raspberry Pi neu, indem Sie den folgenden Befehl ausführen:

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a>Setup launch.jsin Visual Studio Code

Fügen Sie dem *launch.js* des Projekts eine Startkonfiguration hinzu. Wenn für das Projekt keine Datei *launch.js* vorhanden ist, fügen Sie eine Datei hinzu, indem Sie zur Registerkarte **Ausführen** wechseln, die Option **launch.jsfür Datei erstellen** auswählen und im Dialogfeld **.net** oder **.net Core** auswählen.

Die neue Konfiguration in *launch.jsauf* sollte in etwa wie folgt aussehen:

```json
"configurations": [
    {
        "name": ".NET Core Launch (remote console)",
        "type": "coreclr",
        "request": "launch",
        "preLaunchTask": "build",
        "program": "/home/pi/.dotnet/dotnet",
        "args": ["/home/pi/sample/Sample.dll"],
        "cwd": "/home/pi/sample",
        "stopAtEntry": false,
        "console": "internalConsole",
        "pipeTransport": {
            "pipeCwd": "${workspaceFolder}",
            "pipeProgram": "C:\\Program Files\\PuTTY\\PLINK.EXE",
            "pipeArgs": [
                "-pw",
                "P@ssw0rd",
                "root@raspberrypi"
            ],
            "debuggerPath": "/home/pi/vsdbg/vsdbg"
        }
    },
```

Beachten Sie Folgendes:

- `program` ist der Pfad zur .NET-Laufzeit auf dem Pi.
- `args` der Pfad zu der Assembly, die auf dem Pi debuggt werden soll.
- `cwd` das Arbeitsverzeichnis, das beim Starten der APP auf dem Pi verwendet werden soll.
- `pipeProgram` ist der Pfad zu einem SSH-Client auf dem lokalen Computer.
- `pipeArgs` die Parameter, die an den SSH-Client übermittelt werden sollen. Stellen Sie sicher, dass Sie den Parameter "Password" und den `root` Benutzer im Format angeben `<user>@<hostname>` .

> [!IMPORTANT]
> Im obigen Beispiel wird *plink* verwendet, eine Komponente des [PuTTY](https://www.ssh.com/ssh/putty/) - <span class="docon docon-navigate-external x-hidden-focus"></span> SSH-Clients. [OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> , das in den aktuellen Versionen von Windows und Linux enthalten ist, kann stattdessen verwendet werden. OpenSSH unterstützt jedoch nicht das Senden von Kenn Wörtern als Befehlszeilenparameter. Um OpenSSH zu verwenden, [Konfigurieren Sie Ihren Raspberry Pi für den Zugriff per Kennwort für den SSH-Zugriff](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span> .

### <a name="deploy-the-app"></a>Bereitstellen der App

Stellen Sie die APP wie unter Bereitstellen [von .net-apps für Raspberry Pi](deployment.md)beschrieben bereit. Stellen Sie sicher, dass es sich bei dem Bereitstellungs Pfad um denselben Pfad handelt, der im `cwd` *launch.js* der Konfiguration angegeben ist.

### <a name="launch-the-debugger"></a>Starten Sie den Debugger.

Wählen Sie auf der Registerkarte **Ausführen** die Konfiguration **.net Core-Start (Remote Konsole)** aus, und wählen Sie **Debuggen starten** aus. Die APP wird auf dem Raspberry Pi gestartet. Der Debugger kann verwendet werden, um Haltepunkte festzulegen, die lokalen Variablen zu überprüfen.

## <a name="references"></a>Referenzen

[Remote Debuggen mit vs Code unter Windows zu einem Raspberry Pi unter Verwendung von .net Core auf Arm](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)<span class="docon docon-navigate-external x-hidden-focus"></span>

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a>Debuggen von Visual Studio unter Windows

Visual Studio kann .net-apps auf Remote Geräten über SSH Debuggen. Auf dem Gerät ist keine spezielle Konfiguration erforderlich. Ausführliche Informationen zur Verwendung von Visual Studio zum Remote Debuggen von .net finden Sie unter [Remote Debuggen von .net unter Linux mit SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).

::: zone-end
