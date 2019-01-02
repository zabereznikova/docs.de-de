---
title: Organisieren von Projekten für .NET Framework und .NET Core
description: Dieser Artikel soll Projektbesitzern dabei helfen, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren.
author: conniey
ms.date: 04/06/2017
ms.custom: seodec18
ms.openlocfilehash: 97673e1ccaeb094bf8c7cb835a84ae9389fac502
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169130"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organisieren Ihres Projekts zur Unterstützung von sowohl .NET Framework als auch .NET Core

Erfahren Sie, wie Sie eine Lösung erstellen, die .NET Framework und .NET Core parallel kompiliert. Es gibt mehrere Optionen zum Organisieren von Projekten, um dieses Ziel zu erreichen. Im Folgenden finden Sie einige Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten. Die Liste deckt möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.

* [**Combine existing projects and .NET Core projects into single projects**][option-csproj] (Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelnen Projekten)

  *Es dient folgenden Zwecken:*
  * Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.
  * Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten müssen. Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.
  * Einfaches Generieren eines NuGet-Pakets zum Verbrauch.
  * Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.

  *Nicht unterstützte Szenarios:*
  * Entwickler benötigen Visual Studio 2017, um vorhandene Projekte zu öffnen. Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).

* <a name="support-vs"></a>[**Trennen vorhandener und neuer .NET Core-Projekte**][option-csproj-folder]

  *Es dient folgenden Zwecken:*
  * Entwicklung in bereits erstellten Projekten wird weiterhin unterstützt. Entwickler oder Mitwirkende, die eventuell nicht über Visual Studio 2017 verfügen, müssen kein Upgrade durchführen.
  * Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.

## <a name="example"></a>Beispiel

Betrachten Sie das folgende Repository:

![Vorhandenes Projekt][example-initial-project]

[**Quellcode**][example-initial-project-code]

Im Folgenden sind verschiedene Möglichkeiten beschrieben, Unterstützung für .NET Core für dieses Repository hinzuzufügen. Dies ist abhängig von den Einschränkungen und der Komplexität bestehender Projekte.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Ersetzen von vorhandenen Projekten mit mehrfachzielorientierten .NET Core Projekten

Organisieren Sie das Repository neu, sodass alle vorhandenen *\*.csproj*-Dateien entfernt werden, und eine einzelne *\*.csproj*-Datei erstellt wird, die mehrere Frameworks als Ziel hat. Dies ist eine hervorragende Option, da ein einzelnes Projekt für andere Frameworks kompilieren kann. Außerdem kann die Option verschiedene Kompilierungsoptionen und Abhängigkeiten pro Zielframework behandeln.

![Erstellen einer csproj, die mehrere Frameworks als Ziel hat][example-csproj]

[**Quellcode**][example-csproj-code]

Zu beachtende Änderungen:

* Der Ersatz für *packages.config* und *\*.csproj* mit einer neuen [.NET Core *\*.csproj*][example-csproj-netcore]. NuGet-Pakete werden mit `<PackageReference> ItemGroup` angegeben.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts

Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.

![.NET Core-Projekt mit vorhandenem Projekt in anderem Ordner][example-csproj-different-folder]

[**Quellcode**][example-csproj-different-code]

Zu beachtende Änderungen:

* .NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.
  * Projekte in separaten Ordnern zu speichern, vermeidet, dass Sie über Visual Studio 2017 verfügen müssen. Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.

## <a name="see-also"></a>Siehe auch

* Weitere Anleitungen zum Migrieren zu .NET Core finden Sie in der [Dokumentation zum Portieren von .NET Core][porting-doc].

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Vorhandenes Projekt"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Erstellen einer csproj, die mehrere Frameworks als Ziel hat"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png ".NET Core-Projekt mit vorhandener PLC in anderem Ordner"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
