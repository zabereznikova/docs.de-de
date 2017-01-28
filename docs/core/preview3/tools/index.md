---
title: "Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)"
description: "Dies ist ein Überblick über die Befehlszeilenschnittstelle (CLI) und deren wesentliche Funktionen"
keywords: CLI, CLI-Tools, .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b70e9ac0-c8be-49f7-9332-95ab93e0e7bc
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: be8fbdf806a3e27923f01b015de87c3fc1be7a7d

---

# <a name="net-core-command-line-interface-tools"></a>Tools für die .NET Core-Befehlszeilenschnittstelle

Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine neue, grundlegende plattformübergreifende Toolkette zur Entwicklung von .NET Core-Anwendungen. Sie ist wichtig, da dies die erste Ebene ist, auf der weitere Tools auf höherer Ebene aufbauen können, wie z.B. integrierte Entwicklungsumgebungen (Integrated Development Environments, IDEs), Editoren und Build-Koordinatoren. 

Sie ist auch standardmäßig plattformübergreifend und verfügt über denselben Oberflächenbereich auf jeder der unterstützen Plattformen. Wenn Sie also lernen, wie die Tools zu verwenden sind, können Sie diese auf jeder der unterstützten Plattformen in der gleichen Weise nutzen. 

## <a name="installation"></a>Installation
Wie bei jeden Tools ist der erste Schritt, die Tools auf dem Computer zu installieren. Je nach Szenario können Sie entweder den nativen Installer verwenden, um die CLI zu installieren, oder das Installations-Shellskript.

