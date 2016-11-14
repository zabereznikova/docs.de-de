---
title: "Organisieren Ihres Projekts zur Unterstützung von .NET Framework und .NET Core"
description: "Organisieren Ihres Projekts zur Unterstützung von .NET Framework und .NET Core"
keywords: .NET, .NET Core
author: conniey
manager: wpickett
ms.date: 07/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: ca63b25bb5f5e98167aaa8b74a7204fcd77b3523

---

# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a>Organisieren Ihres Projekts zur Unterstützung von .NET Framework und .NET Core

Dieser Artikel soll Projektbesitzer unterstützen, die Ihre eigene Lösung parallel für .NET Framework und .NET Core kompilieren wollen.  Es werden mehrere Optionen zum Organisieren von Projekten behandelt, die Entwickler beim Erreichen dieses Ziels unterstützen sollen.  Im Folgenden finden Sie einige Szenarios, die Sie bei der Entscheidung bedenken sollten, wie Sie Ihr Projektlayout mit .NET Core einrichten.  Sie decken möglicherweise nicht alle Punkte ab, die Sie benötigen. Sie können abhängig von den Anforderungen Ihrer Projekte priorisieren.

* [**Combine existing projects and .NET Core projects into single projects (Kombinieren von vorhandenen Projekten und .NET Core-Projekten in einzelne Projekte)**][option-xproj]
  
  *Es dient folgenden Zwecken:*
  * Vereinfachen Ihres Buildprozesses durch Kompilieren eines einzelnen Projekts statt mehrerer Projekte, die alle eine andere Version von .NET Framework oder eine andere Plattform als Ziel haben.
  * Vereinfachen der Verwaltung von Quelldateien für mehrfachzielorientierte Projekte, da Sie eine einzelne Projektdatei verwalten.  Beim Hinzufügen/Entfernen von Quelldateien müssen Sie diese bei den Alternativen manuell mit Ihren Projekten synchronisieren.
  * Einfaches Generieren eines NuGet-Pakets zum Verbrauch.
  * Ermöglicht das Schreiben von Code für eine bestimmte .NET Framework-Version in Ihren Bibliotheken mithilfe von Compileranweisungen.
  
  *Nicht unterstützte Szenarios:*
  * Ohne Visual Studio 2015 können Entwickler keine bestehenden Projekte öffnen. Zur Unterstützung von älteren Versionen von Visual Studio ist es eine bessere Option, [Ihre Projektdateien in unterschiedlichen Ordnern zu speichern](#support-vs).
  * Das Teilen von .NET Core-Bibliotheken zwischen verschiedenen Projekttypen in der gleichen Lösungsdatei ist nicht möglich. Es ist eine bessere Option, [eine Portable Klassenbibliothek zu erstellen](#support-pcl), um dies zu unterstützen.
  * Änderungen des Build- und Ladeprozesses des Projekts, die von MSBuild Ziele und Aufgaben unterstützt werden, sind nicht möglich. Es ist eine bessere Option, [eine Portable Klassenbibliothek zu erstellen](#support-pcl), um dies zu unterstützen.

* [**Keep existing projects and new .NET Core projects separate (Trennen vorhandener und neuer .NET Core-Projekte)**][option-xproj-folder]
  
  *Es dient folgenden Zwecken:*
  * Entwicklung in bereits erstellten Projekten wird weiterhin unterstützt. Entwickler oder Mitwirkende, die eventuell nicht über Visual Studio 2015 verfügen, müssen kein Upgrade durchführen.
  * Minimieren der Möglichkeit, neue Probleme in vorhandenen Projekten zu erstellen, da in diesen Projekten keine Codeänderung erforderlich ist.

* [**Keep existing projects and create Portable Class Libraries (PCLs) targeting .NET Core (Behalten bestehender Projekte, und Erstellen Portabler Klassenbibliotheken (Portable Class Libraries, PCLs) mit .NET Core als Ziel)**][option-plc]

  *Es dient folgenden Zwecken:*
  * Verweist auf Ihre .NET Core-Bibliotheken in Desktop und/oder Webprojekten, die das komplette .NET Framework in derselben Lösung als Ziel haben.
  * Unterstützung von Änderungen im Projektbuild- oder Ladeprozess. Diese Änderungen können z.B. die Aufnahme von MSBuild-Aufgaben und Zielen in Ihre `*.csproj`-Datei beinhalten.

  *Nicht unterstützte Szenarios:*
  * Das Schreiben von Code für eine spezifische Version von .NET Framework ist nicht möglich, da [vordefinierte Präprozessorsymbole][how-to-multitarget] nicht unterstützt werden.

## <a name="example"></a>Beispiel

Betrachten Sie das folgende Repository:

![Vorhandenes Projekt][example-initial-project]

[**Quellcode**][beispiel-erstes-projekt-code]

Es gibt verschiedene Arten, Unterstützung für .NET Core für dieses Repository hinzuzufügen. Dies ist abhängig von den Einschränkungen und der Komplexität bestehender Projekte, die im Folgenden beschrieben werden.

## <a name="replace-existing-projects-with-a-multitargeted-net-core-project-xproj"></a>Ersetzen von vorhandenen Projekten mit mehrfachzielorientierten .NET Core Projekten (xproj)

Das Repository kann neu organisiert werden, sodass alle vorhandenen `*.csproj`-Dateien entfernt werden, und eine einzelne `*.xproj`-Datei erstellt wird, die mehrere Frameworks als Ziel hat.  Dies ist eine hervorragende Option, da ein einzelnes Projekt für andere Frameworks kompilieren kann.  Außerdem kann die Option verschiedene Kompilierungsoptionen, Abhängigkeiten usw. pro Zielframework behandeln.

![Erstellen einer xproj, die mehrere Frameworks als Ziel hat][example-xproj]

[**Quellcode:**][example-xproj-code]

Zu beachtende Änderungen:
* Addition von `global.json`
* Ersetzung von `packages.config` und `*.csproj` durch `project.json` und `*.xproj`
* Änderungen in der Datei [Car's project.json][example-xproj-projectjson] und dessen Datei[test project][example-xproj-projectjson-test], um das Erstellen für das bestehende .NET Framework und andere zu unterstützen

## <a name="create-a-portable-class-library-pcl-to-target-net-core"></a>Erstellen einer Portablen Klassenbibliothek (Portable Class Library, PCL), um .NET Core als Ziel festzulegen

Wenn vorhandene Projekte komplexe Buildvorgänge oder Eigenschaften in ihrer Datei `*.csproj` enthalten, ist es möglicherweise einfacher, eine PCL zu erstellen.

![][example-pcl]

[**Quellcode:**][beispiel-plc-code]

Zu beachtende Änderungen:
*  Umbenennen von `project.json` in `{project-name}.project.json`
    * Dies verhindert mögliche Konflikte in Visual Studio beim Wiederherstellen von Paketen für die Bibliotheken in dasselbe Verzeichnis. Weitere Informationen finden Sie in englischer Sprache unter [NuGet FAQ (NuGet – Häufig gestellte Fragen)](https://docs.nuget.org/consume/nuget-faq#working-with-packages) unter „_I have multiple projects in the same folder, how can I use separate packages.config or project.json files for each project? (Ich habe mehrere Projekte in einem Ordner, wie kann ich separate „packages.config“- oder „project.json“-Dateien für jedes Projekt verwenden?)_“.
    *  **Alternative**: Erstellen Sie die PCL in einem anderen Ordner, und verweisen Sie auf den ursprünglichen Quellcode, um dieses Problem zu vermeiden.  Die PCL in einem anderen Ordner abzulegen hat noch einen weiteren Vorteil: Benutzer, die nicht über Visual Studio 2015 verfügen, können dennoch an Ihren alten Projekten arbeiten, ohne die neue Lösung zu laden.
*  Um .NET Standard nach dem Erstellen der PCL als Ziel festzulegen, öffnen Sie in Visual Studio die **Projekteigenschaften**. Klicken Sie im Abschnitt **Ziele** auf den Link **„Target .NET Platform Standard“**.  Diese Änderung kann rückgängig gemacht werden, indem Sie die gleichen Schritte wiederholen.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Behalten vorhandener Projekte und Erstellen eines .NET Core-Projekts

Wenn es vorhandene Projekte gibt, die ältere Frameworks als Ziel haben, empfiehlt es sich, diese Projekte unverändert zu lassen und ein .NET Core-Projekt zu verwenden, um kommende Frameworks als Ziel festzulegen.

![.NET Core-Projekt mit vorhandener PLC in anderem Ordner][example-xproj-different-folder]

[**Quellcode:**][beispiel-xproj-different-code]

Zu beachtende Änderungen:
* .NET Core-Projekte und vorhandene Projekte werden in separaten Ordnern gespeichert.
    * Dadurch wird das Problem beim Wiederherstellen von Paketen vermieden. Wie weiter oben erwähnt, entsteht dieses Problem aufgrund mehrerer „project.json“/„package.config“-Dateien im selben Ordner.
    * Projekte in separaten Ordnern zu speichern, vermeidet, dass Sie über Visual Studio 2015 verfügen müssen (aufgrund von „project.json“).  Sie können eine separate Lösung erstellen, die nur die alten Projekte öffnet.

## <a name="see-also"></a>Siehe auch

Weitere Anleitungen zum Wechsel auf „project.json“ und „xproj“ finden Sie in der Dokumentation zum Portieren von .NET Core [.NET Core porting documentation][porting-doc].

[portieren-von-doc]: index.md
[beispiel-anfangs-projekt]: media/project-structure/project.png "bestehendes Projekt"
[beispiel-anfänglicher-projekt-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

[beispiel-xproj]: media/project-structure/project.xproj.png "Erstellen einer xproj, die mehrere Frameworks als Ziel hat"
[beispiel-xproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/
[beispiel-xproj-projectjson]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/src/Car/project.json
[beispiel-xproj-projectjson-test]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/tests/Car.Tests/project.json

[beispiel-xproj-anderer-ordner]: media/project-structure/project.xproj.different.png ".NET Core-Projekt mit vorhandener PLC in anderem Ordner"
[beispiel-xproj-anderer-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj-keep-csproj/

[beispiel-pcl]: media/project-structure/project.pcl.png "PCL mit .NET Core als Ziel"
[beispiel-pcl-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-pcl

[option-xproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project-xproj
[option-pcl]: #create-a-portable-class-library-pcl-to-target-net-core
[option-xproj-ordner]: #keep-existing-projects-and-create-a-net-core-project

[festlegen-der-zielversion]: ../tutorials/libraries.md#how-to-multitarget



<!--HONumber=Nov16_HO1-->


