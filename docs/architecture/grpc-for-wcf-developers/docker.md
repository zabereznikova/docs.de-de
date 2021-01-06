---
title: Docker-GrpC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.net Core GrpC-Anwendungen
ms.date: 12/15/2020
ms.openlocfilehash: f662dbd67f00b828f3e1dfa47359a450dd1c5900
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938415"
---
# <a name="create-docker-images"></a>Erstellen von Docker-Images

In diesem Abschnitt wird die Erstellung von Docker-Images für ASP.net Core GrpC-Anwendungen behandelt, die in Docker, Kubernetes oder anderen Container Umgebungen ausgeführt werden können. Die Beispielanwendung, die mit einer ASP.net Core MVC-Web-App und einem GrpC-Dienst verwendet wird, ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Microsoft-Basis Images für ASP.net Core Anwendungen

Microsoft bietet eine Reihe von Basis Images zum entwickeln und Ausführen von .net Core-Anwendungen. Zum Erstellen eines ASP.net Core 3,0-Abbilds verwenden Sie zwei Basis Images:

- Ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung.
- Ein Lauf Zeit Image für die Bereitstellung.

| Image | BESCHREIBUNG |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/) | Zum Entwickeln von Anwendungen mit `docker build` . Nicht zur Verwendung in der Produktion. |
| [mcr.microsoft.com/dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/) | Enthält die Lauf Zeit-und ASP.net Core Abhängigkeiten. Für Produktionszwecke. |

Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren und durch Tags unterschieden werden.

| Imagetag (e) | Linux | Notizen |
| --------- | ----- | ----- |
| 5,0-Buster, 5,0 | Debian 10 | Das Standardbild, wenn keine Betriebssystem Variante angegeben ist. |
| 5,0-Alpine | Alpine 3,9 | Alpine Base-Images sind wesentlich kleiner als Debian oder Ubuntu. |
| 5,0-Disco | Ubuntu 19.04 | |
| 5,0-Bionic | Ubuntu 18.04 | |

Das Alpine Base-Image ist um 100 MB im Vergleich zu 200 MB für die Debian-und Ubuntu-Images. Einige Softwarepakete oder-Bibliotheken sind in der Alpine-Paketverwaltung möglicherweise nicht verfügbar. Wenn Sie nicht sicher sind, welches Image verwendet werden soll, sollten Sie wahrscheinlich das standardmäßige Debian auswählen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie für den Build und die Laufzeit dieselbe Variante von Linux verwenden. Anwendungen, die auf einem Variant erstellt und veröffentlicht werden, funktionieren möglicherweise nicht auf einem anderen.

## <a name="create-a-docker-image"></a>Erstellen eines Docker-Image

Ein docker-Image wird durch eine *dockerfile-Datei* definiert. Bei dieser *dockerfile-Datei* handelt es sich um eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung und zum Installieren von Abhängigkeiten erforderlich sind, die zum Erstellen oder Ausführen der Anwendung erforderlich sind. Das folgende Beispiel zeigt die einfachste dockerfile-Datei für eine ASP.net Core 5,0-Anwendung:

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:5.0 as build

WORKDIR /src

COPY ./StockKube.sln .
COPY ./src/StockData/StockData.csproj ./src/StockData/
COPY ./src/StockWeb/StockWeb.csproj ./src/StockWeb/

RUN dotnet restore

COPY . .

RUN dotnet publish --no-restore -c Release -o /published src/StockData/StockData.csproj

FROM mcr.microsoft.com/dotnet/aspnet:5.0 as runtime

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=build /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Die dockerfile-Datei besteht aus zwei Teilen: der erste verwendet das `sdk` Basis Image, um die Anwendung zu erstellen und zu veröffentlichen. das zweite erstellt ein Lauf Zeit Image aus der `aspnet` Basis. Dies liegt daran, dass das `sdk` Image ungefähr 900 MB groß ist, im Vergleich zu etwa 200 MB für das Lauf Zeit Image, und der meiste Inhalt ist zur Laufzeit unnötig.

### <a name="the-build-steps"></a>Die Buildschritte

| Schritt | BESCHREIBUNG |
| ---- | ----------- |
| `FROM ...` | Deklariert das Basis Image und weist den `builder` Alias zu. |
| `WORKDIR /src` | Erstellt das `/src` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest. |
| `COPY . .` | Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Bild. |
| `RUN dotnet restore` | Stellt alle externen Pakete wieder her (ASP.net Core 3,0-Framework ist mit dem SDK vorinstalliert). |
| `RUN dotnet publish ...` | Erstellt und veröffentlicht einen Releasebuild. Beachten Sie, dass das- `--runtime` Flag nicht erforderlich ist. |

### <a name="the-runtime-image-steps"></a>Die Schritte zum Lauf Zeit Image

| Schritt | BESCHREIBUNG |
| ---- | ----------- |
| `FROM ...` | Deklariert ein neues Basis Image. |
| `WORKDIR /app` | Erstellt das `/app` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest. |
| `COPY --from=builder ...` | Kopiert die veröffentlichte Anwendung aus dem vorherigen Bild mithilfe des `builder` Alias aus der ersten `FROM` Zeile. |
| `ENTRYPOINT [ ... ]` | Legt den Befehl fest, der beim Starten des Containers ausgeführt wird. Der `dotnet` Befehl im Lauf Zeit Image kann nur DLL-Dateien ausführen. |

