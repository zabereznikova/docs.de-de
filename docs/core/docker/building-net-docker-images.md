---
title: Erstellen von .NET Core Docker-Images
description: Grundlegendes zu Docker-Images und .NET Core
keywords: .NET, .NET Core, Docker
author: spboyer
manager: wpickett
ms.date: 08/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
translationtype: Human Translation
ms.sourcegitcommit: 9b3c2cf0bf2d7e93fb643caa55fd41c75ab9f657
ms.openlocfilehash: 0702c53ddaec7ae391dfa584ae13550c8fa64e6d

---
 

#<a name="building-docker-images-for-net-core-applications"></a>Erstellen von Docker-Images für .NET Core-Anwendungen

Docker und .NET Core werden zusammen verwendet. Hierzu sollten Sie die verschiedenen Docker-Images kennen, die angeboten werden, und wann der richtige Anwendungsfall für sie ist. Die angebotenen Variationen sind nachfolgend aufgeführt. Sie erfahren, wie Sie eine ASP.NET Core-Web-API oder mithilfe von Yeoman Docker-Tools einen debugfähigen Container erstellen, und wie Visual Studio-Code diesen Prozess unterstützen kann. 

## <a name="docker-image-optimizations"></a>Docker-Image-Optimierungen

Beim Erstellen von Docker-Images für Entwickler standen drei wichtige Szenarios im Mittelpunkt:

- Images zum Entwickeln von .NET Core-Apps
- Images zum Erstellen von .NET Core-Apps
- Images zum Ausführen von .NET Core-Apps

