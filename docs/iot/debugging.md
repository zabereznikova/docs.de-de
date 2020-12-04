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
# <a name="debug-net-apps-on-raspberry-pi"></a><span data-ttu-id="eecd2-103">Debuggen von .net-apps auf Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="eecd2-103">Debug .NET apps on Raspberry Pi</span></span>

<span data-ttu-id="eecd2-104">Das Debuggen von .net-apps auf ARM-basierten IOT-Geräten wie Raspberry Pi stellt eine besondere Herausforderung dar.</span><span class="sxs-lookup"><span data-stu-id="eecd2-104">Debugging .NET apps running on ARM-based IoT devices like Raspberry Pi presents a unique challenge.</span></span> <span data-ttu-id="eecd2-105">Es ist möglich, .net-apps auf Arm-Geräten zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="eecd2-105">It is possible to develop .NET apps on ARM devices.</span></span> <span data-ttu-id="eecd2-106">Allerdings ist omnisharp, das zum Debuggen von .net-apps außerhalb von Visual Studio erforderlich ist, nicht mit Arm-Geräten kompatibel.</span><span class="sxs-lookup"><span data-stu-id="eecd2-106">However, OmniSharp, which is required for debugging .NET apps outside of Visual Studio, is not compatible with ARM devices.</span></span> <span data-ttu-id="eecd2-107">Folglich müssen apps Remote von einer kompatiblen Plattform deentschlbelt werden.</span><span class="sxs-lookup"><span data-stu-id="eecd2-107">As a result, apps must be debugged remotely from a compatible platform.</span></span>

::: zone pivot="vscode"

## <a name="debug-from-visual-studio-code-cross-platform"></a><span data-ttu-id="eecd2-108">Debuggen von Visual Studio Code (plattformübergreifend)</span><span class="sxs-lookup"><span data-stu-id="eecd2-108">Debug from Visual Studio Code (cross-platform)</span></span>

<span data-ttu-id="eecd2-109">Das Debuggen von .net auf Raspberry Pi über Visual Studio Code erfordert Konfigurationsschritte auf dem Raspberry Pi und in der *launch.js* Datei des Projekts.</span><span class="sxs-lookup"><span data-stu-id="eecd2-109">Debugging .NET on Raspberry Pi from Visual Studio Code requires configuration steps on the Raspberry Pi and in the project's *launch.json* file.</span></span>

### <a name="enable-ssh-on-the-raspberry-pi"></a><span data-ttu-id="eecd2-110">Aktivieren von SSH auf dem Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="eecd2-110">Enable SSH on the Raspberry Pi</span></span>

<span data-ttu-id="eecd2-111">SSH ist für das Remote Debuggen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eecd2-111">SSH is required for remote debugging.</span></span> <span data-ttu-id="eecd2-112">Informationen zum Aktivieren von SSH [finden Sie unter *Aktivieren von SSH* in der Raspberry Pi-Dokumentation](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="eecd2-112">To enable SSH, [refer to *Enable SSH* in the Raspberry Pi documentation](https://www.raspberrypi.org/documentation/remote-access/ssh/) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

### <a name="install-the-visual-studio-remote-debugger-on-the-raspberry-pi"></a><span data-ttu-id="eecd2-113">Installieren des Visual Studio Remote Debugger auf dem Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="eecd2-113">Install the Visual Studio Remote Debugger on the Raspberry Pi</span></span>

<span data-ttu-id="eecd2-114">Führen Sie in einer bash-Konsole auf dem Raspberry PI (entweder lokal oder über SSH) die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="eecd2-114">Within a Bash console on the Raspberry Pi (either locally or via SSH), complete the following steps:</span></span>

1. <span data-ttu-id="eecd2-115">Führen Sie den folgenden Befehl aus, um die Visual Studio Remote Debugger auf dem Raspberry Pi herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="eecd2-115">Execute the following command to download and install the Visual Studio Remote Debugger on the Raspberry Pi:</span></span>

    ```bash
    curl -sSL https://aka.ms/getvsdbgsh | /bin/sh /dev/stdin -v latest -l ~/vsdbg
    ```