### <a name="https-in-docker"></a>HTTPS in docker

Microsoft Base Images für docker legen die `ASPNETCORE_URLS` Umgebungsvariable auf fest `http://+:80` . Dies bedeutet, dass Kestrel ohne HTTPS an diesem Port ausgeführt wird. Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie in [selbstgeh osteten GrpC-Anwendungen](self-hosted.md)beschrieben), sollten Sie diese Konfiguration außer Kraft setzen. Legen Sie die Umgebungsvariable im Rahmen der Lauf Zeit Image Erstellung der dockerfile-Datei fest.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/aspnet:5.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Die. dockerignore-Datei

Ähnlich wie `.gitignore` Dateien, die bestimmte Dateien und Verzeichnisse aus der Quell Code Verwaltung ausschließen, `.dockerignore` kann die Datei verwendet werden, um Dateien und Verzeichnisse auszuschließen, die während des Buildvorgangs in das Image kopiert werden. Diese Datei spart nicht nur Zeit, das kopiert werden kann, sondern kann auch einige Fehler vermeiden, die dazu führen, dass das `obj` Verzeichnis von Ihrem PC in das Abbild kopiert wird. Sie sollten der Datei mindestens Einträge für und hinzu `bin` fügen `obj` `.dockerignore` .

```console
bin/
obj/
```

## <a name="build-the-image"></a>Erstellen des Image

Für eine `StockKube.sln` Lösung, die zwei verschiedene Anwendungen `StockData` und enthält `StockWeb` , ist es am einfachsten, die dockerfile-Datei für jede dieser Dateien im Basisverzeichnis zu platzieren. Verwenden Sie in diesem Fall den folgenden Befehl aus dem Verzeichnis, in dem sich die Datei befindet, um das Image zu erstellen `docker build` `.sln` .

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

Das verwirrend benannte `--tag` Flag (das auf gekürzt werden kann `-t` ) gibt den vollständigen Namen des Bilds an, einschließlich des tatsächlichen Tags, wenn angegeben. Der `.` am Ende gibt den Kontext an, in dem der Build ausgeführt wird, das aktuelle Arbeitsverzeichnis für die `COPY` Befehle in der dockerfile-Datei.

Wenn Sie mehrere Anwendungen in einer einzelnen Projekt Mappe haben, können Sie die dockerfile-Datei für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren. Sie sollten weiterhin den `docker build` Befehl aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projekt Mappe und alle Projekte in das Image kopiert werden. Sie können eine dockerfile-Datei unterhalb des aktuellen Verzeichnisses angeben, indem Sie das- `--file` Flag (oder `-f` ) verwenden.

```console
docker build -t stockdata:1.0.0 -f .\src\StockData\Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Ausführen des Images in einem Container auf Ihrem Computer

Verwenden Sie den Befehl, um das Image in der lokalen docker-Instanz auszuführen `docker run` .

```console
docker run -ti -p 5000:80 stockdata:1.0.0
```

Das `-ti` -Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt. Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 für den Container an Port 5000 auf der localhost-Netzwerkschnittstelle.

## <a name="push-the-image-to-a-registry"></a>Pushen des Images in eine Registrierung

Nachdem Sie überprüft haben, ob das Image funktioniert, überführen Sie es per Push an eine docker-Registrierung, um es auf anderen Systemen verfügbar zu machen. Interne Netzwerke müssen eine docker-Registrierung bereitstellen. Diese Aktivität kann so einfach sein wie das Ausführen [des eigenen `registry` Images von Docker](https://docs.docker.com/registry/deploying/) (die Docker-Registrierung wird in einem docker-Container ausgeführt), es sind jedoch verschiedene umfassendere Lösungen verfügbar. Für die externe Freigabe und die cloudnutzung stehen verschiedene verwaltete Registrierungen zur Verfügung, z. b. [Azure Container Registry](/azure/container-registry/) oder [docker Hub](https://docs.docker.com/docker-hub/repos/).

Um per Push an docker Hub zu übernehmen, stellen Sie dem Image Namen den Namen Ihres Benutzers oder Ihrer Organisation voran.

```console
docker tag stockdata:1.0.0 <myorg>/stockdata:1.0.0
docker push <myorg>/stockdata:1.0.0
```

Um per Push in eine private Registrierung zu übernehmen, stellen Sie dem Image Namen den Namen des Registrierungs Hosts und den Organisationsnamen voran.

```console
docker tag stockdata <internal-registry:5000>/<myorg>/stockdata:1.0.0
docker push <internal-registry:5000>/<myorg>/stockdata:1.0.0
```

Nachdem sich das Image in einer Registrierung befindet, können Sie es auf einzelnen docker-Hosts oder in einer Container Orchestrierungs-Engine wie Kubernetes bereitstellen.

>[!div class="step-by-step"]
>[Zurück](self-hosted.md)
>[Weiter](kubernetes.md)
