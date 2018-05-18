---
title: Ausführen von Konsolenanwendungen in Docker
description: Erfahren Sie, wie Sie eine vorhandene .NET Framework-Konsolenanwendung in einem Windows Docker-Container ausführen können.
author: spboyer
ms.date: 09/28/2016
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.openlocfilehash: 266c439163888962075f804a0f5651a8e7d83151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="running-console-applications-in-windows-containers"></a>Ausführen von Konsolenanwendungen in Windows-Containern

Konsolenanwendungen werden für verschiedene Zwecke verwendet – vom einfachen Abfragen eines Status bis hin zu Aufgaben zur Verarbeitung von Dokumentbildern mit langer Laufzeit. In allen Fällen wird die Möglichkeit, diese Anwendungen zu starten und zu skalieren, durch Hardwarekäufe, Startzeiten oder die Ausführung mehrerer Instanzen eingeschränkt.

Indem Sie Ihre Konsolenanwendungen in Docker- und Windows Server-Container verlagern, können diese Anwendungen mit einem fehlerfreien Status gestartet werden, den Vorgang ausführen und dann ordnungsgemäß beendet werden. Dieses Thema erläutert die Schritte, die erforderlich sind, um eine Konsolenanwendung in einen Windows-basierten Container zu verlagern und mithilfe eines PowerShell-Skripts zu starten.

Als Beispiel dient eine einfache Konsolenanwendung, die ein Argument akzeptiert – in diesem Fall eine Frage – und eine zufällige Antwort zurückgibt. Die Anwendung könnte auch eine `customer_id` akzeptieren und die entsprechenden Steuern berechnen oder eine Miniaturansicht für ein `image_url`-Argument erstellen.

Zusätzlich zur Antwort wurde der Antwort auch der `Environment.MachineName` hinzugefügt, um den Unterschied zwischen der Ausführung der Anwendung im lokalen System oder in einem Windows-Container zu zeigen. Wenn die Anwendung lokal ausgeführt wird, wird der Name des lokalen Computers zurückgegeben. Bei Ausführung in einem Windows-Container wird die ID der Containersitzung zurückgegeben.

