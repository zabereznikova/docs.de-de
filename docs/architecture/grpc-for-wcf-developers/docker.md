---
title: Docker - gRPC für WCF-Entwickler
description: Erstellen von Docker-Images für ASP.NET Core-gRPC-Anwendungen
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148113"
---
# <a name="create-docker-images"></a>Erstellen von Docker-Images

In diesem Abschnitt werden die Erstellung von Docker-Images für ASP.NET Core-gRPC-Anwendungen behandelt, die in Docker-, Kubernetes- oder anderen Containerumgebungen ausgeführt werden können. Die verwendete Beispielanwendung mit einer ASP.NET Core MVC-Web-App und einem gRPC-Dienst ist im [Repository dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.

## <a name="microsoft-base-images-for-aspnet-core-applications"></a>Microsoft-Basisbilder für ASP.NET-Kernanwendungen

Microsoft bietet eine Reihe von Basisabbildern zum Erstellen und Ausführen von .NET Core-Anwendungen. Um ein ASP.NET Core 3.0-Bild zu erstellen, verwenden Sie zwei Basisbilder:

- Ein SDK-Image zum Erstellen und Veröffentlichen der Anwendung.
- Ein Laufzeitabbild für die Bereitstellung.

| Image | Beschreibung |
| ----- | ----------- |
| [mcr.microsoft.com/dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | Für Gebäudeanwendungen `docker build`mit . Nicht in der Produktion verwendet werden. |
| [mcr.microsoft.com/dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | Enthält die Laufzeit- und ASP.NET Core-Abhängigkeiten. Für die Produktion. |

Für jedes Image gibt es vier Varianten, die auf verschiedenen Linux-Distributionen basieren, die sich durch Tags unterscheiden.

| Bild-Tag(e) | Linux | Notizen |
| --------- | ----- | ----- |
| 3,0-Buster, 3,0 | Debian 10 | Das Standardabbild, wenn keine Betriebssystemvariante angegeben ist. |
| 3.0-alpin | Alpine 3,9 | Alpine Basis-Images sind viel kleiner als Debian- oder Ubuntu-Images. |
| 3.0-Disco | Ubuntu 19.04 | |
| 3.0-bionic | Ubuntu 18.04 | |

Das Alpine-Basis-Image beträgt etwa 100 MB, verglichen mit 200 MB für die Debian- und Ubuntu-Images. Einige Softwarepakete oder Bibliotheken sind möglicherweise nicht in der Paketverwaltung von Alpine verfügbar. Wenn Sie nicht sicher sind, welches Image Sie verwenden sollen, sollten Sie wahrscheinlich das Standard-Debian wählen.

> [!IMPORTANT]
> Stellen Sie sicher, dass Sie die gleiche Linux-Variante für den Build und die Laufzeit verwenden. Anwendungen, die für eine Variante erstellt und veröffentlicht wurden, funktionieren möglicherweise nicht auf einer anderen.

## <a name="create-a-docker-image"></a>Erstellen eines Docker-Image

Ein Docker-Image wird durch eine *Dockerfile*definiert. Dies ist eine Textdatei, die alle Befehle enthält, die zum Erstellen der Anwendung und zum Installieren aller Abhängigkeiten erforderlich sind, die zum Erstellen oder Ausführen der Anwendung erforderlich sind. Das folgende Beispiel zeigt die einfachste Dockerfile-Datei für eine ASP.NET Core 3.0-Anwendung:

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

Die Dockerfile besteht aus zwei `sdk` Teilen: Der erste verwendet das Basisabbild, um die Anwendung zu erstellen und zu veröffentlichen. die zweite erstellt ein Laufzeitbild von der `aspnet` Basis aus. Dies liegt `sdk` daran, dass das Abbild etwa 900 MB groß ist, verglichen mit etwa 200 MB für das Laufzeitabbild, und der größte Teil seines Inhalts zur Laufzeit nicht erforderlich ist.

### <a name="the-build-steps"></a>Die Buildschritte

| Schritt | Beschreibung |
| ---- | ----------- |
| `FROM ...` | Deklariert das Basisbild und `builder` weist den Alias zu. |
| `WORKDIR /src` | Erstellt `/src` das Verzeichnis und legt es als aktuelles Arbeitsverzeichnis fest. |
| `COPY . .` | Kopiert alles unterhalb des aktuellen Verzeichnisses auf dem Host in das aktuelle Verzeichnis auf dem Image. |
| `RUN dotnet restore` | Stellt alle externen Pakete wieder her (ASP.NET Core 3.0-Framework ist mit dem SDK vorinstalliert). |
| `RUN dotnet publish ...` | Erstellt und veröffentlicht einen Release-Build. Beachten Sie, dass das `--runtime` Flag nicht erforderlich ist. |

### <a name="the-runtime-image-steps"></a>Die Laufzeitbildschritte

| Schritt | Beschreibung |
| ---- | ----------- |
| `FROM ...` | Deklariert ein neues Basisbild. |
| `WORKDIR /app` | Erstellt `/app` das Verzeichnis und legt es als aktuelles Arbeitsverzeichnis fest. |
| `COPY --from=builder ...` | Kopiert die veröffentlichte Anwendung aus dem `builder` vorherigen Bild, `FROM` indem der Alias aus der ersten Zeile verwendet wird. |
| `ENTRYPOINT [ ... ]` | Legt fest, dass der Befehl ausgeführt wird, wenn der Container gestartet wird. Der `dotnet` Befehl im Laufzeitabbild kann nur DLL-Dateien ausführen. |

### <a name="https-in-docker"></a>HTTPS in Docker

Microsoft-Basisabbilder für `ASPNETCORE_URLS` Docker `http://+:80`legen die Umgebungsvariable auf fest, d. h., Kestrel wird ohne HTTPS auf diesem Port ausgeführt. Wenn Sie HTTPS mit einem benutzerdefinierten Zertifikat verwenden (wie in [selbstgehosteten gRPC-Anwendungen](self-hosted.md)beschrieben), sollten Sie dies überschreiben. Legen Sie die Umgebungsvariable im Laufzeitbilderstellungsteil Ihrer Dockerfile fest.

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a>Die .dockerignore-Datei

Ähnlich `.gitignore` wie Dateien, die bestimmte Dateien und `.dockerignore` Verzeichnisse aus der Quellcodeverwaltung ausschließen, kann die Datei verwendet werden, um dateien- und Verzeichnisse davon auszuschließen, während des Builds in das Bild kopiert zu werden. Dies spart nicht nur Zeit beim Kopieren, sondern `obj` kann auch einige Fehler vermeiden, die entstehen, wenn das Verzeichnis von Ihrem PC in das Bild kopiert wird. Sie sollten mindestens Einträge für `bin` `obj` und `.dockerignore` zu Ihrer Datei hinzufügen.

```console
bin/
obj/
```

## <a name="build-the-image"></a>Erstellen des Image

Für eine Lösung mit einer einzelnen Anwendung und damit einer einzelnen Dockerfile ist es am einfachsten, die Dockerfile im Basisverzeichnis zu speichern. Mit anderen Worten, legen Sie es `.sln` in das gleiche Verzeichnis wie die Datei. Verwenden Sie in diesem Fall zum `docker build` Erstellen des Images den folgenden Befehl aus dem Verzeichnis, das die Dockerfile enthält.

```console
docker build --tag stockdata .
```

Das verwirrend `--tag` benannte Flag (das `-t`auf gekürzt werden kann) gibt den gesamten Namen des Bildes an, einschließlich des tatsächlichen Tags, falls angegeben. Der `.` am Ende gibt den Kontext an, in dem der Build ausgeführt wird. das aktuelle Arbeitsverzeichnis `COPY` für die Befehle in der Dockerfile.

Wenn Sie mehrere Anwendungen in einer einzigen Lösung haben, können Sie die Dockerfile für jede Anwendung in einem eigenen Ordner neben der `.csproj` Datei aufbewahren. Sie sollten den `docker build` Befehl weiterhin aus dem Basisverzeichnis ausführen, um sicherzustellen, dass die Projektmappe und alle Projekte in das Abbild kopiert werden. Sie können eine Dockerfile unterhalb des `--file` aktuellen `-f`Verzeichnisses angeben, indem Sie das Flag (oder ) verwenden.

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a>Ausführen des Images in einem Container auf Ihrem Computer

Verwenden Sie den `docker run` Befehl, um das Image in Ihrer lokalen Docker-Instanz auszuführen.

```console
docker run -ti -p 5000:80 stockdata
```

Das `-ti` Flag verbindet Ihr aktuelles Terminal mit dem Terminal des Containers und wird im interaktiven Modus ausgeführt. Der `-p 5000:80` veröffentlicht (verknüpft) Port 80 auf dem Container zu Port 5000 auf der lokalen Host-Netzwerkschnittstelle.

## <a name="push-the-image-to-a-registry"></a>Pushen des Images in eine Registrierung

Nachdem Sie überprüft haben, ob das Image funktioniert, übertragen Sie es an eine Docker-Registrierung, um es auf anderen Systemen verfügbar zu machen. Interne Netzwerke müssen eine Docker-Registrierung bereitstellen. Dies kann so einfach sein wie das [Ausführen des eigenen `registry` Images](https://docs.docker.com/registry/deploying/) von Docker (die Docker-Registrierung wird in einem Docker-Container ausgeführt), aber es stehen verschiedene umfassendere Lösungen zur Verfügung. Für die externe Freigabe und Cloudnutzung stehen verschiedene verwaltete Registrierungsstellen zur Verfügung, z. B. [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) oder Docker [Hub](https://docs.docker.com/docker-hub/repos/).

Um einen Push-Code an Docker Hub zu übertragen, setzen Sie dem Imagenamen den Namen Ihres Benutzers oder Ihrer Organisation voran.

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

Um einen Push zu einer privaten Registrierung zu erstellen, setzen Sie dem Imagenamen den Namen des Registrierungshosts und den Organisationsnamen voran.

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

Nachdem sich das Image in einer Registrierung befindet, können Sie es auf einzelnen Docker-Hosts oder in einem Containerorchestrierungsmodul wie Kubernetes bereitstellen.

>[!div class="step-by-step"]
>[VorherigeS](self-hosted.md)
>[Weiter](kubernetes.md)
