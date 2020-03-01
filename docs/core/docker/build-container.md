---
title: 'Tutorial: Containerisieren einer .NET Core-App mit Docker'
description: In diesem Tutorial erfahren Sie, wie Sie eine .NET Core-Anwendung mit Docker containerisieren können.
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e1904430a591b0e74a69d50a53869a130fc0a248
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157829"
---
# <a name="tutorial-containerize-a-net-core-app"></a>Tutorial: Containerisieren einer .NET Core-App

In diesem Tutorial erfahren Sie, wie ein Docker-Image erstellt wird, das Ihre .NET Core-Anwendung enthält. Das Image kann zum Erstellen von Containern für Ihre lokale Entwicklungsumgebung, eine private Cloud oder eine öffentliche Cloud verwendet werden.

Es werden die folgenden Themen abgedeckt:

> [!div class="checklist"]
>
> - Erstellen und Veröffentlichen einer einfachen .NET Core-App
> - Erstellen und Konfigurieren einer Dockerfile-Datei für .NET Core
> - Erstellen eines Docker-Images
> - Erstellen und Ausführen eines Docker-Containers

Hier erfahren Sie mehr über die Aufgaben für das Erstellen und Bereitstellen von Docker-Containern für eine .NET Core-Anwendung. Die *Docker-Plattform* verwendet die *Docker-Engine*, um Pakete schnell als *Docker-Images* zu erstellen und zu packen. Diese Images werden im *Dockerfile*-Format geschrieben, um in einem mehrstufigen Container bereitgestellt und ausgeführt zu werden.

> [!TIP]
> Wenn Sie mit einer vorhandenen ASP.NET Core-Anwendung arbeiten, finden Sie weitere Informationen im Tutorial [Informationen zum Containerisieren einer ASP.NET Core-Anwendung](/aspnet/core/host-and-deploy/docker/building-net-docker-images).

## <a name="prerequisites"></a>Voraussetzungen

Die folgenden Komponenten müssen installiert sein:

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)\
Wenn Sie .NET Core installiert haben, verwenden Sie den Befehl `dotnet --info`, um festzustellen, welches SDK Sie verwenden.

