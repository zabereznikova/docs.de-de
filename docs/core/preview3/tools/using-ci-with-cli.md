---
title: Verwenden des .NET Core SDKs und der entsprechenden Tools in Continuous Integration (CI) | Microsoft-Dokumentation
description: Verwenden des .NET Core SDK und der entsprechenden Tools in Continuous Integration (CI)
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0d6e1e34-277c-4aaf-9880-3ebf81023857
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 95c7f0f9911c7cb37c12afec74d0e942db77fbf6

---

# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci-net-core-tools-rc4"></a>Verwenden des .NET Core SDKs und der entsprechenden Tools in Continuous Integration (CI) (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Informationen zu .NET Core Preview 2-Tools finden Sie im Thema [Verwenden des .NET Core SDKs und der entsprechenden Tools in Continuous Integration (CI)](../../tools/using-ci-with-cli.md).

## <a name="overview"></a>Übersicht
In diesem Dokument wird die Verwendung des .NET Core SDK und der entsprechenden Tools auf dem Buildserver beschrieben. Im Allgemeinen soll die Installation auf einem CI-Buildserver auf eine beliebige Weise automatisiert werden. Für die Automatisierung sollten im Idealfall möglichst keine Administratorrechte erforderlich sein. 

Für SaaS-CI-Projektmappen stehen mehrere Optionen zur Verfügung. In diesem Dokument werden die beiden sehr populären Optionen [TravisCI](https://travis-ci.org/) und [AppVeyor](https://www.appveyor.com/) beschrieben. Es gibt natürlich noch viele andere Dienste, die Mechanismen zur Installation und Nutzung sollten jedoch vergleichbar sein.

## <a name="installation-options-for-ci-build-servers"></a>Installationsoptionen für CI-Buildserver

## <a name="using-the-native-installers"></a>Verwenden der nativen Installationsprogramme
Wenn die Verwendung von Installationsprogrammen, für die Administratorrechte erforderlich sind, kein Problem darstellen, können für alle Plattformen native Installationsprogramme zum Einrichten des Buildservers verwendet werden. Dieser Ansatz hat vor allem bei Linux-Buildservern einen Vorteil: Abhängigkeiten, die zum Ausführen des SDK benötigt werden, werden automatisch installiert. Die nativen Installationsprogramme installieren darüber hinaus auch eine systemweite Version des SDK, was möglicherweise wünschenswert ist. Falls nicht, lesen Sie den Abschnitt zur [Verwendung des Installationsprogrammskripts](#using-the-installer-script) weiter unten. 

Die Verwendung dieses Konzepts ist einfach. Bei Linux können Sie entweder einen feedbasierten Paket-Manager, wie etwa `apt-get` für Ubuntu oder `yum` für CentOS, oder die Pakete selbst (also DEB oder RPM) verwenden. Im ersten Fall müssen Sie den Feed einrichten, der die Pakete enthält.

Bei Windows-Plattformen können Sie die MSI-Datei verwenden. 

Alle Binärdateien finden Sie auf der Seite [Erste Schritte mit .NET Core](https://aka.ms/dotnetcoregs), auf der auf die neuesten stabilen Versionen verwiesen wird. Wenn Sie neuere (und potenziell instabile) Versionen oder die neueste Version verwenden möchten, können Sie die Links aus dem [CLI-Repository](https://github.com/dotnet/cli) verwenden. 

## <a name="using-the-installer-script"></a>Verwenden des Installationsprogrammskripts
Das Installationsprogrammskript ermöglicht die Installation ohne Administratorrechte auf dem Buildserver. Zudem ermöglicht es eine besonders einfache Automatisierung. Das Skript selbst lädt die erforderlichen ZIP/tarball-Dateien herunter und entpackt sie. Darüber hinaus fügt es auf dem lokalen Computer den Installationspfad zum PFAD hinzu, sodass die Tools sofort nach der Installation aufgerufen werden können. 

Die Installationsprogrammdateien können mühelos zu Beginn des Buildvorgangs automatisiert werden, sodass die erforderliche Version des SDK abgerufen und installiert wird. Die „erforderliche Version“ ist die Version, die von der zu erstellenden Anwendung benötigt wird. Sie können den Installationspfad so auswählen, dass Sie das SDK lokal installieren und nach Abschluss des Buildvorgangs löschen können. Dadurch wird der Buildvorgang noch stärker verkapselt und noch weniger teilbar. 

Den Verweis auf das Installationsprogrammskript finden Sie im Dokument [dotnet-install](dotnet-install-script.md). 

### <a name="dealing-with-the-dependencies"></a>Umgang mit den Abhängigkeiten
Wenn Sie das Installationsprogrammskript verwenden, werden die nativen Abhängigkeiten nicht automatisch installiert und Sie müssen sie manuell installieren, sofern das Betriebssystem, das Sie installieren, diese nicht bereits installiert hat. Die Liste mit den erforderlichen Komponenten finden Sie im [CLI-Repository](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md). 

## <a name="ci-services-setup-examples"></a>Beispiele für die Einrichtung von CI-Diensten
In den folgenden Abschnitten finden Sie Beispiele für die Konfiguration mit den beschriebenen CI-SaaS-Optionen. 

### <a name="travisci"></a>TravisCI

[travis-ci](https://travis-ci.org/) kann so konfiguriert werden, dass das .NET Core SDK mit der Sprache `csharp` und dem Schlüssel `dotnet` installiert wird.

Verwenden Sie einfach Folgendes:

```yaml
dotnet: 1.0.0-preview2-003121
```

Travis kann sowohl `osx`- (OS X 10.11) als auch `linux`-Jobs (Ubuntu 14.04 ) in einer Buildmatrix ausführen. Weitere Informationen finden Sie im Beispiel für [.travis.yml](https://github.com/dotnet/docs/blob/master/.travis.yml).

### <a name="appveyor"></a>AppVeyor

Bei [appveyor.com ci](https://www.appveyor.com/) ist .NET Core SDK Preview 2 bereits im Build-Worker-Image `Visual Studio 2015` installiert.

Verwenden Sie einfach Folgendes:

```yaml
os: Visual Studio 2015
```

Es ist möglich, eine bestimmte Version des .NET Core SDK zu installieren. Weitere Informationen hierzu finden Sie im Beispiel für [appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml). 

In dem Beispiel werden die Binärdateien des .NET Core SDK heruntergeladen, in einem Unterverzeichnis entpackt und zur Umgebungsvariablen `PATH` hinzugefügt.

Zum Ausführen von Integrationstests mit mehreren Versionen des .NET Core SDK kann eine Buildmatrix hinzugefügt werden.

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.0-preview2-003121
    - CLI_VERSION: Latest

install:
  # .NET Core SDK binaries
  - ps: $url = "https://dotnetcli.blob.core.windows.net/dotnet/preview/Binaries/$($env:CLI_VERSION)/dotnet-dev-win-x64.$($env:CLI_VERSION.ToLower()).zip"
  # follow normal installation from binaries
```


<!--HONumber=Feb17_HO2-->