Das [vollständige Beispiel](https://github.com/dotnet/samples/tree/master/framework/docker/ConsoleRandomAnswerGenerator) finden Sie im „dotnet/samples“-Repository auf GitHub. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Sie müssen sich mit einigen Docker-Begriffen vertraut machen, bevor Sie damit beginnen, Ihre Anwendung in einen Container zu verlagern.

> Ein *Docker-Image* ist eine schreibgeschützte Vorlage, die die Umgebung für einen ausgeführten Container definiert, einschließlich Betriebssystem, Systemkomponenten und Anwendung(en).

Ein wichtiges Merkmal der Docker-Images ist es, dass Images aus einem Basisimage zusammengestellt werden. Jedes neue Image fügt einen kleinen Satz an Funktionen zu einem vorhandenen Image hinzu. 

> Ein *Docker-Container* ist eine ausgeführte Instanz eines Images. 

Sie skalieren eine Anwendung, indem Sie das gleiche Image in mehreren Containern ausführen.
Vom Konzept her ähnelt dieses Vorgehen der Ausführung der gleichen Anwendung auf mehreren Hosts.

Weitere Informationen zur Docker-Architektur finden Sie auf der Docker-Website unter [Docker Overview](https://docs.docker.com/engine/understanding-docker/) (Übersicht über Docker). 

Die Verlagerung Ihrer Konsolenanwendung erfordert nur einige wenige Schritte.

1. [Erstellen der Anwendung](#building-the-application)
1. [Erstellen einer Dockerfile-Datei für das Image](#creating-the-dockerfile)
1. [Erstellen und Ausführen des Docker-Containers](#creating-the-image)

## <a name="prerequisites"></a>Erforderliche Komponenten
Windows-Container werden unter [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) oder [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server) unterstützt.

> [!NOTE]
>Wenn Sie Windows Server 2016 verwenden, müssen Sie Container manuell aktivieren, da das Installationsprogramm für Docker für Windows die Funktion nicht aktiviert. Stellen Sie sicher, dass alle Updates für das Betriebssystem ausgeführt wurden, und folgen Sie dann den Anweisungen des Artikels [Containerhostbereitstellung](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment), um die Container und Docker-Funktionen zu installieren.

Sie müssen über Docker für Windows, Version 1.12 Beta 26 oder höher, verfügen, um Windows-Container zu unterstützen. Standardmäßig arbeitet Docker mit Linux-basierten Containern. Wechseln Sie zu Windows-Containern, indem Sie in der Taskleiste mit der rechten Maustaste auf das Docker-Symbol klicken und **Zu Windows-Containern wechseln** auswählen. Docker führt den Änderungsprozess aus. Möglicherweise ist ein Neustart erforderlich.

![Windows-Container](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a>Erstellen der Anwendung
Konsolenanwendungen werden üblicherweise über ein Installationsprogramm, einen FTP-Speicherort oder eine Dateifreigabe verteilt. Wenn Sie eine Anwendung in einem Container bereitstellen, müssen die Assets kompiliert und an einem Speicherort bereitgestellt werden, der beim Erstellen des Docker-Images verwendet werden kann.

In *build.ps1* verwendet das Skript [MSBuild](/visualstudio/msbuild/msbuild), um die Anwendung zu kompilieren und so die Erstellung der Assets abzuschließen. Es werden einige Parameter an MSBuild übergeben, um die benötigten Assets zu finalisieren. Der Name der Projektdatei oder Projektmappe, die kompiliert werden soll, der Speicherort der Ausgabe und schließlich die Konfiguration („Release“ oder „Debug“).

Im Aufruf von `Invoke-MSBuild` ist der `OutputPath` auf **publish** festgelegt und die `Configuration` auf **Release**. 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj /p:OutputPath=.\publish /p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a>Erstellen der Dockerfile-Datei
Das für eine .NET Framework-Konsolenanwendung verwendete Basisimage ist `microsoft/windowsservercore`, öffentlich verfügbar im [Docker-Hub](https://hub.docker.com/r/microsoft/windowsservercore/). Das Basisimage umfasst eine Minimalinstallation mit Windows Server 2016 und .NET Framework 4.6.2 und dient als grundlegendes Betriebssystemimage für Windows-Container.

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
Die erste Zeile der Dockerfile-Datei gibt mithilfe der [`FROM`](https://docs.docker.com/engine/reference/builder/#/from)-Anweisung das Basisimage an. Danach kopiert [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in der Datei die Anwendungsassets aus dem Ordner **publish** in den Stammordner des Containers, und zum Schluss wird mit [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) der Befehl oder die Anwendung festgelegt, der bzw. die beim Starten des Containers ausgeführt wird. 

## <a name="creating-the-image"></a>Erstellen des Images
Um das Docker-Image zu erstellen, wird dem Skript *build.ps1* folgender Code hinzugefügt. Wenn das Skript ausgeführt wird, wird das `console-random-answer-generator`-Image mithilfe der Assets erstellt, die aus dem im Abschnitt [Erstellen der Anwendung](#building-the-application) definierten MSBuild kompiliert wurden.

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

Führen Sie das Skript unter Verwendung von `.\build.ps1` in der PowerShell-Befehlszeile aus.

Wenn der Build abgeschlossen ist, verwenden Sie den Befehl `docker images` in einer Befehlszeile oder PowerShell-Eingabeaufforderung. Damit wird das Image erstellt und ist bereit zur Ausführung.

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a>Ausführen des Containers
Sie können den Container mithilfe der Docker-Befehle in der Befehlszeile starten.

```
docker run console-random-answer-generator "Are you a square container?"
```

Ausgabe:

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

Wenn Sie den `docker ps -a`-Befehl in PowerShell ausführen, können Sie sehen, dass der Container immer noch vorhanden ist.

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

Die Statusspalte zeigt bei „About a minute ago“, dass die Anwendung vor ungefähr einer Minute abgeschlossen wurde und beendet werden kann. Wenn der Befehl hundert Mal ausgeführt wurde, würden hundert Container in statischem Zustand ohne Aufgabe zurückbleiben. Im Anfangsszenario bestand der ideale Vorgang darin, die erforderlichen Funktionen auszuführen und dann zu beenden oder zu bereinigen. Um diesen Workflow vollständig durchzuführen, fügen Sie die Option `--rm` zum `docker run`-Befehl hinzu, um den Container zu entfernen, sobald das Signal `Exited` empfangen wurde.

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

Führen Sie den Befehl mit dieser Option aus, und betrachten Sie dann die Ausgabe des `docker ps -a`-Befehls. Sie werden feststellen, dass sich die Container-ID (`Environment.MachineName`) nicht mehr in der Liste befindet.

### <a name="running-the-container-using-powershell"></a>Ausführen des Container mithilfe von PowerShell
In den Beispielprojektdateien befindet sich auch die Datei *run.ps1*. Diese ist ein Beispiel dafür, wie Sie PowerShell verwenden, um die Anwendung auszuführen, wobei die Argumente akzeptiert werden.

Um die Datei auszuführen, öffnen Sie PowerShell, und verwenden Sie folgenden Befehl:

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a>Zusammenfassung
Sie können Ihre .NET Framework-Konsolenanwendungen in Containern ausführen, indem Sie einfach eine Dockerfile-Datei hinzufügen und die Anwendung veröffentlichen. So können Sie mehrere Instanzen ausführen, sauber starten und beenden und von mehr Windows Server 2016-Funktionen profitieren, ohne den Anwendungscode selbst in irgendeiner Weise zu ändern.
