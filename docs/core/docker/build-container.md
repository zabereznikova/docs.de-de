---
title: 'Tutorial: Containerisieren einer .NET Core-App mit Docker'
description: In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können.
ms.date: 04/27/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7605f847a76907f4f9d0a451ba69332d6d174615
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724727"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Tutorial: Containerisieren einer .NET Core-App

In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können. Container haben viele Features und Vorteile, z. B. eine unveränderliche Infrastruktur, eine portable Architektur und die Skalierbarkeit. Das Image kann zum Erstellen von Containern für Ihre lokale Entwicklungsumgebung, eine private Cloud oder eine öffentliche Cloud verwendet werden.

In diesem Tutorial:

> [!div class="checklist"]
>
> - Erstellen und Veröffentlichen einer einfachen .NET Core-App
> - Erstellen und Konfigurieren einer Dockerfile-Datei für .NET Core
> - Erstellen eines Docker-Images
> - Erstellen und Ausführen eines Docker-Containers

Hier erfahren Sie mehr über die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung. Die *Docker-Plattform* verwendet die *Docker-Engine*, um Pakete schnell als *Docker-Images* zu erstellen und zu packen. Diese Images werden im *Dockerfile*-Format geschrieben, um in einem mehrstufigen Container bereitgestellt und ausgeführt zu werden.

> [!NOTE]
> Dieses Tutorial gilt **nicht** für ASP.NET Core-Apps. Wenn Sie mit ASP.NET Core arbeiten, lesen Sie das Tutorial [Informationen zum Containerisieren einer ASP.NET Core-Anwendung](/aspnet/core/host-and-deploy/docker/building-net-docker-images).

## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Komponenten müssen installiert sein:

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)\
Wenn Sie .NET Core installiert haben, verwenden Sie den Befehl `dotnet --info`, um festzustellen, welches SDK Sie verwenden.
- [Docker Community Edition](https://www.docker.com/products/docker-desktop)
- Ein temporärer Arbeitsordner für das *Dockerfile* und eine .NET Core-Beispiel-App. In diesem Tutorial trägt der Arbeitsordner den Namen *docker-working*.

## <a name="create-net-core-app"></a>Erstellen der .NET Core-App

Sie benötigen eine.NET Core-App, die der Docker-Container ausführen kann. Öffnen Sie Ihr Terminal, erstellen Sie einen Arbeitsordner, falls noch nicht geschehen, und geben Sie den Ordnernamen ein. Führen Sie im Arbeitsordner den folgenden Befehl aus, um ein neues Projekt im Unterverzeichnis *app* zu erstellen:

```dotnetcli
dotnet new console -o App -n NetCore.Docker
```

Ihre Ordnerstruktur sollte wie folgt aussehen:

```
docker-working
    └──App
        ├──NetCore.Docker.csproj
        ├──Program.cs
        └──obj
            ├──NetCore.Docker.csproj.nuget.dgspec.json
            ├──NetCore.Docker.csproj.nuget.g.props
            ├──NetCore.Docker.csproj.nuget.g.targets
            ├──project.assets.json
            └──project.nuget.cache
```

Über den Befehl `dotnet new` wird ein neuer Ordner namens *App* erstellt und eine „Hallo Welt“-Konsolenanwendung generiert. Ändern Sie die Verzeichnisse, und navigieren Sie in der Terminalsitzung zum Ordner *App*. Verwenden Sie den `dotnet run`-Befehl, um die App zu starten. Die Anwendung wird ausgeführt, und `Hello World!` wird unter dem Befehl ausgegeben:

```dotnetcli
dotnet run
Hello World!
```

Die Standardvorlage erstellt eine App, die eine Ausgabe im Terminal anzeigt und dann sofort beendet wird. Für dieses Tutorial verwenden Sie eine App, die auf unbestimmte Zeit ausgeführt wird. Öffnen Sie die Datei *Program.cs* in einem Text-Editor.

> [!TIP]
> Wenn Sie Visual Studio Code verwenden, geben Sie in der vorherigen Terminalsitzung den folgenden Befehl ein:
>
> ```console
> code .
> ```
>
> Dadurch wird der Ordner *App* geöffnet, der das Projekt in Visual Studio Code enthält.

Die *Program.cs*-Datei sollte dem folgenden C#-Code entsprechen:

```csharp
using System;

namespace NetCore.Docker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Ersetzen Sie die Datei durch den folgenden Code, der die Zahlen pro Sekunde zählt:

```csharp
using System;
using System.Threading.Tasks;

namespace NetCore.Docker
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                Console.WriteLine($"Counter: {++counter}");
                await Task.Delay(1000);
            }
        }
    }
}
```

Speichern Sie die Datei, und testen Sie das Programm erneut mit `dotnet run`. Denken Sie daran, dass diese App auf unbestimmte Zeit ausgeführt wird. Verwenden Sie zum Beenden den Befehl <kbd>STRG+C</kbd>, um diese anzuhalten. Nachfolgend sehen Sie eine Beispielausgabe:

```dotnetcli
dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Wenn Sie eine Zahl auf der Kommandozeile an die App übergeben, zählt sie nur bis zu diesem Betrag und wird dann beendet. Probieren Sie es mit`dotnet run -- 5`, um bis Fünf zu zählen.

