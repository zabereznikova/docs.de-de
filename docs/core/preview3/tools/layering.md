---
title: Architektur der .NET Core-Befehlszeilentools von RC4 | Microsoft-Dokumentation
description: "RC4 weist verschiedene Änderungen hinsichtlich der Ebenen der gesamten .NET Core-Tools auf."
keywords: CLI, Erweiterbarkeit, benutzerdefinierte Befehle, .NET Core
author: blackdwarf
ms.date: 11/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 7fff0f61-ac23-42f0-9661-72a7240a4456
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 305d046c698ca9f7ebb5ac56387cfef00145393e

---

# <a name="high-level-overview-of-changes-in-cli-rc4"></a>Allgemeine Übersicht über Änderungen in CLI RC4

[!INCLUDE[preview-warning](../../../includes/warning.md)]

In diesem Dokument werden die allgemeinen Änderungen beschrieben, die der Wechsel von `project.json` zu MSBuild und zum `csproj`-Projektsystem mit sich bringt. Erläutert wird die neue Weise, in der Tools in Schichten angeordnet sind, welche neuen Elemente verfügbar sind und wo sie sich im Gesamtbild einordnen. Nach der Lektüre dieses Artikels sollten Sie alle Elemente besser verstehen, die die .NET Core-Tools nach dem Wechsel zu MSBuild und `csproj` bilden. 

## <a name="moving-away-from-projectjson"></a>Abkehr von „project.json“
Die größte Änderung in den RC4-Tools für .NET Core ist sicherlich die [Abkehr von „project.json“ hin zu „csproj“](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) als Projektsystem. Die RC4-Version der Befehlszeilentools ist das erste Release von .NET Core-Befehlszeilentools ohne jegliche Unterstützung für „project.json“. Das heißt, dass diese Version nicht zum Erstellen, Ausführen und Veröffentlichen von auf „project.json“ basierenden Anwendungen und Bibliotheken verwendet werden kann. Um diese Version der Tools verwenden zu können, müssen Sie Ihre vorhandenen Projekte migrieren oder neue beginnen. 

