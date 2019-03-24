---
title: Organisieren von Projekten für .NET Framework und .NET Core
description: Dieser Artikel soll Projektbesitzern dabei helfen, Ihre eigene Lösung parallel für .NET Framework und .NET Core zu kompilieren.
author: conniey
ms.date: 12/07/2018
ms.custom: seodec18
ms.openlocfilehash: ab484ccc2c5b51b2ee1dca57df51669d288f3e6b
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "58186064"
---
# <a name="organize-your-project-to-support-both-net-framework-and-net-core"></a>Organisieren Ihres Projekts zur Unterstützung von sowohl .NET Framework als auch .NET Core

Erfahren Sie, wie Sie eine Lösung erstellen, die .NET Framework und .NET Core parallel kompiliert. Es gibt mehrere Optionen zum Organisieren von Projekten, um dieses Ziel zu erreichen. Im Folgenden finden Sie einige Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten. Die Liste deckt möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.

* [**Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelnen Projekten**](#replace-existing-projects-with-a-multi-targeted-net-core-project)

  *Es dient folgenden Zwecken:*
  * Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.
  * Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten müssen. Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.
  * Einfaches Generieren eines NuGet-Pakets zum Verbrauch.
  * Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.

  *Nicht unterstützte Szenarios:*
  * Entwickler benötigen Visual Studio 2017, um vorhandene Projekte zu öffnen. Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).

* <a name="support-vs"></a>[**Trennen vorhandener und neuer .NET Core-Projekte**](#keep-existing-projects-and-create-a-net-core-project)

  *Es dient folgenden Zwecken:*
  * Entwicklung in bereits erstellten Projekten wird weiterhin unterstützt. Entwickler oder Mitwirkende, die eventuell nicht über Visual Studio 2017 verfügen, müssen kein Upgrade durchführen.
  * Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.

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

* Der Ersatz für *packages.config* und *\*.csproj* mit einer neuen [.NET Core*\*.csproj*](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj). NuGet-Pakete werden mit `<PackageReference> ItemGroup` angegeben.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts

Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.

![.NET Core-Projekt mit vorhandenem Projekt in anderem Ordner](./media/project-structure/separate-projects-same-source.png)

[**Quellcode**](https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/)

Zu beachtende Änderungen:

* .NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.
  * Projekte in separaten Ordnern zu speichern, vermeidet, dass Sie über Visual Studio 2017 verfügen müssen. Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.

## <a name="see-also"></a>Siehe auch

Weitere Anleitungen zum Migrieren zu .NET Core finden Sie in der [Dokumentation zum Portieren von .NET Core](index.md).