> [!IMPORTANT]
> Jegliche Parameter, die auf `--` folgen, werden nicht an den Befehl `dotnet run`, sondern an Ihre Anwendung übergeben.

## <a name="publish-net-core-app"></a>Veröffentlichen der .NET Core-App

Bevor Sie die .NET Core-App dem Docker-Image hinzufügen, muss sie veröffentlicht werden. Es ist am besten, wenn der Container die veröffentlichte Version der App ausführt. Führen Sie den folgenden Befehl aus, um die App zu veröffentlichen:

```dotnetcli
dotnet publish -c Release
```

Dieser Befehl kompiliert Ihre App in den Ordner *publish*. Der Pfad zum Ordner *publish* aus dem Arbeitsordner sollte wie folgt lauten: `.\App\bin\Release\netcoreapp3.1\publish\`

#### <a name="windows"></a>[Windows](#tab/windows)

Rufen Sie über den Ordner *App* eine Verzeichnisliste des Veröffentlichungsordners ab, um sicherzustellen, dass die Datei *NetCore.Docker.dll* erstellt wurde.

```powershell
dir .\bin\Release\netcoreapp3.1\publish\

    Directory: C:\Users\dapine\App\bin\Release\netcoreapp3.1\publish

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        4/27/2020   8:27 AM            434 NetCore.Docker.deps.json
-a----        4/27/2020   8:27 AM           6144 NetCore.Docker.dll
-a----        4/27/2020   8:27 AM         171520 NetCore.Docker.exe
-a----        4/27/2020   8:27 AM            860 NetCore.Docker.pdb
-a----        4/27/2020   8:27 AM            154 NetCore.Docker.runtimeconfig.json
```

#### <a name="linux"></a>[Linux](#tab/linux)

Verwenden Sie den Befehl `ls`, um eine Verzeichnisliste abzurufen, und überprüfen Sie, ob die Datei *NetCore.Docker.dll* erstellt wurde.

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
```

---

## <a name="create-the-dockerfile"></a>Erstellen der Dockerfile

Die *Dockerfile*-Datei wird vom Befehl `docker build` zum Erstellen des Containerimage verwendet. Diese Datei ist eine Textdatei mit dem Namen *Dockerfile*, die keine Erweiterung besitzt.

Erstellen Sie eine Datei namens *Dockerfile* in dem Verzeichnis mit der *CSPROJ*-Datei, und öffnen Sie sie in einem Text-Editor. In diesem Tutorial wird das ASP.NET Core-Runtimeimage (das das .NET Core-Runtimeimage enthält) verwendet, das der .NET Core-Konsolenanwendung entspricht.

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:3.1
```

> [!NOTE]
> Das ASP.NET Core-Runtimeimage wird hier absichtlich verwendet, obwohl auch das `mcr.microsoft.com/dotnet/runtime:3.1`-Image verwendet werden könnte.

Für das `FROM`-Schlüsselwort ist der vollqualifizierte Name des Docker-Containerimages erforderlich. Die Microsoft Container Registry (MCR, mcr.microsoft.com) ist ein Konsortium von Docker Hub, das öffentlich zugängliche Container hostet. Das `dotnet/core`-Segment ist das Containerrepository, wobei das `aspnet`-Segment der Name des Containerimages ist. Das Image wird für die Versionsverwaltung mit `3.1` gekennzeichnet. Daher entspricht `mcr.microsoft.com/dotnet/aspnet:3.1` der .NET Core 3.1-Runtime. Stellen Sie sicher, dass Sie die .NET Core-Runtimeversion pullen, die der Runtime entspricht, die das Ziel Ihres SDK ist. Beispielsweise verwendet die im vorherigen Abschnitt erstellte App das .NET Core 3.1 SDK, und das Basisimage, auf das in der *Dockerfile*-Datei verwiesen wird, ist mit **3.1** gekennzeichnet.

Speichern Sie das *Dockerfile*. Die Verzeichnisstruktur des Arbeitsordners sollte wie folgt aussehen. Einige Dateien und Ordner, die sich auf tieferen Ebenen befinden, sind in diesem Beispiel nicht enthalten, um Platz zu sparen:

```
docker-working
    └──App
        ├──Dockerfile
        ├──NetCore.Docker.csproj
        ├──Program.cs
        ├──bin
        │   └──Release
        │       └──netcoreapp3.1
        │           └──publish
        │               ├──NetCore.Docker.deps.json
        │               ├──NetCore.Docker.exe
        │               ├──NetCore.Docker.dll
        │               ├──NetCore.Docker.pdb
        │               └──NetCore.Docker.runtimeconfig.json
        └──obj
            └──...