Im Rahmen dieses Wechsels wurde das benutzerdefinierte Buildmodul, das zum Erstellen von „project.json“-Projekten entwickelt wurde, durch ein ausgereiftes und vollausgestattetes Buildmodul namens [MSBuild](https://github.com/Microsoft/msbuild) ersetzt. MSBuild ist ein bekanntes Modul in der .NET-Community, da es seit der ersten Version der Plattform eine wichtige Technologie darstellt. Da mit MSBuild .NET Core-Anwendungen erstellt werden müssen, wurde MSBuild zu .NET Core portiert und kann auf allen Plattformen genutzt werden, auf denen .NET Core ausgeführt wird. Eines der wichtigsten Ziele von .NET Core ist ein plattformübergreifender Entwicklungsstapel, und wir haben dafür gesorgt, dass auch nach diesem Wechsel dieses Ziel erfüllt wird.

> [!NOTE]
> Wenn Sie noch nicht mit MSBuild vertraut sind und mehr darüber erfahren möchten, lesen Sie zum Einstieg den Artikel [MSBuild Concepts](https://docs.microsoft.com/visualstudio/msbuild/msbuild-concepts) (MSBuild-Konzepte). 

## <a name="the-tooling-layers"></a>Die Toolschichten
Die Frage, die sich nach der Abkehr vom vorhandenen Projektsystem und aufgrund des Wechsels des Buildmoduls zwangsläufig stellt, ist, ob sich durch diese Änderungen die allgemeinen Schichten des gesamten Ökosystems von .NET Core-Tools ändern? Gibt es neue Bits und Komponenten?

Lassen Sie uns als schnelle Auffrischung mit den Schichten in Preview 2 beginnen, die die folgende Abbildung zeigt:

![Allgemeine Architektur der Preview 2-Tools](media/p2-arch.png)

Die Schichtung der Tools ist recht einfach. Ganz unten haben wir die .NET Core-Befehlszeilentools als Fundament. Alle anderen Tools auf höherer Ebene wie Visual Studio oder Visual Studio Code hängen zum Erstellen von Projekten, Wiederherstellen von Abhängigkeiten usw. von der CLI ab. Dies bedeutete, dass wenn Visual Studio z.B. eine Wiederherstellung durchführen wollte, der Befehl `dotnet restore` in der CLI aufgerufen werden musste. 

Durch den Wechsel zum neuen Projektsystem ändert sich die vorherige Abbildung: 

![Allgemeine Architektur der RC4-Tools](media/p3-arch.png)

Der Hauptunterschied besteht darin, dass die CLI nicht mehr die Fundamentschicht darstellt. Diese Rolle wird jetzt von der „freigegebenen SDK-Komponente“ übernommen. Diese freigegebene SDK-Komponente ist eine Gruppe von Zielen und zugehörigen Aufgaben, die für das Kompilieren Ihres Codes, seine Veröffentlichung, das Packen von NuGet-Paketen usw. verantwortlich sind. Das SDK selbst ist Open Source und auf GitHub im Repository [SDK](https://github.com/dotnet/sdk) verfügbar. 

> [!NOTE]
> Ein „Ziel“ ist ein MSBuild-Ausdruck, der einen benannten Vorgang angibt, den MSBuild aufrufen kann. Es ist in der Regel an eine oder mehrere Aufgaben gekoppelt, die dem Ziel entsprechende Logik ausführen. MSBuild unterstützt viele vorgefertigte Ziele, z.B. `Copy` oder `Execute`. Außerdem können Benutzer mithilfe von verwaltetem Code eigene Aufgaben schreiben und Ziele definieren, um diese Aufgaben ausführen. Weitere Informationen finden Sie unter [MSBuild-Aufgaben](https://docs.microsoft.com/visualstudio/msbuild/msbuild-tasks). 

Alle Toolsets nutzen nun die freigegebene SDK-Komponente und ihre Ziele. Das gibt auch für die CLI. Beispielsweise ruft die nächste Version von Visual Studio nicht den Befehl `dotnet restore` auf, um die Abhängigkeiten für .NET Core-Projekte wiederherzustellen, sondern direkt das Ziel von „restore“. Da es sich MSBuild-Ziele handelt, können Sie MSBuild auch „roh“ verwenden, um sie mit dem Befehl [dotnet msbuild](dotnet-msbuild.md) auszuführen. 

### <a name="rc4-cli-commands"></a>RC4-CLI-Befehle
Die freigegebene SDK-Komponente bedeutet, dass die meisten vorhandenen CLI-Befehle als MSBuild-Aufgaben und -Ziele neu implementiert wurden. Was bedeutet dies für die CLI-Befehle und Ihre Nutzung des Toolsets? 

Aus Benutzersicht ändert sich nicht die Art der Verwendung der CLI. Die CLI weist noch immer die Hauptbefehle auf, die in der Preview 2-Version vorhanden sind:

* `new`
* `restore`
* `run` 
* `build`
* `publish`
* `test`
* `pack` 

Diese Befehle werden weiter wie erwartet ausgeführt (Erstellen, Veröffentlichen, Packen eines Projekts usw.). Die meisten Optionen haben sich nicht geändert und sind weiterhin vorhanden. Um sich mit den Änderungen vertraut zu machen, können Sie entweder die Hilfebildschirme der Befehle (über `dotent <command> --help`) oder die RC4-Dokumentation auf dieser Website konsultieren. 

Aus Sicht der Ausführung verwenden die CLI-Befehle ihre Parameter und erstellen einen Aufruf an „rohes“ MSBuild, woraufhin das Modul die benötigten Eigenschaften festlegt und das gewünschte Ziel ausführt. Um dies besser zu veranschaulichen, betrachten Sie den folgenden Befehl: 

    `dotnet publish -o pub -c Release`
    
Mit diesem Befehl wird eine Anwendung im Ordner `pub` mithilfe der Konfiguration „Release“ veröffentlicht. Intern wird dieser Befehl in den folgenden MSBuild-Aufruf übersetzt: 

    `dotnet msbuild /t:Publish /p:OutputPath=pub /p:Configuration=Release`

Die wichtige Ausnahme dieser Regel sind die Befehle `new` und `run`, da sie nicht als MSBuild-Ziele implementiert wurden. 

## <a name="conclusion"></a>Schlussfolgerung 
In diesem Dokument werden in allgemeiner Form die Änderungen beschrieben, die an der gesamten Architektur der CLI-Tools und -Funktionen in RC4 vorgenommen wurden. Ferner werden die freigegebene SDK-Komponente und die Funktionsweise der CLI-Befehle aus technischer Sicht in RC4 vorgestellt.


<!--HONumber=Feb17_HO2-->


