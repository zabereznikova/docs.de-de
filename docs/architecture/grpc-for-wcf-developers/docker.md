---
title: Docker-GrpC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.net Core GrpC-Anwendungen
ms.date: 09/02/2019
ms.openlocfilehash: a5aceb4b5270cb828965e990a62db4147012adff
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967841"
---
# <a name="docker"></a>Docker

In diesem Abschnitt wird die Erstellung von Docker-Images für ASP.net Core GrpC-Anwendungen behandelt, die in Docker, Kubernetes oder anderen Container Umgebungen ausgeführt werden können. Die Beispielanwendung, die mit einer ASP.net Core MVC-Web-App und einem GrpC-Dienst verwendet wird, ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Microsoft-Basis Images für ASP.net Core Anwendungen

Microsoft bietet eine Reihe von Basis Images zum entwickeln und Ausführen von .net Core-Anwendungen. Zum Erstellen eines ASP.net Core 3,0-Images werden zwei Basis Images verwendet: ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung und ein Lauf Zeit Image für die Bereitstellung.

| Bild | Beschreibung |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Zum Entwickeln von Anwendungen mit `docker build`. Nicht zur Verwendung in der Produktion. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Enthält die Lauf Zeit-und ASP.net Core Abhängigkeiten. Für die Produktion. |

Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren und durch Tags unterschieden werden.

| Imagetag (e) | Linux | Hinweise |
| --------- | ----- | ----- |
| 3,0-Buster, 3,0 | Debian 10 | Das Standardbild, wenn keine Betriebssystem Variante angegeben ist. |
| 3,0-Alpine | Alpine 3,9 | Alpine Base-Images sind wesentlich kleiner als Debian oder Ubuntu. |
| 3,0-Disco | Ubuntu 19,04 | |
| 3,0-Bionic | Ubuntu 18.04 | |

Das Alpine Base-Image ist um 100 MB im Vergleich zu 200 MB für die Debian-und Ubuntu-Images, aber einige Softwarepakete oder-Bibliotheken sind in der Alpine-Paketverwaltung möglicherweise nicht verfügbar. Wenn Sie nicht sicher sind, welches Image verwendet werden soll, ist es am besten, wenn Sie eine andere Distribution verwenden müssen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie für den Build und die Laufzeit dieselbe Variante von Linux verwenden. Anwendungen, die auf einem Variant erstellt und veröffentlicht werden, funktionieren möglicherweise nicht auf einem anderen.

## <a name="create-a-docker-image"></a>Erstellen eines docker-Images

Ein docker-Image wird durch eine *dockerfile-Datei*definiert. Dies ist eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung benötigt werden, und alle Abhängigkeiten zu installieren, die zum Erstellen oder Ausführen der Anwendung erforderlich sind. Das folgende Beispiel zeigt die einfachste dockerfile-Datei für eine ASP.net Core 3,0-Anwendung:

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

Die dockerfile-Datei besteht aus zwei Teilen: der erste verwendet das `sdk` Basis Image, um die Anwendung zu erstellen und zu veröffentlichen. die zweite erstellt ein Lauf Zeit Bild aus der `aspnet` Basis. Dies liegt daran, dass das `sdk` Abbild ungefähr 900 MB im Vergleich zu etwa 200 MB für das Lauf Zeit Image liegt und der meiste Inhalt zur Laufzeit unnötig ist.

### <a name="the-build-steps"></a>Die Buildschritte

| Schritt | Beschreibung |
| ---- | ----------- |
| `FROM ...` | Deklariert das Basis Image und weist den `builder` Alias zu (Weitere Erläuterungen finden Sie im nächsten Abschnitt). |
| `WORKDIR /src` | Erstellt das `/src` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest. |
| `COPY . .` | Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Bild. |
| `RUN dotnet restore` | Stellt alle externen Pakete wieder her (ASP.net Core 3,0-Framework ist mit dem SDK vorinstalliert). |
| `RUN dotnet publish ...` | Erstellt und veröffentlicht einen Releasebuild. Beachten Sie, dass das `--runtime`-Flag nicht erforderlich ist. |

### <a name="the-runtime-image-steps"></a>Die Schritte zum Lauf Zeit Image

| Schritt | Beschreibung |
| ---- | ----------- |
| `FROM ...` | Deklariert ein neues Basis Image. |
| `WORKDIR /app` | Erstellt das `/app` Verzeichnis und legt es als Aktuelles Arbeitsverzeichnis fest. |
| `COPY --from=builder ...` | Kopiert die veröffentlichte Anwendung aus dem vorherigen Bild unter Verwendung des `builder` Alias aus der ersten `FROM` Zeile. |
| `ENTRYPOINT [ ... ]` | Legt den Befehl fest, der beim Starten des Containers ausgeführt wird. Der Befehl `dotnet` im Lauf Zeit Image kann nur DLL-Dateien ausführen. |