```

Führen Sie in Ihrem Terminal den folgenden Befehl aus:

```console
docker build -t counter-image -f Dockerfile .
```

Docker verarbeitet die einzelnen Zeilen aus dem *Dockerfile*. Durch den Punkt `.` im Befehl `docker build` wird Docker angewiesen, im aktuellen Ordner nach einem *Dockerfile* zu suchen. Dieser Befehl erstellt das Image und ein lokales Repository namens **counter-image**, das auf dieses Image zeigt. Nachdem dieser Befehl abgeschlossen ist, führen Sie `docker images` aus, um eine Liste der installierten Images anzuzeigen:

```console
docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              e6780479db63        4 days ago          190MB
mcr.microsoft.com/dotnet/aspnet         3.1                 e6780479db63        4 days ago          190MB
```

Beachten Sie, dass die beiden Images den gleichen **IMAGE ID**-Wert haben. Der Wert ist zwischen beiden Images gleich, da der einzige Befehl in der *Dockerfile* war, das neue Image auf Basis eines vorhandenen Images zu erstellen. Fügen Sie drei Befehle zum *Dockerfile* hinzu. Jeder Befehl erstellt eine neue Imageebene, wobei der letzte Befehl das Image darstellt, auf das der Repositoryeintrag **counter-image** verweist.

```dockerfile
COPY bin/Release/netcoreapp3.1/publish/ App/
WORKDIR /App
ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
```

Der Befehl `COPY` weist Docker an, den angegebenen Ordner auf Ihrem Computer in einen Ordner im Container zu kopieren. In diesem Beispiel wird der Ordner *publish* in einen Ordner mit dem Namen *App* im Container kopiert.

Mit dem Befehl `WORKDIR` wird das **aktuelle Verzeichnis** im Container in *App* geändert.

Der nächste Befehl, `ENTRYPOINT`, weist Docker an, den Container so zu konfigurieren, dass er als ausführbare Datei ausgeführt wird. Wenn der Container gestartet wird, wird die `ENTRYPOINT`-Befehl ausgeführt. Wenn dieser Befehl beendet wird, wird der Container automatisch beendet.

Führen Sie von Ihrem Terminal aus `docker build -t counter-image -f Dockerfile .` aus, und wenn dieser Befehl abgeschlossen ist, führen Sie `docker images` aus.

```console
docker build -t counter-image -f Dockerfile .
Sending build context to Docker daemon  1.117MB
Step 1/4 : FROM mcr.microsoft.com/dotnet/aspnet:3.1
 ---> e6780479db63
Step 2/4 : COPY bin/Release/netcoreapp3.1/publish/ App/
 ---> d1732740eed2
Step 3/4 : WORKDIR /App
 ---> Running in b1701a42f3ff
Removing intermediate container b1701a42f3ff
 ---> 919aab5b95e3
Step 4/4 : ENTRYPOINT ["dotnet", "NetCore.Docker.dll"]
 ---> Running in c12aebd26ced
Removing intermediate container c12aebd26ced
 ---> cd11c3df9b19
Successfully built cd11c3df9b19
Successfully tagged counter-image:latest

docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
counter-image                           latest              cd11c3df9b19        41 seconds ago      190MB
mcr.microsoft.com/dotnet/aspnet         3.1                 e6780479db63        4 days ago          190MB
```

Jeder Befehl in der *Dockerfile* generierte eine Ebene und erstellte eine **IMAGE ID**. Der endgültige **IMAGE ID**-Wert (Ihrer wird anders sein) ist **cd11c3df9b19**. Als Nächstes erstellen Sie einen Container auf Grundlage dieses Images.

## <a name="create-a-container"></a>Erstellen eines Containers

Da Sie nun ein Image haben, das Ihre App enthält, können Sie einen Container erstellen. Für die Erstellung eines Containers haben Sie zwei Möglichkeiten. Erstellen Sie zunächst einen neuen Container, der beendet wird.

```console
docker create --name core-counter counter-image
0f281cb3af994fba5d962cc7d482828484ea14ead6bfe386a35e5088c0058851
```

Der obige Befehl `docker create` erstellt einen Container auf Grundlage des Images **counter-image**. Die Ausgabe dieses Befehls zeigt Ihnen die **CONTAINER ID** (Ihre wird anders sein) des erstellten Containers. Um eine Liste *aller* Container zu erhalten, verwenden Sie den `docker ps -a`-Befehl:

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED           STATUS     PORTS    NAMES
0f281cb3af99    counter-image    "dotnet NetCore.Dock…"    40 seconds ago    Created             core-counter
```

### <a name="manage-the-container"></a>Verwalten des Containers

Der Container wurde mit dem spezifischen Namen `core-counter` erstellt, der zum Verwalten des Containers verwendet wird. Das folgende Beispiel verwendet den Befehl `docker start`, um den Container zu starten, und verwendet dann den Befehl `docker ps`, um nur die laufenden Container anzuzeigen:

```console
docker start core-counter
core-counter

docker ps
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS          PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    2 minutes ago    Up 11 seconds            core-counter
```

In ähnlicher Weise beendet der Befehl `docker stop` den Container. Im folgenden Beispiel wird der Befehl `docker stop` verwendet, um den Container zu beenden, und dann der Befehl `docker ps`, um anzuzeigen, dass keine Container ausgeführt werden:

```console
docker stop core-counter
core-counter

docker ps
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="connect-to-a-container"></a>Herstellen einer Verbindung mit einem Container

Nachdem ein Container ausgeführt wird, können Sie sich mit ihm verbinden, um die Ausgabe anzuzeigen. Verwenden Sie die Befehle `docker start` und `docker attach`, um den Container zu starten und den Ausgabestream anzuzeigen. In diesem Beispiel wird die Tastenkombination <kbd>STRG+C</kbd> verwendet, um die Trennung vom ausgeführten Container durchzuführen. Diese Tastenkombination beendet den Prozess im Container, sofern nicht anders angegeben, was den Container anhalten würde. Der Parameter `--sig-proxy=false` stellt sicher, dass <kbd>STRG+C</kbd> den Prozess im Container nicht anhält.

Nachdem Sie den Container abgetrennt haben, fügen Sie ihn erneut an, um sicherzustellen, dass er noch läuft und zählt.

```console
docker start core-counter
core-counter

docker attach --sig-proxy=false core-counter
Counter: 7
Counter: 8
Counter: 9
^C

docker attach --sig-proxy=false core-counter
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Löschen eines Containers

Für die Zwecke dieses Artikels wollen Sie nicht, dass Container einfach nur vorhanden sind und nichts tun. Löschen Sie den zuvor erstellten Container. Wenn der Container ausgeführt wird, beenden Sie ihn.

```console
docker stop core-counter
```

Das folgende Beispiel listet alle Container auf. Anschließend wird der Container mit dem Befehl `docker rm` gelöscht und dann wird ein zweites Mal auf laufende Container überprüft.

```console
docker ps -a
CONTAINER ID    IMAGE            COMMAND                   CREATED          STATUS                        PORTS    NAMES
2f6424a7ddce    counter-image    "dotnet NetCore.Dock…"    7 minutes ago    Exited (143) 20 seconds ago            core-counter

docker rm core-counter
core-counter

docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="single-run"></a>Einzelausführung

Docker bietet den Befehl `docker run`, um den Container als einen einzigen Befehl zu erstellen und auszuführen. Dieser Befehl erübrigt die Ausführung von `docker create` und dann `docker start`. Sie können diesen Befehl auch so einstellen, dass der Container beim Beenden des Containers automatisch gelöscht wird. Verwenden Sie beispielsweise `docker run -it --rm`, um zwei Dinge zu tun: 1) um sich automatisch über das aktuelle Terminal mit dem Container zu verbinden, und 2) wenn der Container fertig ist, um ihn zu entfernen:

```console
docker run -it --rm counter-image
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Der Container übergibt auch Parameter an die Ausführung der .NET Core-App, um diese anzuweisen, nur bis 3 zu zählen und dann 3 zu übergeben.