Der native Installer ist vorwiegend für Entwicklercomputer vorgesehen. Die CLI wird mithilfe jedes nativen Installationsmechanismus der nativen Plattform verteilt, z.B. DEB-Pakete unter Ubuntu oder MSI-Bündel unter Windows. Diese Installer installieren die Umgebung und richten Sie nach Bedarf des Nutzers ein, damit die CLI sofort nach der Installation genutzt werden kann. Jedoch benötigen sie auch Administratorrechte auf dem Computer. Die Installationsanweisungen finden Sie auf der Seite [.NET Core getting started page (Erste Schritte mit .NET Core)](https://aka.ms/dotnetcoregs).

Installationsskripts hingegen erfordern keine Administratorrechte. Allerdings installieren diese auch keine erforderlichen Komponenten auf dem Computer. Sie müssen alle erforderlichen Komponenten manuell installieren. Die Skripts werden hauptsächlich für die Einrichtung von Buildservern verwendet, oder wenn Sie die Tools ohne Administratorrechte erstellen möchten (beachten Sie hierzu die Einschränkungen der erforderlichen Komponenten oben). Weitere Informationen finden Sie unter [dotnet-install scripts reference (Referenz zu dotnet-Installationsskripts)](dotnet-install-script.md). Wenn Sie erfahren möchten, wie eine CLI auf Ihrem Buildserver der Continuous Integration (fortlaufende Integration, CI) eingerichtet wird, dann sehen Sie sich das Thema [Using .NET Core SDK and tools in Continuous Integration (CI) (Verwenden der .NET Core-SDK und Tools in der Continuous Integration (CI))](using-ci-with-cli.md) an. 

Standardmäßig wird die CLI parallel installiert (SxS). Das bedeutet, dass mehrere Versionen der CLI-Tools jederzeit auf einem Computer koexistieren können. Wie die richtige Version verwendet wird, wird ausführlicher im Abschnitt [Treiber](#driver) erklärt. 

### <a name="what-commands-come-in-the-box"></a>Welche Befehle sind in der Installation enthalten?
Die folgenden Befehle werden standardmäßig erstellt:

* [new](dotnet-new.md)
* [migrate](dotnet-migrate.md)
* [restore](dotnet-restore.md)
* [run](dotnet-run.md)
* [build](dotnet-build.md)
* [test](dotnet-test.md)
* [publish](dotnet-publish.md)
* [pack](dotnet-pack.md)

Es gibt auch eine Möglichkeit, mehrere Befehle auf einer Pro-Projekt-Basis zu importieren sowie Ihre eigenen Befehle hinzuzufügen. Dies wird ausführlicher im Abschnitt [Erweiterbarkeit](#extensibility) erläutert. 

## <a name="working-with-the-cli"></a>Arbeiten mit der CLI

Bevor wir weiter ins Detail gehen, sehen wir uns an, wie das Arbeiten mit der CLI aus 10.000 Fuß Höhe aussieht. Im folgenden Beispiel werden mehrere Befehle aus der CLI-Standardinstallation verwendet, um eine neue, einfache Konsolenanwendung zu initialisieren, die Abhängigkeiten wiederherzustellen und um die Anwendung zu erstellen und dann auszuführen. 

```console
dotnet new
dotnet restore
dotnet build --output /stuff
dotnet /stuff/new.dll
```

Wie Sie im vorherigen Beispiel sehen können, gibt es ein Muster, je nachdem wie Sie die CLI-Tools verwenden. In diesem Muster können wir drei wichtige Bestandteile der jeweiligen Befehle identifizieren:

1. [Der Treiber („dotnet“)](#driver)
2. [Der Befehl oder das „Verb“](#the-verb)
3. [Befehlsargumente](#the-arguments)

### <a name="driver"></a>Treiber
Der Treiber hat den Namen [dotnet](dotnet.md). Er ist der erste Teil von dem, was Sie aufrufen. Der Treiber hat zwei Aufgaben:

1. Das Ausführen portabler Apps
2. Das Ausführen des Verbs

Er ist jedoch von dem abhängig, was in der Befehlszeile angegeben ist. Im ersten Fall würden Sie eine DLL einer portablen App angeben, sodass `dotnet` ähnlich wie hier ausgeführt wird: `dotnet /path/to/your.dll`. 

Im zweiten Fall versucht der Treiber, den angegebenen Befehl aufzurufen. Dadurch wird der Ausführungsprozess des CLI-Befehls gestartet. Zunächst bestimmt der Treiber die Version des Tools, die Sie haben möchten. Sie können die Version in der Datei [global.json](global-json.md) mithilfe des Parameters `version` angeben. Wenn diese nicht verfügbar ist, sucht der Treiber die neueste Version des Tools, das auf dem Datenträger installiert ist und verwendet diese Version. Wenn die Version bestimmt ist, wird der Befehl ausgeführt. 

### <a name="the-verb"></a>Das „Verb“
Das Verb ist einfach ein Befehl, der eine Aktion ausführt. `dotnet build` erstellt Ihren Code. `dotnet publish` veröffentlicht Ihren Code. Das Verb wird als eine Konsolenanwendung implementiert, die nach Konvention benannt wird: `dotnet-{verb}`. Die gesamte Logik wird in der Konsolenanwendung implementiert, die das Verb repräsentiert. 

### <a name="the-arguments"></a>Die Argumente
Die Argumente, die Sie der Befehlszeile übergeben, sind die Argumente für das tatsächlich aufgerufene Verb / des tatsächlich aufgerufenen Befehls. Wenn Sie z.B. `dotnet publish --output publishedapp` eingeben, wird das `--output`-Argument dem `publish`-Befehl übergeben. 

## <a name="types-of-application-portability"></a>Typen der Anwendungsportabilität
CLI ermöglicht, dass Anwendungen auf zwei Arten portiert werden können:

1. Vollständig portierbare Anwendungen, die überall ausgeführt werden können, wo .NET Core installiert ist
2. Eigenständige Bereitstellungen

Erfahren Sie mehr über diese beiden Möglichkeiten im Thema [.NET Core application deployment (.NET Core-Anwendungsbereitstellung)](../deploying/index.md). 

## <a name="migration-from-preview-3projectjson"></a>Migration von „project.json“ zu Preview 3
Wenn Sie Preview 2-Tools und „project.json“-Projekte genutzt haben, können Sie die Dokumentation zum Befehl [dotnet migrate](dotnet-migrate.md) konsultieren, um sich mit dem Befehl vertraut zu machen und Ihr Projekt zu migrieren. 

> [!NOTE]
> Der Befehl `dotnet migrate` eignet sich derzeit nicht zum Migrieren von „project.json“-Dateien vor Preview 2. 

## <a name="extensibility"></a>Erweiterungen
Natürlich ist nicht jedes Tool, das Sie in Ihren Workflows verwenden können, Teil der CLI-Tools von .NET Core. Jedoch verfügt die .NET Core-CLI über ein Erweiterbarkeitsmodell, mit dem Sie zusätzliche Tools für Ihre Projekte angeben können. Weitere Informationen finden Sie im Thema [.NET Core CLI extensibility model (.NET Core-CLI-Erweiterbarkeitsmodell)](extensibility.md).

## <a name="summary"></a>Zusammenfassung
Dies wer ein kurzer Überblick über die wichtigsten Funktionen der CLI. Mithilfe der Referenz- und Konzeptthemen auf dieser Website können Sie mehr erfahren. Es gibt natürlich auch andere Ressourcen, die Sie nutzen können:
* [dotnet/cli](https://github.com/dotnet/cli/) auf GitHub (in englischer Sprache)
* [Anleitung zu den ersten Schritten mit .NET Core](https://aka.ms/dotnetcoregs/)



<!--HONumber=Jan17_HO3-->


