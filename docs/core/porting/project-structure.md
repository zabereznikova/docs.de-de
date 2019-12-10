---
title: Organisieren von Projekten für .NET Framework und .NET Core
description: Dieser Artikel soll Projektbesitzern dabei helfen, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: 789f50ffb61b80f590a24bc45693df895b3424f7
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801928"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organisieren Ihres Projekts zur Unterstützung von sowohl .NET Framework als auch .NET Core

Erfahren Sie, wie Sie eine Lösung erstellen, die .NET Framework und .NET Core parallel kompiliert. Es gibt mehrere Optionen zum Organisieren von Projekten, um dieses Ziel zu erreichen. Im Folgenden finden Sie einige Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten. Die Liste deckt möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.

- [**Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelnen Projekten**](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  *Es dient folgenden Zwecken:*
  - Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.
  - Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten müssen. Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.
  - Einfaches Generieren eines NuGet-Pakets zum Verbrauch.
  - Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.

  *Nicht unterstützte Szenarios:*
  - Entwickler benötigen Visual Studio 2017 oder höher, um vorhandene Projekte zu öffnen. Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).

- <a name="support-vs"></a>[**Trennen vorhandener und neuer .NET Core-Projekte**](#keep-existing-projects-and-create-a-net-core-project)

  *Es dient folgenden Zwecken:*
  - Unterstützung der Entwicklung in bestehenden Projekten für Entwickler und Mitwirkende, die möglicherweise nicht über Visual Studio 2017 oder eine höhere Version verfügen.
  - Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.

## <a name="example"></a>Beispiel

Betrachten Sie das folgende Repository:

![Vorhandenes Projekt](./media/project-structure/existing-project-structure.png)

[**Quellcode**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/)

Im Folgenden sind verschiedene Möglichkeiten beschrieben, Unterstützung für .NET Core für dieses Repository hinzuzufügen. Dies ist abhängig von den Einschränkungen und der Komplexität bestehender Projekte.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Ersetzen von vorhandenen Projekten mit mehrfachzielorientierten .NET Core Projekten

Organisieren Sie das Repository neu, sodass alle vorhandenen *\*.csproj*-Dateien entfernt werden, und eine einzelne *\*.csproj*-Datei erstellt wird, die mehrere Frameworks als Ziel hat. Dies ist eine hervorragende Option, da ein einzelnes Projekt für andere Frameworks kompilieren kann. Außerdem kann die Option verschiedene Kompilierungsoptionen und Abhängigkeiten pro Zielframework behandeln.

![CSPROJ-Datei für mehrere Zielframeworks erstellen](./media/project-structure/multi-targeted-project.png)

[**Quellcode**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/)

Zu beachtende Änderungen:

- Der Ersatz für *packages.config* und *\*.csproj* mit einer neuen [.NET Core *\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj). NuGet-Pakete werden mit `<PackageReference> ItemGroup` angegeben.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts

Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.

![.NET Core-Projekt mit vorhandenem Projekt in anderem Ordner](./media/project-structure/separate-projects-same-source.png)

[**Quellcode**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

Zu beachtende Änderungen:

- .NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.
  - Durch das Speichern der Projekte in separaten Ordnern ist es nicht mehr notwendig, Visual Studio 2017 oder eine spätere Version zu besitzen. Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.

## <a name="see-also"></a>Siehe auch

- [Dokumentation zur .NET Core-Portierung](index.md)