```console
docker run -it --rm counter-image 3
Counter: 1
Counter: 2
Counter: 3
```

Bei `docker run -it` hält der Befehl <kbd>STRG + C</kbd> den Prozess an, der im Container ausgeführt wird, was wiederum den Container anhält. Da der Parameter `--rm` angegeben wurde, wird der Container beim Anhalten des Prozesses automatisch gelöscht. Stellen Sie sicher, dass er nicht vorhanden ist:

```console
docker ps -a
CONTAINER ID    IMAGE    COMMAND    CREATED    STATUS    PORTS    NAMES
```

### <a name="change-the-entrypoint"></a>Ändern des EINSTIEGSPUNKTS

Mit dem Befehl `docker run` können Sie auch den Befehl `ENTRYPOINT` aus der *Dockerfile* ändern und etwas anderes ausführen, jedoch nur für diesen Container. Verwenden Sie beispielsweise den folgenden Befehl, um `bash` oder `cmd.exe` auszuführen. Bearbeiten Sie den Befehl nach Bedarf.

#### <a name="windows"></a>[Windows](#tab/windows)

In diesem Beispiel wird `ENTRYPOINT` in `cmd.exe` geändert. <kbd>STRG+C</kbd> wird gedrückt, um den Prozess zu beenden und den Container anzuhalten.

```console
docker run -it --rm --entrypoint "cmd.exe" counter-image

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a>[Linux](#tab/linux)

In diesem Beispiel wird `ENTRYPOINT` in `bash` geändert. Der Befehl `exit` wird ausgeführt, der den Prozess beendet und den Container stoppt.

```bash
docker run -it --rm --entrypoint "bash" counter-image
root@b735b9799abf:/App# ls
NetCore.Docker.deps.json  NetCore.Docker.dll  NetCore.Docker.exe  NetCore.Docker.pdb  NetCore.Docker.runtimeconfig.json
root@b735b9799abf:/App# dotnet NetCore.Docker.dll 3
Counter: 1
Counter: 2
Counter: 3
root@b735b9799abf:/App# exit
exit
```

---

## <a name="essential-commands"></a>Grundlegende Befehle

Docker bietet viele verschiedene Befehle für die Erstellung, Verwaltung und Interaktion mit Containern und Images. Diese Docker-Befehle sind für die Verwaltung Ihrer Container unerlässlich:

- [docker build](https://docs.docker.com/engine/reference/commandline/build/)
- [docker run](https://docs.docker.com/engine/reference/commandline/run/)
- [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
- [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
- [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
- [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
- [docker image](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

In diesem Tutorial haben Sie Container und Images erstellt. Wenn Sie möchten, können Sie diese Ressourcen löschen. Führen Sie die folgenden Befehle für diese Aktionen aus:

01. Zum Anzeigen aller Container

    ```console
    docker ps -a
    ```

02. Zum Anhalten aller ausgeführten Container nach Namen

    ```console
    docker stop counter-image
    ```

03. Zum Löschen des Containers

    ```console
    docker rm counter-image
    ```

Löschen Sie anschließend alle Images, die Sie nicht mehr auf Ihrem Computer benötigen. Löschen Sie das von Ihrer *Dockerfile* erstellte Image und löschen Sie dann das .NET Core-Image, auf dem die *Dockerfile* basiert. Sie können die **IMAGE ID** oder die mit **REPOSITORY:TAG** formatierte Zeichenfolge verwenden.

```console
docker rmi counter-image:latest
docker rmi mcr.microsoft.com/dotnet/aspnet:3.1
```

Verwenden Sie den Befehl `docker images`, um eine Liste der installierten Images anzuzeigen.

> [!TIP]
> Imagedateien können groß sein. Normalerweise würden Sie temporäre Container entfernen, die Sie während des Tests und der Entwicklung Ihrer App erstellt haben. In der Regel behalten Sie die Basisimages mit installierter Runtime, wenn Sie planen, andere Images auf Basis dieser Runtime zu erstellen.

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellen einer ASP.NET Core-Anwendung im Container.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Schauen Sie sich das Tutorial zu ASP.NET Core-Microservices an.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [Überprüfen Sie die Azure-Dienste, die Container unterstützen.](https://azure.microsoft.com/overview/containers/)
- [Erfahren Sie mehr über Dockerfile-Befehle.](https://docs.docker.com/engine/reference/builder/)
- [Containertools in Visual Studio](/visualstudio/containers/overview)