Warum drei Images?
Beim Entwickeln, Erstellen und Ausführen von Container-Anwendungen gibt es unterschiedliche Prioritäten.
- **Entwicklung:** Wie schnell Änderungen durchgeführt und ob sie debugged werden können. Die Größe des Images ist nicht so wichtig. Entscheidend ist, dass Sie Änderungen am Code vornehmen und diese schnell sehen können. Einige der Tools wie [yo docker](https://aka.ms/yodocker) für die Verwendung in VS-Code verwenden dieses Image während der Entwicklungszeit. 
- **Build:** Was Sie benötigen, um Ihre App zu kompilieren. Dies schließt den Compiler und alle anderen Abhängigkeiten zum Optimieren der Binärdateien ein. Dieses Image ist nicht das Image, das Sie bereitstellen, es handelt sich vielmehr um ein Image, das Sie verwenden, um den Inhalt zu erstellen, den Sie in einem Produktions-Image platzieren. Dieses Image wird in der fortlaufenden Integration oder Buildumgebung verwendet. Anstatt alle Abhängigkeiten direkt auf einem Build-Agent zu installieren, würde der Build-Agent beispielsweise ein Build-Image erstellen, um die Anwendung mit allen Abhängigkeiten zu kompilieren, die zum Erstellen der in dem Image enthaltenen App erforderlich sind. Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird. 
- **Produktion:** Wie schnell Sie das Image bereitstellen und starten können. Dieses Image ist klein, sodass es schnell über das Netzwerk aus der Docker-Registrierung zu den Docker-Hosts übertragen werden kann. Die Inhalte sind bereit zur Ausführung und ermöglichen in kürzester Zeit nach dem Dockerlauf das Verarbeiten von Ergebnissen. Im unveränderlichen Docker-Modell besteht keine Notwendigkeit zur dynamischen Kompilierung des Codes. Die Inhalte, die Sie in diesem Image platzieren, sind auf die Binärdateien und Inhalte beschränkt, die zum Ausführen der Anwendung erforderlich sind. Zum Beispiel die veröffentlichte Ausgabe mit `dotnet publish`, die die kompilierten Binärdateien, Images, JS- und CSS-Dateien enthält. Im Laufe der Zeit sehen Sie Images, die JIT-kompilierte Pakete enthalten.  

Obwohl mehrere Versionen des .NET Core-Images verfügbar sind, verwenden alle eine oder mehrere Ebenen gemeinsam. Der benötigte Speicherplatz oder das Delta, das aus der Registrierung abgerufen wird, ist wesentlich kleiner als das gesamte Image, da alle Images eine oder mehrere Ebenen teilen.  

## <a name="docker-image-variations"></a>Docker-Image-Varianten

Um die oben genannten Ziele zu erreichen, stehen Image-Varianten unter [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) zur Verfügung.

- `microsoft/dotnet:<version>-sdk`: das Image **microsoft/dotnet:1.0.0-preview2-sdk** enthält das .NET Core SDK, .NET Core und Befehlszeilentools (CLI). Dieses Image ist dem **Entwicklungsszenario** zugeordnet. Dieses Image wird für lokale Entwicklung, Debuggen und Testen von Einheiten verwendet. Beispielsweise für alle Entwicklungen, bevor Sie Ihren Code einchecken. Dieses Image kann auch für **Build**-Szenarios verwendet werden.

- `microsoft/dotnet:<version>-core`: Das Image **microsoft/dotnet:1.0.0-core** führt [portable .NET Core-Anwendungen](../deploying/index.md) aus und ist für die Ausführung von Anwendungen in der **Produktion** optimiert. Es enthält nicht das SDK und soll die optimierte Ausgabe von `dotnet publish` übernehmen. Die portable Laufzeit ist gut geeignet für Docker-Container-Szenarios, da mehrere laufende Container von gemeinsamen Image-Ebenen profitieren.  

## <a name="alternative-images"></a>Alternative Images

Zusätzliche Images zu den optimierten Szenarios für Entwicklung, Erstellung und Produktion:

- `microsoft/dotnet:<version>-onbuild`: Das Image **microsoft/dotnet:1.0.0-preview2-onbuild** enthält [ONBUILD](https://docs.docker.com/engine/reference/builder/#/onbuild) Trigger. Der Buildvorgang [KOPIERT](https://docs.docker.com/engine/reference/builder/#/copy) die Anwendung, führt `dotnet restore` aus und erstellt eine [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) `dotnet run` Anweisung, um die Anwendung auszuführen, wenn das Docker-Image ausgeführt wird. Auch wenn es kein optimiertes Image für die Produktion ist, können einige es hilfreich finden, einfach ihren Quellcode in ein Image zu kopieren und auszuführen. 

- `microsoft/dotnet:<version>-core-deps`: Das Image **microsoft/dotnet:1.0.0-core-deps** zum Ausführen eigenständiger Anwendungen. Es enthält das Betriebssystem mit allen nativen Abhängigkeiten, die von .NET Core benötigt werden. Dieses Image kann auch als Basisimage verwendet werden, für Ihre eigenen benutzerdefinierten CoreFX oder CoreCLR Builds. Während die Variante **onbuild** optimiert ist, um einfach Code in einem Image zu platzieren und es auszuführen, ist dieses Image darauf optimiert, nur die benötigten Betriebssystemabhängigkeiten zum Ausführen von .NET Core-Apps bereitzustellen, die die .NET Runtime im Anwendungspaket haben. Dieses Image ist im Allgemeinen nicht für das Ausführen mehrerer .NET Core-Container auf dem gleichen Host optimiert, da jedes Image die .NET Core Runtime in der Anwendung hat und eine Image-Überlagerung keinen Vorteil bringt.   

Aktuelle Versionen jeder Variante:

- `microsoft/dotnet`oder `microsoft/dotnet:latest` (einschließlich SDK)
- `microsoft/dotnet:onbuild`
- `microsoft/dotnet:core`
- `microsoft/dotnet:core-deps`

Es folgt eine Liste der Images nach einem `docker pull <imagename>` auf einem Entwicklungscomputer mit den verschiedenen Größen. Beachten Sie, dass die Entwicklungs/Build-Variante `microsoft/dotnet:1.0.0-preview2-sdk` größer ist, da sie das SDK zum Entwickeln und Erstellen der Anwendung enthält. Die Produktionsvariante `microsoft/dotnet:core` ist kleiner, da sie nur die .NET Core Runtime enthält. Das minimale Image `core-deps`, das unter Linux verwendet werden kann, ist sehr viel kleiner, jedoch muss die Anwendung eine private Kopie der .NET Runtime beinhalten. Da Container bereits private Isolationsbarrieren sind, verlieren Sie diese Optimierung, wenn mehrere Dotnet-basierte Container ausgeführt werden. 

```
REPOSITORY          TAG                     IMAGE ID            SIZE
microsoft/dotnet    1.0.0-preview2-onbuild  19b6a6c4b1db        540.4 MB
microsoft/dotnet    onbuild                 19b6a6c4b1db        540.4 MB
microsoft/dotnet    1.0.0-preview2-sdk      a92c3d9ad0e7        540.4 MB
microsoft/dotnet    core                    5224a9f2a2aa        253.2 MB
microsoft/dotnet    1.0.0-core-deps         c981a2eebe0e        166.2 MB
microsoft/dotnet    core-deps               c981a2eebe0e        166.2 MB
microsoft/dotnet    latest                  03c10abbd08a        540.4 MB
microsoft/dotnet    1.0.0-core              b8da4a1fd280        253.2 MB
```

## <a name="prerequisites"></a>Erforderliche Komponenten

Zum Erstellen und Ausführen benötigen Sie Folgendes:

- [.NET Core](http://dot.net)
- [Docker](https://www.docker.com/products/docker) zum lokalen Ausführen der Docker-Container 
- [Yeoman-Generator für ASP.NET](https://github.com/omnisharp/generator-aspnet) zum Erstellen der Web-API-Anwendung
- [Yeoman-Generator für Docker](http://aka.ms/yodocker) von Microsoft

Installieren Sie die Yeoman-Generatoren für ASP.NET Core und Docker mithilfe von npm 

```
npm install -g yo generator-aspnet generator-docker
```

> [!NOTE]
> In diesem Beispiel wird [Visual Studio Code](http://code.visualstudio.com) für den Editor verwendet.

## <a name="creating-the-web-api-application"></a>Erstellen der Web-API-Anwendung

Als Bezugspunkt, bevor die Anwendung containerisiert wird, führen Sie die Anwendung zunächst lokal aus. 

Erstellen Sie ein Verzeichnis für die Anwendung.

Öffnen Sie einen Befehl oder eine Terminal-Sitzung in diesem Verzeichnis, und verwenden Sie den ASP.NET Yeoman-Generator, indem Sie Folgendes eingeben:
```
yo aspnet
```

Wählen Sie **Web-API-Anwendung**, geben Sie **api** für den Namen der App ein, und tippen Sie auf die EINGABETASTE.  Sobald das Gerüst der Anwendung steht, wechseln Sie in das Verzeichnis `/api`, und stellen Sie die NuGet-Abhängigkeiten mithilfe von `dotnet restore` wieder her.

```
cd api
dotnet restore
```

Testen Sie die Anwendung mit `dotnet run`, und gehen Sie zu **http://localhost:5000/api/values**

```javascript
[
    "value1",
    "value2"
]
```

Verwenden Sie `Ctrl+C`, um die Anwendung zu beenden.

## <a name="adding-docker-support"></a>Hinzufügen der Docker-Unterstützung

Hinzufügen der Docker-Unterstützung für das Projekt durch die Verwendung des Yeoman-Generators von Microsoft. Er unterstützt derzeit .NET Core-, Node.js- und Go-Projekte durch Erstellen einer Docker-Datei und Skripts, mit deren Hilfe Projekte in Containern erstellt und ausgeführt werden. Visual Studio Code-spezifische Dateien werden ebenfalls hinzugefügt (launch.json, tasks.json), für Editor-Debuggen und Befehlspalettenunterstützung.

```console
$ yo docker

     _-----_     ╭──────────────────────────╮
    |       |    │   Welcome to the Docker  │
    |--(o)--|    │        generator!        │
   `---------´   │     Let's add Docker     │
    ( _´U`_ )    │  container magic to your │
    /___A___\   /│           app!           │
     |  ~  |     ╰──────────────────────────╯
   __'.___.'__
 ´   `  |° ´ Y `

? What language is your project using? (Use arrow keys)
❯ .NET Core
  Golang
  Node.js

```

- Wählen Sie `.NET Core` als Projekttyp
- `rtm` für die Version von .NET Core
- `Y` das Projekt verwendet einen Webserver
- `5000` ist der Port, der von der Web-API-Anwendung (http://localhost:5000) überwacht wird.
- `api` für den Image-Namen
- `api` für den Dienstnamen
- `api` für das Verfassen-Projekt 
- `Y` zum Überschreiben der aktuellen Dockerfile-Datei

Nach Abschluss des Generators werden die folgenden Dateien zum Projekt hinzugefügt

- .vscode/launch.json
- Dockerfile.debug
- Docker-Datei
- docker-compose.debug.yml
- docker-compose.yml
- dockerTask.ps1
- dockerTask.sh
- .vscode/tasks.json

Der Generator erstellt zwei Docker-Dateien.

Die Datei **Dockerfile.Debug** basiert auf dem Image **microsoft/dotnet:1.0.0-preview2-sdk**, das wie in der Liste der Varianten aufgeführt SDK, CLI und .NET Core umfasst, und das Image für Entwicklung und Debuggen (F5) ist. Mit all diesen Komponenten hat das Image eine Größe von ungefähr 540 MB.

**Dockerfile** ist das Release-Image basierend auf dem Image **microsoft/dotnet:1.0.0-core**, und soll für die Produktion verwendet werden. Dieses Image ist nach dem Erstellen etwa 253 MB groß.

### <a name="creating-the-docker-images"></a>Erstellen der Docker-Images
Mithilfe des Skripts `dockerTask.sh` oder `dockerTask.ps1` können Image und Container für die **api**-Anwendung für eine bestimmte Umgebung erstellt oder verfasst werden. Erstellen des **debug**-Image durch Ausführen des folgenden Befehls.

```bash
./dockerTask.sh build debug
```

Das Image erstellt die ASP.NET-Anwendung, führt `dotnet restore` aus, fügt den Debugger dem Image hinzu, setzt einen `ENTRYPOINT`, und kopiert die App in das Image. Das Ergebnis ist ein Docker-Image mit dem Namen *api* mit einem `TAG` von *debug*.  Sehen Sie sich die Images auf dem Computer mit `docker images` an.

```bash
docker images

REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        a few seconds ago   779.8 MB
```

Alternativ können Sie durch Öffnen der Anwendung in Visual Studio Code und Verwenden der Debugging-Tools das Image erstellen und die Anwendung innerhalb des Docker-Containers ausführen. 

Wählen Sie das Debug-Symbol in der Ansichtsleiste auf der linken Seite von VSCode aus.

![vscode-Debug-Symbol](./media/building-net-docker-images/debugging_debugicon.png)

Tippen Sie dann auf das Wiedergabesymbol oder F5, um das Image zu generieren, und starten Sie die Anwendung innerhalb des Containers. Die Web-API wird unter http://localhost:5000 mit Ihrem Standard-Webbrowser gestartet.

![VSCode Docker-Tools Debug](./media/building-net-docker-images/docker-tools-vscode-f5.png)

Sie können Haltepunkte in Ihrer Anwendung setzen, durchlaufen usw., als ob die Anwendung lokal auf dem Entwicklungscomputer statt in dem Container ausgeführt würde. Der Vorteil beim Debuggen innerhalb des Containers ist, dass dies das gleiche Image ist, das in einer Produktionsumgebung bereitgestellt würde.

Erstellen des Releases oder Produktions-Images erfordert einfach das Ausführen des Befehls über das Terminal und die Übergabe des Namens der `release`-Umgebung.

```bash
./dockerTask build release
```

Der Befehl erstellt das Image basierend auf dem kleineren Basis-Image **microsoft/dotnet:core**, macht Port 5000 [verfügbar](https://docs.docker.com/engine/reference/builder/#/expose), legt den [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#/entrypoint) für `dotnet api.dll` fest und kopiert diesen in das Verzeichnis `/app`. Es gibt keinen Debugger, kein SDK oder `dotnet restore`, die zu einem viel kleineren Image führen. Das Image wird **api** benannt mit einem `TAG` **aktuell**.

```
REPOSITORY          TAG                  IMAGE ID            CREATED             SIZE
api                 debug                70e89fbc5dbe        1 hour ago        779.8 MB
api                 latest               ef17184c8de6        1 hour ago        260.7 MB
```

## <a name="summary"></a>Zusammenfassung

Mithilfe des Docker-Generators können Sie erforderliche Dateien für eine Web-API-Anwendung hinzufügen. Dies vereinfacht die Erstellung von Entwicklungs- und Produktionsversionen der Images.  Die Tools sind plattformübergreifend. Durch die Bereitstellung eines PowerShell-Skripts können die gleichen Ergebnisse für Windows und Visual Studio Code erreicht werden mit schrittweisem Debuggen der Anwendung innerhalb des Containers. Wenn Sie die Imagevarianten und die Zielszenarios kennen, können Sie Ihre Entwicklungsschleifen verbessern und optimierte Images für Produktionsbereitstellungen erreichen.  





<!--HONumber=Nov16_HO1-->