### <a name="https-in-docker"></a>HTTPS in docker

Die Basis Images von Microsoft für docker legen die `ASPNETCORE_URLS`-Umgebungsvariable auf `http://+:80`fest. Dies bedeutet, dass Kestrel ohne HTTPS an diesem Port ausgeführt wird. Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie im [vorherigen Abschnitt](self-hosted.md)beschrieben), sollten Sie dies überschreiben, indem Sie die Umgebungsvariable **im Rahmen der Lauf Zeit Image Erstellung** der dockerfile-Datei festlegen.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Die. dockerignore-Datei

Ähnlich wie `.gitignore` Dateien, die bestimmte Dateien und Verzeichnisse aus der Quell Code Verwaltung ausschließen, kann die `.dockerignore` Datei verwendet werden, um zu verhindern, dass Dateien und Verzeichnisse während des Buildvorgangs in das Image kopiert werden. Dadurch wird nicht nur Zeit gespart, sondern es können auch einige verwirrende Fehler vermieden werden, die dazu führen, dass (insbesondere) das `obj` Verzeichnis von Ihrem PC in das Abbild kopiert wird. Sie sollten der `.dockerignore` Datei mindestens Einträge für `bin` und `obj` hinzufügen.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Erstellen des Images

Für eine Lösung mit einer einzelnen Anwendung und somit einer einzelnen dockerfile-Datei ist es am einfachsten, die dockerfile-Datei im Basisverzeichnis zu platzieren. Das heißt, dasselbe Verzeichnis wie die `.sln` Datei. Verwenden Sie in diesem Fall den folgenden `docker build` Befehl aus dem Verzeichnis mit der dockerfile-Datei, um das Image zu erstellen.

```console
docker build --tag stockdata .
```

Das verwirrende `--tag`-Flag (das auf `-t`verkürzt werden kann) gibt den gesamten Namen des Bilds an, *einschließlich* des tatsächlichen Tags, wenn angegeben. Der `.` am Ende gibt den *Kontext* an, in dem der Build ausgeführt wird. das aktuelle Arbeitsverzeichnis für die `COPY`-Befehle in der dockerfile-Datei.

Wenn Sie mehrere Anwendungen in einer einzelnen Projekt Mappe haben, können Sie die dockerfile-Datei für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren, aber Sie sollten trotzdem den `docker build` Befehl aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projekt Mappe und alle Projekte in das Image kopiert werden. Sie können eine dockerfile-Datei unterhalb des aktuellen Verzeichnisses angeben, indem Sie das `--file`-Flag (oder `-f`) verwenden.

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Ausführen des Images in einem Container auf Ihrem Computer

Verwenden Sie den Befehl `docker run`, um das Image in der lokalen docker-Instanz auszuführen.

```console
docker run -ti -p 5000:80 stockdata
```

Das `-ti`-Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt. Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 im Container an Port 80 auf der localhost-Netzwerkschnittstelle.

## <a name="push-the-image-to-a-registry"></a>Übertragung des Images per Push in eine Registrierung

Nachdem Sie überprüft haben, ob das Image funktioniert, müssen Sie es per Push an eine docker-Registrierung überführen, damit es auf anderen Systemen verfügbar ist. Interne Netzwerke müssen eine docker-Registrierung bereitstellen. Dies kann so einfach sein wie das Ausführen [des eigenen `registry` Images von Docker](https://docs.docker.com/registry/deploying/) (die Docker-Registrierung wird in einem docker-Container ausgeführt), es gibt jedoch verschiedene umfassendere Lösungen. Für die externe Freigabe und die cloudnutzung stehen verschiedene verwaltete Registrierungen zur Verfügung, z. b. [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) oder [docker Hub](https://docs.docker.com/docker-hub/repos/).

Um per Push an den docker-Hub zu übernehmen, stellen Sie dem Image Namen den Namen Ihres Benutzers oder Ihrer Organisation voran.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Um per Push in eine private Registrierung zu übernehmen, stellen Sie dem Image Namen den Namen des Registrierungs Hosts und den Organisationsnamen voran.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Sobald sich das Image in einer Registrierung befindet, können Sie es auf einzelnen docker-Hosts oder in einer Container Orchestrierungs-Engine wie Kubernetes bereitstellen.

>[!div class="step-by-step"]
>[Zurück](self-hosted.md)
>[Weiter](kubernetes.md)