1. <span data-ttu-id="eecd2-116">Der Debugger erfordert, dass als ausgeführt wird `root` .</span><span class="sxs-lookup"><span data-stu-id="eecd2-116">The debugger requires running as `root`.</span></span> <span data-ttu-id="eecd2-117">Standardmäßig `root` hat kein Kennwort für Raspberry Pi.</span><span class="sxs-lookup"><span data-stu-id="eecd2-117">By default, `root` has no password on Raspberry Pi.</span></span> <span data-ttu-id="eecd2-118">Legen Sie ein Kennwort für fest, `root` indem Sie den folgenden Befehl ausführen und den Anweisungen folgen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-118">Set a password for `root` by executing the following command and following the prompts.</span></span>

    ```bash
    sudo passwd root
    ```

1. <span data-ttu-id="eecd2-119">Visual Studio Code verwendet das SSH-Protokoll für die Remote Debuggen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-119">Visual Studio Code uses the SSH protocol to debug remotely.</span></span> <span data-ttu-id="eecd2-120">Aus Sicherheitsgründen `root` ist nicht berechtigt, sich standardmäßig über SSH anzumelden.</span><span class="sxs-lookup"><span data-stu-id="eecd2-120">For security purposes, `root` is not permitted to log on via SSH by default.</span></span> <span data-ttu-id="eecd2-121">Führen Sie `root` die folgenden Schritte aus, um die Anmeldung über SSH zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="eecd2-121">To enable `root` to log on via SSH, complete the following steps:</span></span>

    1. <span data-ttu-id="eecd2-122">Führen Sie den folgenden Befehl aus, um */etc/ssh/sshd_config* in [Nano](https://www.nano-editor.org/docs.php) zu öffnen <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="eecd2-122">Execute the following command to open */etc/ssh/sshd_config* in [nano](https://www.nano-editor.org/docs.php) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

        ```bash
        sudo nano /etc/ssh/sshd_config
        ```

    1. <span data-ttu-id="eecd2-123">Drücken Sie <kbd>STRG + W</kbd> , und suchen Sie nach **PermitRootLogin**.</span><span class="sxs-lookup"><span data-stu-id="eecd2-123">Press <kbd>Ctrl+W</kbd> and search for **PermitRootLogin**.</span></span>
    1. <span data-ttu-id="eecd2-124">Heben Sie die Auskommentierung der Zeile mit **PermitRootLogin** auf, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eecd2-124">Uncomment the line with **PermitRootLogin** if needed.</span></span>
    1. <span data-ttu-id="eecd2-125">Ändern Sie die Zeile wie folgt:</span><span class="sxs-lookup"><span data-stu-id="eecd2-125">Change the line to read as follows:</span></span>

        ```console
        PermitRootLogin yes
        ```

        > [!NOTE]
        > <span data-ttu-id="eecd2-126">Wenn in */etc/ssh/sshd_config* keine **PermitRootLogin** -Zeile vorhanden ist, fügen Sie eine neue Zeile mit dem oben gezeigten Wert hinzu.</span><span class="sxs-lookup"><span data-stu-id="eecd2-126">If there is no **PermitRootLogin** line in */etc/ssh/sshd_config*, add a new line with the value shown above.</span></span>

    1. <span data-ttu-id="eecd2-127">Drücken Sie <kbd>STRG + X</kbd> , um zu beenden und Ihre Wahrscheinlichkeit zu sparen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-127">Press <kbd>Ctrl+X</kbd> to exit and save your chances.</span></span> <span data-ttu-id="eecd2-128">Wenn Sie zum **Speichern des geänderten Puffers** aufgefordert werden, drücken Sie <kbd>Y</kbd> zur Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="eecd2-128">When prompted **Save modified buffer?**, press <kbd>Y</kbd> to confirm.</span></span> <span data-ttu-id="eecd2-129">Drücken <kbd>Sie die Eingabe</kbd> Taste, um das Überschreiben der ursprünglichen Datei zu bestätigen</span><span class="sxs-lookup"><span data-stu-id="eecd2-129">Press <kbd>Enter</kbd> to confirm overwriting the original file.</span></span>
    1. <span data-ttu-id="eecd2-130">Starten Sie den Raspberry Pi neu, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="eecd2-130">Reboot the Raspberry Pi by executing the following command:</span></span>

        ```bash
        sudo reboot
        ```

### <a name="setup-launchjson-in-visual-studio-code"></a><span data-ttu-id="eecd2-131">Setup launch.jsin Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="eecd2-131">Setup launch.json in Visual Studio Code</span></span>

<span data-ttu-id="eecd2-132">Fügen Sie dem *launch.js* des Projekts eine Startkonfiguration hinzu.</span><span class="sxs-lookup"><span data-stu-id="eecd2-132">Add a launch configuration to the project's *launch.json*.</span></span> <span data-ttu-id="eecd2-133">Wenn für das Projekt keine Datei *launch.js* vorhanden ist, fügen Sie eine Datei hinzu, indem Sie zur Registerkarte **Ausführen** wechseln, die Option **launch.jsfür Datei erstellen** auswählen und im Dialogfeld **.net** oder **.net Core** auswählen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-133">If the project doesn't have a *launch.json* file, add one by switching to the **Run** tab, selecting **create a launch.json file**, and selecting **.NET** or **.NET Core** in the dialog.</span></span>

<span data-ttu-id="eecd2-134">Die neue Konfiguration in *launch.jsauf* sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="eecd2-134">The new configuration in *launch.json* should look similar to this:</span></span>

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

<span data-ttu-id="eecd2-135">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eecd2-135">Notice the following:</span></span>

- <span data-ttu-id="eecd2-136">`program` ist der Pfad zur .NET-Laufzeit auf dem Pi.</span><span class="sxs-lookup"><span data-stu-id="eecd2-136">`program` is the path to the .NET runtime on the Pi.</span></span>
- <span data-ttu-id="eecd2-137">`args` der Pfad zu der Assembly, die auf dem Pi debuggt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eecd2-137">`args` is the path to the assembly to debug on the Pi.</span></span>
- <span data-ttu-id="eecd2-138">`cwd` das Arbeitsverzeichnis, das beim Starten der APP auf dem Pi verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eecd2-138">`cwd` is the working directory to use when launching the app on the Pi.</span></span>
- <span data-ttu-id="eecd2-139">`pipeProgram` ist der Pfad zu einem SSH-Client auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="eecd2-139">`pipeProgram` is the path to an SSH client on the local machine.</span></span>
- <span data-ttu-id="eecd2-140">`pipeArgs` die Parameter, die an den SSH-Client übermittelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-140">`pipeArgs` are the parameters to be passed to the SSH client.</span></span> <span data-ttu-id="eecd2-141">Stellen Sie sicher, dass Sie den Parameter "Password" und den `root` Benutzer im Format angeben `<user>@<hostname>` .</span><span class="sxs-lookup"><span data-stu-id="eecd2-141">Be sure to specify the password parameter, as well as the `root` user in the format `<user>@<hostname>`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eecd2-142">Im obigen Beispiel wird *plink* verwendet, eine Komponente des [PuTTY](https://www.ssh.com/ssh/putty/) - <span class="docon docon-navigate-external x-hidden-focus"></span> SSH-Clients.</span><span class="sxs-lookup"><span data-stu-id="eecd2-142">The above example uses *plink*, a component of the [PuTTY](https://www.ssh.com/ssh/putty/)<span class="docon docon-navigate-external x-hidden-focus"></span> SSH client.</span></span> <span data-ttu-id="eecd2-143">[OpenSSH](https://www.openssh.com/) <span class="docon docon-navigate-external x-hidden-focus"></span> , das in den aktuellen Versionen von Windows und Linux enthalten ist, kann stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eecd2-143">[OpenSSH](https://www.openssh.com/)<span class="docon docon-navigate-external x-hidden-focus"></span>, which is included in recent versions of Windows and Linux, may be used instead.</span></span> <span data-ttu-id="eecd2-144">OpenSSH unterstützt jedoch nicht das Senden von Kenn Wörtern als Befehlszeilenparameter.</span><span class="sxs-lookup"><span data-stu-id="eecd2-144">However, OpenSSH doesn't support sending passwords as a command-line parameter.</span></span> <span data-ttu-id="eecd2-145">Um OpenSSH zu verwenden, [Konfigurieren Sie Ihren Raspberry Pi für den Zugriff per Kennwort für den SSH-Zugriff](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span> .</span><span class="sxs-lookup"><span data-stu-id="eecd2-145">To use OpenSSH, [configure your Raspberry Pi for passwordless SSH access](https://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md) <span class="docon docon-navigate-external x-hidden-focus"></span>.</span></span>

### <a name="deploy-the-app"></a><span data-ttu-id="eecd2-146">Bereitstellen der App</span><span class="sxs-lookup"><span data-stu-id="eecd2-146">Deploy the app</span></span>

<span data-ttu-id="eecd2-147">Stellen Sie die APP wie unter Bereitstellen [von .net-apps für Raspberry Pi](deployment.md)beschrieben bereit.</span><span class="sxs-lookup"><span data-stu-id="eecd2-147">Deploy the app as described in [Deploy .NET apps to Raspberry Pi](deployment.md).</span></span> <span data-ttu-id="eecd2-148">Stellen Sie sicher, dass es sich bei dem Bereitstellungs Pfad um denselben Pfad handelt, der im `cwd` *launch.js* der Konfiguration angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="eecd2-148">Ensure the deployment path is the same path specified in the `cwd` parameter in the *launch.json* configuration.</span></span>

### <a name="launch-the-debugger"></a><span data-ttu-id="eecd2-149">Starten Sie den Debugger.</span><span class="sxs-lookup"><span data-stu-id="eecd2-149">Launch the debugger</span></span>

<span data-ttu-id="eecd2-150">Wählen Sie auf der Registerkarte **Ausführen** die Konfiguration **.net Core-Start (Remote Konsole)** aus, und wählen Sie **Debuggen starten** aus.</span><span class="sxs-lookup"><span data-stu-id="eecd2-150">On the **Run** tab, select the **.NET Core Launch (remote console)** configuration and select **Start Debugging**.</span></span> <span data-ttu-id="eecd2-151">Die APP wird auf dem Raspberry Pi gestartet.</span><span class="sxs-lookup"><span data-stu-id="eecd2-151">The app launches on the Raspberry Pi.</span></span> <span data-ttu-id="eecd2-152">Der Debugger kann verwendet werden, um Haltepunkte festzulegen, die lokalen Variablen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-152">The debugger may be used to set breakpoints, inspect locals, and more.</span></span>

## <a name="references"></a><span data-ttu-id="eecd2-153">Referenzen</span><span class="sxs-lookup"><span data-stu-id="eecd2-153">References</span></span>

<span data-ttu-id="eecd2-154">[Remote Debuggen mit vs Code unter Windows zu einem Raspberry Pi unter Verwendung von .net Core auf Arm](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm)<span class="docon docon-navigate-external x-hidden-focus"></span></span><span class="sxs-lookup"><span data-stu-id="eecd2-154">[Remote debugging with VS Code on Windows to a Raspberry Pi using .NET Core on ARM](https://www.hanselman.com/blog/remote-debugging-with-vs-code-on-windows-to-a-raspberry-pi-using-net-core-on-arm) <span class="docon docon-navigate-external x-hidden-focus"></span></span></span>

::: zone-end

::: zone pivot="visualstudio"

## <a name="debug-from-visual-studio-on-windows"></a><span data-ttu-id="eecd2-155">Debuggen von Visual Studio unter Windows</span><span class="sxs-lookup"><span data-stu-id="eecd2-155">Debug from Visual Studio on Windows</span></span>

<span data-ttu-id="eecd2-156">Visual Studio kann .net-apps auf Remote Geräten über SSH Debuggen.</span><span class="sxs-lookup"><span data-stu-id="eecd2-156">Visual Studio can debug .NET apps on remote devices via SSH.</span></span> <span data-ttu-id="eecd2-157">Auf dem Gerät ist keine spezielle Konfiguration erforderlich.</span><span class="sxs-lookup"><span data-stu-id="eecd2-157">No specialized configuration is required on the device.</span></span> <span data-ttu-id="eecd2-158">Ausführliche Informationen zur Verwendung von Visual Studio zum Remote Debuggen von .net finden Sie unter [Remote Debuggen von .net unter Linux mit SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="eecd2-158">For details on using Visual Studio to debug .NET remotely, see [Remote debug .NET on Linux using SSH](/visualstudio/debugger/remote-debugging-dotnet-core-linux-with-ssh?view=vs-2019).</span></span>

::: zone-end