- [Docker Community Edition](https://www.docker.com/products/docker-desktop)

- Ein temporärer Arbeitsordner für das *Dockerfile* und eine .NET Core-Beispiel-App. In diesem Tutorial trägt der Arbeitsordner den Namen *docker-working*.

## <a name="create-net-core-app"></a>Erstellen der .NET Core-App

Sie benötigen eine.NET Core-App, die der Docker-Container ausführen kann. Öffnen Sie Ihr Terminal, erstellen Sie einen Arbeitsordner, falls noch nicht geschehen, und geben Sie den Ordnernamen ein. Führen Sie im Arbeitsordner den folgenden Befehl aus, um ein neues Projekt im Unterverzeichnis *app* zu erstellen:

```dotnetcli
dotnet new console -o app -n myapp
```

Ihre Ordnerstruktur sollte wie folgt aussehen:

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

Über den Befehl `dotnet new` wird ein neuer Ordner namens *app* erstellt und eine „Hallo Welt“-App generiert. Geben Sie den Ordner *app* ein, und führen Sie den Befehl `dotnet run` aus. Die folgende Ausgabe wird angezeigt:

```console
> dotnet run
Hello World!
```

Die Standardvorlage erstellt eine App, die über das Terminal druckt und dann beendet wird. Für dieses Tutorial verwenden Sie eine App, die auf unbestimmte Zeit ausgeführt wird. Öffnen Sie die Datei *Program.cs* in einem Text-Editor. Diese sollte derzeit wie der folgende Code aussehen:

```csharp
using System;

namespace myapp
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

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

Speichern Sie die Datei, und testen Sie das Programm erneut mit `dotnet run`. Denken Sie daran, dass diese App auf unbestimmte Zeit ausgeführt wird. Verwenden Sie zum Beenden den Abbruchbefehl <kbd>STRG</kbd>+<kbd>C</kbd>. Die folgende Ausgabe wird angezeigt:

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

Wenn Sie eine Zahl auf der Kommandozeile an die App übergeben, zählt sie nur bis zu diesem Betrag und wird dann beendet. Probieren Sie es mit`dotnet run -- 5`, um bis Fünf zu zählen.

> [!NOTE]
> Jegliche Parameter, die auf `--` folgen, werden nicht an den Befehl `dotnet run`, sondern an Ihre Anwendung übergeben.

## <a name="publish-net-core-app"></a>Veröffentlichen der .NET Core-App

Bevor Sie Ihre .NET Core-App zum Docker-Image hinzufügen, veröffentlichen Sie sie. Sie sollten sich vergewissern, dass der Container die veröffentlichte Version der App ausführt, wenn er gestartet wird.

Geben Sie im Arbeitsordner den Ordner *app* mit dem exemplarischen Quellcode ein, und führen Sie den folgenden Befehl aus:

```dotnetcli
dotnet publish -c Release
```

Dieser Befehl kompiliert Ihre App in den Ordner *publish*. Der Pfad zum Ordner *publish* aus dem Arbeitsordner sollte wie folgt lauten: `.\app\bin\Release\netcoreapp3.1\publish\`

Rufen Sie aus dem Ordner *app* eine Verzeichnisliste des Veröffentlichungsordners ab, um sicherzustellen, dass die Datei *myapp.dll* erstellt wurde.

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

Wenn Sie Linux oder macOS verwenden, verwenden Sie den Befehl `ls`, um eine Verzeichnisauflistung abzurufen, und überprüfen Sie, ob die Datei *myapp.dll* erstellt wurde.

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a>Erstellen der Dockerfile

Die *Dockerfile*-Datei wird vom Befehl `docker build` zum Erstellen des Containerimage verwendet. Diese Datei ist eine Textdatei mit dem Namen *Dockerfile*, die keine Erweiterung besitzt.

Navigieren Sie in Ihrem Terminal ein Verzeichnis nach oben zu dem Arbeitsordner, den Sie zu Beginn erstellt haben. Erstellen Sie eine Datei namens *Dockerfile* in Ihrem Arbeitsordner, und öffnen Sie diese in einem Text-Editor. Abhängig von der Art der Anwendung, die Sie containerisieren möchten, wählen Sie entweder die ASP.NET Core-Runtime oder die .NET Core-Runtime aus. Wählen Sie im Zweifelsfall die ASP.NET Core-Runtime aus, die die .NET Core-Runtime enthält. In diesem Tutorial wird das ASP.NET Core-Runtimeimage verwendet, aber die in den vorherigen Abschnitten erstellte Anwendung ist eine .NET Core-Anwendung.

- ASP.NET Core-Runtime

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- .NET Core-Runtime

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

Der Befehl `FROM` weist Docker an, das mit **3.1** gekennzeichnete Image aus dem angegebenen Repository herunterzuladen. Stellen Sie sicher, dass Sie die .NET Core-Runtimeversion pullen, die der Runtime entspricht, die das Ziel Ihres SDK ist. Beispielsweise verwendet die im vorherigen Abschnitt erstellte App das .NET Core 3.1 SDK, und das Basisimage, auf das in der *Dockerfile*-Datei verwiesen wird, ist mit **3.1** gekennzeichnet.

Speichern Sie das *Dockerfile*. Die Verzeichnisstruktur des Arbeitsordners sollte wie folgt aussehen. Einige Dateien und Ordner, die sich auf tieferen Ebenen befinden, sind in diesem Beispiel nicht enthalten, um Platz zu sparen:

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

Führen Sie in Ihrem Terminal den folgenden Befehl aus:

```console
docker build -t myimage -f Dockerfile .
```

Docker verarbeitet die einzelnen Zeilen aus dem *Dockerfile*. Durch den Punkt `.` im Befehl `docker build` wird Docker angewiesen, im aktuellen Ordner nach einem *Dockerfile* zu suchen. Dieser Befehl erstellt das Image und ein lokales Repository namens **myimage**, das auf dieses Image zeigt. Nachdem dieser Befehl abgeschlossen ist, führen Sie `docker images` aus, um eine Liste der installierten Images anzuzeigen:

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

Beachten Sie, dass die beiden Images den gleichen **IMAGE ID**-Wert haben. Der Wert ist zwischen beiden Images gleich, da der einzige Befehl in der *Dockerfile* war, das neue Image auf Basis eines vorhandenen Images zu erstellen. Fügen Sie zwei Befehle zur *Dockerfile* hinzu. Jeder Befehl erstellt eine neue Imageebene, wobei der letzte Befehl das Image darstellt, auf das der Repositoryeintrag **myimage** verweist.

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

Der Befehl `COPY` weist Docker an, den angegebenen Ordner auf Ihrem Computer in einen Ordner im Container zu kopieren. In diesem Beispiel wird der Ordner *publish* in einen Ordner mit dem Namen *app* im Container kopiert.

Der nächste Befehl, `ENTRYPOINT`, weist Docker an, den Container so zu konfigurieren, dass er als ausführbare Datei ausgeführt wird. Wenn der Container gestartet wird, wird die `ENTRYPOINT`-Befehl ausgeführt. Wenn dieser Befehl beendet wird, wird der Container automatisch beendet.

Führen Sie von Ihrem Terminal aus `docker build -t myimage -f Dockerfile .` aus, und wenn dieser Befehl abgeschlossen ist, führen Sie `docker images` aus.

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

Jeder Befehl in der *Dockerfile* generierte eine Ebene und erstellte eine **IMAGE ID**. Die endgültige **IMAGE ID** (Ihre wird anders sein) ist **ddcc6646461b**. Als nächstes werden Sie einen Container basierend auf diesem Image erstellen.

## <a name="create-a-container"></a>Erstellen eines Containers

Da Sie nun ein Image haben, das Ihre App enthält, können Sie einen Container erstellen. Für die Erstellung eines Containers haben Sie zwei Möglichkeiten. Erstellen Sie zunächst einen neuen Container, der beendet wird.

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

Der Befehl `docker create` von oben erstellt einen Container basierend auf dem Image **myimage**. Die Ausgabe dieses Befehls zeigt Ihnen die **CONTAINER ID** (Ihre wird anders sein) des erstellten Containers. Um eine Liste *aller* Container zu erhalten, verwenden Sie den `docker ps -a`-Befehl:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a>Verwalten des Containers

Jedem Container ist ein Zufallsname zugeordnet, mit dem Sie auf diese Containerinstanz verweisen können. Beispielsweise wurde für den automatisch erstellten Container der Name **gallant_lehmann** gewählt (Ihr Name wird anders lauten), und dieser Name kann zum Starten des Containers verwendet werden. Mit dem Parameter `docker create --name` überschreiben Sie den automatischen Namen durch einen bestimmten Namen.

Das folgende Beispiel verwendet den Befehl `docker start`, um den Container zu starten, und verwendet dann den Befehl `docker ps`, um nur die laufenden Container anzuzeigen:

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

In ähnlicher Weise beendet der Befehl `docker stop` den Container. Im folgenden Beispiel wird der Befehl `docker stop` verwendet, um den Container zu beenden, und dann der Befehl `docker ps`, um anzuzeigen, dass keine Container ausgeführt werden:

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a>Herstellen einer Verbindung mit einem Container

Nachdem ein Container ausgeführt wird, können Sie sich mit ihm verbinden, um die Ausgabe anzuzeigen. Verwenden Sie die Befehle `docker start` und `docker attach`, um den Container zu starten und den Ausgabestream anzuzeigen. In diesem Beispiel wird die Tastenkombination <kbd>STRG+C</kbd> verwendet, um die Trennung vom ausgeführten Container auszuführen. Durch diese Tastenkombination kann der Prozess im Container tatsächlich beendet werden, wodurch auch der Container beendet wird. Der Parameter `--sig-proxy=false` stellt sicher, dass der Prozess im Container durch das Drücken von <kbd>STRG+C</kbd> nicht angehalten wird.

Nachdem Sie den Container abgetrennt haben, fügen Sie ihn erneut an, um sicherzustellen, dass er noch läuft und zählt.

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a>Löschen eines Containers

Für die Zwecke dieses Artikels wollen Sie nicht, dass Container einfach nur vorhanden sind und nichts tun. Löschen Sie den zuvor erstellten Container. Wenn der Container ausgeführt wird, beenden Sie ihn.

```console
> docker stop gallant_lehmann
```

Das folgende Beispiel listet alle Container auf. Anschließend wird der Container mit dem Befehl `docker rm` gelöscht und dann wird ein zweites Mal auf laufende Container überprüft.

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a>Einzelausführung

Docker bietet den Befehl `docker run`, um den Container als einen einzigen Befehl zu erstellen und auszuführen. Dieser Befehl erübrigt die Ausführung von `docker create` und dann `docker start`. Sie können diesen Befehl auch so einstellen, dass der Container beim Beenden des Containers automatisch gelöscht wird. Verwenden Sie beispielsweise `docker run -it --rm`, um zwei Dinge zu tun: 1) um sich automatisch über das aktuelle Terminal mit dem Container zu verbinden, und 2) wenn der Container fertig ist, um ihn zu entfernen:

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

Bei `docker run -it` beendet der Befehl <kbd>STRG + C</kbd> den Prozess, der im Container ausgeführt wird, was wiederum den Container beendet. Da der Parameter `--rm` angegeben wurde, wird der Container beim Anhalten des Prozesses automatisch gelöscht. Stellen Sie sicher, dass er nicht vorhanden ist:

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a>Ändern des EINSTIEGSPUNKTS

Mit dem Befehl `docker run` können Sie auch den Befehl `ENTRYPOINT` aus der *Dockerfile* ändern und etwas anderes ausführen, jedoch nur für diesen Container. Verwenden Sie beispielsweise den folgenden Befehl, um `bash` oder `cmd.exe` auszuführen. Bearbeiten Sie den Befehl nach Bedarf.

#### <a name="windows"></a>Windows

In diesem Beispiel wird `ENTRYPOINT` in `cmd.exe` geändert. <kbd>STRG</kbd>+<kbd>C</kbd> wird gedrückt, um den Prozess zu beenden und den Container anzuhalten.

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

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

#### <a name="linux"></a>Linux

In diesem Beispiel wird `ENTRYPOINT` in `bash` geändert. Der Befehl `quit` wird ausgeführt, der den Prozess beendet und den Container stoppt.

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a>Grundlegende Befehle

Docker hat viele verschiedene Befehle, die behandeln, was Sie mit Ihrem Container und Ihren Images machen wollen. Diese Docker-Befehle sind für die Verwaltung Ihrer Container unerlässlich:

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
    > docker ps -a
    ```

02. Zum Anhalten aller ausgeführten Container. `CONTAINER_NAME` steht für automatisch dem Container zugewiesenen Namen.

    ```console
    > docker stop CONTAINER_NAME
    ```

03. Zum Löschen des Containers

    ```console
    > docker rm CONTAINER_NAME
    ```

Löschen Sie anschließend alle Images, die Sie nicht mehr auf Ihrem Computer benötigen. Löschen Sie das von Ihrer *Dockerfile* erstellte Image und löschen Sie dann das .NET Core-Image, auf dem die *Dockerfile* basiert. Sie können die **IMAGE ID** oder die mit **REPOSITORY:TAG** formatierte Zeichenfolge verwenden.

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

Verwenden Sie den Befehl `docker images`, um eine Liste der installierten Images anzuzeigen.

> [!NOTE]
> Imagedateien können groß sein. Normalerweise würden Sie temporäre Container entfernen, die Sie während des Tests und der Entwicklung Ihrer App erstellt haben. In der Regel behalten Sie die Basisimages mit installierter Runtime, wenn Sie planen, andere Images auf Basis dieser Runtime zu erstellen.

## <a name="next-steps"></a>Nächste Schritte

- [Bereitstellen einer ASP.NET Core-Anwendung im Container.](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [Schauen Sie sich das Tutorial zu ASP.NET Core-Microservices an.](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [Überprüfen Sie die Azure-Dienste, die Container unterstützen.](https://azure.microsoft.com/overview/containers/)
- [Erfahren Sie mehr über Dockerfile-Befehle.](https://docs.docker.com/engine/reference/builder/)
- [Containertools in Visual Studio](/visualstudio/containers/overview)
